=================
Jekyll网站本地化
=================

Jekyll网站本地化示例：
* `英文Jekyll官网 <https://jekyllrb.com>`_
* `中文Jekyll官网 <https://www.jekyll.com.cn>`_

网站素材：`Allan Lab @ Leiden University <https://github.com/mpa139/allanlab>`_
网站预览：http://www.allanlab.org


网站本地化步骤
====================

辨识语言资源
--------------

如下文件中有需要本地化的语言资源：

* _config.yml
* _data中的 yml数据
* _includes中的各html
* _pages中的MD文件



语言资源准备
------------------

为 SDL Trados 准备
^^^^^^^^^^^^^^^^^^^^^^^

yml文件的准备

::

   start:  ^.*?:\s"
   end: "$

markdown文件的准备


html文件的准备



使用Okapi准备
^^^^^^^^^^^^^^^^^^^^^^^

Okaipi 工具：http://okapiframework.org