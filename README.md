# Your First Website

This is a simple website built with Astro, which is a modern tool that makes websites fast and easy to work with. You'll be writing HTML and CSS (the fundamental languages of the web), but Astro helps organize everything in a way that makes sense.

The site you'll start with is intentionally minimal—black text on white backgrounds, simple layouts, no fancy animations. This isn't because simple is bad, but because simple lets you focus on learning the important stuff first. You can always add complexity later.

## How your files are organized

```
/
├── src/
│   ├── layouts/Layout.astro    ← The template used by every page
│   ├── pages/                  ← Each file here becomes a page on your site
│   ├── components/             ← Reusable pieces of code
│   └── styles/global.css       ← CSS that applies everywhere
├── learn/                      ← Step-by-step learning chapters
├── public/                     ← Images and other files
└── package.json               ← Project configuration
```

The `src/pages/` folder is where the magic happens. Every `.astro` file you put in there automatically becomes a page on your website. So `about.astro` becomes `yoursite.com/about`. Pretty straightforward.

## Getting started

You'll need to have Node.js installed on your computer first. If you don't have it, go download it from [nodejs.org](https://nodejs.org/).

Then, in your terminal:

```bash
pnpm install
pnpm run dev
```

This installs everything you need and starts a development server. Open `http://localhost:4321` in your browser and you should see your site. Now here's the fun part: leave that browser tab open, and start editing files. Your changes will show up automatically.

## Understanding Astro files

Astro files might look a bit weird at first, but they're actually pretty simple. Each one has two parts:

```astro
---
// This is "frontmatter" - JavaScript that runs when the page loads
const message = "Hello world";
---

<!-- This is the template - HTML that gets shown to visitors -->
<h1>{message}</h1>
```

The stuff between the `---` lines is JavaScript. The stuff below is HTML (with a few extra features, like being able to use `{message}` to insert variables).

## CSS Variables

I've set up CSS variables in `src/styles/global.css` that control colors, spacing, and typography across the entire site. This means if you want to change the main color from black to, say, blue, you just change one line:

```css
--color-accent: blue;
```

And that change applies everywhere. This is how real websites work—you define your design system once, then use it consistently.

## Learning path

**New to web development?** Follow the step-by-step learning path in the `learn/` folder:

**[Start here: Learning Path →](learn/00-start-here.md)**

This takes you through 8 chapters from basic changes to building a complete portfolio website. Each chapter builds on the previous one and includes clear success criteria.

## What to try first

1. **Change some text**: Open `src/pages/index.astro` and edit the heading
2. **Try a different color**: In `src/styles/global.css`, change `--color-accent` to `red` or `#0066cc`
3. **Add a new page**: Create a new file in `src/pages/` and see what happens
4. **Look at the Button component**: Check out `src/components/Button.astro` to see how reusable components work

## Commands you'll use

- `npm run dev` - Start the development server
- `npm run build` - Build your site for publishing
- `npm run preview` - Preview your built site

## When you get stuck

You will get stuck. Everyone does. Here's how to get unstuck:

<details>
<summary><strong>My changes aren't showing up</strong></summary>

First, check that your dev server is still running (you should see logs in your terminal). If it stopped, run `npm run dev` again.

If it's running but changes aren't appearing:
- Save your file (Ctrl+S / Cmd+S)
- Check the terminal for any error messages
- Try refreshing your browser
- Make sure you're editing the right file
</details>

<details>
<summary><strong>I want to change the layout/styling</strong></summary>

- **Colors**: Edit the CSS variables in `src/styles/global.css`
- **Spacing**: Also in the CSS variables - change `--space-small`, `--space-large`, etc.
- **Typography**: Change `--font-size-base` and `--font-size-large` in variables
- **Layout**: Look in `src/layouts/Layout.astro` for the overall page structure
- **Page-specific styling**: Each page has its own `<style>` section at the bottom
</details>

<details>
<summary><strong>I want to add something new</strong></summary>

- **New page**: Create a new `.astro` file in `src/pages/`. The filename becomes the URL.
- **New component**: Create a new `.astro` file in `src/components/`, then import it in pages
- **Images**: Put them in the `public/` folder, then use `/filename.jpg` in your HTML
- **More blog posts**: Add `.md` files to `src/pages/blog/`
</details>

<details>
<summary><strong>I broke something and don't know what</strong></summary>

1. Look at your terminal - there's probably an error message there
2. Check your browser's developer console (F12, then look at the Console tab)
3. Try undoing your last change
4. Common issues:
   - Missing closing tags (`</div>`)
   - Typos in CSS variable names (`var(--color-textt)` instead of `var(--color-text)`)
   - Missing quotes around attributes (`class=hero` instead of `class="hero"`)
</details>

<details>
<summary><strong>Using AI tools to help</strong></summary>

AI can be really helpful, but use it smartly:

**Good prompts:**
- "How do I center this div in CSS?"
- "What's the difference between margin and padding?"
- "Help me debug this CSS - my text isn't showing up"

**Include context:**
- Share your actual code
- Explain what you expected vs. what happened
- Mention you're using Astro

**Red flags:**
- If the AI suggests overly complex solutions
- If it wants you to install lots of new packages
- If you don't understand what it's suggesting

**Remember**: Always try to understand the solution, don't just copy-paste. Ask follow-up questions like "why does this work?"
</details>

<details>
<summary><strong>Where to find good information</strong></summary>

**For specific problems:**
- [MDN Web Docs](https://developer.mozilla.org) - The definitive reference for HTML/CSS
- [Astro docs](https://docs.astro.build) - Well-written and beginner-friendly
- Stack Overflow - Search your error message

**For learning:**
- [CSS Tricks](https://css-tricks.com) - Practical tutorials
- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) - For layout
- [A Complete Guide to CSS Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) - For complex layouts

**Pro tip**: When googling, include "MDN" in your search for CSS properties, or "Astro" for framework-specific questions.
</details>
