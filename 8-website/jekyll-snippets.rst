=================
Jekyll 常用代码
=================


使用_data/nav.yml构建导航栏
=================================

1. _data/nav.yml

::

    - title: "Home"
    href: "/"

    - title: "News"
    href: "/news/"

    - title: "Snippets"
    subcategories:
        - subtitle: "Example1"
        subhref: "#"
        - subtitle: "Example2"
        subhref: "#"


2. _includes/nav.html

 .. code-block:: html

    <nav>
    <ul>
        {% for nav in site.data.nav %}
        {% if nav.subcategories != null %}
            <li>
            <a href="{{ site.url }}{{ nav.url }}">{{ nav.title }} ▼</a>
            <ul>
            {% for subcategory in nav.subcategories %}
                <li><a href="{{ site.url }}{{ subcategory.subhref }}">{{ subcategory.subtitle }}</a></li>
            {% endfor %}
            </ul>
            </li>
        {% elsif nav.title == page.title %}
            <li class="active">
            <a href="{{ nav.url }}">{{ nav.title }}</a>
            </li>
        {% else %} 
            <li>
            <a href="{{ site.url }}{{ nav.href }}">{{ nav.title }}</a>
            </li>
        {% endif %}
        {% endfor %}
    </ul>
    </nav>     


    .. note ::

        Note: U+25BC (&#x25BC;) is the unicode for a black down-pointing triange (e.g. ▼)    




添加预估阅读时间
====================

1. 在post模板中 

::

    {% include reading_time.html %}

2. 创建 _includes/reading_time.html

::

    <span class="reading-time" title="Estimated read time">
    {% assign words = content | number_of_words %}
    {% if words < 360 %}
        1 min
    {% else %}
        {{ words | divided_by:180 }} mins
    {% endif %}
    </span>    





参考来源：

