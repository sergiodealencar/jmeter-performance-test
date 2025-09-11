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
```

### 2. Open the Test Plan

Launch JMeter GUI

Go to File → Open

Select automation-practice-safe-test.jmx from the jmeter/ folder

### 3. Run the Test

Click the green Start button (▶️) in the JMeter toolbar

Monitor execution using the Summary Report or Aggregate Report

### 4. View Results

After execution, open the Summary Report to see:

Average response times

Min/Max times

Throughput

Error percentage

### 5. Export Results

Right-click on a Listener → Save Table Data → Export to CSV

Or use JMeter CLI (non-GUI mode, recommended for performance):

```
jmeter -n -t jmeter/automation-practice-safe-test.jmx -l reports/results.csv -e -o reports/html-report
```

This generates an HTML Dashboard Report inside reports/html-report/.
