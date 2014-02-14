---
created: ''
creator: ''
description: ''
title: 首页
theme: home.html
---
.. raw:: html

        <div class="jumbotron">
            <div class="row">
                <div class="col-xs-6 col-md-4">
                  <h2 style="margin-top: 70px; font-size: 50px; text-align: center;">在线查看文档</h2>
                  <h3 style="text-align: center;">最佳的解决方案</h3>
                  <div class="list-group" style="margin-top: 25px;">
                      <p class="list-group-item">公司网站产品资料查看<span class="glyphicon glyphicon-ok" style="float: right;"></span></p>
                      <p class="list-group-item">政府公文在线查看<span class="glyphicon glyphicon-ok" style="float: right;"></span></p>
                      <p class="list-group-item">轻博客文档分享<span class="glyphicon glyphicon-ok" style="float: right;"></span></p>
                      <p class="list-group-item">云存储类服务<span class="glyphicon glyphicon-ok" style="float: right;"></span></p>
                      <p class="list-group-item">文档分享网站<span class="glyphicon glyphicon-ok" style="float: right;"></span></p>
                      <p class="list-group-item">邮件附件查看<span class="glyphicon glyphicon-ok" style="float: right;"></span></p>
                    </div>
                </div>

                <div class="col-xs-12 col-md-8">
                <div id="edoviewer"></div>
                <script type="text/javascript">
                    var viewer = EdoViewer.createViewer('edoviewer', {
                      server_url: 'http://viewer.everydo.com:9870',
                      source_url: 'http://download.zopen.cn/demo/edo-viewer.ppt',
                      width: 700,
                      height: 537
                   });
                   viewer.load();
                </script>
                </div>
            </div>
        </div>
        
        <div class="row" style="margin: 0px;">
        <div class="hero-unit col-md-4" >
            <h3 style="text-align: center;">百种文件支持，强劲转换</h3>
            <div style="margin-left: 44px;">
            <p>支持 100 多种格式文档，方便</p>
            <a class="btn btn-primary btn-large" style="float: right;margin-right: 44px;margin-top: 12px;" href="product/">更多</a>
            <p>按需转换，随转随看，快速</p>
            <p>支持压缩包转换，超强</p>
            </div>
        </div>
        <div class="hero-unit col-md-4">
            <h3 style="text-align: center;">8 种查看方式，跨终端浏览</h3>
            <div style="margin-left: 34px;">
            <p>缩略图式查看</p>
            <a class="btn btn-primary btn-large" style="float: right;margin-right: 32px;margin-top: 12px;" href="product/#id7">更多</a>
            <p>浏览器、手机等多终端支持</p>
            <p>流式查看，快速、节约流量</p>
            </div>
        </div>
        <div class="hero-unit col-md-4">
            <h3 style="text-align: center;">按需扩展，运维便捷</h3>
            <div style="margin-left: 67px;">
            <p>根据需求随时扩展</p>
            <a class="btn btn-primary btn-large" style="float: right;margin-right: 67px;margin-top: 12px;" href="tech/7">更多</a>
            <p>支持分布式存储</p>
            <p>转换异常处理</p>
            </div>
        </div>

        <div class="clear"></div>
        
        <div class="row" style="margin-right: 0px;margin-left: 0px; margin-top: 185px;">
        <div class="col-xs-6 col-md-2">
           <h2 style="text-align: center;margin-top: 8px;">他们在使用</h2>
          </div>
          <div class="col-xs-6 col-md-2">
            <a href="http://www.joyoung.com.cn/" target="_blank" class="">
              <img style="height: 50px; width: 157px; display: block;" src= "http://ww4.sinaimg.cn/large/6355763cgw1edioyk2iqoj20a00453yl.jpg">
            </a>
          </div>
          <div class="col-xs-6 col-md-2">
            <a href="http://pan.sohu.net/" target="_blank" class="">
              <img style="height: 50px; width: 157px; display: block;" src= "https://pan.sohu.net/dpstatic/img/logo.png">
            </a>
          </div>
          <div class="col-xs-6 col-md-2">
              <img style="height: 50px; width: 157px; display: block;" src= "http://www.everydo.com/cases/img/logo-wangyi.gif">
          </div>
          <div class="col-xs-6 col-md-2">
              <img style="height: 50px; width: 157px; display: block;" src= "http://www.everydo.com/cases/img/logo-hmzdfxx.gif">
          </div>
          <div class="col-xs-6 col-md-2">
            <a href="http://jxzx.cc" target="_blank" class="">
              <img style="height: 50px; width: 157px; display: block;" src= "http://jxzx.cc/images/log1.jpg">
            </a>
          </div>
        </div>
