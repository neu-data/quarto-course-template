<div align="center">

<img src="https://raw.githubusercontent.com/neu-data/.github/main/assets/banner.svg" alt="Neudata Consulting Ltd" width="100%" />

# Neudata course website template

**A branded workshop website — schedule, setup, sessions with slides and practicals, and an instructor version with solutions.**

![Quarto](https://img.shields.io/badge/Quarto-website-055F56?style=flat&logo=quarto&logoColor=white)
![Pages](https://img.shields.io/badge/GitHub%20Pages-published-0B376C?style=flat&logo=github&logoColor=white)
![Neudata](https://img.shields.io/badge/Neudata-brand-04242F?style=flat)

</div>

---

## What you get

| Page | Contents |
|---|---|
| **Home** | Hero banner with badges and *Register* button, key facts, learning outcomes, trainers, audience |
| **Schedule** | Session table with links, assignment deadline |
| **Setup** | Install R, RStudio and packages; download the course data |
| **Sessions** | One folder per session: overview page, **Neudata revealjs slides**, hands-on **practical** |
| **Resources** | Books, cheat sheets, help |
| **Certificate** | Completion criteria (links to the certificate generator for instructors) |

All slides use the [Neudata Quarto slides](https://github.com/neu-data/quarto-slides-template) format, so they match the PowerPoint and Beamer templates.

## Participant and instructor versions

Solutions and instructor notes live in the same files, inside

```markdown
::: {.content-visible when-profile="instructor"}
::: {.solution}
...
:::
:::
```

| Build | Command | Output | Published? |
|---|---|---|---|
| Participant site | `quarto render` | `_site/` | ✅ automatically to GitHub Pages |
| Instructor site (with solutions) | `quarto render --profile instructor` | `_site-instructor/` | ❌ never — keep it local or share privately |

The publishing workflow checks that no solutions reached the participant site before it deploys.

## Start a new course

1. Click **Use this template** on GitHub and name the repository after the course.
2. Edit `_quarto.yml`: `title`, `site-url`, `repo-url` and the **Sessions** menu.
3. Edit `index.qmd`, `schedule.qmd` and `setup.qmd`.
4. Copy a folder in `sessions/` for each session (`index.qmd`, `slides.qmd`, `practical.qmd`).
5. Replace `data/patients.csv` with your course data (synthetic or properly de-identified only).
6. Preview with `quarto preview`, then render once locally so code results are stored in `_freeze/`.
7. Commit **including `_freeze/`**, push, and set **Settings → Pages → Source: GitHub Actions**.

The site appears at `https://neu-data.github.io/<repository-name>/`.

## Translations

For a bilingual course (e.g. English and Vietnamese), duplicate the pages with a suffix (`index-vi.qmd`) and add a language menu to the navbar.

## Data protection

Never put participant lists, emails, attendance or grades in this repository — it is public. Keep them in private storage and use the [certificate generator](https://github.com/neu-data/certificate-template) locally.

---

<div align="center">

**Neudata Consulting Ltd** · *Insight. Impact. Innovation.*
[www.neu-data.com](https://www.neu-data.com) · [contact@neu-data.com](mailto:contact@neu-data.com)

</div>
