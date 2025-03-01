# Venefish Project Documentation

## Project Architecture

### Directory Structure
- `/app`: Next.js app router pages and layouts
- `/components`: Reusable UI components and Firebase providers
- `/lib`: Utility functions and helpers
- `/pages/api`: API routes for server-side functionality
- `/public`: Static assets

### Technology Stack
- **Frontend**: Next.js, React, TypeScript
- **Styling**: Tailwind CSS, shadcn/ui
- **Authentication**: Firebase Auth with Google Sign-In
- **Database**: Firebase Firestore
- **Deployment**: Vercel

## Logic Map

### Authentication Flow
1. User visits the site
2. Firebase Auth provider initializes in `components/firebase-providers.tsx`
3. Auth state is managed through ReactFire hooks
4. Protected routes check auth state before rendering
5. User can sign in with Google via the login page
6. After successful authentication, user is redirected to the app page

### Google Sign-In Implementation
1. Google Sign-In is enabled in Firebase Console
2. The application uses `ProviderLoginButtons` component to handle authentication
3. When user clicks the Google button, `signInWithPopup` is called with a `GoogleAuthProvider`
4. After successful authentication, a toast notification is shown and the user is redirected

### Data Flow
1. Components use ReactFire hooks to interact with Firestore
2. Data is fetched and updated through Firebase SDK
3. UI updates reactively based on data changes

## Key Components

### Firebase Integration
- `components/firebase-providers.tsx`: Sets up Firebase providers for the application
- Firebase configuration is stored in `.env.local` file
- `components/auth/provider-login-buttons.tsx`: Handles provider-based authentication (Google, GitHub)

### Authentication Components
- `components/auth-card.tsx`: Main authentication card component
- `components/auth/sign-in-form.tsx`: Email/password sign-in form
- `components/auth/sign-up-form.tsx`: Email/password sign-up form
- `components/auth/provider-login-buttons.tsx`: Social provider authentication buttons

### UI Components
- Built with shadcn/ui and Tailwind CSS
- Customizable through the component props and Tailwind classes

## Design Decisions

### Next.js App Router
- Uses the newer App Router architecture for better performance and features
- Provides better support for server components and data fetching

### Firebase + Vercel
- Chosen for free tier capabilities until scaling to higher user numbers
- Seamless integration between frontend and backend services

### Authentication Strategy
- Uses Firebase Authentication for simplicity and security
- Implements both email/password and social provider authentication
- Google Sign-In enabled for easier user onboarding

## Important Notes
- Remember to update Firebase configuration in `.env.local` before using the template
- The template is designed to be a starting point - customize as needed for your specific application
- Firebase Admin SDK setup is optional and only needed for certain server-side operations 