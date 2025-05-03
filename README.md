# Ansible Monitoring Stack

This project automates the setup of a monitoring stack using **Ansible**. It installs and configures:

- **Prometheus** – For metrics collection
- **Grafana** – For dashboards and visualization
- **Node Exporter** – For system-level metrics
- **Alertmanager** – For alerts and notifications

---

## 📁 Folder Structure

```
monitoring_setup/
├── inventory               # List of target servers
├── site.yml                # Main playbook
└── roles/                  # Ansible roles
    ├── prometheus/
    ├── grafana/
    ├── node_exporter/
    └── alertmanager/
```

---

## ✅ Requirements

- Linux servers (Ubuntu 22.04 or 24.04 recommended)
- SSH access to target machines
- Sudo privileges on target servers
- Ansible installed on your local or control machine

---

## ⚙️ How to Use

1. **Edit the Inventory File**

Update `inventory` with your target servers, like:

```
[monitoring]
server1 ansible_host=192.168.1.10
server2 ansible_host=192.168.1.11
```

2. **Run the Playbook**

Use this command to start the installation:

```bash
ansible-playbook -i inventory site.yml --ask-become-pass
```

3. **Change Component Versions**

Each role has a `defaults/main.yml` file where you can set the version, for example:

```yaml
prometheus_version: "2.52.0"
grafana_version: "11.0.0"
```

---

## 🔐 Pushing to GitHub

To push this project to a private GitHub repository:

```bash
git init
git remote add origin https://github.com/YOUR_USERNAME/your-private-repo.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

---

## 📄 License

This project is licensed under the MIT License.
