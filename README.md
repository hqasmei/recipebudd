# RecipeBudd - A Recipe Management Application

A modern full-stack application built with Bun, React, Shadcn UI, and PostgreSQL, featuring secure GitHub authentication.

<div align="center">
  <img src="https://github.com/user-attachments/assets/ef3909c6-f371-4fb7-80f2-71b4c64eb9ef" alt="App">
</div>

## About The Project 📖

This project demonstrates a clean, efficient, and modern approach to full-stack web development. It combines the speed of Bun with the flexibility of React and the reliability of PostgreSQL to create a seamless development experience, while providing secure user authentication through GitHub.

### How It Works

The application follows a clear separation of concerns:

- **Frontend**: A React application built with Vite that handles the user interface and client-side logic. React Router v7 manages navigation between different views, while Shadcn UI provides beautiful, accessible components that speed up development without sacrificing customization. User authentication is handled through Better Auth's client SDK.

- **Backend**: A Bun-powered server using Hono as a lightweight, fast web framework. The API endpoints communicate with a PostgreSQL database through Drizzle ORM, which provides type-safe database operations and schema management. The backend also manages authentication flows with GitHub through Better Auth, handling OAuth callbacks and session management.

- **Authentication**: The application uses Better Auth for GitHub social login. The authentication flow begins on the frontend where users initiate the GitHub OAuth process. The backend handles the OAuth callback, validates the user, and establishes a secure session. This approach provides a seamless login experience while maintaining security best practices.

- **Data Flow**: When a user interacts with the frontend, React components trigger API calls to the backend. The backend processes these requests, performs necessary database operations using Drizzle ORM, and returns the results to the frontend. Protected routes and API endpoints verify authentication status before allowing access to private data.

### Why This Tech Stack?

This combination of technologies offers several advantages:

- **Performance**: Bun's speed significantly reduces build times and server response times.
- **Developer Experience**: TypeScript provides type safety across the entire stack.
- **Maintainability**: The modular architecture makes it easy to update or replace individual components.
- **Scalability**: Each part of the stack is designed to handle growth, from the database to the frontend.
- **Security**: Better Auth provides a robust authentication system that follows OAuth best practices, eliminating the need to build complex authentication flows from scratch.
- **Cross-Origin Architecture**: The separate frontend and backend servers (ports 3000 and 3001) demonstrate proper CORS configuration for secure cross-origin requests with authentication.

## Tech Stack 💻

- **Frontend** 🎨
  - [React](https://react.dev) with [Vite](https://vitejs.dev)
  - [React Router](https://reactrouter.com) v7 (routing)
  - [Shadcn UI](https://ui.shadcn.com) components
  - [TypeScript](https://www.typescriptlang.org)
  - [Better Auth](https://better-auth.com) for GitHub authentication
  
- **Backend** ⚙️
  - [Bun](https://bun.sh) runtime
  - [Hono](https://hono.dev) (web framework)
  - [PostgreSQL](https://www.postgresql.org) database
  - [Drizzle ORM](https://orm.drizzle.team) (SQL toolkit)

## Project Checklist ✅

> **Note:** This project is currently in development. Below is a high-level checklist of remaining tasks.

- [x] Project structure and monorepo setup
- [x] Frontend and backend basic configuration 
- [x] Authentication system with Better Auth (GitHub)
- [ ] Error handling and validation
- [ ] Production environment configuration
- [ ] Deployment setup
- [ ] Documentation

## Current Status 🚀

The application is currently working in the local development environment:
- Backend API server functions correctly on port 3001
- GitHub authentication flow is successfully implemented and tested
- Frontend-backend communication is properly configured with CORS

For production deployment, all localhost URLs will need to be updated:
- Change callback URL from `http://localhost:3001/api/auth/callback/github` to your production backend URL
- Update trusted origins to include your production frontend URL
- Modify any hardcoded localhost references in the code
- Ensure proper CORS configuration between your production frontend and backend domains

## Prerequisites ✅

- [Bun](https://bun.sh) installed
- [PostgreSQL](https://www.postgresql.org/) installed and running
- Node.js 16.0 or higher

## Getting Started 🎯

1. Clone the repository:
```bash
git clone git@github.com:hqasmei/recipebudd.git
cd recipebudd
```

2. Install dependencies:
```bash
bun install
```

3. Set up environment variables:
```bash
# In frontend directory
cp .env.example .env.local

# In backend directory
cp .env.example .env
```

4. Start the development servers:
```bash
# Run both frontend and backend
bun run dev

# Run frontend only
bun run dev:frontend

# Run backend only
bun run dev:backend
```

The frontend will be available at `http://localhost:3000` and the backend at `http://localhost:3001`.

## Project Structure 📁

```
├── frontend/           # React frontend application
├── backend/           # Bun backend server
├── package.json      # Root package.json for running both services
└── README.md
```

## Contributing 🤝

1. Create a new branch for your feature
2. Make your changes
3. Submit a pull request

## License 📝

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
