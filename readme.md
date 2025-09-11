# 🚀 Performance Testing Project – Automation Practice (Safe Portfolio Version)

## 📌 Project Objective
This project demonstrates the use of **Apache JMeter** to design, execute, and analyze performance tests on the [Automation Practice](http://www.automationpractice.pl/index.php) demo e-commerce site.  

---

## 🛠 Tools
- [Apache JMeter 5.6.3](https://jmeter.apache.org/)  
- Git & GitHub for version control and documentation  

---

## 🔍 Test Scenario (User Flow)
Simulated actions for a virtual user:
1. Open the **Home Page**  
2. Navigate to a **Product Category**  
3. Open a **Product Page**  
4. Add a product to the **Cart**  

---

## ⚙️ JMeter Test Plan
### Thread Group
- **Load Test**:  
  - Users: **5**  
  - Ramp-up: **60 seconds**  
  - Loop Count: **2**

### Samplers
- `1 - Home Page` → GET `/index.php`  
- `2 - Category Page` → GET `/index.php?id_category=3`  
- `3 - Product Page` → GET `/index.php?id_product=5`  
- `4 - Add to Cart` → POST `/index.php?controller=cart`  

### Assertions
- Verify **HTTP 200 OK**  
- Check for expected text (e.g., “Cart”) after adding an item  

### Listeners
- **Summary Report**  
- **Aggregate Report**  
- **Graph Results**  
- **View Results Tree** (debugging only)  

---

## 📊 Metrics Collected
- Response times (average, min, max)  
- Throughput (requests per second)  
- Error percentage  
- Observed responsiveness under light load  

---

## 📑 Reports & Analysis
- Results exported to **CSV** and **HTML Dashboard Reports**  
- Example report included in the repo under `reports/`  
  - [Sample CSV Results](reports/results.csv)  
  - [Sample HTML Dashboard](reports/html-report/index.html)  

---

## 📂 Repository Structure

```
automation-practice-load-testing/
│
├── README.md                  # Project overview and instructions
├── jmeter/                    # JMeter test plans
│   └── automation-practice-safe-test.jmx
├── reports/                   # Example results (CSV, HTML, screenshots)
└── LICENSE
```


---

## ▶️ How to Run the Test

### 1. Install JMeter
Download and extract [Apache JMeter 5.6.3](https://jmeter.apache.org/download_jmeter.cgi).  
Make sure you can run it from terminal:  
```bash
jmeter

