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

Education and experience entries support a `logos` list with `name`, `image`, and `url`. Logos are stored locally under `images/institutions/` and link to the corresponding institution or lab. Experience entries may also set `group_url` to link the lab or department name.

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

Institution and lab artwork was copied from the following sources without redrawing. THUNLP uses the image selected by Chenyu; the other assets come from official institution websites. The Liverpool shield retains its original blue variant, with the SVG's automatic white-on-dark override removed because the homepage displays logos on white backgrounds.

| Local asset | Source |
| --- | --- |
| `thunlp-logo.png` | [THUNLP image supplied by Chenyu](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSS1VhVhNiYAdOZCwIrn9ev_cW4xkNIwY0Ioowv37e8Qw&s=10) |
| `aim3.png` | [AIM3 Lab website logo](https://www.ruc-aim3.com/assets/logo/aim3-logo.png) |
| `oxford.png` | [Oxford website crest](https://www.cs.ox.ac.uk/apple-touch-icon-114x114.png) |
| `microsoft.svg` | [Microsoft's downloadable symbol](https://learn.microsoft.com/en-us/entra/identity-platform/media/howto-add-branding-in-apps/ms-symbollockup_mssymbol_19.svg) |
| `ut-austin.png` | [UT Austin website shield](https://www.utexas.edu/android-chrome-512x512.png) |
| `liverpool-shield.svg` | [University of Liverpool website shield](https://www.liverpool.ac.uk/rb/assets/icon.svg) |
| `xjtlu.svg` | [Xi’an Jiaotong-Liverpool University website logo](https://www.xjtlu.edu.cn/wp-content/uploads/2024/01/en-header-logo.svg) |

These marks identify the institutions mentioned in Chenyu's education and experience; their ownership remains with the respective institutions.

Academic Pages derives from Michael Rose's Minimal Mistakes theme. The original [MIT license](LICENSE) is retained.
