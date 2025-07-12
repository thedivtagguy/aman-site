# Chapter 7: Project Pages

Turn your portfolio cards into clickable links that lead to individual project pages. You'll learn how to create detailed pages for each piece of work.

## Goal

Create individual pages for your projects and link them from your portfolio cards.

## What you'll learn

- How to create multiple related pages
- How to organize project content
- How to create a specialized layout for projects

## Step 1: Create a project layout

First, let's create a special layout just for project pages. Create `src/layouts/ProjectLayout.astro`:

```astro
---
import Layout from "./Layout.astro";
const { title, subtitle } = Astro.props;
---

<Layout title={title}>
  <div class="project-header">
    <h1>{title}</h1>
    {subtitle && <p class="project-subtitle">{subtitle}</p>}
  </div>
  
  <div class="project-content">
    <slot />
  </div>
  
  <div class="project-nav">
    <a href="/portfolio" class="back-link">← Back to Portfolio</a>
  </div>
</Layout>

<style>
  .project-header {
    text-align: center;
    margin-bottom: var(--space-xlarge);
  }
  
  .project-header h1 {
    font-size: var(--font-size-xxl);
    font-weight: var(--font-weight-bold);
    margin-bottom: var(--space-small);
  }
  
  .project-subtitle {
    font-size: var(--font-size-large);
    color: var(--color-text-light);
  }
  
  .project-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--space-xlarge);
    align-items: start;
    margin-bottom: var(--space-xlarge);
  }
  
  .project-nav {
    text-align: center;
    padding-top: var(--space-large);
    border-top: 1px solid var(--color-border);
  }
  
  .back-link {
    color: var(--color-accent);
    text-decoration: none;
    font-weight: var(--font-weight-medium);
  }
  
  .back-link:hover {
    text-decoration: underline;
  }
</style>
```

## Step 2: Create your first project page

Create a new file: `src/pages/project-1.astro`

```astro
---
import ProjectLayout from "../layouts/ProjectLayout.astro";
---

<ProjectLayout title="Project One" subtitle="Brief description of what this project is">
  <div class="project-image">
    <img src="/images/project-1.jpg" alt="Project one main image">
  </div>
  
  <div class="project-details">
    <h2>About This Project</h2>
    <p>
      Write about what you made here. What materials did you use? 
      What was the process like? What did you learn?
    </p>
    
    <h3>Details</h3>
    <ul>
      <li><strong>Medium:</strong> (e.g., Watercolor, Digital, Clay, etc.)</li>
      <li><strong>Time:</strong> (e.g., 2 weeks, Weekend project)</li>
      <li><strong>Purpose:</strong> (e.g., Class assignment, Personal exploration)</li>
    </ul>
  </div>
</ProjectLayout>

<style>
  .project-image img {
    width: 100%;
    border: 1px solid var(--color-border);
  }
  
  .project-details h2 {
    font-size: var(--font-size-xl);
    margin-bottom: var(--space-medium);
  }
  
  .project-details h3 {
    font-size: var(--font-size-large);
    margin: var(--space-large) 0 var(--space-small) 0;
  }
  
  .project-details ul {
    margin-bottom: var(--space-large);
  }
  
  .project-details li {
    margin-bottom: var(--space-small);
  }
</style>
```

## Step 3: Simplify your ImageCard component

Update `src/components/ImageCard.astro` to always include links:

```astro
---
const { title, description, link, image, imageAlt } = Astro.props;
---

<a href={link} class="image-card-link">
  <div class="image-card">
    <div class="image-container">
      <img src={image} alt={imageAlt || title} />
    </div>
    
    <div class="card-content">
      <h3>{title}</h3>
      <p>{description}</p>
      <span class="card-link">View Project →</span>
    </div>
  </div>
</a>

<style>
  .image-card-link {
    text-decoration: none;
    color: inherit;
    display: block;
  }
  
  .image-card {
    border: 1px solid var(--color-border);
    background: var(--color-background);
    overflow: hidden;
    height: 100%;
  }
  
  .image-card:hover {
    border-color: var(--color-accent);
  }
  
  .image-container {
    width: 100%;
    height: 200px;
    overflow: hidden;
  }
  
  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  
  .card-content {
    padding: var(--space-large);
  }
  
  .card-content h3 {
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-medium);
    margin-bottom: var(--space-small);
    color: var(--color-text);
  }
  
  .card-content p {
    color: var(--color-text-light);
    margin-bottom: var(--space-medium);
  }
  
  .card-link {
    color: var(--color-accent);
    font-weight: var(--font-weight-medium);
    font-size: var(--font-size-small);
  }
</style>
```

## Step 4: Update your portfolio to use the new cards

Open `src/pages/portfolio.astro` and update your ImageCards:

```astro
<div class="portfolio-grid">
  <ImageCard 
    title="Project One" 
    description="Description of your actual work. Click to see more details."
    image="/images/project-1.jpg"
    imageAlt="Description of what's in the image"
    link="/project-1"
  />
  
  <ImageCard 
    title="Project Two" 
    description="Another piece of work you're proud of."
    image="/images/project-2.jpg"
    imageAlt="Description of what's in the image"
    link="/project-2"
  />
  
  <ImageCard 
    title="Project Three" 
    description="Even work-in-progress projects are worth showing."
    image="/images/project-3.jpg"
    imageAlt="Description of what's in the image"
    link="/project-3"
  />
</div>
```

## Step 5: Create pages for your other projects

Create `src/pages/project-2.astro` and `src/pages/project-3.astro` using the same structure as project-1, but with your own content and images.

## Checklist

- [ ] You have a ProjectLayout that handles common project page elements
- [ ] You can click on portfolio cards to visit individual project pages
- [ ] Each project page shows detailed information about your work
- [ ] There's a clear way to navigate back to the portfolio
- [ ] All your portfolio cards link to actual project pages

## What just happened?

You learned how to create specialized layouts for different types of content. The ProjectLayout handles the common elements (header, navigation) while each individual project page focuses on its unique content.

## Troubleshooting

**Cards aren't clickable**
- Make sure you added the `link` prop to all your ImageCard components
- Check that the href matches your page filename exactly

**Project pages look broken**
- Make sure you're importing ProjectLayout correctly
- Check that image paths are correct (images should be in `public/images/`)


## Make it your own

- Add multiple images to project pages
- Create different project layouts for different types of work
- Include process photos or sketches
- Add a "Next Project" link to connect your work
- Experiment with different grid layouts in the ProjectLayout

---

**Previous:** [Chapter 6: Images & Media](./06-images-media.md) | **Next:** [Chapter 8: Mobile-Friendly](./08-mobile-friendly.md)