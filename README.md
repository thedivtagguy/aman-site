# Your first Astro website

A minimal website starter built with Astro, designed for people comfortable with basic HTML and CSS who want to learn modern web development without the complexity.

This starter is intentionally simple.

## File Structure

```
/
├── src/
│   ├── layouts/MainLayout.astro    ← Template used by every page
│   ├── pages/                  ← Each file becomes a page (index.astro → /)
│   │   └── blog/              ← Blog posts (.md files)
│   ├── components/            ← Reusable components (Button, Card)
│   └── styles/global.css      ← All your CSS in one place
├── public/                    ← Images and static files
└── package.json              ← Project setup
```

## Getting Started

1. **Install Node.js** from [nodejs.org](https://nodejs.org/) if you don't have it
2. **Clone this project** and open it in your code editor
3. **Install dependencies** and start the dev server:

```bash
npm install
npm run dev
```

4. **Open your browser** to `http://localhost:4321`
5. **Start editing!** Changes appear automatically in your browser

## Understanding the Code

### Astro Files (.astro)

Each Astro file has two parts:

```astro
---
// JavaScript section - runs on the server
const title = "My Page";
---

<!-- HTML section - what visitors see -->
<h1>{title}</h1>
```

### Components

Look at `src/components/Button.astro` to see how props work:

```astro
---
const { text = "Click me" } = Astro.props;
---
<button class="btn">{text}</button>
```

Use it like: `<Button text="Custom Text" />`

### Layouts

This starter has two layouts to show how they work:

- **MainLayout.astro** - Used by regular pages (home, about, blog index)
- **BlogLayout.astro** - Used by blog posts (different navigation, styling)

### Markdown Blog Posts

Files in `src/pages/blog/` become blog posts. They use the BlogLayout:

```markdown
---
layout: ../../layouts/BlogLayout.astro
title: "My Post"
date: "2024-01-15"
---

# My Post Content

Regular markdown content goes here.
```

## Quick Start Tasks

1. **Edit the homepage**: Change text in `src/pages/index.astro`
2. **Customize colors**: Edit `src/styles/global.css`
3. **Add a new page**: Create `src/pages/contact.astro`
4. **Try the components**: Use `<Button>` and `<Card>` in your pages

## Commands

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview built site

---

## Things to try

Here are some ideas for making this starter your own:

**Start with the basics:**

- Change the colors in `src/styles/global.css` - pick your favorite color instead of gray
- Edit the homepage text to be about you instead of the placeholder content
- Try different fonts by changing `font-family` in the CSS
- Write a real blog post about something you're interested in

**Add your own stuff:**

- Create a new page like `contact.astro` or `projects.astro`
- Add it to the navigation in `MainLayout.astro`
- Put some images in the `public/` folder and use them in your content
- Change the footer to say something else

**Play with components:**

- Look at how `Button.astro` works - it takes text as a prop
- Try making your own component, maybe for a quote or an alert box
- Use your component in multiple places to see how reusable code works

**Try different layouts:**

- Compare `MainLayout.astro` and `BlogLayout.astro` to see the differences
- Create a new page and try both layouts to see how they look
- Make your own layout for a different type of page

**If you want to get fancy:**

- Add hover effects to buttons and links
- Try a dark color scheme
- Make the layout wider or narrower by changing `max-width`
- Add some simple animations with CSS transitions

Don't try to do everything at once. Pick one thing that sounds interesting and start there. If you break something, just undo your changes and try again.
