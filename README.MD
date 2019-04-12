# Project Title

Automated cross-account AMI creation lambda function.

A github like service [Codespaces](https://www.infoworld.com/article/2608076/murder-in-the-amazon-cloud.html) that was hosted on AWS was compromised and all resources within their AWS account were deleted, including their backups.
This was created to provide an additional layer of isolation.

## Getting Started

Please note that this utilizes queues in a way that I probably wouldn't do now that Lambda step functions have been released. Also, I'd probably use serverless or zappa to package and deploy if I were to ever revisit this. April 2019

### Installing

For install steps, look inside the individual directories.

Source Account:<br />
Creates AMi and snapshot of ec2 instances with the tag Backup=true <br />
Sets AMI and Snapshot permissions granting access to them from the destination account. <br />
Deletes AMIs and Snapshots when tag DeleteOn=whateverRetentionDate. <br />

Destionation Account: <br />
Makes a copy of the AMI and Snapshot that has been shared with the destination account. <br />
Deletes the AMI and Snapshot based on the image DeleteOn date <br />

## Built With

Lambda functions that run python. SQS queues

## Authors

- **Dane Fetterman**

## Acknowledgments

- Heavily modified version of **R. Kozora** cross region ami copy
