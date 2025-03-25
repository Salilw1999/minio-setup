# MinIO Setup using Docker Compose

This guide provides step-by-step instructions to set up MinIO using Docker Compose.

## Prerequisites
- Docker installed on your system
- Docker Compose installed

## Installation Steps

### Step 1: Clone the Repository
```bash
git clone https://github.com/Salilw1999/minio-setup.git
cd minio-setup
```

### Step 2: Create Necessary Folders
```bash
sudo mkdir -p /etc/default/minio
```

### Step 3: Configure MinIO Credentials
```bash
echo "MINIO_ROOT_USER=admin" | sudo tee /etc/default/minio
echo "MINIO_ROOT_PASSWORD=admin123" | sudo tee -a /etc/default/minio
```

### Step 4: Create an `.env` File for Environment Variables
Create a `.env` file in the project directory with the following content:
```
MINIO_ROOT_USER=admin
MINIO_ROOT_PASSWORD=admin123
```

### Step 5: Run the Docker Compose File
```bash
docker-compose up -d
```
This will start the MinIO container in detached mode.

### Step 6: Access MinIO Web Interface
Open your web browser and go to:
```
http://localhost:9090
```
Login using:
- **Username:** `admin`
- **Password:** `admin123`

## Stopping and Removing Containers
To stop and remove the MinIO container, run:
```bash
docker-compose down
```

## Troubleshooting
If you encounter issues, check the container logs:
```bash
docker logs minio_minio1_1
```
Ensure that the required directories exist before running the container.

---

Enjoy using MinIO! 🚀

