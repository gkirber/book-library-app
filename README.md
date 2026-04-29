# Book Library App

A full-stack sample application for managing a personal book list.

The project consists of:
- a React + Redux frontend for adding, filtering, and managing books
- an Express API that returns random books from a local dataset

## Features

- Add books manually (title + author)
- Add a random book from local frontend JSON data
- Add a random book from the API (including a delayed request example)
- Mark books as favorites
- Delete books from the list
- Filter books by title, author, and favorites only
- Highlight matched filter text in the book list
- Display validation/API errors with toast notifications

## Tech Stack

### Frontend

<p>
  <img alt="React" src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  <img alt="Redux Toolkit" src="https://img.shields.io/badge/Redux_Toolkit-593D88?style=for-the-badge&logo=redux&logoColor=white" />
  <img alt="React Redux" src="https://img.shields.io/badge/React_Redux-593D88?style=for-the-badge&logo=redux&logoColor=white" />
  <img alt="Axios" src="https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white" />
  <img alt="React Toastify" src="https://img.shields.io/badge/React_Toastify-CB3837?style=for-the-badge&logo=npm&logoColor=white" />
  <img alt="React Icons" src="https://img.shields.io/badge/React_Icons-CB3837?style=for-the-badge&logo=npm&logoColor=white" />
</p>

### Backend

<p>
  <img alt="Node.js" src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
  <img alt="Express" src="https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white" />
  <img alt="cors (npm)" src="https://img.shields.io/badge/cors-CB3837?style=for-the-badge&logo=npm&logoColor=white" />
</p>

## Project Structure

```text
book-library-app/
├── api/                 # Express server
│   ├── data/books.json
│   └── index.js
├── frontend/            # React app
│   ├── src/components/
│   ├── src/redux/slices/
│   └── src/data/books.json
└── package.json         # root scripts to run frontend/api
```

## Prerequisites

- Node.js 18+ (recommended)
- npm 9+ (recommended)

## Installation

Install dependencies for all parts of the project:

```bash
# from project root
npm install
npm install --prefix frontend
npm install --prefix api
```

## Running the App

You need two terminals:

### 1) Start API server

```bash
npm run start:api
```

The API runs on `http://localhost:4000`.

### 2) Start frontend

```bash
npm start
```

The frontend runs on `http://localhost:3000`.

## Available Scripts

From the project root:

- `npm start` - starts the frontend app (`frontend`)
- `npm run start:api` - starts the backend API (`api`)

From `frontend/`:

- `npm start` - run development server
- `npm run build` - build production bundle
- `npm test` - run tests

From `api/`:

- `npm start` - start Express server
- `npm run dev` - start server with nodemon

## API Endpoints

- `GET /random-book` - returns a random book immediately
- `GET /random-book-delayed` - returns a random book after ~2 seconds

Base URL: `http://localhost:4000`

## Notes

- The frontend currently requests API data from `http://localhost:4000/random-book-delayed`.
- Random books can come from two sources:
  - local frontend data (`frontend/src/data/books.json`)
  - backend data (`api/data/books.json`)
