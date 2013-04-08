在线演示
//////////////////

.. contents::


下载文件预览API
===============================
使用易度云查看的JS API，可动将下载链接转换为在线阅读，点击下面的链接直接体验效果。

- PPT文档: http://download.zopen.cn/demo/edo-viewer.ppt

- 视频: http://download.zopen.cn/demo/mm%5B1%5D.mpg

- 音频: http://download.zopen.cn/demo/demo.wav

- 压缩包: http://download.zopen.cn/demo/everydo-test-archive-file.rar

- 代码: http://download.zopen.cn/demo/application.py

.. raw:: html

   <script src="http://viewer.everydo.com:9870/static/api.js"></script>
   <script>
    cloudview('http://viewer.everydo.com:9870/');
   </script>

内嵌查看
===============================
使用易度云查看的内嵌查看JS API，可在网页中内嵌查看文档.

Office 文档
----------------------
.. image::images/flash-viewer.png

.. raw:: html

   <script src="http://viewer.everydo.com:9870/static/edo_viewer.js"></script>
   <div id="doc-viewer-01"></div>
   <script type="text/javascript">
       edo_viewer('http://viewer.everydo.com:9870', 'http://download.zopen.cn/demo/edo-viewer.ppt', 'doc-viewer-01', 717, 537)
   </script>

视频
---------
.. image::images/video-viewer.png

.. raw:: html

   <div id="doc-viewer-02"></div>
   <script type="text/javascript">
       edo_viewer('http://viewer.everydo.com:9870', 'http://download.zopen.cn/demo/mm[1].mpg', 'doc-viewer-02', 717, 717)
   </script>


音频
------
.. image::images/audio-viewer.png

.. raw:: html

   <div id="doc-viewer-03"></div>
   <script type="text/javascript">
       edo_viewer('http://viewer.everydo.com:9870', 'http://download.zopen.cn/demo/demo.wav', 'doc-viewer-03', 700, 700)
   </script>

压缩包
-----------
.. image::images/rar-viewer.png

.. raw:: html

   <style type="text/css">
   #doc-viewer-04 img {margin:0 !important; padding:0 !important; border:0 !important;}
   </style>
   <div id="doc-viewer-04"></div>
   <script type="text/javascript">
       edo_viewer('http://viewer.everydo.com:9870', 'http://download.zopen.cn/demo/everydo-test-archive-file.rar', 'doc-viewer-04', 700, 700)
   </script>


程序代码
------------
.. image::images/rar-viewer.png

.. raw:: html

   <div id="doc-viewer-05"></div>
   <script type="text/javascript">
       edo_viewer('http://viewer.everydo.com:9870', 'http://download.zopen.cn/demo/application.py', 'doc-viewer-05', 700, 500)
   </script>


图片
--------
.. image::images/image-viewer.png

.. raw:: html

   <div id="doc-viewer-08"></div>
   <script type="text/javascript">
       edo_viewer('http://viewer.everydo.com:9870', 'http://download.zopen.cn/demo/exif.jpg', 'doc-viewer-08', 700, 700)
   </script>


在线体验
===============================
在这里上传文件，体验转换效果。

.. raw:: html

   <div class="box">
       <div style="padding:1%; border:1px solid #CCC; background:#F5F5F5; width:46%; border-radius:3px;">
           <form method="post" enctype="multipart/form-data" action="http://viewer.everydo.com:9870/@@upload" target="_blank">
               <p><input type="file" value="选择文件" name="file"></p>
               <p><input type="submit" value="查看" class="submit" /></p>
           </form>
       </div>
   </div>
