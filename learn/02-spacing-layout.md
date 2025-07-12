# Chapter 2: Spacing & Layout

Now that you're comfortable making changes, let's understand how space works on websites.

## Goal

Understand and modify the spacing system, then experiment with different layouts for the features section.

## What you'll learn

- How CSS spacing variables work
- The difference between margin and padding
- How to change layouts from vertical to horizontal

## Step 1: Understand the spacing system

Open `src/styles/global.css` and look at the spacing variables (around lines 15-19):

```css
/* Spacing */
--space-small: 0.5rem;
--space-medium: 1rem;
--space-large: 2rem;
--space-xlarge: 3rem;
```

These control all the spacing on your site. Try changing `--space-large` from `2rem` to `3rem` and see what happens to your homepage.

## Step 2: Experiment with the hero section spacing

Open `src/pages/index.astro` and find the hero styles at the bottom (around line 37):

```css
.hero {
    text-align: center;
    padding: var(--space-xlarge) 0;
}
```

Try changing `var(--space-xlarge)` to `var(--space-large)` or even `4rem`. See how it affects the white space around your main heading.

*FYI: [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) controls space inside an element, while [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) controls space outside it.*

## Step 3: Change the features layout

Right now, the features stack vertically. Let's make them horizontal. In the same file, find the `.features` style (around line 52) and replace it with:

```css
.features {
    margin: var(--space-xlarge) 0;
    display: flex;
    gap: var(--space-large);
}
```

Now your three features should appear side by side instead of stacked.

*FYI: [`display: flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout) is one of the most important layout tools in CSS. The [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap) property controls spacing between flex items.*

## Step 4: Adjust feature box styling

Since they're now horizontal, you might want to adjust the individual feature styling. Find `.feature` (around line 56) and replace the border styling:

```css
.feature {
    border: 1px solid var(--color-border);
    padding: var(--space-large);
    flex: 1;
}

.feature:last-child {
    border: 1px solid var(--color-border);
}
```

This gives each feature box a border and makes them equal width.

## Checklist

- [ ] You understand what the spacing variables do
- [ ] You've experimented with different spacing values
- [ ] Your features section displays horizontally
- [ ] The layout looks balanced and readable

## What just happened?

You learned that websites use consistent spacing systems instead of random numbers. The `display: flex` property is one of the most important layout tools in CSS - it lets you arrange things horizontally and control how they space out.

## Troubleshooting

**The spacing feels too tight or too loose**
- Adjust the gap value: `gap: var(--space-medium);` for tighter, `gap: var(--space-xlarge);` for looser
- Remember you can use custom values too: `gap: 1.5rem;`

## Make it your own

- Try different spacing values throughout the site
- Experiment with `justify-content: center;` or `justify-content: space-between;` in the `.features` style
- Add more feature boxes and see how the layout adapts

---

**Previous:** [Chapter 1: First Changes](./01-first-changes.md) | **Next:** [Chapter 3: Typography & Fonts](./03-typography-fonts.md)