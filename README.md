# Sai Saran Rangisetti - Portfolio

A modern, interactive portfolio built with SvelteKit showcasing AI/ML projects, technical expertise, and interactive labs.

## Development

This portfolio was developed using modern web technologies with a focus on performance and user experience:

- **SvelteKit 5** - Full-stack framework with SSR
- **TypeScript** - Type safety throughout the codebase
- **Tailwind CSS 4** - Utility-first styling
- **MDsveX** - Markdown blog integration
- **Vercel** - Deployment platform

### Key Features

- **Interactive Labs**: DSA Visualizer, Game of Life, Tic Tac Toe with AI
- **Project Showcase**: AI/ML projects with live demos
- **Blog Integration**: Technical writing with MDsveX
- **Responsive Design**: Mobile-first approach
- **Performance Optimized**: Fast loading and smooth animations

## How to Run

### Prerequisites

- Node.js 20+ 
- pnpm (recommended) or npm

### Installation

```bash
# Clone the repository
git clone https://github.com/saranRangisetti/Saran-portfolio-2025.git
cd Saran-portfolio-2025

# Install dependencies
pnpm install
```

### Development

```bash
# Start development server
pnpm dev

# Open http://localhost:5173 in your browser
```

### Production Build

```bash
# Build for production
pnpm build

# Preview production build
pnpm preview
```

### Deployment

The portfolio is configured for Vercel deployment:

```bash
# Deploy to Vercel
vercel --prod
```

## Project Structure

```
src/
├── content/blog/          # Markdown blog posts
├── labs/                  # Interactive lab projects
├── lib/components/        # Reusable Svelte components
├── routes/               # SvelteKit pages
└── static/              # Static assets
```

## Technologies Used

- **Frontend**: SvelteKit, TypeScript, Tailwind CSS
- **Content**: MDsveX for blog posts
- **Deployment**: Vercel
- **Version Control**: Git, GitHub
