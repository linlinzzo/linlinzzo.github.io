---
title: "本站提供公益Umami统计服务"
categories: [ "网站" ]
tags: [  ]
draft: false
slug: "umami-yes"
date: "2022-11-25T22:23:39+08:00"
---

<!-- wp:paragraph -->
<p>为了知道网站的访客数量，我打算使用像百度统计、CNZZ、51la统计之类的第三方统计。但百度统计没有广告，它靠什么来维持服务器的支出我们不得而知。我个人对百度统计不太放心，怕它会对网站的访客做分析。（仅仅只是猜测而已）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>之前在开往了解到Umami统计。今天请杜老师折腾一整天帮忙装了下Umami。（博客今天也寂了大半天了）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Umami相比于不蒜子统计，还可以看到Referrer访问来源，看看访客来自哪个网站，说不定可以发现博客呢。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>这个Umami可以添加多个网站，还有多用户。独乐乐不如众乐乐。我打算开放出来让大家申请，只要向我申请一下就可以轻松用上Umami。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>请将以下信息发到我的邮箱<strong>xiaozonglin200701@outlook.com</strong>：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>你想要的用户名</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>将要部署Umami的网站名称</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>网站域名</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>我在收到邮件后会回复你：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>初始密码（记得登录后要改密码哦）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>统计代码（请放置在头部&lt;head&gt;中）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>申请条件：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>不要有其他的第三方统计代码</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>内容合法合规</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>其他我认为有必要作为申请条件的要求</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>避免统计被广告拦截器拦截的方法</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>示例：<a href="https://f.xiaozonglin.cn/" data-type="URL" data-id="https://f.xiaozonglin.cn/" target="_blank" rel="noreferrer noopener">https://f.xiaozonglin.cn/</a></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>将umami.js部署在自己的网站上，并对文件重命名。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>将追踪代码中的src改为自己网站上的js文件地址。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>在标签中添加data-host-url="https://u.xiaozonglin.cn"。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>故障报告</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>2022年11月27日上午7时，在检查统计数据状况的时候发现“杜老师说”和“林林杂语”网站的统计数据存在数小时的空窗。对Umami服务的两个容器进行监控，发现两个容器的磁盘IO均为0。用开发人员选项对两个网站的网页进行检查发现，访客仅下载了umami.js脚本，并没有对应用程序接口发送数据。在本站将<em>data-cache</em>、<em>data-auto-track</em>、<em>data-do-not-track</em>三个属性删除后，发现统计结果恢复正常。据此可以推断，本次故障是由于添加属性导致访客没有发送数据造成的。本次故障已通知“杜老师说”的站长，等待站长响应（已恢复正常）。本次故障暴露出“我个人在推荐属性时并没有对属性可能造成的后果进行试验，只是按照官方文档上的描述进行推断”这一问题，会在今后的维护中改正。我将持续对统计结果进行关注，并及时解决问题。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2022年12月4日，收到来自“启涵”和“Rose”的反馈，并在“杜老师说”网站控制台中发现相似的问题。我修改了CDN的CORS跨域设置，目前“杜老师说”的数据已恢复正常。“Rose个人博客”和“启涵的博客”的数据恢复情况还有待确认。本次故障是由于跨域没有设置允许的请求方法导致的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2022年12月29日15时52分，服务器的CPU利用率升至92.4%，此后腾讯云的监控失效，硬盘IO等待时间在近25分钟内保持高位。“林林杂语”博客主站、Umami后台（统计脚本受CDN缓存不受影响）、博文集萃服务均不可用。16时17分，服务器相关指标落回正常区间，服务均恢复正常。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":206,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image aligncenter size-large"><img src="https://www.xiaozonglin.cn/wp-content/uploads/2022/12/image-7-1024x526.png" alt="" class="wp-image-206"/></figure>
<!-- /wp:image -->