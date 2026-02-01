# OpenOrbit - Astro Version

This is the Astro framework version of the OpenOrbit website, migrated from Next.js.

## Project Structure

```
astro/
├── src/
│   ├── actions/
│   │   └── contact.ts          # Form actions for contact/newsletter
│   ├── components/
│   │   ├── landing/            # Landing page React components
│   │   │   ├── Navbar.tsx
│   │   │   ├── Hero.tsx
│   │   │   ├── Services.tsx
│   │   │   ├── Work.tsx
│   │   │   ├── Testimonials.tsx
│   │   │   ├── CTA.tsx
│   │   │   ├── Footer.tsx
│   │   │   ├── FloatingCTA.tsx
│   │   │   └── PortfolioPage.tsx
│   │   └── ui/                 # UI utility components
│   │       ├── Parallax.tsx
│   │       └── Reveal.tsx
│   ├── layouts/
│   │   └── Layout.astro        # Root layout with fonts & metadata
│   ├── pages/
│   │   ├── index.astro         # Home page
│   │   └── portfolio.astro     # Portfolio page
│   └── styles/
│       └── global.css          # Tailwind + custom styles
├── public/
│   ├── sitemap.xml
│   ├── robots.txt
│   └── favicon.ico
├── astro.config.mjs
├── package.json
└── tsconfig.json
```

## Key Features

- **Framework**: Astro 5.x with React integration
- **Styling**: Tailwind CSS v4 with custom animations
- **Animations**: Framer Motion (React islands)
- **Forms**: Astro Actions API for contact/newsletter forms
- **SEO**: Full metadata, Open Graph, Twitter Cards, Schema.org
- **Performance**: Static site generation with hybrid output for actions

## Pages

1. **Home** (`/`) - Landing page with all sections
2. **Portfolio** (`/portfolio`) - Full project showcase

## Getting Started

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Environment Variables

Create a `.env` file with:

```env
SENDGRID_API_KEY=your_sendgrid_api_key
CONTACT_EMAIL=hello@openorbit.io
FROM_EMAIL=noreply@openorbit.io
COMPANY_NAME=OpenOrbit
```

## Differences from Next.js Version

- **Routing**: File-based routing instead of App Router
- **Forms**: Astro Actions instead of API routes
- **Components**: React components used as "islands" with client directives
- **Build**: Static + server hybrid output for form actions
- **Links**: Regular `<a>` tags instead of `next/link`

## Client Directives

Components use hydration directives:
- `client:load` - Navbar (immediate interactivity needed)
- `client:visible` - Sections (hydrate when visible)
- `client:idle` - Footer, FloatingCTA (low priority)

## Migration Notes

- All Framer Motion animations preserved
- All Tailwind CSS styling preserved
- All React component logic preserved
- SendGrid email functionality migrated to actions
- SEO metadata fully migrated
