# 📝 README: Secure SSH Connection Between Two Ubuntu Containers

## 🌟 Project Overview
This project demonstrates how to establish a secure SSH connection between two Ubuntu containers in Docker, ensuring:
- ✅ **Confidentiality** of shared data
- ✅ **Integrity** of communications
- ✅ **Secure** data transmission

## 🚀 Why This Project?
Docker containers provide:
- ✅ Easy management
- ✅ Better collaboration
- ✅ Scalability
- ✅ Portability

## 🛠️ Tools Used
- 🐳 Docker
- 🖥️ Ubuntu (official Docker image)
- 🔒 OpenSSH (server & client)
- ✏️ VS Code (or any text editor)

## 📋 Prerequisites
- Docker installed on your system
- Basic knowledge of Linux commands
- Internet connection (to pull Docker images)

## 🧰 Installation Steps

### 1️⃣ Pull Ubuntu Image
```bash
docker pull ubuntu:latest
```

### 2️⃣ Create and Configure Containers

#### Create both containers (run in separate terminals):
```bash
# Container 1 (SSH Server)
docker run -it --name ssh_server ubuntu:latest

# Container 2 (SSH Client)
docker run -it --name ssh_client ubuntu:latest
```

#### In both containers, first run:
```bash
apt update && apt upgrade -y
apt install -y openssh-server openssh-client net-tools vim
```

### 3️⃣ Configure SSH Server (Container 1)

Inside the SSH Server container:
```bash
# Start SSH service
service ssh start

# Set root password (for SSH login)
passwd
[Enter your secure password twice]

# Get container IP address
ifconfig
[Note the IP address, typically 172.17.0.x]
```

### 4️⃣ Configure SSH Client (Container 2)

Inside the SSH Client container:
```bash
# Test connection to server (use IP from server container)
ping 172.17.0.x
[Should see successful pings]

# Connect via SSH
ssh root@172.17.0.x
[Enter password when prompted]
```

## 🔒 Security Considerations
- Change the default root password
- Consider using SSH key authentication instead of passwords
- Keep containers updated with security patches

## 🚨 Troubleshooting
- **Connection refused**: Ensure SSH service is running on server (`service ssh status`)
- **Password not accepted**: Verify password set correctly with `passwd`
- **IP address changed**: Docker may assign new IPs - check with `ifconfig`

## 📂 Project Structure
```
secure-ssh-docker/
├── README.md          # This file
├── server-setup.sh    # Optional: Automated server setup script
└── client-setup.sh    # Optional: Automated client setup script
```

## 🤝 Contribution
Contributions are welcome! Please fork the repository and submit a pull request.

## 📜 License
This project is open-source and available under the MIT License.

---

💡 **Pro Tip**: For production environments, consider using SSH key authentication and non-root users for better security!
