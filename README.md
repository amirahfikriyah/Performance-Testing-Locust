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

# Raw Data Presentation
## Load Test Results
![Load Test Statistics](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/load%20test%20statistic.png)
![Load Test Chart](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/load%20test%20chart.png)

## Soak Test Results
![Soak Test Statistics](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/soak%20test%20statistic.png)
![Soak Test Chart](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/soak%20test%20chart.png)

## Stress Test Results
![Stress Test Statistics](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/stress%20test%20statistic.png)
![Stress Test Chart](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/stress%20test%20chart.png)

# Summary of Test Results
1️⃣ Load Test Summary

The load test processed 16,911 requests at a constant throughput of 43–44 RPS with zero failures throughout the run. Response times were very consistent, usually around 250 ms, with only occasional spikes. This suggests the API is resilient to moderate loads.

2️⃣ Stress Test Summary

During the testing phase, there were a total of 173,355 connections generated from the test session and at least 280 to 290 RPS being handled as a maximum throughput. However, 1,035 connections were unable to connect due to connection errors or timeouts and the response time per connection increased exponentially to above 105 seconds. The above results illustrate that the system cannot handle extreme amounts of concurrent connections without degradation in performance.

3️⃣ Soak Test Summary

At the completion of the 44-minute soak test, the system successfully handled a total of 119,804 requests with no failed requests, providing a consistent response time of approximately 253 milliseconds and producing steady throughput between 45 and 47 requests per second. Additionally, there was no evidence of memory leaks or prolonged periods of instability, thus demonstrating that the system can sustain itself under heavy and sustained workloads.

# Analysis of Collected Metrics
Clear patterns of behavior emerged for the API across the three tests. The Load and Soak tests revealed stable response times, consistent throughput, and no failures, indicating that the API is efficient in handling moderate and sustained traffic. Conversely, the Stress Test showed distinct performance degradation under extreme concurrency, as evidenced by increasing latency, loss of responsiveness, and increased error rates. Response-time percentiles and RPS charts all confirm that the API continues to be reliable until the system limits are approached. While utilization of the backend CPU and memory was not measured directly, the stability during the soak test would indicate that resources were within healthy ranges during prolonged activity.

# Identified Bottlenecks
During the stress testing process, the stress test results showed bottlenecks when there were phases in which the connection had 'time-outs', and extreme latencies were experienced, indicating that the solution had become fully saturated. Testing indicated that once the users reached 500, the API began to have issues maintaining its expected response times, causing delays to exceed 100 seconds. Soak testing demonstrated stable performance, however, minor fluctuations in testing were evident, indicating the backend would experience degradation in its ability to process under sudden workloads. The system performs okay under moderate workloads, but severe concurrency cannot be managed without impact.

# Recommendations for Improvement
Currently, the main recommendation to improve the system's performance consists of several best practices:


-Establish an auto-scaling solution that can automatically allocate additional resources when the system is under heavy load.


-Utilize load balancing techniques to more evenly distribute incoming requests.


-Improve backend transactions by optimizing database queries, using caching techniques, etc.


-Implement connection Timeout handling enhancements to allow for the resilience of connections during periods of stress.


-Utilize performance monitoring tools (like Grafana, Prometheus, APM, etc.) to analyze performance in-depth.


-Add additional future test scenarios, including multi-endpoint testing and authenticated workflow testing.

# Conclusion
Overall, the outcomes of this project demonstrate the performance capacity of the API under a variety of loads while clearly identifying the difference between a stable operational state and an overloaded or stressed system state. The API is heavily optimised to operate at a high level for both moderate and prolonged periods of load, showing consistent performance across the Load and Soak testing phases. However, the maximum operating threshold on the API is reached when subjected to extremely high levels of concurrency (as seen in the Stress Test). These results demonstrate just how critical it is to conduct performance testing to understand what a system is capable of so that any bottlenecks that exist within the system can be found and corrected prior to further optimisation of the API.

## Project Documentation
- 📄 [Final Report (PDF)](https://github.com/amirahfikriyah/Performance-Testing-Locust/blob/main/Network%20Programming%20Individual%20Assignment_Nur%20Amirah%20Fikriyah.pdf)
- 
