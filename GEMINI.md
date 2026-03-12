# GEMINI.md - Resume Template Context

This project is a Jekyll-based resume template designed to be hosted on GitHub Pages. It allows users to create a professional, web-based resume by editing simple YAML data files and a configuration file.

## Project Overview

- **Type:** Static Site (Jekyll)
- **Primary Technologies:** Jekyll (Ruby), Sass, HTML/Liquid, Docker
- **Architecture:**
  - **Configuration:** `_config.yml` contains site-wide settings, social links, and section toggles.
  - **Content:** Located in `_data/` as YAML files (e.g., `experience.yml`, `education.yml`, `skills.yml`).
  - **Layouts:** `_layouts/resume.html` is the main template.
  - **Styles:** Modular Sass in `_sass/`, entry point at `css/main.scss`.
  - **Assets:** Icons in `_assets/` and `_includes/icons/`, images in `images/`.

## Building and Running

### Local Development
To run the project locally, you need Ruby and Bundler installed:

1.  **Install dependencies:**
    ```bash
    bundle install
    ```
2.  **Start the Jekyll server:**
    ```bash
    bundle exec jekyll serve
    ```
    The site will be available at `http://localhost:4000`.

### Using Docker
1.  **Build the image:**
    ```bash
    docker image build -t resume-template .
    ```
2.  **Run the container:**
    ```bash
    docker run --rm --name resume-template -v "$PWD":/home/app --network host resume-template
    ```

### Deployment
- The project is optimized for **GitHub Pages**.
- Push changes to the `gh-pages` branch for automatic deployment.
- A `CNAME` file is present for custom domain support.

## Development Conventions

### Customizing Content
- **Personal Info:** Edit `_config.yml` for your name, title, contact info, and "looking for work" status.
- **Resume Sections:** Edit the corresponding files in `_data/`:
  - `associations.yml`: Professional memberships.
  - `education.yml`: Academic history.
  - `experience.yml`: Work history (supports HTML in `summary`).
  - `interests.yml`: Personal hobbies.
  - `links.yml`: Additional portfolio or social links.
  - `projects.yml`: Notable projects.
  - `recognitions.yml`: Awards and honors.
  - `skills.yml`: Professional skills.

### Styling
- Styles are written in SCSS and located in `_sass/`.
- `_variables.scss` contains color and typography settings.
- `_resume.scss` contains the core resume layout styles.
- The project uses a "print-only" class for elements that should only appear when printing the resume.

### Adding Icons
- Icons are stored as SVG snippets in `_includes/icons/`.
- To add a new social link icon, add the SVG to `_includes/icons/` and update `_includes/icon-links.html`.

## Key Files
- `index.html`: The entry point that uses the `resume` layout.
- `_config.yml`: The central configuration hub.
- `_layouts/resume.html`: The master template for the resume.
- `Gemfile`: Ruby dependencies (Jekyll and its plugins).
- `Dockerfile`: Environment for running the site in a container.
