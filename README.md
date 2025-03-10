# 🚀 osTicket Help Desk Deployment (Ubuntu & LAMP Stack)

## 📌 Overview
This project details the **installation and configuration of osTicket**, an open-source help desk ticketing system, on an **Ubuntu Server** using the **LAMP (Linux, Apache, MySQL, PHP) stack**.

## 🔧 Key Features
- **LAMP Stack Deployment**: Installed **Apache, MySQL, and PHP**.
- **osTicket Setup**: Deployed **osTicket**, created a MySQL database, and configured web access.
- **User Support System**: Configured **ticket submission, admin panel, and workflows**.
- **Security & Performance**: Set proper **file permissions, MySQL optimizations, and Apache configurations**.

## 📜 Technologies Used
- **Ubuntu Server 22.04**
- **Apache Web Server**
- **MySQL Database**
- **PHP (LAMP Stack)**
- **osTicket**

## 🏗️ Installation & Setup
### **1️⃣ Update System & Install LAMP Stack**
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql php-mbstring php-xml php-bcmath php-imap php-gd php-intl php-cli php-common php-zip unzip -y
```
### **2️⃣ Download and Configure osTicket**
```bash
cd /var/www/html
sudo wget https://github.com/osTicket/osTicket/releases/download/v1.17.2/osTicket-v1.17.2.zip
sudo unzip osTicket-v1.17.2.zip -d osticket
sudo chown -R www-data:www-data /var/www/html/osticket
sudo chmod -R 755 /var/www/html/osticket
```
### **3️⃣ Configure Apache for osTicket**
```bash
sudo nano /etc/apache2/sites-available/osticket.conf
```
Add the following:
```apache
<VirtualHost *:80>
    ServerAdmin admin@example.com
    DocumentRoot /var/www/html/osticket
    ServerName localhost
    <Directory /var/www/html/osticket>
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```
Then, enable the site and restart Apache:
```bash
sudo a2ensite osticket.conf
sudo systemctl restart apache2
```
### **4️⃣ Set Up MySQL Database for osTicket**
```sql
CREATE DATABASE osticket;
CREATE USER 'osticket_user'@'localhost' IDENTIFIED BY 'StrongPassword123!';
GRANT ALL PRIVILEGES ON osticket.* TO 'osticket_user'@'localhost';
FLUSH PRIVILEGES;
```
### **5️⃣ Complete osTicket Web Installation & Remove Setup Files**
```bash
sudo rm -rf /var/www/html/osticket/setup/
```

## 📸 Program Walkthrough
Below are screenshots documenting the osTicket installation and configuration process.

### **1️⃣**
![Screenshot 1](https://github.com/user-attachments/assets/321e0d58-91b1-4d56-820f-5e05c1c087bb)

### **2️⃣**
![Screenshot 2](https://github.com/user-attachments/assets/0010ed51-62b5-480b-80ce-003f5edf8085)

### **3️⃣**
![Screenshot 3](https://github.com/user-attachments/assets/bedec13e-e14a-44d5-9472-c1c50ab7b05c)

### **4️⃣**
![Screenshot 4](https://github.com/user-attachments/assets/800ba545-5436-4b44-9a24-1b08bb77cae2)

### **5️⃣**
![Screenshot 5](https://github.com/user-attachments/assets/69ce4892-158b-4b34-9f6c-0730a804c611)

### **6️⃣**
![Screenshot 6](https://github.com/user-attachments/assets/9429bc49-60d1-4c39-a7f8-64e5c5a2477c)

### **7️⃣**
![Screenshot 7](https://github.com/user-attachments/assets/8d849e80-6f65-4a0d-b261-447455c46739)

### **8️⃣**
![Screenshot 8](https://github.com/user-attachments/assets/8fc309c9-ac90-4c4d-b4c7-06ccdbcb852d)

### **9️⃣**
![Screenshot 9](https://github.com/user-attachments/assets/bcc138cc-5f51-437e-b83c-728801b69e3a)

### **🔟**
![Screenshot 10](https://github.com/user-attachments/assets/219f6d46-b0fa-4b3a-8bd5-2ff57fbd3cbe)

### **1️⃣1️⃣**
![Screenshot 11](https://github.com/user-attachments/assets/6fa79fc3-4327-4a69-ba34-2650c82ba106)

### **1️⃣2️⃣**
![Screenshot 12](https://github.com/user-attachments/assets/fac1d303-632b-4eca-bcbe-f7c405277539)

### **1️⃣3️⃣**
![Screenshot 13](https://github.com/user-attachments/assets/35ca6b94-9592-4c82-8f24-9c830e3ab917)

### **1️⃣4️⃣**
![Screenshot 14](https://github.com/user-attachments/assets/ac872ede-b242-45c1-b5f8-753deed07e8d)

### **1️⃣5️⃣**
![Screenshot 15](https://github.com/user-attachments/assets/7275f491-5e05-4184-b09b-39f507c670d1)

### **1️⃣6️⃣**
![Screenshot 16](https://github.com/user-attachments/assets/2b6805f2-d54a-4542-a7ef-cd84e2a2da5f)

### **1️⃣7️⃣**
![Screenshot 17](https://github.com/user-attachments/assets/83c34af8-d01b-430f-9be9-24f7459e2fc6)

### **1️⃣8️⃣**
![Screenshot 18](https://github.com/user-attachments/assets/1746db7b-bb58-4183-966b-1d015e097cc7)

### **1️⃣9️⃣**
![Screenshot 19](https://github.com/user-attachments/assets/30a1e703-2e81-4641-b687-20f341ac4141)

### **2️⃣0️⃣**
![Screenshot 20](https://github.com/user-attachments/assets/8a25abd8-ed3c-40c5-9fd6-c6094e0ae063)

## 📩 Contact & More
If you have any questions or want to collaborate, feel free to reach out!
