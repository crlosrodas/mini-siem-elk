# 🛡️ Mini-SIEM with ELK Stack & Docker

A beginner-friendly Security Information and Event Management (SIEM) system using Elasticsearch, Logstash, Kibana, and Docker. Perfect for learning cybersecurity monitoring and containerization!

---

## 🎯 What is This Project?

This project sets up a **mini-SIEM** that:
- ✅ Collects and processes security logs
- ✅ Stores events in Elasticsearch
- ✅ Provides real-time visualization in Kibana
- ✅ Runs in isolated Docker containers
- ✅ Generates sample security events for testing

---

## 🚀 Quick Start

### ▶️ Start the ELK Stack
```bash
docker-compose up -d
````

### 🌐 Access the Applications

* **Kibana Dashboard** → [http://localhost:5601](http://localhost:5601)
* **Elasticsearch API** → [http://localhost:9200](http://localhost:9200)

### 📂 View Sample Security Events

1. Open **Kibana → Discover**
2. Select **siem-logs-*** index pattern
3. Watch real-time security events populate!

### 🛠️ First-Time Kibana Setup

* Wait **1–2 minutes** for services to start
* Go to **Stack Management → Index Patterns**
* Create index pattern: `siem-logs-*`
* Set **Time field**: `@timestamp`

---

## 🏗️ Project Architecture

```
Log Sources → Logstash → Elasticsearch → Kibana
    ↓            ↓           ↓            ↓
  System     Processing   Storage    Visualization
  Logs       Pipeline     Engine     Dashboard
```

### 🔧 Components

* **Elasticsearch** → NoSQL database for log storage and search
* **Logstash** → Data processing pipeline for log ingestion
* **Kibana** → Web interface for visualization and analysis
* **Docker** → Containerization platform for easy deployment

---

## 📊 Features

### 🔒 Security Monitoring

* Real-time log collection and analysis
* Sample security event generation
* Custom log parsing and enrichment
* Time-series data visualization

### 🐳 Docker Benefits

* Isolated container environments
* Easy setup and teardown
* Consistent dev/prod environments
* Version-controlled infrastructure

### 📈 Visualization

* Kibana **Discover** for log exploration
* Customizable dashboards
* Real-time monitoring
* Index pattern management

---

## 🛠️ Technical Details

### 📁 File Structure

```
mini-siem-elk/
├── docker-compose.yml          # Container orchestration
├── elasticsearch/config/       # ES configuration
├── logstash/
│   ├── config/                 # Logstash settings
│   └── pipelines/              # Data processing pipelines
├── kibana/config/              # Kibana settings
├── data/                       # Persistent data volumes
└── README.md                   # This file
```

### 🔌 Services & Ports

* **Elasticsearch** → [http://localhost:9200](http://localhost:9200)
* **Kibana** → [http://localhost:5601](http://localhost:5601)
* **Logstash** → 5044 (Beats), 5000 (TCP)

---

## 🎓 Learning Outcomes

After completing this project, you’ll understand:

### 🐳 Docker & Containerization

* Docker Compose orchestration
* Container networking
* Volume management
* Multi-service applications

### 📦 ELK Stack

* Elasticsearch indices and mappings
* Logstash pipelines (input/filter/output)
* Kibana visualization and dashboards
* Log analysis and monitoring

### 🔐 Security Engineering

* SIEM fundamentals
* Log collection and normalization
* Security event correlation
* Real-time monitoring concepts

---

## 🚨 Sample Security Events

This project includes a **Logstash generator** that creates events every 30 seconds:

* Failed login attempts
* Firewall blocks
* Port scan detections
* Access denied events

---

## 🛑 Management Commands

### ▶️ Start Services

```bash
docker-compose up -d
```

### ⏹️ Stop Services

```bash
docker-compose down
```

### 📜 View Logs

```bash
docker-compose logs -f
```

### 🔎 Check Service Status

```bash
docker-compose ps
```

---

## ❗ Troubleshooting

* **"Port already in use" error**
  Stop other services using ports **5601, 9200, or 5044**, or update `docker-compose.yml`.

* **"Cannot connect to Kibana"**
  Wait **2–3 minutes** for all services to initialize.

* **"No data in Kibana"**
  Check if Logstash is running:

  ```bash
  docker logs logstash
  ```

  Verify index pattern: *Stack Management → Index Patterns → siem-logs-*

* **Memory issues**
  Ensure Docker has at least **8GB RAM** allocated and close other heavy applications.

---

## 🤝 Contributing

Feel free to fork this project and submit pull requests for any improvements!

---

## 📝 License

This project is licensed under the **MIT License** – see the LICENSE file for details.

---

## 🙋‍♂️ Author

**CRZ**
GitHub: [@crlosrodas](https://github.com/crlosrodas)
Project: **Mini-SIEM ELK**

⭐ If you found this project helpful, please give it a **star**! ⭐