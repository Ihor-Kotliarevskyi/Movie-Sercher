# 🎬 Movie Searcher

A responsive movie search app powered by the TMDB API. Search for any film, browse paginated results, and open a detailed preview modal — all with smooth async UX.

[![React](https://img.shields.io/badge/React-19-61DAFB?style=flat&logo=react&logoColor=black)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-7-646CFF?style=flat&logo=vite&logoColor=white)](https://vite.dev/)
[![TanStack Query](https://img.shields.io/badge/TanStack_Query-5-FF4154?style=flat&logo=reactquery&logoColor=white)](https://tanstack.com/query)
[![TMDB](https://img.shields.io/badge/API-TMDB-01B4E4?style=flat&logo=themoviedatabase&logoColor=white)](https://www.themoviedb.org/)

---

## ✨ Features

- 🔍 **Movie Search** — Query the TMDB API by title with instant results
- 📄 **Pagination** — Navigate through result pages with `react-paginate`; pagination renders both above and below the grid
- 🎞️ **Movie Grid** — Poster cards with title and rating displayed in a responsive grid
- 🪟 **Detail Modal** — Click any movie to open a full-detail modal with backdrop image, overview, release date, and rating
- ⌨️ **Keyboard & Click to Close** — Modal closes on `Escape` key or backdrop click; scroll lock applied while open
- 🔔 **Toast Notifications** — Feedback on empty search or zero results via `react-hot-toast`
- ⚡ **Query Caching** — TanStack Query caches results for 2 minutes and keeps previous page data while loading the next (`keepPreviousData`)
- 🚫 **Adult Content Filtered** — `include_adult: false` passed on all requests

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| UI Library | React 19 |
| Language | TypeScript 5 |
| Build Tool | Vite 7 (SWC plugin) |
| Server State | TanStack Query v5 |
| HTTP Client | Axios |
| Notifications | react-hot-toast |
| Styling | CSS Modules + modern-normalize |
| External API | TMDB (The Movie Database) |

---

## 📂 Project Structure

```
src/
├── components/
│   ├── App/            # Root component: state, query, layout
│   ├── SearchBar/      # Search form with validation
│   ├── MovieGrid/      # Responsive grid of movie cards
│   ├── MovieModal/     # Portal-based detail modal
│   ├── Pagination/     # Page navigation
│   ├── Loader/         # Loading spinner
│   └── ErrorMessage/   # Error display
├── services/
│   └── movieService.ts # Axios call to TMDB search endpoint
└── types/
    └── movie.ts        # Movie TypeScript interface
```

---

## ⚙️ Getting Started

### Prerequisites

- Node.js `v18+`
- TMDB API token — get one free at [themoviedb.org](https://www.themoviedb.org/settings/api)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Ihor-Kotliarevskyi/Movie-Searcher.git
cd Movie-Searcher

# 2. Install dependencies
npm install

# 3. Configure environment variables
echo "VITE_TMDB_TOKEN=your_tmdb_bearer_token" > .env

# 4. Start the development server
npm run dev
```

### Environment Variables

```env
VITE_TMDB_TOKEN=your_tmdb_api_read_access_token
```

> The token is a **Bearer token** (JWT) from the TMDB API settings — not the shorter API key.

---

## 🧪 Available Scripts

```bash
npm run dev      # Start dev server with HMR
npm run build    # Type-check + production build
npm run preview  # Preview production build locally
npm run lint     # Run ESLint
```

---

## 📝 What I Learned

- Fetching and caching external API data with TanStack Query v5 (`useQuery`, `keepPreviousData`, `staleTime`)
- Rendering modals outside the component tree using `createPortal`
- Managing keyboard events and body scroll lock inside `useEffect` cleanup
- Structuring a React + TypeScript app with Vite and CSS Modules
- Working with the TMDB REST API (Bearer token auth, search endpoint, image CDN)

---

<p align="center">
  Powered by <a href="https://www.themoviedb.org/">TMDB</a> &nbsp;·&nbsp;
  Made with ☕ by <a href="https://github.com/Ihor-Kotliarevskyi">Ihor Kotliarevskyi</a>
</p>
