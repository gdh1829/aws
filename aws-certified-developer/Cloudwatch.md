---
Title: Cloudwatch
---
# Cloudwatch

- Metrics
  - default
    - EC2: CPU Utilization, Network Packet
  - custom metrics
    - metrics that a user creates with shell script collected data, etc
    - PutMetricData API

- Metrics Resolutions
  - standard: default 5 minute
  - high: less than 1 minute like 1, 5, 10, 30, 60 second

- Retention Period
	- Data points with a period of less than 60 seconds are available for 3 hours. These data points are high-resolution custom metrics
	- Data points with a period of 60 seconds are available for 15 days
	- Data points with a period of 300 seconds are available for 63 days.
	- Data points with a period of 3600 seconds(1 hour) are available for 455 days(15 months)

- Confused words
  - Enabled detailed monitoring: store metric data in one-minute granularity
	- Enabled enhanced monitoring: primarily used only in RDS

