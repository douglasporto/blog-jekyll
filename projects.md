---
layout: main
---

<main class="home projects" id="post" role="main" itemprop="mainContentOfPage" itemscope="itemscope" itemtype="http://schema.org/Blog">
    {% assign items = site.projects | sort: 'date' | reverse %}
    {% for projects in items %}
        {% assign mod = forloop.index | modulo: 2 %}
        <div id="grid" class="row flex-grid {%if mod == 0 %} grid-invert {% endif %}">
          <article class="box-item post-{{post.main-class}}" itemscope="itemscope" itemtype="http://schema.org/BlogPosting" itemprop="blogPost">            
                <div class="box-body">
                    {% if projects.image %}
                        <div class="cover cover-project">
                            {% include new-post-tag.html date=projects.date %}
                            <a href="{{ projects.link | prepend: site.baseurl }}">
                                <img src="../assets/img/placeholder.png" data-url="{{ projects.image }}" class="preload">
                            </a>
                        </div>
                    {% endif %}
                </div>
            </article>
            <div class="box-item-info">
              <header class="info-header">
                <h2 class="post-title" itemprop="name">
                    {{ projects.title }} douglas
                </h2>
              </header>
              <p class="description">{{ projects.introduction }}</p>
              <div class="footer-info">
                <ul>
                    <li>
                        <meta itemprop="datePublished" content="{{ projects.date | date_to_xmlschema }}">
                        <time itemprop="datePublished" datetime="{{ projects.date | date_to_xmlschema }}" class="date">
                            <svg data-v-5ea290a8="" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-calendar"><rect data-v-5ea290a8="" x="3" y="4" width="18" height="18" rx="2" ry="2"></rect><line data-v-5ea290a8="" x1="16" y1="2" x2="16" y2="6"></line><line data-v-5ea290a8="" x1="8" y1="2" x2="8" y2="6"></line><line data-v-5ea290a8="" x1="3" y1="10" x2="21" y2="10"></line></svg>
                            <span>{% include date.html date=projects.date %}</span>
                        </time>
                    </li>
                    <li>
                        <div class="project-url">
                          <svg data-v-5ea290a8="" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-link"><path data-v-5ea290a8="" d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path data-v-5ea290a8="" d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>
                          {% if projects.link %}
                          <span><a href="{{ projects.url | prepend: site.baseurl }}">{{ projects.link }}</a></span>
                          {% else %}
                          <span>Projeto em andamento ou fora do ar</span>
                          {% endif %}
                        </div>
                    </li>
                    <li>
                        <div class="tags">
                            <svg data-v-5ea290a8="" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-tag"><path data-v-5ea290a8="" d="M20.59 13.41l-7.17 7.17a2 2 0 0 1-2.83 0L2 12V2h10l8.59 8.59a2 2 0 0 1 0 2.82z"></path><line data-v-5ea290a8="" x1="7" y1="7" x2="7" y2="7"></line></svg>
                            
                            {% for tag in projects.tags %}
                                <span>#{{ tag }}</span>
                            {% endfor %}
                            
                        </div>    
                    </li>
                </ul>
              </div>
            </div>
        </div>
    {% endfor %}
</main>
