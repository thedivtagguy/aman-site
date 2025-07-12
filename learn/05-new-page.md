# Chapter 5: New Page

Time to add a completely new page to your site. You'll create a Portfolio page to showcase your creative work.

## Goal

Create a new Portfolio page with navigation, and learn how routing works in Astro.

## What you'll learn

- How to create new pages in Astro
- How routing works (how the filename becomes a URL)
- How to organize content for portfolios

## Step 1: Create the Portfolio page

Create a new file: `src/pages/portfolio.astro`

```astro
---
import Layout from "../layouts/Layout.astro";
import Card from "../components/Card.astro";
---

<Layout title="Portfolio">
  <div class="portfolio-header">
    <h1>My Work</h1>
    <p>A collection of things I've created</p>
  </div>

  <div class="portfolio-grid">
    <Card 
      title="Project One" 
      description="Description of something you've made. This could be art, design work, crafts, or anything creative."
    />
    
    <Card 
      title="Project Two" 
      description="Another piece of work. Don't worry about having fancy projects - include things you're proud of."
    />
    
    <Card 
      title="Project Three" 
      description="Even simple projects count. The goal is to practice organizing and presenting your work."
    />
  </div>
</Layout>

<style>
  .portfolio-header {
    text-align: center;
    margin-bottom: var(--space-xlarge);
  }
  
  .portfolio-header h1 {
    font-size: var(--font-size-xxl);
    font-weight: var(--font-weight-bold);
    margin-bottom: var(--space-small);
  }
  
  .portfolio-header p {
    font-size: var(--font-size-large);
    color: var(--color-text-light);
  }
  
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--space-large);
  }
</style>
```

## Step 2: Add Portfolio to your navigation

Open `src/layouts/Layout.astro` and update the navigation:

```astro
<nav class="container">
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/portfolio">Portfolio</a></li>
    <li><a href="/blog">Blog</a></li>
  </ul>
</nav>
```

## Step 3: Test your new page

Visit `http://localhost:4321/portfolio` in your browser. You should see your new page.

## Step 4: Link to Portfolio from your homepage

In `src/pages/index.astro`, update the hero button to point to your portfolio:

```astro
<a href="/portfolio" class="btn">View My Work</a>
```

*FYI: [`display: grid`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) creates a flexible grid layout. The [`repeat(auto-fit, minmax(300px, 1fr))`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat) makes columns that are at least 300px wide and automatically adjust to screen size.*

## Checklist

- [ ] You can visit `/portfolio` and see your new page
- [ ] The navigation includes Portfolio and links work
- [ ] Your homepage button links to the portfolio
- [ ] The portfolio uses a grid layout for projects

## What just happened?

You learned that in Astro, every `.astro` file in the `pages` folder automatically becomes a page on your website. The filename becomes the URL - `portfolio.astro` becomes `/portfolio`.

## Troubleshooting

**I get a 404 when visiting /portfolio**
- Make sure the file is named `portfolio.astro` exactly
- Check that it's in the `src/pages/` folder
- Make sure your dev server is running

## Make it your own

- Replace the placeholder projects with real things you've made
- Add different types of content (not just cards)
- Create other pages like Contact or Resume

---

**Previous:** [Chapter 4: First Component](./04-first-component.md) | **Next:** [Chapter 6: Images & Media](./06-images-media.md)