# Personal Aesthetic Galaxy Portfolio

## Overview

This is a personal portfolio website featuring an immersive, cosmic-themed single-page application. The project emphasizes atmospheric visual design with smooth animations, including a galaxy background with floating meteors and text effects. Built as a full-stack TypeScript application with React frontend and Express backend, it's designed to provide an emotional, Awwwards-style creative portfolio experience.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Build System**
- **React 18** with TypeScript for component-based UI development
- **Vite** as the build tool and development server, configured with HMR (Hot Module Replacement)
- **Wouter** for client-side routing (lightweight alternative to React Router)
- Path aliases configured (`@/`, `@shared/`, `@assets/`) for cleaner imports

**UI Component System**
- **shadcn/ui** component library with Radix UI primitives
- **Tailwind CSS** for utility-first styling with custom design tokens
- Custom theme system using CSS variables for colors and spacing
- Comprehensive UI component collection (40+ components including buttons, dialogs, forms, navigation, etc.)

**Design Philosophy**
- Full-screen immersive experience prioritizing visual impact over traditional navigation
- Mobile-first responsive approach
- Typography: Poppins font family from Google Fonts
- Atmospheric effects: Text shadows, animations, and ethereal glow effects
- Color scheme: Cosmic/space theme with neutral base colors

**State Management**
- **TanStack Query (React Query)** for server state management and API data fetching
- Custom query client configuration with optimized caching and refetch strategies
- Form state managed with **React Hook Form** and **Zod** validation via @hookform/resolvers

### Backend Architecture

**Server Framework**
- **Express.js** on Node.js with TypeScript
- Dual server setup: development (`index-dev.ts`) and production (`index-prod.ts`) entry points
- Custom logging middleware tracking request paths, durations, and responses
- Support for raw body parsing for webhooks/special integrations

**Development vs Production**
- Development: Vite middleware integration for HMR and on-demand compilation
- Production: Static file serving from pre-built `dist/public` directory
- Build process uses esbuild for server bundle and Vite for client bundle

**API Design**
- RESTful API structure with routes prefixed under `/api`
- Centralized route registration in `server/routes.ts`
- Storage abstraction layer for data operations

### Data Storage Solutions

**Database Configuration**
- **PostgreSQL** as the primary database (via Neon serverless)
- **Drizzle ORM** for type-safe database queries and schema management
- Schema definition in `shared/schema.ts` enables code sharing between client and server
- Database migrations managed through Drizzle Kit

**Current Schema**
- Users table with id (UUID), username (unique), and password fields
- Schema uses `drizzle-zod` for automatic validation schema generation

**Dual Storage Implementation**
- In-memory storage (`MemStorage`) for development/testing without database
- Database storage for production (can be implemented using Drizzle)
- Storage interface (`IStorage`) defines CRUD operations for easy swapping

**Rationale**: The dual storage approach allows development without database dependencies while maintaining production-ready architecture. Drizzle ORM provides excellent TypeScript integration and migration management.

### Authentication & Authorization

Currently implements basic user storage structure but no active authentication flow. The schema and storage interface are prepared for implementing username/password authentication.

### External Dependencies

**UI & Styling**
- Radix UI primitives (@radix-ui/*) - 20+ component packages for accessible, unstyled UI components
- Tailwind CSS with PostCSS and Autoprefixer for styling
- class-variance-authority and clsx for conditional class management
- Poppins font from Google Fonts

**State & Data Management**
- @tanstack/react-query v5 for server state
- react-hook-form with @hookform/resolvers for form handling
- Drizzle ORM (@neondatabase/serverless, drizzle-orm, drizzle-zod) for database operations

**Development Tools**
- Vite with specialized Replit plugins (runtime error overlay, cartographer, dev banner)
- TypeScript for type safety across the stack
- tsx for TypeScript execution in development
- esbuild for production server bundling

**UI Component Libraries**
- embla-carousel-react for carousels
- cmdk for command palette interfaces
- date-fns for date manipulation
- lucide-react for icons
- vaul for drawer components
- input-otp for OTP input fields
- react-day-picker for calendar/date selection
- recharts for data visualization

**Backend Services**
- Express.js web framework
- @neondatabase/serverless for PostgreSQL connectivity
- connect-pg-simple for PostgreSQL session storage (configured but not actively used)

**Asset Management**
- Galaxy background image stored in `attached_assets/`
- Static HTML/CSS reference files in `attached_assets/` demonstrating original design concept