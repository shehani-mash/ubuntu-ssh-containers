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
- 🗃️ Ubuntu Virtual machine

## 📋 Prerequisites
- Docker is installed on your system
- Basic knowledge of Linux commands
- Internet connection (to pull Docker images)

## 🧰 Installation Steps

### 1️⃣ Pull Ubuntu Image

### 2️⃣ Create and Configure Containers

### 3️⃣ Configure SSH Server (Container 1)

### 4️⃣ Configure SSH Client (Container 2)


## 🔒 Security Considerations
- Change the default root password
- Consider using SSH key authentication instead of passwords

## 🚨 Troubleshooting
- **Connection refused**: Ensure SSH service is running on server (`service ssh status`)
- **Password not accepted**: Verify password set correctly with `passwd`
- **IP address changed**: Docker may assign new IPs - check with `ifconfig`

