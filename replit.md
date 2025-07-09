# SIRIUS Technologies Website

## Overview

This is a modern, multilingual (English/French) corporate website for SIRIUS Technologies, a technology company specializing in mobile development, ERP solutions, and AI-powered analytics. The application is built as a full-stack web application with a React frontend and Express.js backend, featuring a PostgreSQL database for contact form submissions.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with shadcn/ui component library
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management
- **Animations**: Framer Motion for smooth animations and transitions
- **UI Components**: Radix UI primitives with custom styling
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database ORM**: Drizzle ORM for type-safe database operations
- **Database**: PostgreSQL (configured for Neon Database) - **ACTIVE**
- **Storage**: DatabaseStorage class implementing IStorage interface
- **Development**: Hot module replacement with Vite integration

## Key Components

### Frontend Structure
- **Single Page Application**: One main route serving a multi-section landing page
- **Component-based Architecture**: Modular components for Hero, Services, About, Portfolio, Contact, and Footer sections
- **Responsive Design**: Mobile-first approach with responsive breakpoints
- **Internationalization**: Context-based translation system supporting English and French
- **Form Handling**: React Hook Form with Zod validation for contact forms

### Backend Services
- **Contact API**: RESTful endpoint for handling contact form submissions
- **Data Storage**: PostgreSQL database with Drizzle ORM for type-safe operations
- **Health Check**: API endpoint for monitoring database connectivity
- **Error Handling**: Centralized error handling with appropriate HTTP status codes
- **Development Tools**: Custom logging and request tracking middleware

### Database Schema
- **Users Table**: Basic user authentication structure (id, username, password)
- **Contact Messages Table**: Stores contact form submissions with fields for name, email, service type, and message
- **Timestamps**: Automatic creation timestamps for audit trails

## Data Flow

1. **User Interaction**: Users interact with the multilingual landing page
2. **Form Submission**: Contact form data is validated client-side with Zod schemas
3. **API Communication**: TanStack Query manages API calls to the Express backend
4. **Data Persistence**: Contact messages are stored in PostgreSQL via Drizzle ORM
5. **Response Handling**: Success/error states are managed with toast notifications
6. **Language Switching**: Real-time language switching updates all UI text

## External Dependencies

### Core Technologies
- **@neondatabase/serverless**: PostgreSQL database connection for Neon Database
- **drizzle-orm & drizzle-kit**: Type-safe ORM and migration tools
- **@tanstack/react-query**: Server state management and caching
- **framer-motion**: Animation and gesture library
- **@radix-ui/***: Accessible UI component primitives

### Development Tools
- **TypeScript**: Type safety across the entire application
- **Tailwind CSS**: Utility-first CSS framework
- **Vite**: Build tool with hot reload and optimization
- **shadcn/ui**: Pre-built component library with consistent design

### Styling & UI
- **Custom Design System**: SIRIUS brand colors and consistent spacing
- **Dark Mode Support**: CSS variables for theme switching
- **Responsive Typography**: Fluid typography scales
- **Gradient Effects**: Custom gradient backgrounds and text effects

## Deployment Strategy

### Build Process
- **Frontend Build**: Vite builds static assets to `dist/public`
- **Backend Build**: ESBuild compiles TypeScript server code to `dist`
- **Database Migrations**: Drizzle Kit manages schema migrations
- **Environment Configuration**: Environment variables for database connections

### Production Considerations
- **Static File Serving**: Express serves built frontend assets in production
- **Database Connection**: Uses DATABASE_URL environment variable for PostgreSQL
- **Error Handling**: Production-safe error messages without sensitive data exposure
- **Performance**: Optimized bundle sizes and lazy loading where appropriate

### Development Workflow
- **Hot Reload**: Vite provides instant feedback during development
- **Type Checking**: TypeScript ensures type safety across client and server
- **Database Schema**: Drizzle migrations maintain database consistency
- **Code Organization**: Clear separation between client, server, and shared code

The application is designed to be easily deployable on modern hosting platforms with PostgreSQL support, with particular optimization for Replit's environment through specialized plugins and configurations.