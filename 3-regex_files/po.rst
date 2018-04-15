PO格式
######################

PO文件有 Entries 组成。每个 Entry 中包含了原文

PO格式结构

::

    white-space
    #  translator-comments
    #. extracted-comments
    #: reference…
    #, flag…
    #| msgid previous-untranslated-string
    msgid untranslated-string
    msgstr translated-string


一个典型的PO文件如下：

.. code-block:: po

    #: lib/error.c:116
    msgid "Unknown system error"
    msgstr "未知系统错误"





参考资料：
[1]：http://docs.translatehouse.org/projects/localization-guide/en/latest/guide/project/howto.html    