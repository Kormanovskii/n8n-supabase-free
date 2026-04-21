# n8n-supabase-free
This repository provides a template for deploying a free, self-updating instance of n8n on Hugging Face Spaces, using Supabase as the database backend.
---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**---
title: n8n Free
emoji: 🔄
colorFrom: blue
colorTo: purple
sdk: docker
pinned: false
license: mit
---

# n8n-free on Hugging Face Spaces

[![Hugging Face](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)](https://huggingface.co/spaces)
[![n8n](https://img.shields.io/badge/n8n-automation-red)](https://n8n.io)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green)](https://supabase.com)

> **Free, self-updating n8n instance** on Hugging Face Spaces with Supabase as the database backend.

## ✨ Features

- 🆓 **Completely free** (Hugging Face Spaces + Supabase free tier)
- 🔄 **Self-updating** - automatically stays on the latest n8n version
- 💾 **Persistent storage** with Supabase PostgreSQL
- 🚀 **Easy deployment** - just a few clicks
- 🔐 **Secure** - all secrets stored as environment variables

## 📋 Prerequisites

- [Hugging Face](https://huggingface.co/join) account
- [Supabase](https://supabase.com) account (free tier works great)

## 🚀 Quick Start

### Step 1: Create Supabase Database

1. Go to [Supabase Dashboard](https://app.supabase.com)
2. Click **"New Project"**
3. Fill in:
   - **Name**: `n8n-database`
   - **Database Password**: (save this somewhere safe)
   - **Region**: Choose closest to you
4. Wait for database to be ready (2-3 minutes)
5. Go to **Project Settings → API**
6. Copy your credentials:
   - `Project URL`
   - `anon public key` (⚠️ NOT the service_role key!)

### Step 2: Create Hugging Face Space

1. Go to [Hugging Face Spaces](https://huggingface.co/new-space)
2. Configure:
   - **Owner**: Your username
   - **Space Name**: `n8n-free`
   - **License**: MIT
   - **SDK**: Docker
3. Click **"Create Space"**

### Step 3: Add Environment Variables

In your Space settings (**Settings → Repository Secrets**), add:

| Secret Name | Value |
|-------------|-------|
| `SUPABASE_URL` | Your Supabase Project URL |
| `SUPABASE_KEY` | Your Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | Generate a random 32-character string |

> **⚠️ Important:** Never commit these secrets to git!

### Step 4: Deploy

The Space will automatically deploy. Wait 3-5 minutes, then:
1. Click on the **"App"** tab
2. You should see the n8n welcome screen
3. Create your first workflow! 🎉

## 📁 Project Structure
n8n-free/
├── Dockerfile # Container configuration
├── docker-compose.yml # Multi-container setup
├── .gitignore # Ignored files
├── README.md # This file
└── nginx.conf # Reverse proxy config (optional)

text

## 🔧 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SUPABASE_URL` | ✅ | Your Supabase project URL |
| `SUPABASE_KEY` | ✅ | Supabase anon public key |
| `N8N_ENCRYPTION_KEY` | ✅ | For credentials encryption |
| `N8N_PORT` | ❌ | Default: `5678` |
| `WEBHOOK_URL` | ❌ | External URL for webhooks |

## 🔄 Self-Updating Mechanism

This template uses:
- **Latest n8n Docker image** - always gets security updates
- **Automatic rebuilds** - Hugging Face rebuilds on git push
- **Database migrations** - Supabase handles schema updates

To manually update:
```bash
git commit --allow-empty -m "Trigger rebuild"
git push
💾 Data Persistence
Workflows: Stored in Supabase PostgreSQL

Credentials: Encrypted in database

Execution history: Persistent in database

Files: Stored as database records

🛠️ Customization
Adding npm packages
Edit Dockerfile:

dockerfile
FROM n8nio/n8n:latest
USER root
RUN npm install -g your-package-name
USER node
Changing n8n version
dockerfile
FROM n8nio/n8n:0.234.0  # Pin specific version
🐛 Troubleshooting
Space fails to start
Check logs in Settings → Logs

Verify Supabase credentials

Ensure database is accessible

Database connection errors
Check if Supabase project is active

Verify IP isn't blocked (Supabase free tier has limits)

Test connection with psql command

"Encryption key missing" error
Set N8N_ENCRYPTION_KEY in Repository Secrets

Generate one: openssl rand -hex 16

📊 Resource Limits (Hugging Face Free Tier)
CPU: 2 vCPUs

RAM: 16 GB

Storage: 50 GB

Sleep after: 48 hours of inactivity

Build time: 1 hour max

💡 Keep your Space active by using a free uptime monitor like UptimeRobot

🔐 Security Best Practices
✅ Use environment variables for all secrets

✅ Rotate encryption keys regularly

✅ Enable Supabase Row Level Security (RLS)

✅ Use strong database passwords

❌ Never commit .env files

❌ Don't use service_role key for n8n

📚 Resources
n8n Documentation

Supabase Docs

Hugging Face Spaces

n8n Docker Guide

🤝 Contributing
Found a bug or have an improvement?

Fork the repository

Make your changes

Submit a Pull Request

📄 License
MIT License - see LICENSE file for details

⭐ Support
If this template helps you:

⭐ Star the repository

🐛 Report issues

💡 Share your workflows

🔄 Fork and improve

Made with ❤️ for the automation community

text

---

## Как добавить:

1. На странице вашего Space нажмите **"Add file"** → **"Create a new file"**
2. В поле имени введите: `README.md`
3. Скопируйте весь текст выше и вставьте в большое поле
4. Внизу напишите сообщение коммита: `Add README`
5. Нажмите **"Commit new file"**
