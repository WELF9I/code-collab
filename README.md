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
   NEXT_PUBLIC_SUPABASE_URL=https://your-supabase-url.supabase.co/
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
   
   # NextAuth configuration
   NEXTAUTH_URL=http://localhost:3000
   NEXTAUTH_SECRET=your-nextauth-secret
   
   # Google OAuth credentials (for NextAuth)
   GOOGLE_CLIENT_ID=your-google-client-id
   GOOGLE_CLIENT_SECRET=your-google-client-secret


4. Run the development server:
   ```bash
   pnpm dev

## Database Structure 📂
This project uses Supabase for its database management. Below is the schema used for managing sheets and collaborators:

### Sheets Table
Stores the details of code sheets created by users:
```bash
CREATE TABLE sheets (
  id UUID DEFAULT uuid_generate_v4() PRIMARY KEY,
  title TEXT NOT NULL,
  content TEXT DEFAULT '',
  created_at TIMESTAMP WITH TIME ZONE DEFAULT TIMEZONE('utc'::text, NOW()),
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT TIMEZONE('utc'::text, NOW()),
  owner_id UUID NOT NULL
);
```
### Sheet Collaborators Table
Manages the relationship between sheets and their collaborators:
   ```bash
   CREATE TABLE sheet_collaborators (
     sheet_id UUID REFERENCES sheets(id) ON DELETE CASCADE,
     user_id TEXT NOT NULL,
     created_at TIMESTAMP WITH TIME ZONE DEFAULT TIMEZONE('utc'::text, NOW()),
     PRIMARY KEY (sheet_id, user_id)
   );
```
### Row Level Security (RLS) Policies
Row Level Security is enabled to ensure secure access control for the sheets and sheet_collaborators tables:
   ```bash
   -- Enable Row Level Security
   ALTER TABLE sheets ENABLE ROW LEVEL SECURITY;
   ALTER TABLE sheet_collaborators ENABLE ROW LEVEL SECURITY;
   
   -- Policies for sheets
   CREATE POLICY "Enable insert for authenticated users"
   ON public.sheets
   FOR INSERT 
   WITH CHECK (true);
   
   CREATE POLICY "Enable read access for all"
   ON public.sheets
   FOR SELECT
   USING (true);
   
   CREATE POLICY "Enable update for all"
   ON public.sheets
   FOR UPDATE
   USING (true);
```
### Notes:
Replace "Enable update for all" with more restrictive rules as needed to enhance security.


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



