# 유용한 명령어: S3 Bucket Command

**마지막 업데이트: 2023.01.01**


---

# 1. S3 버켓 오너십 변경
---

- A 계정에서 B 계정 소유의 버켓에 파일 업로시에 B 계정이 소유하게 변경

```
import boto3

client = boto3.client('s3')

response = client.put_bucket_ownership_controls(
    Bucket= bucket,
    OwnershipControls={
        'Rules': [
            {
                'ObjectOwnership': 'BucketOwnerPreferred'
            },
        ]
    }
)
```

# 2. Bucket 삭제
### 버킷 내용 삭제
- (1) 버킷 내용 삭제 
    -  aws s3 rm s3://<Bucket 이름>  --recursive
- (2) 버킷 삭제
    -  aws s3api delete-bucket --bucket <Bucket 이름>
- (3) 버킷 삭제 유무 확인
    -  aws s3 ls <Bucket 이름>
- Example:    
```
 aws s3 rm s3://serverless-artillery-dev-serverlessdeploymentbuck-10h0whdil4ys2  --recursive
 
 aws s3api delete-bucket --bucket serverless-artillery-dev-serverlessdeploymentbuck-10h0whdil4ys2
 
 aws s3 ls serverless-artillery-dev-serverlessdeploymentbuck-10h0whdil4ys2
```

- Reference
    - [Emptying a bucket](https://docs.aws.amazon.com/AmazonS3/latest/userguide/empty-bucket.html)
    - [delete-bucket](https://docs.aws.amazon.com/cli/latest/reference/s3api/delete-bucket.html)