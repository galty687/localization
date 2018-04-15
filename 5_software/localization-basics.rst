软件本地化相关概念
==================== 

Locale
================


locale的命名方式，通常为 ``ll_cc``。 ll 指的是国际标准 ISO639 的两位语言编码，cc指的是国际标准 ISO3166中的两位国家编码。例如德国德语，ll 为 de，cc 为DE。德国的locale名称为 de_DE。大陆中文则为，zh_CN。

常见语言代码


常见国家编码

gettext标准
=====================

`gettext <https://www.gnu.org/software/gettext/manual/gettext.html>`_ 是一套完整的国际化和本地化标准。它可以将程序中需要本地化的内容提取出来。