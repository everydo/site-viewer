---
created: ''
creator: ''
description: ''
title: 首页
theme: home.html
---
.. raw:: html

    <div class="container text-center">
      <h1>“在线查看文档”&nbsp;最佳解决方案</h1>
      <p>适合：云存储/网盘类服务、轻博客文档分享、文档分享网站、邮件附件查看、政府公文在线查看、公司网站产品资料查看…</p>
    </div>

    <div class="jumbotron">
      <div class="container text-center">
        <div id="edoviewer"></div>
          <script type="text/javascript">
            var viewer = EdoViewer.createViewer('edoviewer', {
            server_url: 'http://viewer.everydo.com:9870',
            source_url: 'http://download.zopen.cn/demo/edo-viewer.ppt',
            width: 700,
            height: 537,
            bgcolor: "#E8F2F4",
            });
            viewer.load();
          </script>
      </div>
    </div>
  
    <div class="container">
      <div class="row">
        <div class="col-sm-4">
          <div class="media">
            <img class="pull-left media-object" src="/themes/bootstrap/images/editor.png">
            <div class="media-body">
            <h4 class="media-heading">百种文件支持，强劲转换</h4>
            <p>支持 100 多种格式文档，方便</p>
            <p>按需转换，随转随看，快速</p>
            <p>支持压缩包转换，超强</p>
            </div>
          </div>
        </div>
        <div class="col-sm-4">
          <div class="media">
            <img class="pull-left media-object" src="/themes/bootstrap/images/zoom.png">
            <div class="media-body">
            <h4 class="media-heading">8 种查看方式，跨终端浏览</h4>
            <p>浏览器、手机等多终端支持</p>
            <p>流式查看，快速、节约流量</p>
            <p>缩略图式查看</p>
            </div>
          </div>
        </div>
        <div class="col-sm-4">
          <div class="media">
            <img class="pull-left media-object" src="/themes/bootstrap/images/Cloud.png">
            <div class="media-body">
            <h4 class="media-heading">按需扩展，运维便捷</h4>
            <p>根据需求随时扩展</p>
            <p>支持分布式存储</p>
            <p>转换异常处理</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    
      <div class="container case">
        <div class="row">
          <div class="col-sm-2 col-sm-offset-1 text-center"><h4>他们在使用云查看</h4></div>
          <div class="col-sm-2"><img src="/themes/bootstrap/images/jy.jpg"></div>
          <div class="col-sm-2"><img src="/themes/bootstrap/images/sh.png"></div>
          <div class="col-sm-2"><img src="/themes/bootstrap/images/dq.jpg"></div>
          <div class="col-sm-2"><img src="/themes/bootstrap/images/jx.jpg"></div>
        </div>
      </div>