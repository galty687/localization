======================
使用Jekyll建站
======================

如果需要做网站本地化，则需要对网站制作技术本身有一些了解。目前制作网站的技术非常多，而且更多的网站制作技术还在不断涌现。本节将讲解如何使用Jekyll制作网站，并将其本地化。

Jekyll的优势
-----------------

#. 访问速度快。
#. 安全稳定。
#. 自定义功
#. Github的生态圈


基础准备
================

使用Jekyll建站，需要掌握如下基本知识：

* Jekyll
* HTML，CSS，Javascript
* Liquid 模板语言


Windows下安装Jekyll
-----------------------

Jekyll使用Ruby语言编写，可以参照官方文档 `Installation via RubyInstaller <https://jekyllrb.com/docs/windows/>`_ 中的步骤。简要步骤如下：

#. 下载 RubyInstaller，并安装
#. 运行 ``gem install jekyll bundler``
#. 检查是否安装成功 ``jekyll -v``

素材
-----------------

为了演示方便，选择了W3C的HTML页面：`素材 <https://www.w3.org/Style/Examples/011/firstcss.en.html>`_

素材准备：

#. 复制STEP 1 中的html代码，并命名为 index.html
#. 复制STEP 7 中CSS的代码，并存储为 mystyle.css
#. 在Head中将css与html相连。 

    .. code-block:: html

        <link rel="stylesheet" href="mystyle.css">




演示传统html网站的制作
===============================

最早期的网站，需要不断手动增加所有内容，当内容足够多的时候，基本无法手动维护，很多内容难以复用。

#. 修改index.hml的语言和编码，修改后的代码如下

.. code-block:: html

    <html lang="zh-cn">
    <head>
    <title>My first styled page</title>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <link rel="stylesheet" href="mystyle.css"/>
    </head>

#. 增加footer的版权信息，并改变footer的背景色



演示Jekyll建站
====================

新建Jekyll站点
-------------------

#. 将index.html放入根目录
#. 新建css文件夹，并将mystyle.css放图
#. 新建 _config.yml文件，配置网站基本信息

.. code-block :: html

        ---
        layout: default
        ---




将index.html作为模板
----------------------------

#. 新建 _layout 文件
#. 在 layout 文件夹中新建 default.html
#. 将css引用改为 {{site.baseurl}}/css/mystyle.css，并增加下方liquid语句

::

        {{content}}


#. 在Terminal中运行 ``jekyll serve ``
#. 访问 http://127.0.0.1:4000/ 即可访问该站


制作其他静态页面
----------------------------

    .. code-block :: html

        ---
        layout: default
        ---


制作news.html动态页面
-------------------------

#. 新建 _post 文件夹
#. 在文件夹中增加两个markdown文件，并增加Front Matter

..code-block: html

    ---
    title: PKU is great
    layout: default
    meta: This is an article about PKU.

    ---

#. 在news.html中新增加如下liquid模板

.. code-block:: html

    <ul>
        {% for post in site.posts %}
        <li>
            <a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a>
            <p>{{post.meta}}</p>
        </li>
        {% endfor %}
    </ul>


将default模板拆解
-------------------------
#. 分别将 Nav, footer, address部分另存为 nav.html, footer.html, address.html
#. 使用 {% include nav.html %} 将其添加至default模板，其他部分类似。



将footer.html数据化
--------------------------

#. 新增 _data 文件夹，并在其中新建 website.yml   
#. 在footer.hml中，使 ``{{site.data.website.copyright}}`` 填充数据