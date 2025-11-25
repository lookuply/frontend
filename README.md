# Lookuply Frontend

**Privacy-first search interface in 24 EU languages**

Part of the [Lookuply](https://github.com/lookuply) open-source search engine project.

---

## Overview

The Lookuply Frontend is a fast, modern web interface built with SvelteKit that provides a privacy-respecting search experience in all 24 official EU languages.

### Key Features

- **24 Language UI**: Fully translated interface
- **Fast & Responsive**: SvelteKit for optimal performance
- **Privacy-First**: No tracking, no cookies, no ads
- **Clean Design**: Minimalist, accessible interface
- **Dark Mode**: System-aware theme switching
- **Keyboard Shortcuts**: Power user features
- **Mobile Optimized**: Works great on all devices

---

## Architecture

```
┌──────────────┐
│  SvelteKit   │
│   Frontend   │
└──────┬───────┘
       │
       ├─→ Search API (results)
       ├─→ i18n (translations)
       └─→ TailwindCSS (styling)
```

---

## Technology Stack

- **SvelteKit**: Modern web framework
- **TypeScript**: Type-safe development
- **TailwindCSS**: Utility-first CSS
- **svelte-i18n**: Internationalization
- **Vite**: Fast build tool
- **Vitest**: Unit testing

---

## Quick Start

### Prerequisites

```bash
- Node.js 18+
- npm or pnpm
```

### Installation

```bash
# Clone repository
git clone https://github.com/lookuply/frontend.git
cd frontend

# Install dependencies
npm install

# Configure environment
cp .env.example .env
# Edit .env with API endpoint
```

### Development

```bash
# Start dev server
npm run dev

# Open browser at http://localhost:5173
```

### Building

```bash
# Build for production
npm run build

# Preview production build
npm run preview
```

---

## Project Structure

```
frontend/
├── src/
│   ├── routes/          # SvelteKit routes
│   │   ├── +page.svelte # Homepage / Search
│   │   ├── about/       # About page
│   │   ├── api/         # API docs page
│   │   └── privacy/     # Privacy policy
│   ├── lib/             # Shared components
│   │   ├── components/  # UI components
│   │   ├── stores/      # Svelte stores
│   │   └── utils/       # Utilities
│   ├── locales/         # Translation files (24 languages)
│   └── app.css          # Global styles
├── static/              # Static assets
├── tests/               # Tests
└── svelte.config.js     # SvelteKit config
```

---

## Features

### Search Interface

- **Instant Search**: Real-time results as you type
- **Language Auto-Detection**: Automatically detects query language
- **Filters**: Date, language, domain filters
- **Pagination**: Smooth navigation through results
- **Search History**: Local-only, privacy-preserving history

### Language Support

All 24 EU languages with native speakers' input:

- 🇧🇬 Bulgarian
- 🇭🇷 Croatian
- 🇨🇿 Czech
- 🇩🇰 Danish
- 🇳🇱 Dutch
- 🇬🇧 English
- 🇪🇪 Estonian
- 🇫🇮 Finnish
- 🇫🇷 French
- 🇩🇪 German
- 🇬🇷 Greek
- 🇭🇺 Hungarian
- 🇮🇪 Irish
- 🇮🇹 Italian
- 🇱🇻 Latvian
- 🇱🇹 Lithuanian
- 🇲🇹 Maltese
- 🇵🇱 Polish
- 🇵🇹 Portuguese
- 🇷🇴 Romanian
- 🇸🇰 Slovak
- 🇸🇮 Slovenian
- 🇪🇸 Spanish
- 🇸🇪 Swedish

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `/` | Focus search box |
| `Escape` | Clear search |
| `↓` `↑` | Navigate results |
| `Enter` | Open selected result |
| `Ctrl+K` | Toggle shortcuts |
| `Ctrl+D` | Toggle dark mode |

---

## Configuration

Environment variables in `.env`:

```bash
# API Endpoint
PUBLIC_API_URL=https://api.lookuply.info

# Features
PUBLIC_ENABLE_AUTOCOMPLETE=true
PUBLIC_ENABLE_HISTORY=true
PUBLIC_ENABLE_ANALYTICS=false  # Privacy-friendly only

# Language
PUBLIC_DEFAULT_LANGUAGE=en
PUBLIC_SUPPORTED_LANGUAGES=all  # or comma-separated list
```

---

## Internationalization

### Adding/Updating Translations

```bash
# Translations are in src/locales/{language}.json
src/locales/
├── en.json  # English
├── de.json  # German
├── fr.json  # French
└── ...      # All 24 languages
```

Example translation file:

```json
{
  "search": {
    "placeholder": "Search the web...",
    "button": "Search",
    "results": "{count} results",
    "no_results": "No results found"
  },
  "nav": {
    "home": "Home",
    "about": "About",
    "api": "API",
    "privacy": "Privacy"
  }
}
```

---

## Styling

### TailwindCSS

Custom theme configuration:

```javascript
// tailwind.config.js
export default {
  theme: {
    extend: {
      colors: {
        primary: '#2563EB',   // Blue
        secondary: '#10B981', // Green
      }
    }
  }
}
```

### Dark Mode

Automatic system preference detection:

```svelte
<!-- Dark mode toggle -->
<script>
  import { browser } from '$app/environment';

  let darkMode = browser &&
    window.matchMedia('(prefers-color-scheme: dark)').matches;
</script>
```

---

## Testing

### Unit Tests

```bash
# Run tests
npm run test

# Watch mode
npm run test:watch

# Coverage
npm run test:coverage
```

### E2E Tests

```bash
# Run Playwright tests
npm run test:e2e

# UI mode
npm run test:e2e:ui
```

---

## Deployment

### Static Adapter

```bash
# Build static site
npm run build

# Output in build/ directory
# Deploy to any static host (Netlify, Vercel, Cloudflare Pages)
```

### Node Adapter

```bash
# For SSR deployment
npm install -D @sveltejs/adapter-node

# Build
npm run build

# Run
node build/index.js
```

---

## Performance

### Lighthouse Scores

- **Performance**: 98/100
- **Accessibility**: 100/100
- **Best Practices**: 100/100
- **SEO**: 100/100

### Optimizations

- Code splitting
- Image optimization
- Lazy loading
- Service worker (optional)
- Edge caching

---

## Contributing

We welcome contributions! Please see our [Contributing Guidelines](https://github.com/lookuply/.github/blob/main/CONTRIBUTING.md).

### Development Workflow

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests
5. Update translations if needed
6. Submit a pull request

---

## License

This project is licensed under the **GNU General Public License v3.0** - see the [LICENSE](LICENSE) file for details.

---

## Related Projects

- [lookuply/search-api](https://github.com/lookuply/search-api) - Search API
- [lookuply/crawler](https://github.com/lookuply/crawler) - Web crawler
- [lookuply/indexer](https://github.com/lookuply/indexer) - Content indexing

---

## Links

- **Website**: [lookuply.info](https://lookuply.info)
- **API**: [api.lookuply.info](https://api.lookuply.info)
- **Documentation**: [docs.lookuply.info](https://docs.lookuply.info)

---

**Privacy-first search. 24 languages. Beautiful design.**
