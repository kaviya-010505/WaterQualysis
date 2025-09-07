# HMPI Calculator

## Overview

This is a Heavy Metal Pollution Index (HMPI) calculator web application that analyzes water quality by calculating pollution levels based on heavy metal concentrations. The application allows users to upload water test data files (CSV/Excel) and generates HMPI scores with safety assessments based on WHO and BIS permissible limits. It's built as a full-stack TypeScript application with a React frontend and Express.js backend.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **UI Components**: Radix UI components with shadcn/ui styling system
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for client-side routing
- **Forms**: React Hook Form with Zod validation
- **File Processing**: Client-side Excel/CSV parsing using XLSX library

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **API Design**: RESTful API with JSON responses
- **File Handling**: Multer middleware for file uploads with memory storage
- **Data Processing**: Server-side calculation of HMPI scores using mathematical formulas

### Database & Data Storage
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Database**: Configured for PostgreSQL via Neon Database serverless
- **Schema**: Defines tables for users, heavy metal standards, and water test results
- **Migrations**: Drizzle Kit for database schema management
- **Development Storage**: In-memory storage implementation for development

### Data Models
- **Heavy Metal Standards**: WHO/BIS permissible limits with health impact information
- **Water Test Results**: Sample data with metal concentrations, HMPI scores, and safety status
- **User Management**: Basic user authentication structure

### HMPI Calculation Engine
- **Formula Implementation**: Multi-step calculation process following standard HMPI methodology
- **Quality Rating**: Calculates Qi = (Ci / Si) × 100 for each metal
- **Weight Calculation**: Wi = 1 / Si (inverse of permissible limit)
- **Index Computation**: HMPI = Σ(Wi × Qi) / ΣWi
- **Safety Classification**: Categorizes pollution levels and provides recommendations

### File Processing Pipeline
- **Upload Handling**: Supports CSV and Excel files up to 10MB
- **Data Parsing**: Automatic detection and parsing of different file formats
- **Validation**: File type and size validation with error handling
- **Data Extraction**: Intelligent extraction of metal concentration data from various file structures

## External Dependencies

### Core Libraries
- **@neondatabase/serverless**: PostgreSQL serverless database connection
- **drizzle-orm**: TypeScript ORM for database operations
- **@tanstack/react-query**: Server state management and caching
- **express**: Web application framework for Node.js
- **multer**: File upload handling middleware
- **xlsx**: Excel file parsing and processing

### UI Framework
- **@radix-ui/***: Comprehensive set of accessible UI primitives
- **tailwindcss**: Utility-first CSS framework
- **class-variance-authority**: Variant-based component styling
- **lucide-react**: Icon library

### Development Tools
- **vite**: Fast build tool and dev server
- **tsx**: TypeScript execution for Node.js
- **drizzle-kit**: Database migration and management tools
- **@replit/vite-plugin-***: Replit-specific development plugins

### Validation & Forms
- **zod**: TypeScript-first schema validation
- **react-hook-form**: Performant form handling
- **@hookform/resolvers**: Form validation resolvers

The application follows a modular architecture with clear separation between frontend UI components, backend API handlers, database operations, and business logic for HMPI calculations. The system is designed to handle various file formats and provide real-time feedback during the calculation process.