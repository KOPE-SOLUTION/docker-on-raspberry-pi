# Docker Installation on Raspberry Pi

This guide provides step-by-step instructions to install and configure Docker on a Raspberry Pi.

## **Prerequisites**
Ensure your Raspberry Pi is running the latest version of Raspberry Pi OS.

## **Installation Steps**

### **1. Update and Upgrade the System**
```bash
sudo apt-get update && sudo apt-get upgrade -y
```

### **2. Install Required Dependencies**
```bash
sudo apt install -y curl
```

### **3. Install Docker**
```bash
curl -fsSL https://get.docker.com | sudo sh
```

### **4. Add User to Docker Group (Optional)**
If you want to run Docker without `sudo`, add your user to the Docker group:
```bash
sudo usermod -aG docker $USER
```
Log out and log back in to apply the changes.

### **5. Install Rootless Mode (Optional)**
If you want to run Docker in **rootless mode**, install `uidmap`:
```bash
sudo apt-get install -y uidmap
```
Verify installation:
```bash
dpkg -l | grep uidmap
```
Then, install Docker in rootless mode:
```bash
dockerd-rootless-setuptool.sh install
```

### **6. Verify Docker Installation**
Check the installed Docker version:
```bash
docker --version
```
Enable and start the Docker service:
```bash
sudo systemctl enable docker
sudo systemctl start docker
```
Run a test container:
```bash
docker run hello-world
```

### **7. Install Docker Compose (Optional)**
To install **Docker Compose**, run:
```bash
sudo apt install -y docker-compose
```
Verify the installation:
```bash
docker-compose --version
```

## **Conclusion**
Your Raspberry Pi is now set up with Docker! You can start using Docker to deploy and manage containers.

For more details, visit the [Docker Documentation](https://docs.docker.com/).

---

### **Author**
**KOPE SOLUTION**
