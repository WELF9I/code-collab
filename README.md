# Collaborative Code Editor 📝

A collaborative code editor built with **Next.js** and **Supabase**. This application allows users to create, share, and edit code sheets in real-time, making it an ideal tool for collaborative coding sessions and sharing snippets. 

## Features 🌟

- **Monaco Editor**: Integrated **Monaco Editor** for syntax highlighting and a seamless coding experience. 💻
- **Share functionality**: Easily share your code sheet with others via a link. 🔗
- **Refresh data**: Refresh the content if it’s modified by collaborators. 🔄

## Tech Stack 🛠️

- **Next.js**: A React framework for building modern web applications. ⚛️
- **Supabase**: Open-source backend-as-a-service for database, authentication, and more. 🗄️
- **Monaco Editor**: The code editor used for syntax highlighting and code editing. ✨
- **Tailwind CSS**: A utility-first CSS framework for custom designs. 🎨

## Installation 🚀

### Prerequisites ✅

Ensure you have the following installed:

- [Node.js](https://nodejs.org/) (version 16 or higher) 🟢
- [pnpm](https://pnpm.io/) (recommended) or npm 🚀

### Setup Instructions 🔧

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
   
## Usage 💡
Create or access code sheets: You can either create a new code sheet or access an existing one via the provided URL.
Edit code: Use the integrated Monaco Editor to write and modify code. ✍️
Share code: Share your code sheet by copying the generated link using the Share button. 🔗
Refresh sheet: Click the Refresh button to reload the sheet’s content if any changes have been made by other users. 🔄
Contributing 🤝
We welcome contributions! Here’s how you can contribute:

## Report bugs 🐛
Suggest new features 💡
Improve documentation 📚
Submit bug fixes or features via pull requests. 🔧



