
# Task 3: Containerized Web Server Deployment & Analysis Using Docker

## 📌 Project Overview
A production-optimized, containerized NGINX instance deployed on Kali Linux using the lightweight Alpine Linux distribution layer. This environment implements strict process isolation alongside secure, read-only local storage volume bindings (`:ro`) to serve custom responsive landing assets dynamically while ensuring the complete structural integrity of the host workspace.

## 🛠️ Technical Stack
* **Host Operating System:** Kali Linux
* **Container Subsystem Engine:** Docker Engine (CE)
* **Web Server Image Stack:** NGINX Stable on Alpine (`nginx:alpine`)
* **Front-End Design Interface:** Custom Responsive HTML5/CSS3 Slate-Aesthetic Interface

---

## 📂 Project Structure & Local Architecture
The project workspace is organized using standard infrastructure-as-code conventions:
```text
~/docker-web-server/
├── html/
│   └── index.html   # Custom responsive landing interface
└── README.md        # Complete operational blueprints and code manifests

```

---

## 💻 Source Code Manifests

### 1. Web Asset Configuration (`html/index.html`)

The interface utilizes modern viewport scaling, responsive grid spacing, and an optimized dark-mode styling matrix for instant loading inside the Alpine layer:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Docker Web Server Task</title>
    <style>
        body { font-family: Arial, sans-serif; background: #0f172a; color: #e2e8f0; text-align: center; padding: 50px; }
        .card { background: #1e293b; padding: 30px; border-radius: 8px; display: inline-block; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); }
        h1 { color: #38bdf8; }
    </style>
</head>
<body>
    <div class="card">
        <h1>Task 3: Docker Web Server Successful</h1>
        <p>Containerized NGINX instance serving custom local assets.</p>
    </div>
</body>
</html>

```

### 2. Layout Asset Mechanics

* **Color Matrix:** Employs a modern tech-slate design palette featuring deep body tones (`#0f172a`), contrasting container blocks (`#1e293b`), text contrast enhancements (`#e2e8f0`), and target-selected highlights (`#38bdf8`).
* **Isolation Mapping:** Served directly out of the container's isolated path via the NGINX storage volume binding mapping root: `/usr/share/nginx/html`.

---

## 🚀 Deployment & Container Lifecycle Workflow

### Step 1: Subsystem Daemon Verification

Initialize and confirm the health of the background Docker engine daemon:

```bash
sudo systemctl start docker
sudo docker info

```

### Step 2: Runtime Infrastructure Execution

Deploy the container instance using detached background parameters (`-d`), explicit port-forward mappings (`-p`), naming definitions (`--name`), and host-to-container read-only directory linkages (`-v ... :ro`):

```bash
sudo docker run -d \
  -p 8080:80 \
  --name intern-web-server \
  -v "$(pwd)/html:/usr/share/nginx/html:ro" \
  nginx:alpine

```

### Step 3: Runtime Operations Verification

Confirm that the instance is up, running, and successfully mapping file system calls:

```bash
# Check runtime list matrix
sudo docker ps

# Validate header handshake returns 200 OK
curl -I http://localhost:8080

```

### Step 4: Inter-Container Environment Inspection (Alpine Access)

To verify files directly inside the Alpine micro-kernel environment:

```bash
sudo docker exec -it intern-web-server sh
# Inside container:
ls -la /usr/share/nginx/html
exit

```

---

## 📊 Telemetry & Performance Benchmarks

Resource allocation profiles are retrieved straight from the runtime engine via real-time data streaming hooks:

```bash
sudo docker stats intern-web-server --no-stream

```

### Recorded System Benchmarks

* **CPU Load Profile:** < 0.10% (Idle query state)
* **Active Memory Footprint:** ~2.5 MiB to 3.5 MiB (Optimized via the Alpine minimal layer)
* **Network Input/Output:** Validated healthy HTTP traffic exchanges over loopback interfaces.
EOF

git add README.md
git commit -m "docs: compile comprehensive technical specifications, code manifests, and telemetry records"
git push

```

```
