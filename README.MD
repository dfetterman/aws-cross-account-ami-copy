Automated cross-account AMI creation lambda function.

For install steps, look inside the individual directories.

Source Account:<br />
Creates AMi and snapshot of ec2 instances with the tag Backup=true <br />
Sets AMI and Snapshot permissions granting access to them from the destination account. <br />
Deletes AMIs and Snapshots when tag DeleteOn=whateverRetentionDate. <br />

Destionation Account: <br />
Makes a copy of the AMI and Snapshot that has been shared with the destination account. <br />
Deletes the AMI and Snapshot based on the image DeleteOn date <br />


