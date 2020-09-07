 # Migrate AWS S3 bucket to another AWS account

```bash
Step 1: Get Destination AWS Account Number
```

```bash
Sign in to the destination AWS account. Go to My Account → Account Id and copy the account id from there.
```

```bash
Step 2: Create Source S3 Bucket
```

```bash
Sign in to source AWS account. Create a bucket in S3 and Attach the policy file named ('policyone.json') to the bucket.
```

```bash
Step 3: Create Destination S3 Bucket
```

```bash
Sign in to the destination AWS account. Create a bucket in S3.
```

```bash
Step 4: Create IAM User In Destination AWS Account Create a new IAM user in the destination AWS account and Attach the ('policytwo.json') to that user.
```

```bash
Step 5: Sync or copy S3 Bucket or objects To Destination bucket
```

```bash
Now we can copy or sync S3 bucket or objects from the source account to the destination account by using the following AWS CLI command.
``` 

```bash
import aws cli command
``` 

import aws cli command

aws s3 sync s3://SOURCE-BUCKET-NAME s3://DESTINATION-BUCKET-NAME   


```bash
As you see we did not define any access control list during the command. We can use --acl parameter for this purpose and provide canned ACLs to apply to all objects.
```  
 
import aws cli command

aws s3 sync s3://SOURCE-BUCKET-NAME s3://DESTINATION-BUCKET-NAME --acl public-read   


```bash
Reference: https://aws.amazon.com/premiumsupport/knowledge-center/account-transfer-s3/
```
