# MinIO Deployment Documentation

## Overview

This laboratory uses Docker to deploy MinIO, an S3-compatible object storage server, in the KillerCoda environment.

## Docker Command

```bash
docker run -d \
  -p 9000:9000 \
  -p 9001:9001 \
  --name minio-server \
  -e "MINIO_ROOT_USER=cloudadmin" \
  -e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
  minio/minio server /data --console-address ":9001"
```

## Configuration

- Container name: `minio-server`
- API port: `9000`
- Web console port: `9001`
- Bucket name: `client-photos`
- Storage directory: `/data`

## Environment Variables

The `-e` flags set environment variables inside the container. `MINIO_ROOT_USER` specifies the administrator username, while `MINIO_ROOT_PASSWORD` specifies the administrator password.

## Deployment Verification

The command `docker ps` can be used to verify that the MinIO container is running.

## Bucket and File Upload

The MinIO web console is accessed through port 9001. After logging in, the administrator creates the `client-photos` bucket and uploads a sample image or text file.

## Evidence

- `screenshots/minio-deployed.png`
- `screenshots/minio-bucket-upload.png`
