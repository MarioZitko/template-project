# 🚀 Next.js 15 + TypeScript + ShadCN UI Template

This is a **Next.js 15** template built with **TypeScript** and **ShadCN UI**, optimized for a scalable, component-based frontend.

---

## 🔥 Features
✅ **Next.js 15 with App Router**  
✅ **TypeScript for type safety**  
✅ **ShadCN UI for flexible, customizable components**  
✅ **Tailwind CSS for styling**  
✅ **ESLint & Prettier for code quality**  
✅ **GitHub-ready repository structure**  

---

## 📂 Project Structure
```
my-template/
│── src/
│   ├── app/             # Next.js App Router (Replaces pages/)
│   │   ├── layout.tsx   # Global Layout (Required)
│   │   ├── page.tsx     # Home Page
│   │   ├── api/         # API Routes (If Needed)
│   ├── components/      # Reusable UI components
│   ├── hooks/           # Custom hooks
│   ├── lib/             # Utility functions
│   ├── public/          # Static assets
│   ├── styles/          # Global styles
│   ├── types/           # TypeScript types/interfaces
│── .eslintrc.json       # ESLint config
│── .prettierrc.json     # Prettier config
│── tailwind.config.ts   # Tailwind config
│── tsconfig.json        # TypeScript config
│── next.config.ts       # Next.js config
│── package.json         # Dependencies
```

---

## 🛠️ Installation & Setup
### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

### **2️⃣ Install Dependencies**
```bash
npm install
```

### **3️⃣ Run the Development Server**
```bash
npm run dev
```
Open **`http://localhost:3000`** to see your project.

---

## 🎨 Using ShadCN UI
ShadCN UI is a **customizable component library** built with Radix UI and Tailwind CSS.

### **1️⃣ Install ShadCN UI**
If not already installed, initialize it:
```bash
npx shadcn-ui@latest init
```
It will prompt you to set up the **components directory**.

### **2️⃣ Add New Components**
To add UI components, use:
```bash
npx shadcn-ui@latest add button card input
```
This will generate the components inside **`src/components/ui/`**.

### **3️⃣ Customize Components**
All ShadCN components are fully editable. Open **`src/components/ui/button.tsx`** and modify styles as needed.

Example customization:
```tsx
import { cn } from "@/lib/utils"

export function Button({ children }: { children: React.ReactNode }) {
  return (
    <button className="bg-primary text-primary-foreground px-4 py-2 rounded">
      {children}
    </button>
  )
}
```

---

## 🎨 Theming

### **1️⃣ Enable CSS Variables for Theming**
Modify `components.json`:
```json
{
  "style": "default",
  "rsc": true,
  "tailwind": {
    "config": "tailwind.config.ts",
    "css": "src/app/globals.css",
    "baseColor": "slate",
    "cssVariables": true
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils"
  }
}
```

### **2️⃣ Define Your Theme in `globals.css`**
```css
:root {
  --background: 0 0% 100%;
  --foreground: 222.2 47.4% 11.2%;
  --primary: 222.2 47.4% 11.2%;
  --primary-foreground: 210 40% 98%;
}

.dark {
  --background: 222.2 47.4% 11.2%;
  --foreground: 0 0% 100%;
}
```

### **3️⃣ Update Tailwind Config (`tailwind.config.ts`)**
```ts
import type { Config } from "tailwindcss";
import tailwindcssAnimate from "tailwindcss-animate";

const config: Config = {
  darkMode: ["class"],
  content: [
    "./src/app/**/*.{js,ts,jsx,tsx,mdx}",
    "./src/components/**/*.{js,ts,jsx,tsx,mdx}",
  ],
  theme: {
    extend: {
      colors: {
        background: "hsl(var(--background))",
        foreground: "hsl(var(--foreground))",
        primary: {
          DEFAULT: "hsl(var(--primary))",
          foreground: "hsl(var(--primary-foreground))",
        },
      },
    },
  },
  plugins: [tailwindcssAnimate],
};

export default config;
```

### **4️⃣ Switching Between Light & Dark Mode**
Install `next-themes`:
```bash
npm install next-themes
```
Modify `src/app/layout.tsx`:
```tsx
"use client";

import { ThemeProvider } from "next-themes";
import { ReactNode } from "react";

export default function RootLayout({ children }: { children: ReactNode }) {
  return (
    <html lang="en">
      <body className="bg-background text-foreground">
        <ThemeProvider attribute="class" defaultTheme="system">
          {children}
        </ThemeProvider>
      </body>
    </html>
  );
}
```

---

## ✨ Linting & Formatting
### **ESLint (Code Quality)**
```bash
npm run lint
```
### **Prettier (Code Formatting)**
```bash
npx prettier --write .
```

---

## 📦 Building for Production
To generate a production build:
```bash
npm run build
```
Then, start the app:
```bash
npm start
```

---

## 🚀 Deployment
### **Vercel (Recommended)**
1. Install the Vercel CLI:
   ```bash
   npm install -g vercel
   ```
2. Run:
   ```bash
   vercel
   ```
3. Follow the prompts to deploy.

---

## ❓ Troubleshooting
**ShadCN UI not working?** Run:
```bash
npx shadcn-ui@latest init
npx shadcn-ui@latest add button
```

**TypeScript errors?** Run:
```bash
npx tsc --noEmit
```

---

## 📜 License
This project is open-source under the **MIT License**.

---

🚀 **Happy coding!** If you have questions, feel free to reach out. 🔥
