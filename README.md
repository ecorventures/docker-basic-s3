# ecor/basic-s3

This is an alpine linux image with curl, openssl, and bash. It is
designed specifically for use with
[ecor/scripts-aws-s3](https://github.com/ecorventures/docker-scripts-amazon-s3).

## Usage

```bash
docker run --rm --name store-db-on-s3 \
  --volumes-from scripts-aws-s3 \
  -v /tmp:/tmp \
  -e "AWS_KEY=ABCDEFGH47IJJ3KL7M4N" \
  -e "AWS_SECRET=bDNO3bXHRhKtKl76ItpsKecoYQ6/Oh4rb9iIlNzY" \
  ecor/basic-s3 \
  /scripts/aws/s3/put /tmp/backup.sql.dump /backup.archive.bucket
```
