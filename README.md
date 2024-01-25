# aws-drs-notifications
Send SNS notifications for AWS DRS Events

Creates the following resources: 

* Event Rule
* SNS Topic
* SNS Subscription
* SNS Topic Policy

The event pattern is for a stalled replication state change:
```json
{
  "detail-type": ["DRS Source Server Data Replication Stalled Change"],
  "source": ["aws.drs"]
}
```

## Example Notifications
```json
{"version":"0","id":"xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx","detail-type":"DRS Source Server Data Replication Stalled Change","source":"aws.drs","account":"123456789012","time":"2024-01-25T00:00:00Z","region":"ap-southeast-2","resources":["arn:aws:drs:ap-southeast-2:123456789012:source-server/s-xxxxxxxxxxxxxxxx"],"detail":{"state":"STALLED"}}
```
```json
{"version":"0","id":"xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx","detail-type":"DRS Source Server Data Replication Stalled Change","source":"aws.drs","account":"123456789012","time":"2024-01-25T00:00:00Z","region":"ap-southeast-2","resources":["arn:aws:drs:ap-southeast-2:123456789012:source-server/s-xxxxxxxxxxxxxxxx"],"detail":{"state":"NOT_STALLED"}}
```
## Reference
[Create a Dashboard and Alerts for AWS Elastic Disaster Recovery | Amazon Web Services](https://youtu.be/yYOVMAw7NpE?si=49tlaos2Ibx8HnDn)