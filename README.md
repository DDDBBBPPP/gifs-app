# GIFs App

A GIF discovery app built with **Angular and Tailwind CSS**. Browse trending GIFs, search for something specific, and revisit previous searches.

**[Live Demo](https://dddbbbppp.github.io/gifs-app/)** · **[Source Code](https://github.com/DDDBBBPPP/gifs-app)**

## Overview

GIFs App is a frontend project that integrates the Giphy API to display GIFs in a responsive interface.

### Features

- **Trending GIFs:** explore GIFs currently returned by Giphy's trending endpoint.
- **Search:** find GIFs using a text query.
- **Search history:** revisit previous searches without making the same request again.
- **Local persistence:** search history is stored in the browser using `localStorage`.

The app requests up to 20 GIFs per trending or search request.

## Tech Stack

- Angular 21
- TypeScript
- Tailwind CSS 4
- Giphy API
- Angular Signals
- GitHub Pages and GitHub Actions

## Live Demo

**[Open GIFs App](https://dddbbbppp.github.io/gifs-app/)**

The live demo requires an internet connection and depends on the availability of the Giphy API. Search history is stored locally in your browser rather than in an account or remote database.

## Run Locally

### Requirements

- Node.js and npm
- A Giphy API key

### 1. Clone and install

```bash
git clone https://github.com/DDDBBBPPP/gifs-app.git
cd gifs-app
npm ci
```

### 2. Configure the Giphy API

Create the folder `src/environments` if it does not exist.

Inside that folder, create **both** `environment.ts` and `environment.development.ts` with the following content, replacing the placeholder with your own Giphy API key:

```typescript
export const environment = {
  giphyUrl: 'https://api.giphy.com/v1',
  giphyApiKey: 'YOUR_GIPHY_API_KEY',
  companyName: 'GIFs',
  companyName2: 'App',
  companySlogan: 'Explora y busca GIFs',
};
```

The environment files are excluded from Git by this project. Do not commit personal API keys.

**Important:** this is a client-side application, so an API key included in its browser build or requests can be inspected by visitors. Use a key intended for browser-based applications, and configure any available restrictions in your Giphy account. A GitHub Actions secret prevents the key from being stored directly in the repository, but it does **not** make the key private in the deployed app.

### 3. Start the development server

```bash
npm start
```

Open the local URL displayed in the terminal, typically `http://localhost:4200/`.

### Production build

```bash
npm run build -- --configuration production
```

## Project Scope

GIFs App demonstrates API integration, reactive state management with Angular Signals, and browser-based persistence. It does not provide user accounts or synchronize search history between devices.