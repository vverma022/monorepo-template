# Vasu's Monorepo Template

A modern full-stack monorepo template featuring Next.js frontend, NestJS backend, shared TypeScript types, and shadcn/ui components.

## 🏗️ Project Structure

This monorepo is organized with the following structure:

- **`apps/web/`** - Next.js 14 frontend application with App Router
- **`apps/server/`** - NestJS backend API server
- **`packages/ui/`** - Shared shadcn/ui components library
- **`packages/types/`** - Shared TypeScript type definitions
- **`packages/eslint-config/`** - Shared ESLint configurations
- **`packages/typescript-config/`** - Shared TypeScript configurations

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ 
- pnpm (recommended package manager)

### Installation

```bash
# Clone the repository
git clone <your-repo-url>
cd developer-logs

# Install dependencies
pnpm install

# Start development servers
pnpm dev
```

This will start both the Next.js frontend (port 3000) and NestJS backend (port 3001).

## 📦 Adding shadcn/ui Components

To add components to your web app, run the following command from the root:

```bash
pnpm dlx shadcn@latest add button -c apps/web
```

This will place the ui components in the `packages/ui/src/components` directory, making them available across the monorepo.

## 🎨 Using Components

Import components in your Next.js app from the shared ui package:

```tsx
import { Button } from "@workspace/ui/components/button"

export default function MyPage() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}
```

## 🛠️ Development Scripts

```bash
# Start all applications in development mode
pnpm dev

# Build all packages and applications
pnpm build

# Run tests across the monorepo
pnpm test

# Lint all packages and applications
pnpm lint

# Type check all TypeScript files
pnpm type-check
```

## 🔧 Configuration

### Tailwind CSS

Your `tailwind.config.ts` and `globals.css` are already configured to use components from the `ui` package.

### TypeScript

Shared TypeScript configurations are available in `packages/typescript-config/`:
- `base.json` - Base configuration
- `nextjs.json` - Next.js specific configuration
- `react-library.json` - React library configuration

### ESLint

Shared ESLint configurations are available in `packages/eslint-config/`:
- `base.js` - Base configuration
- `next.js` - Next.js specific rules
- `react-internal.js` - React internal rules

## 📁 Key Features

- **Full-Stack Development**: Next.js frontend with NestJS backend
- **Shared Components**: shadcn/ui components shared across the monorepo
- **Type Safety**: Shared TypeScript types between frontend and backend
- **Modern Tooling**: ESLint, Prettier, and TypeScript configurations
- **Monorepo Management**: Turbo for fast builds and development
- **Package Management**: pnpm workspaces for efficient dependency management

## 🏃‍♂️ Running Individual Apps

```bash
# Run only the Next.js frontend
pnpm --filter web dev

# Run only the NestJS backend
pnpm --filter server dev

# Build only the UI package
pnpm --filter ui build
```

## 📚 Tech Stack

- **Frontend**: Next.js 14, React 18, TypeScript
- **Backend**: NestJS, TypeScript
- **Styling**: Tailwind CSS, shadcn/ui
- **Package Manager**: pnpm
- **Monorepo Tooling**: Turbo
- **Linting**: ESLint
- **Type Checking**: TypeScript
