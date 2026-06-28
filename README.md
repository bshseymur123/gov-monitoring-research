National Jurisprudence Monitoring & Roadmap

A professional documentation website for the "National Jurisprudence Monitoring & Roadmap" project, featuring information on governmental oversight, monitoring frameworks, and institutional roadmaps.

Project Overview
- This project presents a comprehensive framework for neutral governmental monitoring, including:
- Identified Gaps: Analysis of gaps in neutral governmental monitoring systems
- Framework: The "Superior Neutral Auditor" (SGNA) prompt framework
- Roadmap: A phased approach to national stability and future growth

Fixed Issues (v1.1.0)
This is the final corrected, zero-error version with all identified issues resolved:

1. ✅ Configuration Fixed
Issue: pnpm-workspace.yaml had placeholder configuration for allowBuilds.esbuild
Fix: Set allowBuilds.esbuild to true to enable esbuild during installation
2. ✅ Analytics Warnings Eliminated
Issue: Vite build warnings about missing VITE_ANALYTICS_ENDPOINT and VITE_ANALYTICS_WEBSITE_ID
Fix: Removed the analytics script from client/index.html (can be re-added if needed via environment configuration)
Note: Analytics can be optionally enabled by setting environment variables and uncommenting the script
3. ✅ Asset Handling Improved
Issue: Missing attached_assets directory referenced in vite.config.ts
Fix: Created the attached_assets directory for local asset storage
Note: The project uses /manus-storage/ proxy for dynamic asset loading. Configure BUILT_IN_FORGE_API_URL and BUILT_IN_FORGE_API_KEY in .env if using the storage proxy
4. ✅ Environment Configuration
Added: .env file with commented configuration options
Added: .env.example file for documentation and setup reference

Installation
Prerequisites
Node.js 18+ (v22.13.0 recommended)
pnpm 10+ (v11.9.0 recommended)

Setup Instructions
Clone or extract the project
Bash
cd gov-monitoring-research-fixed

Install dependencies
Bash
pnpm install

(Optional) Configure environment variables
Bash
cp .env.example .env
# Edit .env to add your configuration

Run development server
Bash
pnpm run dev
The application will be available at http://localhost:3000

Available Scripts
pnpm run dev - Start development server with hot module reloading
pnpm run build - Build for production (creates dist/ directory )
pnpm run start - Start production server (requires pnpm run build first)
pnpm run preview - Preview production build locally
pnpm run check - Run TypeScript type checking
pnpm run format - Format code with Prettier

Project Structure
Plain Text
gov-monitoring-research-fixed/
├── client/                    # React frontend
│   ├── src/
│   │   ├── pages/            # Page components
│   │   ├── components/       # UI components
│   │   ├── contexts/         # React contexts
│   │   ├── hooks/            # Custom hooks
│   │   ├── lib/              # Utility functions
│   │   └── App.tsx           # Main app component
│   ├── index.html            # HTML template
│   └── public/               # Static assets
├── server/                    # Express server
│   └── index.ts              # Server entry point
├── shared/                    # Shared utilities
├── attached_assets/          # Local asset storage
├── .env                       # Environment variables (local)
├── .env.example              # Environment variables template
├── vite.config.ts            # Vite configuration
├── tailwind.config.js        # Tailwind CSS configuration
├── tsconfig.json             # TypeScript configuration
└── package.json              # Project dependencies


Configuration
Optional Environment Variables
Create a .env file in the project root with any of these optional variables:
env
# Analytics (optional)
VITE_ANALYTICS_ENDPOINT=https://analytics.example.com
VITE_ANALYTICS_WEBSITE_ID=your-website-id

# Storage Backend (optional )
BUILT_IN_FORGE_API_URL=https://storage.example.com
BUILT_IN_FORGE_API_KEY=your-api-key

# OAuth (optional )
VITE_OAUTH_PORTAL_URL=https://oauth.example.com
VITE_APP_ID=your-app-id

Build and Deployment
Production Build
Bash
pnpm run build
This creates:
dist/public/ - Built frontend assets
dist/index.js - Compiled server

Running Production Build
Bash
NODE_ENV=production pnpm run start
The server will listen on port 3000 (or $PORT environment variable ).

Technology Stack
Frontend: React 19, TypeScript, Vite
Styling: Tailwind CSS, shadcn/ui components
Backend: Express.js
Routing: Wouter (lightweight client-side router)
Forms: React Hook Form with Zod validation
UI Components: Radix UI primitives
Build Tools: Vite, esbuild, PostCSS

Troubleshooting
Issue: Port 3000 already in use
Solution: The dev server will automatically find the next available port. Check the console output for the actual port.

Issue: Images not loading
Solution: If using /manus-storage/ paths, ensure BUILT_IN_FORGE_API_URL and BUILT_IN_FORGE_API_KEY are configured in .env. Otherwise, place images in attached_assets/ and update component paths.

Issue: Build fails
Solution: Clear node_modules: rm -rf node_modules pnpm-lock.yaml
Reinstall: pnpm install
Rebuild: pnpm run build

Verification
All errors have been resolved. The project now:
✅ Installs without warnings
✅ Builds without errors
✅ Runs successfully in production
✅ Has proper TypeScript type checking
✅ Includes proper configuration templates

License
MIT

Support
For issues or questions, refer to the documentation or check the project's issue tracker.
Version: 1.1.0 (Final Corrected Release)

Last Updated: 2026-06-28

Status: Production Ready ✅
