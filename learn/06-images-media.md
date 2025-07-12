# Chapter 6: Images & Media

Visual content makes websites more engaging. You'll learn how to add images to your site and create an image-enhanced Card component.

## Goal

Add images to your portfolio and create a new version of your Card component that can display photos.

## What you'll learn

- How to add images to Astro projects
- How to create responsive images
- How to enhance components with optional features

## Step 1: Add images to your project

Create some folders for organization:
- Create `public/images/` folder
- Add 2-3 images of your work (art, crafts, designs, etc.)
- Name them something simple: `project-1.jpg`, `project-2.jpg`

Images in the `public` folder can be accessed directly in your HTML.

## Step 2: Create an enhanced Card component

Create `src/components/ImageCard.astro`:

```astro
---
const { title, description, link, image, imageAlt } = Astro.props;
---

<div class="image-card">
  {image && (
    <div class="image-container">
      <img src={image} alt={imageAlt || title} />
    </div>
  )}
  
  <div class="card-content">
    <h3>{title}</h3>
    <p>{description}</p>
    {link && <a href={link} class="card-link">Learn more</a>}
  </div>
</div>

<style>
  .image-card {
    border: 1px solid var(--color-border);
    background: var(--color-background);
    overflow: hidden;
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
    text-decoration: none;
    font-weight: var(--font-weight-medium);
  }
  
  .card-link:hover {
    color: var(--color-accent-hover);
  }
</style>
```

## Step 3: Update your Portfolio page

Open `src/pages/portfolio.astro` and import your new component:

```astro
---
import Layout from "../layouts/Layout.astro";
import ImageCard from "../components/ImageCard.astro";
---
```

Replace the portfolio grid with ImageCards:

```astro
<div class="portfolio-grid">
  <ImageCard 
    title="Project One" 
    description="Description of your actual work. What did you make? What materials or tools did you use?"
    image="/images/project-1.jpg"
    imageAlt="Description of what's in the image"
  />
  
  <ImageCard 
    title="Project Two" 
    description="Another piece of work you're proud of. Include any interesting details about the process."
    image="/images/project-2.jpg"
    imageAlt="Description of what's in the image"
  />
  
  <ImageCard 
    title="Project Three" 
    description="Even work-in-progress projects are worth showing. What are you learning?"
  />
</div>
```

## Step 4: Add a hero image to your homepage

In `src/pages/index.astro`, you can add an image to the hero section:

```astro
<div class="hero">
  <img src="/images/hero-photo.jpg" alt="Photo of your workspace or work" class="hero-image">
  <h1>Your Name</h1>
  <p>A brief description of what you do</p>
  <a href="/portfolio" class="btn">View My Work</a>
</div>
```

And add this CSS:

```css
.hero-image {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: var(--space-medium);
}
```

## Checklist

- [ ] Your portfolio shows images of your actual work
- [ ] Images are properly sized and don't break the layout
- [ ] You have an ImageCard component that works with or without images
- [ ] Alt text describes your images appropriately

## What just happened?

You learned how images work on the web and created a flexible component that can handle different types of content. The [`object-fit: cover`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) property is especially useful - it crops images to fit while maintaining their aspect ratio.

## Troubleshooting

**My images aren't showing up**
- Make sure they're in the `public/images/` folder
- Check that the file names match exactly (including case)
- Try visiting the image directly: `http://localhost:4321/images/project-1.jpg`

**Images look distorted or weird**
- Use `object-fit: cover` to crop images to fit
- Consider resizing large images before adding them (aim for under 1MB)

## Make it your own

- Experiment with different image sizes and aspect ratios
- Add hover effects to images
- Create a lightbox effect for viewing larger images
- Try different `object-fit` values: `contain`, `fill`, `scale-down`

---

**Previous:** [Chapter 5: New Page](./05-new-page.md) | **Next:** [Chapter 7: Interactivity](./07-project-pages.md)