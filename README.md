# Nit Family Messenger Quick Start

Get the Nit Family Messenger stack running locally using Docker Compose.

## 🚀 Services Included

*   **Database (port 5432):** PostgreSQL instance storing user settings, logs, and message models.
*   **Backend (port 8080):** Go API & WebSocket router providing core media calling, push triggers, and federation relay logic.
*   **Web Admin (port 8082):** Vite Dark-themed administration SPA to manage backend configurations.
*   **Web Client (port 8083):** Vite Dark-themed family chat application.

---

## 🏃 Getting Started

### 1. Configure Environments
Copy the template configuration file:
```bash
cp .env.example .env
```
*(Optionally review and update the variables inside `.env` to secure secrets/passwords).*

### 2. Run the Main Stack
Start the primary database, backend, admin, and chat services:
```bash
docker compose up -d --build
```

### 3. Run the Standalone Proxy (Hosted Separately)
To spin up the backup reverse proxy server on a separate node/server:
```bash
docker compose -f docker-compose.proxy.yml up -d --build
```

### 4. Setup and Access
Once containers are healthy, open your web browser to:
1.  **Server Setup & Admin:** Visit [http://localhost:8082](http://localhost:8082)
    *   Initialize the Server Address (`http://localhost:8080`).
    *   On first run, complete the Setup/Activation Wizard to create your Administrator account.
    *   Navigate to the Dashboard, update settings, and generate an Invite Code.
2.  **Family Chat Client:** Visit [http://localhost:8083](http://localhost:8083)
    *   Point it to the backend Server Address (`http://localhost:8080`).
    *   Sign Up using the invite code generated from the Admin Panel.
    *   Log in and start messaging!
