# revo
Creates a publically accessible s3 bucket with all `assets` synced to the S3 bucket.
These assets can be used within Databricks for reporting and other purposes.

## How to use
1. Run `terraform init -upgrade`
2. Run `terraform plan`
3. Run `terraform apply`

## Sync manually
From the Homedir, execute
```sh
aws s3 sync --acl public-read ./assets/ s3://revo-public/
```

## How to use in Databricks
1. Create a Dashboard
2. Add your TABLE visualization
3. Have queries with Status values like `1` and `2`
4. Go to your column in the Visualization editor and set **Diplay as** to **Image**
5. Set URL Template to **https://revo-public.s3.eu-central-1.amazonaws.com/icons/status/{{status}}.png**