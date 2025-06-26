🛠️ Project Local Setup Guide

This document provides a comprehensive setup guide for running the HR System project on your local machine. Please follow each step carefully. This ensures all team members have a consistent and working environment.

🔧 1. System Requirements & Tools

Install the following system tools:



✅ Note: Use nvm use if .nvmrc file is present for correct Node.js version.

🏗️ 2. Project Setup

Clone the project repository:

git clone https://github.com/your-org/hr-system.git
cd hr-system

Install project dependencies:

npm install
# or
yarn install
# or
pnpm install

Create and configure your environment variables:

cp .env.example .env

Configure .env with the following:

DATABASE_URL=postgresql://username:password@localhost:5432/hr_system_dev
JWT_SECRET=your-secret-key
PORT=3000

Setup Prisma:

npx prisma generate
npx prisma migrate dev --name init

Run Prisma Studio (optional GUI to view database):

npx prisma studio

Start the backend server:

npm run dev

Start the frontend (if applicable):

cd client
npm install
npm run dev

✅ 3. Testing & Seeding

Run backend tests:

npm run test

Seed the database with demo data (e.g., departments, positions):

npx prisma db seed

⚠️ Ensure the seed script is configured in prisma/seed.ts and referenced in package.json.

📦 4. Development Tools



📁 Optional Setup Enhancements



docker-compose up -d



npx husky install



🔄 Syncing with Remote (Git Best Practices)

Always create a new feature branch:

git checkout -b feature/your-task-name

Push regularly and write clear commit messages

Use PRs (Pull Requests) and request reviews before merging to main

✅ You're All Set!

If everything is working, you can start developing features or testing the system.

If you run into issues, please check:

Console logs / errors

.env file correctness

Database is running and accessible

For help, tag @backend-team or @devops-team in your GitHub Issues or Slack.

Happy coding! 🚀


