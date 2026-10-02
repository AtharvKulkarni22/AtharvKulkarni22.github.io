# Atharv Kulkarni - Personal Academic Website

A custom Jekyll + GitHub Pages site for `AtharvKulkarni22.github.io`.

## What is included

- Responsive one-page academic homepage
- About / research summary
- News timeline
- Publication cards with local PDFs, code, paper, and project links
- Research experience and education
- Resume + Research Statement downloads
- Profile photo
- Light/dark mode
- Mobile navigation
- GitHub Actions deployment to GitHub Pages

## 1. Create the GitHub repository

Create a public repository named exactly:

```text
AtharvKulkarni22.github.io
```

Do not initialize it with a README if you are going to push this folder as-is.

## 2. Push this folder

From inside this folder:

```bash
git init
git add .
git commit -m "Launch personal website"
git branch -M main
git remote add origin git@github.com:AtharvKulkarni22/AtharvKulkarni22.github.io.git
git push -u origin main
```

If you prefer HTTPS:

```bash
git remote add origin https://github.com/AtharvKulkarni22/AtharvKulkarni22.github.io.git
```

## 3. Enable GitHub Pages

In the repository:

1. Open **Settings -> Pages**.
2. Under **Build and deployment**, choose **GitHub Actions**.
3. Push to `main` if you have not already.
4. The included workflow builds and deploys the site automatically.

Your site should become available at:

```text
https://atharvkulkarni22.github.io/
```

## 4. Edit content

Most content is kept outside the HTML:

- `_data/profile.yml` - bio, links, research interests, document links
- `_data/news.yml` - news items
- `_data/publications.yml` - publication cards
- `_data/experience.yml` - research/work experience
- `_data/education.yml` - education

The main page layout is `index.html`.

## Add a separate CV later

Put the file here:

```text
assets/docs/Atharv_Kulkarni_CV.pdf
```

Then edit `_data/profile.yml`:

```yaml
cv: "/assets/docs/Atharv_Kulkarni_CV.pdf"
```

The CV button will appear automatically.

## Add a publication

Add another entry to `_data/publications.yml` using this pattern:

```yaml
- title: "Paper title"
  authors: "Author One, Author Two"
  venue: "Conference 2027"
  year: 2027
  status: "Conference"
  image: "/assets/img/paper-image.png"
  description: "One or two sentence description."
  paper: "https://arxiv.org/abs/..."   # Leave blank while under review if you do not want a public paper link.
  code: "https://github.com/..."
  project: "https://..."
  featured: true
```

## Local preview (optional)

Install Ruby + Bundler, then run:

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`.

## Photo crop

The site uses the full original photo and crops it responsively with CSS. To change where the crop focuses, edit:

```css
.photo-frame img { object-position: 39% center; }
```

inside `assets/css/style.scss`.
