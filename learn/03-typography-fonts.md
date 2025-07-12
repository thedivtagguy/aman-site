# Chapter 3: Typography & Fonts

Typography is one of the most powerful design tools you have. In this chapter, you'll learn how to control fonts, text sizes, and create a hierarchy that guides readers through your content.

## Goal

Replace the default Arial font with something more interesting and create a clear visual hierarchy using different text sizes and weights.

## What you'll learn

- How to add web fonts to your site
- How typography variables work
- How to create visual hierarchy with text

## Step 1: Add a web font

Open `src/layouts/Layout.astro` and add this line inside the `<head>` section (around line 16):

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
```

Now update the font-family in the body styles (around line 28):

```css
body {
    font-family: 'Inter', Arial, sans-serif;
    line-height: var(--line-height);
    color: var(--color-text);
    background-color: var(--color-background);
}
```

## Step 2: Create better typography variables

Open `src/styles/global.css` and replace the typography section with:

```css
/* Typography */
--font-size-small: 0.875rem;
--font-size-base: 1rem;
--font-size-large: 1.25rem;
--font-size-xl: 1.5rem;
--font-size-xxl: 2rem;
--font-size-huge: 3rem;

--font-weight-normal: 400;
--font-weight-medium: 500;
--font-weight-bold: 700;
```

## Step 3: Apply the new typography system

In `src/pages/index.astro`, update the hero section styles:

```css
.hero h1 {
    font-size: var(--font-size-huge);
    font-weight: var(--font-weight-bold);
    margin-bottom: var(--space-medium);
}

.hero p {
    font-size: var(--font-size-large);
    font-weight: var(--font-weight-normal);
    color: var(--color-text-light);
    margin-bottom: var(--space-large);
}
```

And update the feature headings:

```css
.feature h2 {
    font-size: var(--font-size-xl);
    font-weight: var(--font-weight-medium);
    margin-bottom: var(--space-small);
}
```

## Checklist

- [ ] Your site uses a web font instead of Arial
- [ ] Text sizes create a clear hierarchy (big heading, medium subheading, normal text)
- [ ] The typography feels more professional and intentional

## What just happened?

You learned that typography is a design system, just like spacing and colors. Good typography uses consistent sizes and weights to help readers understand what's important.

## Troubleshooting

**The font didn't change**
- Check that the Google Fonts link is in the `<head>` section
- Make sure you spelled the font name exactly right (including quotes)

**Text looks too big or too small**
- Adjust the font-size variables in global.css
- Remember that `rem` units scale with the user's browser settings

## Make it your own

- Try different Google Fonts: Poppins, Nunito, Source Sans Pro, or Lora
- Experiment with font weights (300 for light, 600 for semi-bold)
- Add more typography variables for different use cases

---

**Previous:** [Chapter 2: Spacing & Layout](./02-spacing-layout.md) | **Next:** [Chapter 4: First Component](./04-first-component.md)