# Quantum Algorithms and Tensor Analysis Group Website

This site uses Jekyll. In practice, that means most content updates happen in
the files inside `_data/`, and the homepage reads from those files
automatically.

If you want to add a person, publication, presentation, or alumnus, you usually
do not need to edit the HTML.

## Main files

- `_data/group.yml`: general site text
  Use this for the homepage intro, Michael’s profile block, research topics,
  contact text, and research-area tags.
- `_data/people.yml`: current group members
  Add one entry per current member with their name, role, email, image,
  short bio, and research interests.
- `_data/publications.yml`: recent papers
  Add one entry per paper with title, authors, year, venue, links, and a short
  summary.
- `_data/presentations.yml`: talks and presentation materials
  Use this for slide decks, PDFs, posters, videos, and seminar links.
- `_data/repositories.yml`: code repositories
  Use this for GitHub repositories, software projects, and code releases tied
  to the group.
- `_data/alumni.yml`: previous group members
  Use this for former members and where they are now.
- `index.html`: homepage template
  This is the page that renders the data files into the actual website.
- `_layouts/default.html`: shared page wrapper
  This contains the common HTML around the homepage.
- `assets/site.css`: site styling
  Edit this only if you want to change the look and layout.
- `_config.yml`: Jekyll settings
- `Gemfile`: Ruby dependencies for local preview

## Common edits

### Add a new person

Add one new block to `_data/people.yml`.

Each person should have:
- `name`: full name
- `role`: current position in the group
- `email`: public contact email
- `image`: path to their photo
- `summary`: 1-2 sentences about what they work on
- `interests`: a short list of keywords shown as tags
- `website`: optional personal site or profile

Example:

```yml
- name: New Member
  role: PhD Student
  email: new.member@example.com
  image: images/teampic/bio-photo.jpg
  summary: Short description of research interests.
  interests:
    - Tensor networks
    - Quantum algorithms
```

### Add a publication

Add one new block to `_data/publications.yml`.

Each publication should include:
- `title`: full paper title
- `authors`: author list as you want it shown
- `year`: publication year
- `type`: for example `Preprint`, `Conference`, or `Journal`
- `venue`: optional conference or journal information
- `link`: main paper link
- `code`: optional code repository
- `project`: optional project page
- `summary`: 1-2 sentence explanation of what the paper does

Example:

```yml
- title: Paper Title
  authors: Author One, Author Two
  year: 2026
  type: Journal
  venue: Journal / conference details
  link: https://doi.org/...
  code: https://github.com/example/project
  project: https://example.com/project-page
  summary: One-sentence summary of the contribution.
```

### Add a presentation

1. Put the file in `presentations/`.
2. Add one new block to `_data/presentations.yml`.

This section is for:
- slide decks
- talk PDFs
- poster PDFs
- video links
- seminar or workshop resources

```yml
- title: Talk title
  speakers: Speaker Name
  event: Seminar or conference
  year: 2026
  summary: What the talk is about.
  file: presentations/talk-slides.pdf
  file_label: Slides PDF
  video: https://...
```

### Add a repository

Add one new block to `_data/repositories.yml`.

Each repository entry can include:
- `name`: repository or project name
- `category`: short label such as `Research software` or `Library`
- `maintainers`: person or people responsible
- `summary`: 1-2 sentence description
- `link`: main repository link
- `paper`: optional paper link
- `demo`: optional demo or project page
- `topics`: short tags shown on the site

```yml
- name: Project Name
  category: Research software
  maintainers: Person One, Person Two
  summary: Short explanation of what the repository contains.
  link: https://github.com/example/project
  paper: https://arxiv.org/abs/...
  demo: https://example.com
  topics:
    - Tensor networks
    - Machine learning
```

### Add an alumnus

Add one new block to `_data/alumni.yml`.

Each alumnus entry should include:
- `name`: full name
- `role`: former role in the group
- `years`: optional time period in the group
- `now_at`: current job, university, or institution
- `website`: optional personal page or profile

```yml
- name: Former Member
  role: Former Postdoc
  years: 2021-2024
  now_at: Assistant Professor, Example University
  website: https://...
```

## Local preview

GitHub Pages and this `Gemfile` expect a modern Ruby. If `bundle install`
fails with an `ffi` version error, check your Ruby version first:

```bash
ruby -v
which ruby
which bundle
```

If needed, switch to Ruby 3.1+ before installing dependencies.

### Example with `rbenv`

```bash
rbenv install 3.2.2
rbenv local 3.2.2
gem install bundler
bundle install
bundle exec jekyll serve
```

### Example with `conda`

```bash
conda install -c conda-forge ruby=3.2
gem install bundler
bundle install
bundle exec jekyll serve
```

### Check that the site is running

After starting Jekyll, you should see output mentioning a local server such as
`http://127.0.0.1:4000`.

Open that URL in your browser, not `file:///.../index.html`.

You can also verify from the terminal:

```bash
curl -I http://127.0.0.1:4000
```

You should get an HTTP response like `200 OK`.

## Editing workflow

For normal content updates, use this order:

1. Edit the relevant file in `_data/`.
2. Save the file.
3. Refresh the local Jekyll page in the browser.
4. Check that the new text, links, and formatting look correct.

If something does not show up, the most common causes are:
- YAML indentation is incorrect
- a field name does not match the expected one
- the browser is still showing an old cached version
