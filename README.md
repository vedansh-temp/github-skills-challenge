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


#############################  Part 2    ########################################

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


    #############################  Part 3    ########################################

    after running the test_aiops_pipeline.py
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


total anomaly detected 18 in anomaly_detector



#####################################   Part 4 ######################################

after executing the aiops_pipeline.py 
-o/p
python src/aiops_pipeline.py
==================================================
AIOps Pipeline Result
==================================================
Records processed: 10
Anomalies detected: 2
Events consumed: 0

Detected Events:

we can see 2 anomalies detected through the pipeline in the records processed



######################   Part 4(task 6)  #######################

when we try to run aiops pipeline test it doesnt run 
python tests/test_aiops_pipeline.py
Traceback (most recent call last):
  File "/workspaces/github-skills-challenge/tests/test_aiops_pipeline.py", line 3, in <module>
    from src.anomaly_detector import AnomalyDetector
ModuleNotFoundError: No module named 'src'

to rectify this:- we chnage the path
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
