
Update account numbers in code

Create sqs queues
Add policy to dr_amibackup_pending_copy, permitting access from destination account.
create IAM role
create lambda functions (ensure they are configured to share with the proper destination account)
create cloudwatch events

Run Step 1 at 1:15AM EST
15 06 ? * MON-FRI *

Run Step 2 at 1:30AM EST
30 06 ? * MON-FRI *

Run Step 3 at 2:00AM EST
00 07 ? * MON-FRI *
