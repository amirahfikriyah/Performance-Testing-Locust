# Performance-Testing-Locust
# Introduction
This project is aimed at performance testing a publicly available API for three important performance testing techniques, namely Load Test, Stress Test, and Soak Test, using a testing tool known as Locust. The goal is to measure how well the API at https://test-api.k6.io/.
It responds to variations in user load, sustained traffic, and system pressure. Key performance metrics analyzed in this project include response time, throughput, and error rate, which provide insight into the system's scalability, stability, and overall reliability. The outcomes will serve as the basis for identifying performance bottlenecks and recommendations on improvements.
# Test Environment and & Target Application 
Tests were conducted locally using Locust in combination with Python, on a machine with a stable internet connection that ensured the same conditions during entire test execution. The application being tested was the test API, hosted at https://test-api.k6.io/, which is specifically designed as a test API so that load testing can be performed on it in a safe, ethical and legal manner. Production websites typically block automated traffic, while this API allows benchmarking to be performed on it and realistically evaluates the performance of several different endpoints.
# Tool Selection Justification
Locust was chosen for this project because of its flexible Python-based scripting, real-time monitoring dashboard, and support for distributed load generation. It simplifies the process of defining user behavior and allows for clear visualization of performance metrics such as requests per second, response time percentiles, and error rates. Compared to traditional tools like JMeter, Locust provides a lightweight and efficient workflow suitable for both simple and complex load scenarios.
# Hypothesis
The hypothesis made by the creator of the test API was that it would work consistently under average usage with regard to the Load and Soak Tests. However, at high levels of usage (Stress Testing), it was believed that the system would experience some degradation through increased response time, lower throughput, or dropped connections. Overall, the assessment by the developer was that the system would perform adequately at normal operational levels as well as at sustained operational levels; however, performance would clearly decline after exceeding the systems operational limits.
# Test Methodology
1️⃣ Load Test

Purpose: Evaluate system behavior under typical and peak expected user load.
Users: 100
Duration: 6 minutes
Outcome: Measures response stability and error rates under moderate pressure.

2️⃣ Stress Test

Purpose: Identify system breaking points by applying extreme load.
Users: 500
Duration: 10 minutes
Outcome: Reveals maximum throughput and failure thresholds.

3️⃣ Soak Test

Purpose: Assess long-term stability and resource behavior.
Users: 150
Duration: 44 minutes
Outcome: Detects memory leaks, degradation, and prolonged response-time patterns.

## Project Documentation
- 📄 [Final Report (PDF)](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/Network%20Programming%20Individual%20Assignment_Nur%20Amirah%20Fikriyah.pdf)
- 
