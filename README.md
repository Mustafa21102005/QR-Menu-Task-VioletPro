# Restaurant Menu

A simple, responsive restaurant menu page built with **Tailwind CSS** and **DaisyUI**. Menu items are loaded dynamically from a JSON file and rendered as cards, grouped into categories (Appetizers, Main, Drinks, Desserts).

## Features

- 🎨 Light/dark theme toggle (Retro / Coffee themes via DaisyUI), saved to `localStorage`
- 📱 Responsive grid layout (4 columns on desktop, 2 on tablet, 1 on mobile)
- ⚡ Skeleton loading placeholders while menu data is being fetched
- 🔗 Sticky navbar with a dropdown menu for quick jumps to each section
- 🏷️ Price badges and optional tags (e.g. "Non-alcoholic") on menu items
- 📦 Menu content decoupled from markup — stored in `menu.json` for easy editing

## Project Structure

```
├── index.html      # Main page markup, styling, and rendering logic
├── menu.json        # Menu data (appetizers, main, drinks, desserts)
└── assets/
    └── images/       # Dish images referenced in menu.json
```

## How It Works

1. On page load, `loadMenu()` displays skeleton placeholders in each category grid.
2. It fetches `menu.json` and parses the four categories: `appetizers`, `main`, `drinks`, `desserts`.
3. `renderDishes()` builds a card for each dish (image, name, price, description, and optional extra tag) and injects it into the matching container.
4. The theme toggle switches between the `retro` and `coffee` DaisyUI themes and remembers the choice using `localStorage`.

## Editing the Menu

To add, remove, or update dishes, edit `menu.json`. Each item follows this shape:

```json
{
  "id": 1,
  "name": "Dish Name",
  "description": "Short description of the dish.",
  "price": "10",
  "image": "assets/images/example.jpg",
  "extra": "Optional badge text (e.g. Non-alcoholic)"
}
```

- `id`, `name`, `description`, `price`, and `image` are required.
- `extra` is optional — when present, it renders as a small outlined badge on the card.

## Sections to Complete

- [ ] **Add a banner** — Introduce a hero/banner section (e.g. restaurant name, tagline, background image) at the top of the page, above or as part of the navbar.

## Tech Stack

- [Tailwind CSS](https://tailwindcss.com/) (via CDN)
- [DaisyUI](https://daisyui.com/) (via CDN) for components and theming
- Vanilla JavaScript (no build step required)
