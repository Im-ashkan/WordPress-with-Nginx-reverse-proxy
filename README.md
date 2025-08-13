# WordPress-with-Nginx-reverse-proxy
Running WordPress with a Reverse proxy(Nginx) and a real domain name

🔧 **wp1.yml** – WordPress & Database Setup  
This Docker Compose file deploys a WordPress site along with a MariaDB database.

🧱 **Services Defined**:  
- **MariaDB Container**:  
  - Stores WordPress data.  
  - Configured with environment variables (e.g., root password, database name/user).  
  - Persists data using a volume.  
  
- **WordPress Container**:  
  - Depends on the MariaDB service.  
  - Connects to MariaDB using the provided credentials.  
  - Runs on port (host) mapped to (container) port.  
  - Stores site files via a volume.  

📦 **Volumes**:  
- **Database Volume**: Keeps database data across restarts.  
- **WordPress Volume**: Preserves WordPress content.

🧩 **Relationship to Nginx Proxy Manager**:  
The setup includes Nginx Proxy Manager, which can:  
- Reverse proxy traffic from your domain to the WordPress app running on the server.  
- Handle SSL certificates through Let's Encrypt.  
- Provide an easy-to-use interface for managing all of this.  

Together, these components create a basic self-hosted WordPress site with a user-friendly proxy management interface.

🌐 **Proxy Setup Notes**:  
Once WordPress is running, you can log into Nginx Proxy Manager via port 81 and:  
- Create a proxy host that points your domain (e.g., yourdomain.com) to your server's IP address on port 80.  
- Enable SSL using Let's Encrypt.
