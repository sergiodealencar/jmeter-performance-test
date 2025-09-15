# E-commerce Performance Testing with JMeter

## Project Objective

This project was created to evaluate the performance, scalability, and reliability of an e-commerce web application under different user behaviors. Using **Apache JMeter**, we designed test scenarios that simulate browsing, searching, and purchasing flows, as well as the loading of static resources.

## Tools

* **Apache JMeter** (load testing and performance monitoring)
* **Java** (runtime requirement for JMeter)
* **CSV Data Config** (parameterization of test data)
* **Listeners** (to collect and visualize metrics)

## Test Scenario (User Flow)

The JMeter test plan (`ecommerce.jmx`) contains multiple thread groups representing different user profiles:

1. **Usuário Navegador (Browsing User)** – Navigates through the homepage and product pages.
2. **Usuário Buscador (Searching User)** – Uses the search functionality to look up products.
3. **Usuário Comprador (Purchasing User)** – Completes the purchase process (search, add to cart, checkout).
4. **Arquivos Estáticos** – Requests static resources (CSS, JS, images) to simulate real-world page rendering.
5. **Minhas Gravações** – A set of recorded actions simulating a typical user journey.

## Metrics Collected

* **Response Time (ms)** – How long requests take to complete.
* **Throughput (requests/second)** – Number of requests processed per unit of time.
* **Error Rate (%)** – Percentage of failed requests.
* **Latency (ms)** – Time taken before receiving the first response.
* **Concurrent Users** – Simulated load across different thread groups.

## Reports & Analysis

JMeter listeners and reports provide:

* **Aggregate Report** – Summary of response times, throughput, and error percentages.
* **Response Time Graphs** – Visualizing how response time changes under load.
* **Transaction Controller Results** – Measuring end-to-end user flows.
* **HTML Dashboard Report** – Comprehensive test execution report.

### Sample Visuals

[Aggregate Report](https://github.com/sergiodealencar/jmeter-performance-test/blob/main/reports/Aggregate_Report.png)

[Response Time Graph](https://github.com/sergiodealencar/jmeter-performance-test/blob/main/reports/Response_Time_Graph.png)

[HTML Dashboard](reports/sample-html-dashboard.png)

## Repository Structure

```
📂 jmeter-performance-test
 ┣ 📂 reports              # Test execution reports (HTML, PNG screenshots)
 ┣ 📂 results              # JTL result files generated after execution
 ┣ 📄 ecommerce.jmx        # JMeter test plan
 ┣ 📄 README.md            # Project documentation
```

## How to Run the Test

1. **Install JMeter**

   * Download from [https://jmeter.apache.org](https://jmeter.apache.org)
   * Ensure Java is installed and configured.

2. **Clone this Repository**

   ```bash
   git clone https://github.com/sergiodealencar/jmeter-performance-test.git
   cd jmeter-performance-test
   ```

3. **Open the Test Plan in JMeter**

   ```bash
   jmeter -t ecommerce.jmx
   ```

4. **Run in GUI Mode (for debugging/visualization)**

   * Launch JMeter GUI
   * Open `ecommerce.jmx`
   * Run the test and observe listeners

5. **Run in Non-GUI Mode (for performance/load testing)**

   ```bash
   jmeter -n -t ecommerce.jmx -l results/test-results.jtl -e -o reports/test-report
   ```

6. **View the Report**

   * Open `reports/test-report/index.html` in your browser

---

This project demonstrates **load testing best practices** for an e-commerce platform, focusing on **realistic user flows**, **visual reporting**, and **comprehensive performance metrics**.
