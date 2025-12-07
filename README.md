<h1 align="center">🚀 Ansible Project — Deploy Static Web Page on Apache2</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Ansible-Automation-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Apache2-Web%20Server-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Linux-Ubuntu-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/HTML-Static%20Site-green?style=for-the-badge" />
</p>

---

## 📘 Project Overview

This project demonstrates how to automate the deployment of a **static HTML webpage** using **Ansible** on an **Apache2 web server**.

With just one playbook, you can:

- Install Apache2  
- Start & enable the service  
- Copy and deploy your custom `index.html` page  
- Automate the full static site setup  

---

## 📁 Project Structure

```

📦 ansible-web-deploy
┣ 📜 index.html
┣ 📜 deploy_web.yml
┗ 📜 README.md

````

---

## 🧩 Ansible Playbook Used

```yaml
---
- name: installing a web server apache2 and also copy a custom web page file that is index.html.
  hosts: devwebservers
  become: true

  tasks:
    - name: install web server
      apt:
        name: apache2
        state: present

    - name: start a service
      service:
        name: apache2
        state: restarted
        enabled: yes
      notify:
        - copy the custom index.html file to server

  handlers:
    - name: copy the custom index.html file to server
      copy:
        src: index.html
        dest: /var/www/html
````

---

## 🚀 How to Run This Project

### **1️⃣ Clone the repository**

```bash
git clone https://github.com/your-username/ansible-web-deploy.git
cd ansible-web-deploy
```

### **2️⃣ Configure your inventory**

Example:

```
[devwebservers]
192.168.1.10 ansible_user=ubuntu ansible_ssh_private_key_file=key.pem
```

### **3️⃣ Run the playbook**

```bash
ansible-playbook -i hosts deploy_web.yml
```

---

## 🌍 Output

Once deployment completes, open:

```
http://<server-ip>
```

You will see your deployed **static HTML webpage** 🎉

---

## 🛠 Tools Used

| Tool             | Purpose                               |
| ---------------- | ------------------------------------- |
| **Ansible**      | Automation & configuration management |
| **Apache2**      | Web server                            |
| **Ubuntu Linux** | Target server                         |
| **HTML**         | Static website content                |

---

## 🎯 Learning Outcomes

This project helps build confidence in:

* Infrastructure automation
* Using Ansible handlers
* Deploying web servers
* Managing files with Ansible
* Real-world DevOps workflow

---
## 📬 Connect With Me

**👤 Name:** Shaik Mohammad Shoaib
🔗 **LinkedIn:** *https://www.linkedin.com/in/mohammadshoaib8*
⭐ **GitHub:** *https://github.com/mohammadshoaib8*

---

<p align="center">
  ⭐ If you like this project, don’t forget to give it a STAR on GitHub!
</p>

