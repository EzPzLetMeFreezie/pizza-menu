# Papa Andrews Pizza Co. – Pizza Menu

A simple React-based pizza menu that showcases dishes, sold-out states, and a time-based ordering prompt. Built with Create React App and styled with custom CSS.

## Features

- Menu list: Renders 6 pizzas from local `pizzaData` with name, ingredients, price, and image.
- Sold-out styling: Sold-out items are grayscaled and show `SOLD OUT` instead of price.
- Open hours prompt: Displays an order prompt only during opening hours (default 12:00–22:00).
- Clean component structure: `Header / Menu / Pizza / Footer / Order` for easy extension.

## Tech Stack

- React 18 (Create React App)
- CSS (Grid + Flexbox)
- Google Fonts (Roboto Mono)

## Getting Started

Prerequisites: Node.js 16+ and npm 8+ (or an equivalent package manager)

1. Install dependencies: `npm install`
2. Start development server: `npm start`
   - Visit `http://localhost:3000`
3. Build for production: `npm run build`
   - Output goes to `build/`

## Project Structure

- `src/index.js`: App entry point and components (`App`, `Header`, `Menu`, `Pizza`, `Footer`, `Order`).
- `src/index.css`: Styles for layout, colors, and component states.
- `public/index.html`: HTML template and page title.
- `public/pizzas/`: Image assets for the pizza menu.

## Key Components

- `Menu`: Computes the number of items; renders a placeholder when empty; otherwise renders `ul.pizzas`.
- `Pizza`: Receives `pizzaObj` and toggles styles/copy based on `soldOut`.
- `Footer`: Determines whether the store is open based on the current hour; shows a prompt or `Order` component accordingly.
- `Order`: Displays opening hours and an “Order” button.

## Data Model

Each pizza object in `pizzaData` (see `src/index.js`) looks like:

```js
{
  name: string,
  ingredients: string,
  price: number,
  photoName: string, // e.g. "pizzas/margherita.jpg"
  soldOut: boolean
}
```

## Design Notes

- Header: centered title with decorative lines via `::before/::after`.
- Layout: container max-width `80rem`; menu uses two-column CSS Grid; pizza items use Flexbox.
- Visuals: primary highlight color `#edc84b`; sold-out items use grayscale images and subdued text.
- Typography: Roboto Mono from Google Fonts for a monospaced look.

## Customization

- Add a pizza: append an object to `pizzaData` in `src/index.js` and add an image under `public/pizzas/`; reference it via `photoName`.
- Change opening hours: adjust `openHour`/`closeHour` in `Footer`/`Order` logic (currently 12–22).
- Internationalization: extract UI copy or add an i18n layer as needed.

## Acknowledgements

This project is a React learning exercise; the UI and interactions are tailored for educational purposes.
