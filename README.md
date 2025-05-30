# NATS Server on Railway

This repository deploys a simple `nats-server` instance using the official Docker image.

## 🚀 Deployment Instructions

1. Push this folder to a new GitHub repo (e.g., `nats-server`)
2. Create a new Railway project: "Deploy from GitHub Repo"
3. Railway will auto-detect the Dockerfile and deploy your NATS server
4. Copy the internal service domain from Railway's **Settings → Domains**
5. Use that in your `.env`:

```
NATS_EXTERNAL_PUBLISH_SERVER=nats://<your-nats-service>.up.railway.app:4222
```

This allows both `meshserver` and `dataserver` to communicate via this shared NATS broker.
