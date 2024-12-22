# Collaborative Code Editor

A collaborative code editor built with **Next.js** and **Supabase**. This application allows users to create, share, and edit code sheets in real-time, making it an ideal tool for collaborative coding sessions and sharing snippets. 

## Features

- **Real-time collaboration**: Edit code sheets and share them with others in real-time.
- **Code editor**: Integrated **Monaco Editor** for a seamless coding experience.
- **Share button**: Easily share your code sheet with others via a link.

## Tech Stack

- **Next.js**: A React framework for building modern web applications.
- **Supabase**: Open-source backend-as-a-service for database, authentication, and more.
- **Monaco Editor**: The code editor used for syntax highlighting and code editing.
- **Tailwind CSS**: A utility-first CSS framework for building custom designs.

## Installation

### Prerequisites

Make sure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (version 16 or higher)
- [pnpm](https://pnpm.io/) (recommended) or npm

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/WELF9I/code-collab.git
   cd code-collab

2. Install dependencies using pnpm:
   ```bash
   pnpm install

3. Create a .env.local file in the root of the project and add the following configuration:
   ```bash
   # Supabase configuration
  NEXT_PUBLIC_SUPABASE_URL=https:
  NEXT_PUBLIC_SUPABASE_ANON_KEY=
  
  # NextAuth configuration
  NEXTAUTH_URL=
  NEXTAUTH_SECRET=
  
  # Google OAuth credentials (for NextAuth)
  GOOGLE_CLIENT_ID=
  GOOGLE_CLIENT_SECRET=


4. Run the development server:
   ```bash
   pnpm dev
