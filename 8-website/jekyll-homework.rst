=====================
Jekyll网站本地化作业
=====================


**作业素材** ：

* 网站素材：`Allan Lab @ Leiden University <https://github.com/mpa139/allanlab>`_
* 网站预览：http://www.allanlab.org


**作业要求** ：

1. 下载素材，并在本地化运行网站

::

    bundle install
    bundle exec jekyll serve

2. 辨识语言资源

下方仅供参考，需要自行找全文件，并设定解析规则，并将提取规则写在说明文件中。

* _config.yml
* _data中的 yml数据
* _includes中的各html
* _pages中的MD文件（将链接、代码等部分处理为相应的内嵌标签）
* _layouts中homelay.html

3. 将上述语言资源准备为SDL Trados的项目包，并提交至CATTP平台。

.. note::

    创建项目文件包后，译员不需要操心原始格式，可以直接打开进行翻译。


4. 自行练习使用机器翻译预翻译所有语言资源。