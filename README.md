# Three Roads: Choosing a Portfolio Stack with AI

## My constraints and what the portfolio must show

I am working with a free-only budget and I would describe my current level as beginner-to-intermediate. I am comfortable building and styling frontend pages, using Git and GitHub, and learning from examples. I am less confident with authentication, databases, deployment debugging, and maintaining a production backend.

The portfolio needs to do more than display a name and a list of skills. It should show project screenshots, short case studies, links to live demos, and links to source code. It should also give each project enough context to show what I built, what problem it solves, and what I learned. A simple contact method is useful, but I do not need accounts, payments, a dashboard, or user-generated content for the first version.

The work should be easy to maintain after the initial build. I can realistically finish the first version in two weeks if I keep the scope small and reuse a consistent project-card and case-study layout. The backend question is therefore **not yet**: I can use a mail link or a form service later, but I do not need to operate a custom API or database for v1.

The most important display requirement is that the work itself is visible. Screenshots and written case studies should load quickly, and every project should link to a working demo or repository. A portfolio that is technically impressive but hides the work behind a complicated interface would not serve me well.

## Three genuine stack options

### Road 1 — Simplest: HTML/CSS/JavaScript + GitHub Pages

**How I would build it:** I would create a small static site with semantic HTML, CSS, and a little vanilla JavaScript for filtering projects or opening a mobile menu. Each project would be represented by a reusable HTML section or a copied template. Images would live in the repository, and project links would point to their public demos and GitHub repositories.

**Free hosting:** GitHub Pages is the natural host. The repository can publish the site directly from the main branch or through a simple GitHub Actions workflow. There is no server to configure and no database to pay for.

**Backend:** None. A contact button can use `mailto:` or link to a free external form service if I later decide that I need one.

**Trade-off:** This is the fastest and easiest option to understand. It has the smallest failure surface and would be very maintainable for me. The downside is that repeated project markup can become tedious, and updating navigation, metadata, or many case studies by hand is less pleasant as the site grows. It can also feel less polished unless I put deliberate effort into responsive styling and accessibility.

### Road 2 — Balanced choice: Astro + Markdown/MDX + GitHub Pages

**How I would build it:** I would use Astro for the site shell and keep the project case studies as Markdown content. A shared project-card component would render the gallery, while a content template would render each case study. I would add only the JavaScript needed for progressive enhancement, such as a menu or small filter. The repository would contain the content, images, and source code, so the whole portfolio remains reviewable.

**Free hosting:** GitHub Pages can host the generated static output through GitHub Actions. The build happens during deployment, but the published result is still a static site with no server bill.

**Backend:** None for v1. If I eventually need a contact form, I can add a hosted form provider without turning the portfolio into a full backend application.

**Trade-off:** Astro gives me reusable components and a cleaner content workflow without forcing me to learn a large client-side application architecture. It is more setup than plain HTML, so I would need to understand the project structure and deployment configuration. That cost is justified because adding a new case study should become a content task rather than a copy-and-edit task.

### Road 3 — Most powerful: Next.js + TypeScript + a hosted backend

**How I would build it:** I would create a Next.js application with TypeScript, reusable components, and possibly a headless CMS or database for projects. A contact form could use a server action or API route. I could add analytics, a blog, search, draft previews, and richer interactions later.

**Free hosting:** The frontend could be deployed on Vercel's free tier. A database or CMS could use a free tier such as Supabase or another hosted provider. Those services are free only within their limits, so I would need to watch quotas and configuration.

**Backend:** Optional, but likely yes if I use server actions, API routes, a database, or authentication. That creates more moving parts than this portfolio currently needs.

**Trade-off:** This is the most flexible and most impressive stack on paper. It is also the easiest to overbuild. I would spend time maintaining dependencies, deployment settings, API behavior, and possible service limits instead of improving the case studies. For a two-week portfolio, the extra power does not automatically make my work more convincing.

## Pressure-testing the choice

### What breaks if I choose the simplest option?

A plain static site will not break because of a missing database or server. The main risks are organization and consistency. If I add many projects, manually duplicated markup could drift: one project might have different spacing, missing metadata, or a broken image path. I can manage that risk by starting with a small number of projects, using one clear template, and moving to a content-oriented tool if the site becomes difficult to update.

### What do I have to maintain if I choose the most powerful option?

I would need to maintain the framework and packages, environment variables, deployment settings, API or server behavior, and possibly a database schema. I would also need to diagnose failures across multiple services. That maintenance is reasonable for a product that needs accounts or frequently changing data, but it is unnecessary for a mostly static portfolio. I cannot honestly promise that I would maintain all of those pieces well while also finishing the portfolio in two weeks.

### Can I finish in two weeks?

Yes, with Road 1 or Road 2. Road 3 is possible only if I cut the portfolio content and accept that the stack may take more time than the actual presentation of my work. The portfolio should be evaluated on the quality and clarity of the work it shows, not on whether it contains a backend that nobody needs.

### Does each option show my work the way it needs to be shown?

All three can show screenshots, demos, and case studies. Road 1 does this with the least abstraction but requires more manual editing. Road 3 can show it with the most features, but those features could distract from the work. Road 2 gives me reusable layouts and structured case-study content while keeping the final result fast and visually focused.

## Decision

I choose **Road 2: Astro + Markdown/MDX + GitHub Pages**.

It is the best middle ground for my actual constraints. I can build a polished, fast portfolio without paying for hosting or operating a backend. I can keep the source, images, and case studies in GitHub, which makes the work easy to inspect. I also get a maintainable content structure: adding a project should mostly mean adding a Markdown file and its images, not editing the same layout in several places.

I did not choose Road 1 because I expect the portfolio to grow beyond a single landing page, and I want to avoid duplicated markup. I did not choose Road 3 because its backend and service complexity are not required by my current content. The extra capability would increase maintenance before it creates value.

My honest answer is: **yes, I can maintain this**. I can maintain an Astro site with static content, a small number of components, and a GitHub Pages deployment. I would keep the first release deliberately small: home page, about section, three project case studies, screenshots, live-demo links, source links, and a contact link. I would add a backend only after a real requirement appears.

This choice also answers the second question: **yes, it shows my work well**. The portfolio will prioritize readable case studies, visible screenshots, and working links. The stack stays in the background instead of becoming the main thing I am asking a reviewer to admire.

## Two-week build plan

- **Days 1–2:** collect project screenshots and write the content outline.
- **Days 3–5:** create the Astro project, global styles, navigation, and responsive layout.
- **Days 6–9:** add three case studies with screenshots, lessons learned, demo links, and repository links.
- **Days 10–11:** test mobile layout, keyboard navigation, image loading, and broken links.
- **Days 12–13:** deploy to GitHub Pages and fix the deployment path or metadata issues.
- **Day 14:** proofread the writing, review the public page on a phone-sized viewport, and make a final backup commit.

The success criterion is not “use the strongest framework.” It is a portfolio that I can finish, explain, maintain, and keep improving after the assignment is over.
