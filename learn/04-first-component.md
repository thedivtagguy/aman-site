# Chapter 4: First Component

Components are reusable pieces of code. Instead of copying and pasting the same HTML everywhere, you create it once and use it anywhere. You'll build a Card component for displaying content.

## Goal

Create a Card component that you can use to display different types of content consistently across your site.

## What you'll learn

- How components work in Astro
- How to pass data to components (props)
- How to make reusable design elements

## Step 1: Create the Card component

Create a new file: `src/components/Card.astro`

```astro
---
// Props are data passed into the component
const { title, description, link } = Astro.props;
---

<div class="card">
  <h3>{title}</h3>
  <p>{description}</p>
  {link && <a href={link} class="card-link">Learn more</a>}
</div>

<style>
  .card {
    border: 1px solid var(--color-border);
    padding: var(--space-large);
    background: var(--color-background);
  }
  
  .card h3 {
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-medium);
    margin-bottom: var(--space-small);
    color: var(--color-text);
  }
  
  .card p {
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

## Step 2: Use your Card component

Open `src/pages/index.astro` and add the import at the top:

```astro
---
import Layout from "../layouts/Layout.astro";
import Card from "../components/Card.astro";
---
```

Now replace the features section with your Card components:

```astro
<div class="features">
  <Card 
    title="Simple Design" 
    description="Clean and minimal design that's easy to understand."
  />
  
  <Card 
    title="Easy to Edit" 
    description="Change text, colors, and layout with simple code."
    link="/about"
  />
  
  <Card 
    title="Learn by Doing" 
    description="Every file has helpful comments to guide you."
  />
</div>
```

## Step 3: Update the features styling

Since you're now using Card components, update the `.features` CSS:

```css
.features {
  margin: var(--space-xlarge) 0;
  display: flex;
  gap: var(--space-large);
}
```

Remove the old `.feature` styles since the Card component handles its own styling.

## Step 4: Test your component

Try adding another Card somewhere else on the page to see how reusable it is:

```astro
<Card 
  title="My New Card" 
  description="This card appears anywhere I want it to."
  link="/blog"
/>
```

## Checklist

- [ ] You have a Card component in `src/components/Card.astro`
- [ ] Your homepage uses Card components instead of hardcoded HTML
- [ ] You can add new Cards easily by changing props
- [ ] The styling is consistent across all cards

## What just happened?

You learned the fundamental concept of component-based development. Instead of writing the same HTML over and over, you create it once and reuse it. This is how modern websites are built.

## Troubleshooting

**My Card component isn't showing up**
- Check that you imported it correctly at the top of the file
- Make sure the component filename matches the import exactly

**The styling looks different**
- Component styles are scoped, meaning they only apply to that component
- This is actually good - it prevents styling conflicts

## Make it your own

- Create different card variants (maybe a `highlight` prop which if you pass "true" creates different, special styling)
- Use your Card component on other pages

---

**Previous:** [Chapter 3: Typography & Fonts](./03-typography-fonts.md) | **Next:** [Chapter 5: New Page](./05-new-page.md)