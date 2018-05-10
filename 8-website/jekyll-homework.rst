=====================
Jekyll网站本地化作业
=====================


**作业素材** ：

* 网站素材：`Allan Lab @ Leiden University <https://github.com/mpa139/allanlab>`_
* 网站预览：http://www.allanlab.org


**作业要求** ：

1. 下载素材，并在本地运行网站

::

    bundle install
    bundle exec jekyll serve

2. 辨识语言资源

下方所列仅供参考，需要自行找全文件，并设定解析规则，同时将提取规则写在新建文件类型的文件描述区域。

* _config.yml
* _data中的 yml数据
* _includes中的各html
* _pages中的MD文件（将链接、代码等部分处理为相应的内嵌标签）
* _layouts中homelay.html

3. 将上述语言资源准备为SDL Trados的项目包，并提交至 `CATTP平台 <http://cattp.pkucat.com/mod/assignment/view.php?id=5181>`_

截止时间： 2018年5月16日 20:30

.. note::

    创建项目文件包后，译员不需要操心原始格式，可以直接打开进行翻译。


4. 自行练习使用机器翻译预翻译所有语言资源。



Trados 微软机器翻译引擎插件从CATTP上下载，如需其他平台的引擎，单独联系我。


5. 自行在本地化运行机器翻译之后的中文网站，并做简要测试，思考：

* 看是否网站都已本地化，是否有提取不完整的地方
* 链接是否正常，如何自动化校验网站链接有效性
* 网站版面是否有需要调整的地方