---
layout: homepage
permalink: /
title: "About Me"
title_icon: "👋"
description: "Chenyu Li is an undergraduate in Informatics at UT Austin, interested in large language models, responsible AI, computational social science, AI+X, and LLM evaluation."
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

I am an undergraduate student in Informatics at the [School of Information, The University of Texas at Austin](https://ischool.utexas.edu/), concentrating in Human-Centered Data Science.

My research interests focus on the capabilities, safety, and societal implications of large language models. I have had the fortune to work with many amazing research mentors and collaborators, including [Yuxiao Ye](https://yeyuxiao.github.io/), [Huiyuan Xie](https://huiyuanxie.github.io/), [Zhiyuan Liu](https://nlp.csai.tsinghua.edu.cn/~lzy/), [Zhenfei Yin](https://yinzhenfei.github.io/), [Wenxuan Wang](https://jarviswang94.github.io/index.html), [Fangzhao Wu](https://www.microsoft.com/en-us/research/people/fangzwu/), [Xing Xie](https://scholar.google.com/citations?user=5EQfAFIAAAAJ), and many others.

I’m always enthusiastic about collaborating with researchers from diverse fields. If you’re interested in working together, feel free to reach out at [chenyu157@utexas.edu](mailto:chenyu157@utexas.edu).

## <span class="profile-section-icon" aria-hidden="true">🔬</span> Research Interests
{: #research-interests}

- **Agents:** developing long-horizon AI agents for complex tasks, including scientific discovery and AI-for-AI research.
- **Responsible AI:** studying model safety, alignment, and reliability.
- **Computational social science:** investigating human behavior, social dynamics, and the societal impacts of AI.
- **AI+X:** integrating AI with other disciplines, such as law and psychology, to address domain-specific challenges.
- **LLM evaluation:** assessing model capabilities, limitations, and behaviors across these research directions and diverse contexts.

## <span class="profile-section-icon" aria-hidden="true">🎓</span> Education
{: #education}

<div class="profile-entries">
{% for entry in site.data.profile.education %}
  <div class="profile-entry profile-education{% if entry.logos %} profile-entry--with-logo{% endif %}">
    {% include personal-logos.html logos=entry.logos %}
    <div class="profile-entry__body">
    <div class="profile-entry__heading">
      <h3>{{ entry.institution | escape }}{% if entry.status %} <span class="profile-education__status">({{ entry.status | escape }})</span>{% endif %}</h3>
      <span class="profile-entry__date">{{ entry.dates | escape }}</span>
    </div>
    <p>{{ entry.program | escape }}</p>
    <p class="profile-entry__detail">{{ entry.detail | escape }}</p>
    </div>
  </div>
{% endfor %}
</div>

## <span class="profile-section-icon" aria-hidden="true">📄</span> Publications
{: #publications}

{% include personal-publications.html %}

## <span class="profile-section-icon" aria-hidden="true">🏆</span> Honors & Awards
{: #honors-awards}

<ul class="profile-awards">
{% for award in site.data.profile.awards %}
  <li>
    <time class="profile-awards__year" datetime="{{ award.year }}">{{ award.year }}</time>
    <div class="profile-awards__body">
      <strong class="profile-awards__title">{{ award.title | escape }}</strong>
      <div class="profile-awards__meta">
        <span class="profile-entry__detail">{{ award.institution | escape }}</span>
        {% if award.amount %}<span class="profile-awards__amount">{{ award.amount | escape }}</span>{% endif %}
      </div>
    </div>
  </li>
{% endfor %}
</ul>

## <span class="profile-section-icon" aria-hidden="true">💼</span> Selected Experience
{: #experience}

{% for entry in site.data.profile.experience %}
{% include personal-experience.html entry=entry %}
{% endfor %}
