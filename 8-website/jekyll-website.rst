======================
使用Jekyll建站
======================

如果需要做网站本地化，则需要对网站制作技术本身有一些了解。目前制作网站的技术非常多，而且更多的网站制作技术还在不断涌现。本节将讲解如何使用Jekyll制作网站，并将其本地化。


基础知识
================

使用Jekyll建站，需要掌握如下基本知识：
* Jekyll
* HTML，CSS，Javascript
* Liquid 模板语言


Windows下安装Jekyll
-----------------------

Jekyll使用Ruby语言编写，可以参照官方文档 `Installation via RubyInstaller <https://jekyllrb.com/docs/windows/>`_中的步骤。简要步骤如下：

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