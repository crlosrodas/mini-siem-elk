# 🛡️ Mini-SIEM with ELK Stack & Docker

A beginner-friendly Security Information and Event Management (SIEM) system using Elasticsearch, Logstash, Kibana, and Docker. Perfect for learning cybersecurity monitoring and containerization!

--- 

## This project sets up a **mini-SIEM** that:
- ✅ Collects and processes security logs
- ✅ Stores events in Elasticsearch
- ✅ Provides real-time visualization in Kibana
- ✅ Runs in isolated Docker containers
- ✅ Generates sample security events for testing

  ---

### Prerequesites:

- Have a code editor installed such as VS Code
- Have Docker installed

--- 

## 📁 Step One: Create Folder Structure

<img width="344" height="388" alt="Screenshot 2025-10-04 185726" src="https://github.com/user-attachments/assets/99a711ea-214f-4f24-beb5-ac6fefe5627f" />

--

**Should look like this:**

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

---

## Step Two: Create necessary files

Open VS Code and create the following files:



<img width="704" height="369" alt="Screenshot 2025-10-04 185850" src="https://github.com/user-attachments/assets/aa763d5e-c332-4bf7-9ddf-5a2ab247e217" />
<img width="625" height="126" alt="Screenshot 2025-10-04 190006" src="https://github.com/user-attachments/assets/bfc123d3-221b-45fb-b4a9-17226cdbf6ec" />

<img width="800" height="979" alt="Screenshot 2025-10-04 202318" src="https://github.com/user-attachments/assets/4ca9be4e-b5ac-482d-ab3d-31aa362b015c" />
<img width="551" height="844" alt="Screenshot 2025-10-04 190358" src="https://github.com/user-attachments/assets/a53c5b58-7bd1-453e-954d-ff722c17b16e" />
<img width="418" height="317" alt="Screenshot 2025-10-04 202715" src="https://github.com/user-attachments/assets/636e13a7-3315-4679-bbbe-5bc9dc3b4f09" />

---

## ▶️ Step Three: Starting up the stack

<img width="519" height="161" alt="Screenshot 2025-10-04 190505" src="https://github.com/user-attachments/assets/694f2102-c7f0-4878-b018-3caa692e79ce" />

--

**Should see these results:** 

<img width="1085" height="134" alt="Screenshot 2025-10-04 190643" src="https://github.com/user-attachments/assets/efbae512-cf23-4e2f-8af3-7687bd870ed7" />

---

## 🛠️ Step Four: Accessing our mini-siem

To access the siem, we need to open the following on our browser.

* **Elasticsearch** → [http://localhost:9200](http://localhost:9200)
* **Kibana** → [http://localhost:5601](http://localhost:5601)

Logs should be flowing by now.

To view logstash output: 

<img width="280" height="48" alt="image" src="https://github.com/user-attachments/assets/8633f1d1-bd87-4617-b242-8e5333031fc9" />

-- 

To check Elasticsearch indices:

<img width="365" height="45" alt="image" src="https://github.com/user-attachments/assets/7e9dbf0b-9632-445c-b5c8-bdfc75a21850" />

---

## 📊 Step Five: Creating Index-pattern

Navigate to **Stack Management** -> **Data Views** -> **Create Data View** 

- Under **Index Pattern** put "siem-logs-*"
- Under **Timestamp Field** select "@timestamp"
- Click **Save data view to Kibana*

--

Then navigate to **Analytics** -> **Discover**

You should see security events now!

<img width="1913" height="934" alt="Screenshot 2025-10-04 193911" src="https://github.com/user-attachments/assets/4cee65ef-e4fe-4bd3-9183-bb7086999716" />

---

### To shutdown the stack
Run the following command:

```bash
docker-compose down
```
-- 

### To stop and remove data (a clean reset)
Run the following command:

```bash
docker-compose down -v
```
---

## 🎓 Learning Outcomes:

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

## 🙋‍♂️ Author

**Carlos Rodas-Zamora**
GitHub: [@crlosrodas](https://github.com/crlosrodas)
Project: **Mini-SIEM ELK**

--

Thanks :)
