# Chenyu Li's academic homepage

Personal website built with [Academic Pages](https://github.com/academicpages/academicpages.github.io), Jekyll, and GitHub Pages.

The homepage contains About Me, Research Interests, Education, Publications, Honors & Awards, and Selected Experience. Experience entries combine academic and industry roles, with the role, institution and group in the title, followed by dates, a short research description, and advisor links.

## Update content

| Content | File |
| --- | --- |
| Name, affiliation, email, LinkedIn, avatar, site URL | `_config.yml` |
| About Me and Research Interests | `_pages/about.md` |
| Education, honors, and experience | `_data/profile.yml` |
| Publications | `_data/publications.yml` |
| CV PDF and its preview page | `CV.pdf`, `_pages/cv.html`, `assets/cv/chenyu-li-cv-preview.png` |
| Section navigation | `_data/navigation.yml` |
| Homepage layout and styling | `_layouts/homepage.html`, `_sass/layout/_profile.scss` |

To add a portrait, place it in `images/` and set `author.avatar` in `_config.yml` to its filename. The site displays initials when no image is set.

The current `images/chenyu-li.jpg` preserves the supplied photo. `author.avatar_crop` enables a circular CSS crop that removes its outer dark margin. The crop coordinates in `_sass/layout/_profile.scss` are specific to this photo; disable that setting or adjust the crop when replacing it.

Education and experience entries support a `logos` list with `name`, `image`, and `url`. Logos are stored locally under `images/institutions/` and link to the corresponding institution. Education keeps the compact Xi’an Jiaotong-Liverpool shield beside the Liverpool wordmark, with the logo group above the text on mobile. Experience entries each show one institution mark in a compact left column, including on mobile, with consistent visible artwork bounds. Desktop marks are 80px within an 88px column, followed by a 16px gap to the text; the column scales to 72px or 64px on smaller screens. The optional `style` field supports wider wordmarks and CSS framing for crests with large white margins. Experience entries also use `group_url` to retain links on lab or department names.

The supplied `CV.pdf` is published unchanged and linked from `/cv/`. The CV page displays a full-page preview and offers direct PDF viewing and downloading. Both the navigation and author sidebar link to this page. The original template's example CV page and sample files remain excluded from the generated site.

After replacing the current one-page `CV.pdf`, regenerate its preview with Poppler before deploying, so the preview and downloadable file stay in sync:

```powershell
pdftoppm -f 1 -singlefile -r 144 -png CV.pdf assets/cv/chenyu-li-cv-preview
```

If the CV grows beyond one page, add previews for the additional pages and update the page images and their alt text in `_pages/cv.html`.

## Preview on Windows with Docker

Prerequisites: Node.js and a running Docker Desktop.

From this repository, run:

```powershell
npm.cmd install
npm.cmd run build
docker compose up --build
```

Open http://127.0.0.1:4000/. Stop the server with Ctrl+C, then run `docker compose down`.

Markdown and style edits rebuild automatically. Restart the container after changing `_config.yml`. After JavaScript changes, run `npm.cmd run build` again.

Docker, the dev container, and GitHub Actions use Ruby 3.3. The Docker preview uses `_config_docker.yml` for the local site URL.

## Preview with Ruby installed locally

```sh
bundle install
npm install
npm run build
bundle exec jekyll serve --host 127.0.0.1
```

## Publish to GitHub Pages

The existing `.github/workflows/jekyll.yml` workflow builds and deploys pushes to `master`. Set the repository's Pages source to **GitHub Actions**. The public URL configured in `_config.yml` is https://chenyu237.github.io.

## Content sources and layout references

Personal facts, dates, advisors, and contact information come from the supplied CV. ScopeBench's publication details and links were checked against its [ACL Anthology entry](https://aclanthology.org/2026.emnlp-main.1224/).

Academic homepage structure and concise presentation were informed by the homepages of [Yuxiao Ye](https://yeyuxiao.github.io/), [Zhenfei Yin](https://yinzhenfei.github.io/), and [Huanhuan Ma](https://www.huanhuanma.top/). Biographical text was written from Chenyu's own CV.

The compact awards list and a single award icon were informed by [Hao Chen's homepage](https://hmarkc.github.io/) and [Renhao Zhang's homepage](https://renhaoz.github.io/). Award names, dates, institutions, and amounts are unchanged.

The standalone CV page's preview and download/open controls were informed by [Jonas Frey's CV page](https://jonasfrey96.github.io/cv/) and [Bivek Pradhan's CV page](https://bivekpradhan.github.io/cv/).

Institution and lab artwork was copied from the following sources without redrawing. The Liverpool and Xi’an Jiaotong-Liverpool education images were selected by Chenyu. Selected Experience displays only the Tsinghua, Oxford, Renmin, and Microsoft institution marks; the lab and department names remain linked in the text. Source images retain their original pixels and aspect ratios. CSS accounts for each source's white margins so the four experience marks have consistent visible size and alignment. Previously used lab artwork remains available locally, with its sources recorded below.

| Local asset | Source |
| --- | --- |
| `thunlp-logo.png` | [THUNLP image supplied by Chenyu](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSS1VhVhNiYAdOZCwIrn9ev_cW4xkNIwY0Ioowv37e8Qw&s=10) |
| `tsinghua-emblem.jpg` | [Tsinghua official visual identity crest](https://vi.tsinghua.edu.cn/gk/xxbz/xh/bzjbzsy.htm) |
| `aim3-wordmark.png` | [Complete AIM3 official wordmark](https://www.ruc-aim3.com/assets/logo/aim3-logo-all.png) |
| `ruc-emblem.png` | [Renmin University official visual identity crest](https://www.ruc.edu.cn/template/1/out/imgs/VI/1.png) |
| `oxford.png` | [Oxford website crest](https://www.cs.ox.ac.uk/apple-touch-icon-114x114.png) |
| `oxford-engineering.svg` | [Oxford Department of Engineering Science logo](https://eng.ox.ac.uk/images/logo.svg) |
| `microsoft.svg` | [Microsoft's downloadable symbol](https://learn.microsoft.com/en-us/entra/identity-platform/media/howto-add-branding-in-apps/ms-symbollockup_mssymbol_19.svg) |
| `ut-austin-wordmark.svg` | [UT Austin Brand Center](https://umac.utexas.edu/brand-center/university-csu-wordmarks/) · [official horizontal wordmark](https://umac.utexas.edu/wp-content/themes/bellmont/dist/images/utexas-primary-horizontal-logo.svg) |
| `liverpool-selected.png` | [Liverpool image supplied by Chenyu](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTgDsK6R-GlWvtoQljBjhJ-t560W1-eVRKpR93fuLvg2w&s=10) |
| `xjtlu-shield.png` | Xi’an Jiaotong-Liverpool shield image supplied by Chenyu in chat |

These marks identify the institutions mentioned in Chenyu's education and experience; their ownership remains with the respective institutions.

Academic Pages derives from Michael Rose's Minimal Mistakes theme. The original [MIT license](LICENSE) is retained.
