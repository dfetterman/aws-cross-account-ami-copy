# UPDATE 12/2020 - This type of functionality has been introduced to the AWS console so this code is no longer needed.

# Automated cross-account AMI creation lambda function.

This was created to provide an additional layer of isolation for AMI snapshots.

## Getting Started

Please note that this utilizes queues in a way that I probably wouldn't do now that Lambda step functions have been released. April 2019

### Installing

I'd probably use serverless or zappa to package and deploy if I were to ever revisit this. April 2019

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
