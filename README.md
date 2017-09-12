## README for minio-s3

This is a Dockerized deployment of [Minio](https://minio.io/) for quickly simulting an S3 instance, with additional tools for using [s3cmd](http://s3tools.org/usage) to communicate with the instance. 

Minio can also work with AWS::SDK and aws-cli.

### Deployment

* Copy `.env.example` to `.env` and input dummy keys for `MINIO_ACCESS_KEY` and `MINIO_SECRET_KEY`.

* Copy `s3minio.cfg.example` to `s3minio.cfg` and modify the values set for `access_key` (line 2) and `secret_key` (line 57) to match the values of the dummy keys specified in `.env` for `MINIO_ACCESS_KEY` and `MINIO_SECRET_KEY` respectively.

* Run `docker-compose up`.

### Sample commands

#### Add a bucket
```
s3cmd -c s3minio.cfg mb s3://sandwich
```

#### List buckets
```
s3cmd -c s3minio.cfg ls
```

#### Add file(s) to a bucket
```
s3cmd -c s3minio.cfg put FILE [FILE...] s3://sandwich
```

#### List contents of a bucket
```
s3cmd -c s3minio.cfg ls s3://sandwich

```