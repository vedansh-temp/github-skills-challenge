# GitHub Challenge

<img src="https://octodex.github.com/images/Professortocat_v2.png" align="right" height="200px" />

Hey there!

Your challenge is ready.
Follow the instructions provided for this challenge and complete the required tasks in this repository.

Make sure your work is committed and pushed to your repository before submission.

Good luck!


---

&copy; 2025 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)


#############################  Part 1     ########################################

The service being monitored is anomaly detection,
using data like this------------record = {
        "timestamp": "2026-09-20T10:00:00",
        "service": "payment-service",
        "response_time_ms": 120,
        "cpu_percent": 42,
        "memory_percent": 51,
        "log_level": "INFO",
        "message": "Payment request processed successfully"
    }
    by checking the data provided.
  Furthermore, there are services for the Kafka producer and consumer.

  They are being tested in the test/ folder.


#############################  Part 2    ########################################

    In data/service_data.json,
    we have data such as, for example: {
    "timestamp": "2026-09-20T10:00:00",
    "service": "payment-service",
    "response_time_ms": 120,
    "cpu_percent": 42,
    "memory_percent": 51,
    "log_level": "INFO",
    "message": "Payment request processed successfully"
  }

  which shows that there are fields such as:
    timestamp - tells the time of the log
    service - indicates the type of service
    response time
    cpu_percent - indicates CPU usage as a percentage
    memory percent - indicates memory usage as a percentage
    log level
    message - relates to the log

    Also, response time values greater than 600 give the log level "INFO".


    #############################  Part 3    ########################################

    After running test_aiops_pipeline.py:
    "python -m pytest --cov=src --verbose"
=========================================================== test session starts ===========================================================
platform linux -- Python 3.13.15, pytest-8.4.1, pluggy-1.6.0 -- /usr/local/bin/python
cachedir: .pytest_cache
rootdir: /workspaces/github-skills-challenge
plugins: cov-7.1.0
collected 8 items                                                                                                                         

tests/calculations_test.py::test_area_of_circle_positive_radius PASSED                                                              [ 12%]
tests/calculations_test.py::test_area_of_circle_zero_radius PASSED                                                                  [ 25%]
tests/calculations_test.py::test_get_nth_fibonacci_zero PASSED                                                                      [ 37%]
tests/calculations_test.py::test_get_nth_fibonacci_one PASSED                                                                       [ 50%]
tests/test_aiops_pipeline.py::test_normal_record_is_not_anomaly PASSED                                                              [ 62%]
tests/test_aiops_pipeline.py::test_anomalous_record_is_detected PASSED                                                              [ 75%]
tests/test_aiops_pipeline.py::test_producer_publishes_event PASSED                                                                  [ 87%]
tests/test_aiops_pipeline.py::test_consumer_receives_event PASSED                                                                   [100%]

============================================================= tests coverage ==============================================================
____________________________________________ coverage: platform linux, python 3.13.15-final-0 _____________________________________________

Name                      Stmts   Miss  Cover
---------------------------------------------
src/aiops_pipeline.py        37     29    22%
src/anomaly_detector.py      18      3    83%
src/calculations.py          16      6    62%
src/event_consumer.py         6      0   100%
src/event_producer.py         9      1    89%
src/event_topic.py           10      1    90%
---------------------------------------------
TOTAL                        96     40    58%
============================================================ 8 passed in 0.47s


Total anomalies detected: 18 in anomaly_detector.
<img width="1081" height="721" alt="Screenshot (45)" src="https://github.com/user-attachments/assets/bfb88afb-60ea-4b1e-baff-831c9aef6a8d" />



#####################################   Part 4 ######################################

After executing aiops_pipeline.py:
- Output:
python src/aiops_pipeline.py
==================================================
AIOps Pipeline Result
==================================================
Records processed: 10
Anomalies detected: 2
Events consumed: 0

Detected Events:

We can see that 2 anomalies were detected by the pipeline in the processed records.



######################   Part 4(task 6)  #######################

When we try to run the AIOps pipeline test, it does not run:
python tests/test_aiops_pipeline.py
Traceback (most recent call last):
  File "/workspaces/github-skills-challenge/tests/test_aiops_pipeline.py", line 3, in <module>
    from src.anomaly_detector import AnomalyDetector
ModuleNotFoundError: No module named 'src'

To rectify this, we change the path:
PYTHONPATH=.:src python -m pytest tests/test_aiops_pipeline.py --verbose

O/P
====================================== test session starts ======================================
platform linux -- Python 3.13.15, pytest-8.4.1, pluggy-1.6.0 -- /workspaces/github-skills-challenge/.venv/calculations/bin/python
cachedir: .pytest_cache
rootdir: /workspaces/github-skills-challenge
plugins: cov-7.1.0
collected 4 items                                                                               

tests/test_aiops_pipeline.py::test_normal_record_is_not_anomaly PASSED                    [ 25%]
tests/test_aiops_pipeline.py::test_anomalous_record_is_detected PASSED                    [ 50%]
tests/test_aiops_pipeline.py::test_producer_publishes_event PASSED                        [ 75%]
tests/test_aiops_pipeline.py::test_consumer_receives_event PASSED                         [100%]
