# s3_send

Send stdin to S3 by splitting it into chunks and uploading them FIFO in the background.

## Example

To raw send a zfs snapshot in chunks of 512M blobs called 'tank.0000', 'tank.0001', etc:

```bash
zfs send -w tank@snap | s3_send --block-size=512M --prefix=tank s3://my_bucket
```
