# 5. Kinesis Data Analysis

![5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled.png](5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled.png)

---

## Kinesis Analytics, In more depth

![5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled%201.png](5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled%201.png)

---

## Kinesis Data Analytics

- Use cases
    - Streaming ETL: select columns, make simple transformations, on streaming data
    - Continuous metric generation: live leaderboard for a mobile game
    - Responsive analytics: look for certain criteria and build alerting (filtering)
- Features
    - Pay only for resources consumed (but it’s not cheap)
    - Serverless; scales automatically
    - Use IAM permissions to access streaming source and destination(s)
    - SQL or Flink to write the computation
    - Schema discovery
    - Lambda can be used for pre-processing

---

## Machine Learning on Kinesis Data Analytics

- **RANDOM_CUT_FOREST**
    - SQL function used for anomaly detection on numeric columns in a stream
    - Example: detect anomalous subway ridership during the NYC marathon
    - Uses recent history to compute model

    ![5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled%202.png](5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled%202.png)

- **HOTSPOTS**
    - Locate and return information about relatively dense regions in your data
    - Example: a collection of overheated servers in a data center

        ![5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled%203.png](5%20Kinesis%20Data%20Analysis%20fd524a2f72bf410a9f54e4645d862a50/Untitled%203.png)