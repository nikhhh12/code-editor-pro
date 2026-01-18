# Code Editor Pro

**Code Editor Pro** is a sophisticated, browser-based integrated development environment (IDE) that brings a desktop-grade coding experience to the web. Built with a modular architecture and powered by Google Gemini AI, it allows developers to write, debug, and execute full-stack applications without leaving their browser.

---

## Technical Stack

| Category | Technology |
| --- | --- |
| **Framework** | Next.js 14/15 (App Router) |
| **Authentication** | NextAuth.js (Google & GitHub) |
| **Database** | MongoDB with Prisma ORM |
| **AI Integration** | Google Generative AI (Gemini SDK) |
| **Editor Core** | Monaco Editor |
| **In-Browser Runtime** | StackBlitz WebContainers |
| **User Interface** | Tailwind CSS + Shadcn UI |
| **Terminal** | xterm.js |

---

## Key Features

### Modular Architecture

Unlike standard boilerplates, this project uses a modular design. Logic for the AI system, file explorer, and WebContainers is separated into self-contained modules, ensuring the codebase remains maintainable and scalable.

### AI-Driven Workflow

- **Context-Aware Suggestions:** The editor analyzes cursor position and incomplete code patterns to provide accurate ghost-text completions via `gemini-1.5-flash-lite`.
- **Intelligent Chat Assistant:** A specialized chat interface trained on coding patterns helps with refactoring, bug detection, and architectural advice.

### Professional IDE Experience

- **Dynamic Layout:** Uses resizable panel groups for a fully customizable workspace (Sidebar, Editor, Preview, and Terminal).
- **Virtual File System (VFS):** Full CRUD support for files and folders with real-time persistence to MongoDB.
- **In-Browser Execution:** Run Node.js environments and live development servers directly in the browser via WebContainers.


### Collaboration (Live Code Playground)

Code Editor Pro supports an invite-based collaboration system for the Live Code playground, allowing authenticated users to securely collaborate on shared coding sessions.

#### Highlights
- Unique user identity using system-generated user IDs and usernames  
- Invite-based access control for playground collaboration  
- Accept or reject collaboration requests via dashboard UI  
- Secure backend workflows to manage collaboration state  
- Persistent collaboration data managed using Prisma + MongoDB  

#### Workflow
1. Each user is assigned a unique user ID and username at account creation.  
2. A user can invite another registered user to collaborate on a Live Code playground.  
3. The invited user can accept or reject the request from their dashboard.  
4. Once accepted, collaborators gain shared access to the playground environment.  

This design ensures controlled access, clear ownership, and a scalable foundation for future real-time collaboration enhancements.

---

## Installation and Setup

### 1. Prerequisites

- Node.js 18+
- A MongoDB instance (Local or Atlas)
- Google AI Studio API Key

### 2. Clone the Repository

```bash
git clone https://github.com/nikhhh12/code-editor-pro.git
cd code-editor-pro
npm install
```

### 3. Environment Variables

Create a .env.local file in the root directory:
```bash
# Database
DATABASE_URL="mongodb+srv://..."

# NextAuth
NEXTAUTH_SECRET="your_secret"
GOOGLE_CLIENT_ID="your_id"
GOOGLE_CLIENT_SECRET="your_secret"
GITHUB_ID="your_id"
GITHUB_SECRET="your_secret"

# AI
GEMINI_API_KEY="your_google_ai_studio_key"
```

### 4. Database Setup

```bash
npx prisma generate
npx prisma db push
```

### 5. Start Development

```bash
npm run dev
```
Visit http://localhost:3000 in your browser.

---

## Shortcuts and Usage

- Ctrl + S: Save active file to the virtual file system.
- Ctrl + Space: Manually trigger AI code completion.
- Ctrl + `: Toggle the integrated terminal.

