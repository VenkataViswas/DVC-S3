## DVC Remote Storage

Currently, DVC has not been connected to Amazon S3 due to access issues with the AWS root account. Therefore, the data has not been pushed to remote storage.

Once the S3 bucket is configured and connected successfully, DVC will store the remote configuration details in its configuration files, and the tracked data can be uploaded using:

```bash
dvc push
```

### Sample DVC Remote Configuration

```ini
['remote "myremote"']
url = s3://my-bucket-name/path
```

After executing `dvc push`:

- The actual data files will be stored in the S3 bucket.
- DVC will track file versions and metadata through `.dvc` files.
- The project repository will contain only metadata, while large files remain in remote storage.
