## Nuxt E-Commerce

Nuxt E-Commerce is a free and open-source E-Commerce website designed to be extendable and personalized to your own use-case.

Note that Nuxt E-Commerce is in active development, so you might come across issues and missing features, and if so, please let us know by creating an issue.

Here's a list of features you will find:

- Header with items count and total price
- Products list page with a search bar, filters and lazy loading
- Increase, decrease and delete functionality in the products list and checkout pages
- A cart page with persistant items
- Responsive pages, accessibility good practices and i18n support

## Nuxt E-Commerce Project Setup

For the project setup examples, I'll be using yarn, but feel free to use your favorite dependency manager. You can also use pnpm, npm, bun, and others.

First, install all the dependencies using the dependency manager of your preference:

```bash
yarn install
```

To run the project locally, start the development server on `http://localhost:3000` by running:

```bash
yarn dev
```

To build the application for server-side rendering (SSR) for production, run:

```bash
yarn build
```

If you want to preview the production build, run:

```bash
yarn preview
```

To build the application as a static site for production, run:

```bash
yarn generate
```

The command bellow is not something you typically run directly. It's a script that runs automatically after you install Nuxt or certain Nuxt modules.

```bash
yarn postinstall
````