---
title: "WordPress网站优化"
categories: [ "网站" ]
tags: [ "wordpress" ]
draft: false
slug: "wordpress-optimization"
date: "2022-12-04T11:41:44+08:00"
---

<!-- wp:paragraph -->
<p>WordPress网站的优化向来是装几个插件就可以解决问题，之前在虚拟主机上做的优化很局限（Redis之类的没有办法装）。目前网站在浏览器上测试的结果还挺好的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>本文章将持续更新，并且本文章所介绍的内容均免费。（或者免费就够用）</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":144,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image size-full"><img src="https://www.xiaozonglin.cn/wp-content/uploads/2022/12/image.png" alt="" class="wp-image-144"/><figcaption class="wp-element-caption">测试结果</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>速度方面的网站优化</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>HTTP2 push content</strong>插件可以帮你轻松应用http2，它会自动将页面所包含的js和css文件用server push推送出去。关于server push，<a rel="noreferrer noopener" href="https://www.ruanyifeng.com/blog/2018/03/http2_server_push.html" data-type="URL" data-id="https://www.ruanyifeng.com/blog/2018/03/http2_server_push.html" target="_blank">《HTTP/2 服务器推送（Server Push）教程》</a>有对于这项技术可以减少请求次数的说明（大概就是用一两次请求快准狠地解决）。除此之外，又拍云也支持设置http2+server push，不过有一点局限。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Redis Object Cache</strong>插件可以将评论等数据通过Redis数据库进行缓存，在提升网站并发能力的同时加快网站的速度。<strong>WP OPcache</strong>插件可以对PHP脚本进行加速。这两个插件需要服务器安装相应的应用或拓展，虚拟主机没有办法使用本方案。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在CDN这边尽量将js、css以及音频等静态文件的缓存过期时间设大一些。又拍云还有页面的压缩，其中压缩等级设为1就足够，设太大会影响速度。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":145,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://www.xiaozonglin.cn/wp-content/uploads/2022/12/image-1-1024x373.png" alt="" class="wp-image-145"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":146,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image size-full"><img src="https://www.xiaozonglin.cn/wp-content/uploads/2022/12/image-2.png" alt="" class="wp-image-146"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>另外，又拍云还支持http3，建议使用。（不过这个对网站的加载速度没有太大影响）</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>安全方面的网站优化</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>虽然说这个东西对于真的想要攻击的人来说是个徒劳，但作为站长，我们不可能将大门敞开着让别人进来。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>服务器方面，杜老师帮忙给我的服务器装上了微步木马检测，我将面板的安全风险弄到0。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":147,"sizeSlug":"full","linkDestination":"none"} -->
<figure class="wp-block-image size-full"><img src="https://www.xiaozonglin.cn/wp-content/uploads/2022/12/image-3.png" alt="" class="wp-image-147"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>应用方面，我将网站所使用的全部插件开启了自动更新，WordPress版本也将始终保持最新。网站使用<strong>Wordfence安全</strong>插件作为应用防火墙，并按照插件所给的提示修改了php.ini。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最近，暴力破解的形势有点严峻。根据Wordfence提供的数据，大部分攻击者选择使用admin为用户名进行爆破，还有一些使用我的域名、英文名、test开头的用户名进行尝试，本月尝试暴力破解的次数为187次，各类攻击的次数为1116次。目前正在使用Two-Factor Authentication加固登陆，这样即便尝试出了密码也无法登录后台。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>解析方面，本站使用腾讯云进行域名注册，<s>使用Cloudflare进行域名的解析，并开启DNSSec</s>。（好像听说DNSSec没有什么用，<s>就蛮开一下</s>）听说Cloudflare在国内的解析有点问题，就转而使用云盾来作权威解析服务。</p>
<!-- /wp:paragraph -->