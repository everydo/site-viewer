---
created: ''
creator: ''
description: ''
title: 技术文档
---

==================
技术文档
==================

.. contents::
    :class: sidebar
    
系统总体组成
==============

总体组成图如下：

.. image:: images/tech-system.png

其中:

1. 查看器包括8种，在浏览器上运行。如需定制，可以使用我们提供的flash控件，以及相关的js代码。
2. 云查看模块，可以是我们标准的产品，也可以是集成了转换服务接口的系统。这里可能需要限定文档的访问权限。
3. 文档转换服务，是底层进行文档后台转换的一个服务。
4. 监控后台，用于监控文档转换服务，确保系统稳定可靠运行。

云查看API
===================
云查看有3种集成API，包括浏览器的js api，在浏览器中实现集成，非常简单，以及基于OAuth的Open API。

使用云查看APi，您可以：

- 加一行脚本，让您的网站中的文件下载链接，立刻变成文档预览链接
- 在您的网站中嵌入文档查看器
- 和您的内部办公系集成，集成查看权限，支持文档安全水印

最新的详细API参看： http://developer.everydo.com/open/viewer.rst

安装环境
==================
系统采用虚拟机方式发布。

- Ubuntu Server 8.04 以上版本

FTS文档转换服务
======================
FTS文档转换服务，是系统核心的转换服务，内部构成如下：

.. image:: images/tech-engine.png

可以看到：

1. FTS文档转换服务，是以Redis作为中心的数据库，也是和外部通信的接口。
2. 监控后台是可选启动的服务
3. 工作服务器可部署多台，按需平滑扩展，自动负载均衡

云查看链接生成
=======================

假设文件的下载地址是：http://127.0.0.1/test.doc
那么这个文件的MD5就是: a844c1dc43014146a97d06fa86421049

MD5 计算方式：
   
Python版本::

    >> import hashlib
    >> hash_md5 = hashlib.md5()
    >> hash_md5.update(‘http://127.0.0.1/test.doc’)
    >> print hash_md5.hexdigest()
    
下载地址
-----------

{{SERVER_DOMAIN}}/files/{{FILE_MD5}}.{{FILE_EXT}}

FILE_EXT：源文件的后缀

这个例子中，下载地址是：

http://127.0.0.1:6543/files/a844c1dc43014146a97d06fa86421049.py

原始文件路径
----------------

{{FRS_ROOT  }}/{{FILE_MD5}}.{{FILE_EXT}}

FRS_ROOT：在fts_web/app.ini配置文件中定义

转换文件下载地址
------------------

一个源文件可以有多个转换文件，因为每一种文件都能转换成多种其他的文件

{{SERVER_DOMAIN}}/cache/files/{{FILE_MD5}}.{{FILE_EXT}}/.frs.{{VMIME}}/{{RESULT_NAME}}

VMIME：转换文件的MIME Type，将“.”替换为“_”

RESULT_NAME：转换文件的文件名

    - Flash： transformed.swf
    - Html:   transformed.html
    - Audio:  transformed.mp3
    - Video:  transformed.flv
    - Plain:  transformed.txt
    - Pdf:    transformed.pdf
    - Exif:   transformed.json
    - Thumbnail:  large.png，preview.png，
    - Compression:  transformed.json

    Exif是图片中储存的额外信息，转换为json数据
    Thumbnail是图片的缩略图，有几种不同的大小
    Compression是压缩包的转换为json数据，然后由浏览器的javascript渲染，

这个例子中，需要转换为html预览，转换文件下载地址是：

http://127.0.0.1:6543/cache/files/a844c1dc43014146a97d06fa86421049.py/.frs.text_html/transformed.htm

转换文件地址     
------------------

{{FRS_CACHE}}/files/{{FILE_MD5}}.{{FILE_EXT}}/.frs.{{VMIME}}/{{RESULT_NAME}}

FRS_CACHE：在fts_web/app.ini 配置文件中定义，假设是：

/tmp/data/frscache

这个例子中，需要转换为html预览，转换文件地址是：

/tmp/data/frscache/files/a844c1dc43014146a97d06fa86421049.py/.frs.text_html/transformed.html


转换格式明细
=============================

office类文档
--------------------
包括：

Office2003/2007:

- doc (application/msword)
- docx (application/vnd.openxmlformats-officedocument.wordprocessingml.document)
- xls (application/vnd.ms-excel)
- xlsx (application/vnd.openxmlformats-officedocument.spreadsheetml.sheet)
- ppt、pps 、pot (application/vnd.ms-powerpoint)
- pptx (application/vnd.openxmlformats-officedocument.presentationml.presentation)
- rtf (application/rtf )


WPS2009:

- wps (application/kswps)
- et (application/kset)
- dps (application/ksdps )

openoffice:

- odt (application/vnd.oasis.opendocument.text)
- ods (application/vnd.oasis.opendocument.spreadsheet)
- odp (application/vnd.oasis.opendocument.presentation)
- ott (application/vnd.oasis.opendocument.text-template)
- ots (application/vnd.oasis.opendocument.spreadsheet-template)
- otp (application/vnd.oasis.opendocument.presentation-template)


Office文档可以使用如下查看方式：

- 文档flash查看： application/x-shockwave-flash-x
- 纯文本查看：text/plain
- html查看：text/html
- pdf查看： application/pdf
- 缩略图查看：image/png

  这个是我们系统自己定制的， 要缩略图就用这个mime类型

HTML
--------------
包括:

- mht(message/rfc822)
- html( text/html )

查看方式：

- HTML查看

  安全的html, 将javascript, object... 等危险的标签移除

- 纯文本查看
- 缩略图查看
- PDF查看

PDF
--------------
pdf 可以转换如下类型：

- HTML
- 纯文本
- FLASH
- 缩略图

纯文本
---------------
包括：

- txt ( text/plain )
- rst ( text/x-rst )
- xml ( text/xml )
- css ( text/css )
- csv ( text/csv )
- java ( text/x-java )
- c ( text/x-csrc )
- cpp ( text/x-c++src )
- jsp ( text/x-jsp )
- asp ( text/x-asp )
- py ( text/x-python )
- as ( text/x-as )
- sh ( text/x-sh )

纯文本 可以转换如下类型：

- HTML
- PDF

图
------
- 图片：

  - bmp (image/x-ms-bmp)
  - jpg、jpeg (image/jpeg)
  - png (image/png)
  - gif (image/gif)
  - tiff (image/tiff)
  - ppm (image/x-portable-pixmap)

- 矢量图纸：dwg (application/dwg)

图片可以转换如下类型：

- 缩略图预览

音频
----------------

- mp3 (audio/mpeg) * 可以直接预览 *
- wma (audio/x-ms-wma)
- rm (audio/x-pn-realaudio) * 可以直接预览*
- wav (audio/x-wav) * 可以直接预览*
- mid (audio/midi) * 可以直接预览*

音频可以转换如下类型：

- MP3 ( audio/x-mpeg )

视频
----------------

- avi (video/x-msvideo)
- rmvb (video/vnd.rn-realvideo)
- mov (video/quicktime)
- mp4 (video/mp4)
- swf (application/x-shockwave-flash)
- flv (video/x-flv) * 可以直接预览*
- mpg ( video/mpeg )
- ram (application/x-pn-realaudio)
- wmv (video/x-ms-wmv)
- m4v (video/m4v)

可采用如下查看方式

- 缩略图
- FLV (vide/x-flv)

压缩包
------

- rar ： application/rar
- zip： application/zip
- tar： application/tar application/x-tar
- tgz：application/x-gzip application/x-compressed

可转换为包含文件夹内容的 json格式： application/json
