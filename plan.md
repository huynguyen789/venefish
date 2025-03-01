# Venefish Template Setup Plan

## Overview
This document outlines the steps to set up and customize the Venefish template, which is a boilerplate for React TypeScript projects using Next.js, shadcn/ui, Tailwind, and Firebase on Vercel.

## Setup Steps

- [x] Clone the Venefish repository
- [ ] Install dependencies with `npm install`
- [ ] Create a Firebase project and enable authentication
  - [x] Enable Google Sign-In in Firebase Console
- [ ] Get Firebase configuration and update `components/firebase-providers.tsx`
  - [x] Create `.env.local` file with Firebase configuration variables
- [x] Enable Google Sign-In in the application
  - [x] Update `components/auth/provider-login-buttons.tsx` to enable Google authentication
- [ ] Run the development server with `npm run dev`
- [ ] Customize the application for our specific needs

## Firebase Setup
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project
3. Enable Authentication
   - Enable Google Sign-In method
   - Configure authorized domains if necessary
4. Get the Firebase configuration object
5. Update the configuration in `.env.local`

## Optional Firebase Admin Setup
If Firebase Admin functionality is needed:
1. Create `.env.local` file at the root level
2. Get Firebase service account private key
3. Stringify the private key and set it as `FIREBASE_ADMIN_SDK` environment variable
4. Ensure the same environment variable is set in Vercel deployment

## Project Customization
- Update project name and description in `package.json`
- Customize UI components as needed
- Implement specific business logic
- Update README.md with project-specific information

## Deployment
- Connect the repository to Vercel
- Configure environment variables in Vercel
- Deploy the application 