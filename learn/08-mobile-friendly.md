# Chapter 8: Mobile-Friendly

Most people will view your website on their phones. Let's make sure it looks good on small screens by adjusting layouts and testing on different devices.

## Goal

Make your website work well on mobile devices by adjusting layouts that don't work on small screens.

## What you'll learn

- How to test your site on mobile
- What media queries are and how to use them
- How to make layouts responsive

## Step 1: Test your current site on mobile

Open your browser's developer tools:
- **Chrome/Firefox:** Press F12 or right-click → "Inspect"
- Click the device icon (looks like a phone/tablet)
- Try different screen sizes: iPhone, iPad, etc.

Notice what looks broken or hard to use on small screens.

## Step 2: Fix the portfolio grid for mobile

Your portfolio grid probably looks cramped on mobile. Open `src/pages/portfolio.astro` and update the grid:

```css
.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--space-large);
}

/* Mobile adjustments */
@media (max-width: 768px) {
  .portfolio-grid {
    grid-template-columns: 1fr;
    gap: var(--space-medium);
  }
}
```

*FYI: [`@media queries`](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries) let you apply different styles based on screen size. This is the foundation of responsive design.*

## Step 3: Fix the project layout for mobile

Open `src/layouts/ProjectLayout.astro` and make the two-column layout stack on mobile:

```css
.project-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-xlarge);
  align-items: start;
  margin-bottom: var(--space-xlarge);
}

/* Stack columns on mobile */
@media (max-width: 768px) {
  .project-content {
    grid-template-columns: 1fr;
    gap: var(--space-large);
  }
}
```

## Step 4: Make navigation more mobile-friendly

Open `src/layouts/Layout.astro` and adjust the navigation for smaller screens:

```css
nav ul {
  list-style: none;
  display: flex;
  gap: var(--space-large);
}

/* Smaller gaps on mobile */
@media (max-width: 768px) {
  nav ul {
    gap: var(--space-medium);
    justify-content: center;
  }
  
  nav a {
    font-size: var(--font-size-small);
  }
}
```

## Step 5: Adjust hero section for mobile

In `src/pages/index.astro`, make sure the hero section works on small screens:

```css
.hero {
  text-align: center;
  padding: var(--space-xlarge) 0;
}

.hero h1 {
  font-size: var(--font-size-huge);
  font-weight: var(--font-weight-bold);
  margin-bottom: var(--space-medium);
}

/* Smaller text on mobile */
@media (max-width: 768px) {
  .hero {
    padding: var(--space-large) 0;
  }
  
  .hero h1 {
    font-size: var(--font-size-xxl);
  }
  
  .hero p {
    font-size: var(--font-size-base);
  }
}
```

## Step 6: Make sure images work on mobile

Add this to your global CSS (`src/styles/global.css`):

```css
/* Make all images responsive by default */
img {
  max-width: 100%;
  height: auto;
}

/* Ensure containers don't overflow */
* {
  box-sizing: border-box;
}
```

*FYI: [`box-sizing: border-box`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing) makes width calculations more predictable by including padding and borders in the total width.*

## Step 7: Test thoroughly

Go through each page of your site in mobile view:
- Homepage: Does everything fit? Is text readable?
- Portfolio: Do cards stack nicely?
- Project pages: Does the layout make sense?
- Navigation: Can you easily tap all links?

## Checklist

- [ ] Your portfolio grid stacks to one column on mobile
- [ ] Project pages show content in a single column on small screens
- [ ] Navigation is easy to use on touch devices
- [ ] Text is readable without zooming
- [ ] Images don't overflow or break the layout

## What just happened?

You learned about responsive design - making websites that adapt to different screen sizes. Media queries let you apply different styles based on the device width.

## Troubleshooting

**Changes aren't showing up in mobile view**
- Make sure you're testing in the browser's device mode
- Try refreshing the page
- Check that your media query syntax is correct

**Text is too small on mobile**
- Adjust font sizes in your mobile media queries
- Make sure you're not making text smaller than 16px


## Make it your own

- Add a medium-size breakpoint for tablets
- Experiment with different grid layouts for different screen sizes
- Consider hiding or showing different content on mobile
- Test your site on actual phones and tablets

## Congratulations!

You've completed all 8 chapters! You now understand:

- How websites are structured
- How to control design with CSS
- How to create reusable components
- How to organize content across multiple pages
- How to make sites work on smaller devices too

**Next steps:** Sky's the limit! Edit your pages more, add more HTML markup, style it, add more pages; do what you want!

---

**Previous:** [Chapter 7: Project Pages](./07-project-pages.md) | **Back to:** [Start Here](./00-start-here.md)