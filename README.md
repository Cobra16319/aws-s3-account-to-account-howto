Step 1: Get Destination AWS Account Number

Sign in to the destination AWS account. Go to My Account → Account Id and copy the account id from there.

Step 2: Create Source S3 Bucket

Sign in to source AWS account. Create a bucket in S3 and Attach the policy file named <policyone.json> to the bucket.

Step 3: Create Destination S3 Bucket

Sign in to the destination AWS account. Create a bucket in S3.

Step 4: Create IAM User In Destination AWS Account Create a new IAM user in the destination AWS account and Attach the <policytwo.json> to that user.

Step 5: Sync or copy S3 Bucket or objects To Destination bucket

Now we can copy or sync S3 bucket or objects from the source account to the destination account by using the following AWS CLI command.
 aws s3 sync s3://SOURCE-BUCKET-NAME s3://DESTINATION-BUCKET-NAME   
As you see we did not define any access control list during the command. We can use --acl parameter for this purpose and provide canned ACLs to apply to all objects.
 aws s3 sync s3://SOURCE-BUCKET-NAME s3://DESTINATION-BUCKET-NAME --acl public-read   

Reference: https://aws.amazon.com/premiumsupport/knowledge-center/account-transfer-s3/
