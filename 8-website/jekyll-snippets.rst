=================
Jekyll 常用代码
=================


使用_data/nav.yml构建导航栏
=================================

_data/nav.yml

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


_includes/nav.html

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