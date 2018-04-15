软件本地化相关概念
#############################

Locale
================

Locale
    Locale定义了软件处理某个语言与某个国家特殊习惯的方式，例如:时间日期格式、数字，度量单位，货币，每周开始的日子等。

locale的命名方式，通常为 ``ll_cc``。 ll 指的是国际标准 `ISO639.2 <http://www.loc.gov/standards/iso639-2/php/English_list.php>`_ 的两位语言编码，cc指的是国际标准 ISO3166中的两位国家编码。例如德国德语，ll 为 de，cc 为DE。德国的locale名称为 de_DE。大陆中文则为，zh_CN。



.. list-table:: 常见locale编码
   :widths: 10 20 10 20
   :header-rows: 1

   * - 语言
     - 代码
     - 国家
     - 代码
   * - Chinese
     - zh
     - China
     - CN
   * - French
     - Fr
     - France
     - FR
   * - German
     - de
     - Deutsche
     - De
   

CLDR
============
`CLDR <http://cldr.unicode.org>`_ 是各种locale信息汇总交换项目。使用 `LDML <http://www.unicode.org/reports/tr35/>`_ (unicode data markup langauge specification，区域数据标记语言规范）进行数据的标记。

CLDR的使用者：

* Apple (macOS, iOS, watchOS, tvOS, and several applications; Apple Mobile Device Support and iTunes for Windows; …)
* Google (Web Search, Chrome, Android, Adwords, Google+, Google Maps, Blogger, Google Analytics, …)
* IBM (DB2, Lotus, Websphere, Tivoli, Rational, AIX, i/OS, z/OS,…)
* Microsoft (Windows, Office, Visual Studio, …)





常见国家编码

gettext标准
=====================

`gettext <https://www.gnu.org/software/gettext/manual/gettext.html>`_ 是一套完整的国际化和本地化标准。它可以将程序中需要本地化的内容提取出来。


[1]: http://docs.translatehouse.org/projects/localization-guide/en/latest/guide/locales/about.html

[本地化资源]：http://docs.translatehouse.org/projects/localization-guide/en/latest/guide/locale_resource.html
