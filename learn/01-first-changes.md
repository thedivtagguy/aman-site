# Chapter 1: First Changes

Your first task is simple: change some colors and text. 

## Goal

Change the accent color of your site from black to something you like, and update the homepage text to be about you.

## What you'll learn

- How CSS variables work
- Where the homepage content lives
- How changes appear automatically in your browser

## Step 1: Change the accent color

Open `src/styles/global.css` and find this line around line 12:

```css
--color-accent: black;
```

Change `black` to any color you want. You can use:
- Color names: `blue`, `red`, `green`, `purple`
- Hex codes: `#0066cc`, `#ff6b35`, `#2ecc71`

Save the file and look at your browser. The button on the homepage should now be your new color.

## Step 2: Update the homepage text

Open `src/pages/index.astro` and find the hero section (around lines 8-12):

```astro
<div class="hero">
    <h1>My First Website</h1>
    <p>A simple website built with Astro</p>
    <a href="/about" class="btn">Learn More</a>
</div>
```

Change the heading and description to something about you:
- Replace "My First Website" with your name or what you want to call your site
- Replace "A simple website built with Astro" with a short description of yourself

## Step 3: Update the features section

In the same file, find the three feature boxes (around lines 15-30). Change the text to describe things you actually care about or want to showcase.

## Checklist

- [ ] Your site has a different accent color than black
- [ ] The homepage heading is something about you
- [ ] The description reflects who you are or what you do
- [ ] The feature boxes contain your own content

## What just happened?

You learned that CSS variables (the `--color-accent` thing) let you change colors everywhere at once. You also learned that `.astro` files mix HTML structure with content, and styling, and changes appear immediately when you save.

## Troubleshooting

**My changes aren't showing up**
- Make sure your dev server is still running
- Save your files (Ctrl+S / Cmd+S)
- Try refreshing your browser

**I want a specific color but don't know the code**
- Google "color picker" and use the built-in tool
- Try named colors first: `navy`, `crimson`, `forestgreen`, `gold`

## Make it your own

- Try different colors until you find one you love
- Experiment with the hover color too (`--color-accent-hover`)
- Update the page title in the `<Layout title="...">` part

---

**Previous:** [Start Here](./00-start-here.md) | **Next:** [Chapter 2: Spacing & Layout](./02-spacing-layout.md)