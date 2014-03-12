---
created: ''
creator: ''
description: ''
title: 首页
theme: home.html
---
.. raw:: html

    <div class="container text-center fix-padding">
      <h1>“在线查看文档”&nbsp;最佳解决方案</h1>
      <p>适合：云存储/网盘类服务、轻博客文档分享、文档分享网站、邮件附件查看、政府公文在线查看、公司网站产品资料查看…</p>
    </div>

    <div class="jumbotron">
      <div class="container text-center center-block">
          <div id="edoviewer"></div>
          <script type="text/javascript">
            if (/AppleWebKit.*Mobile/i.test(navigator.userAgent) || (/MIDP|SymbianOS|NOKIA|SAMSUNG|LG|NEC|TCL|Alcatel|BIRD|DBTEL|Dopod|PHILIPS|HAIER|LENOVO|MOT-|Nokia|SonyEricsson|SIE-|Amoi|ZTE/.test(navigator.userAgent)))
            {
              var d = document, a = d.compatMode == "BackCompat"
              ? d.body
              : d.documentElement;

              var width = a.clientWidth*0.8;
              var height = width/1.2;
            }
            else
            {
              var width = 700;
              var height = 537;
            }
            var viewer = EdoViewer.createViewer('edoviewer', {
            server_url: 'http://viewer.everydo.com:9870',
            source_url: 'http://download.zopen.cn/demo/edo-viewer.ppt',
            width: width,
            height: height,
            bgcolor:"#E8F2F4"
            });
            viewer.load();
          </script>
      </div>
    </div>
  
    <div class="container features-box">
      <div class="row-fluid">
        <div class="span4">
          <div class="media">
            <img class="pull-left media-object" src="/themes/viewer-bootstrap/img/editor.png">
            <div class="media-body">
            <h4 class="media-heading">百种文件支持，强劲转换</h4>
            <p>支持 100 多种格式文档，方便</p>
            <p>按需转换，随转随看，快速</p>
            <p>支持压缩包转换，超强</p>
            </div>
          </div>
        </div>
        <div class="span4">
          <div class="media">
            <img class="pull-left media-object" src="/themes/viewer-bootstrap/img/zoom.png">
            <div class="media-body">
            <h4 class="media-heading">8 种查看方式，跨终端浏览</h4>
            <p>浏览器、手机等多终端支持</p>
            <p>流式查看，快速、节约流量</p>
            <p>缩略图式查看</p>
            </div>
          </div>
        </div>
        <div class="span4">
          <div class="media">
            <img class="pull-left media-object" src="/themes/viewer-bootstrap/img/Cloud.png">
            <div class="media-body">
            <h4 class="media-heading">方便集成，运维便捷</h4>
            <p>提供浏览器和OAuth API</p>
            <p>动态水印和查看权限限制</p>
            <p>提供转换监控后台</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    
      <div class="container case">
        <div class="row-fluid">
          <div class="span2 offset1 text-center"><h4>他们在使用云查看</h4></div>
          <div class="span2"><img src="/themes/viewer-bootstrap/img/jy.jpg"></div>
          <div class="span2"><img src="/themes/viewer-bootstrap/img/sh.png"></div>
          <div class="span2"><img src="/themes/viewer-bootstrap/img/dq.jpg"></div>
          <div class="span2"><img src="/themes/viewer-bootstrap/img/jx.jpg"></div>
        </div>
      </div>
