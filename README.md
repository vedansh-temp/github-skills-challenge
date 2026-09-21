# GitHub Challenge

<img src="https://octodex.github.com/images/Professortocat_v2.png" align="right" height="200px" />

Hey there!

Your challenge is ready.
Follow the instructions provided for this challenge and complete the required tasks in this repository.

Make sure your work is committed and pushed to your repository before submission.

Good luck!


---

&copy; 2025 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)


Part 1

The service that is being monitored is anomaly detection 
suing data like this------------record = {
        "timestamp": "2026-09-20T10:00:00",
        "service": "payment-service",
        "response_time_ms": 120,
        "cpu_percent": 42,
        "memory_percent": 51,
        "log_level": "INFO",
        "message": "Payment request processed successfully"
    }
    by checking these data provided
further there are services for kafka producer and consumer

and are being tested in test/ folder


Part 2

    in the data/service_data.json
    we have data such as eg:- {
    "timestamp": "2026-09-20T10:00:00",
    "service": "payment-service",
    "response_time_ms": 120,
    "cpu_percent": 42,
    "memory_percent": 51,
    "log_level": "INFO",
    "message": "Payment request processed successfully"
  }

  which tells there are fields such as
    timestamps - tell the time of the log
    service - type of service
    response time
    cpu_percent - tell cpu usage in percent
    memory percent - tells memory used in percent
    log level
    message - related to the log

    also the values of response time being greater than 600 gives log level as "INFO"