# ec2-tags-to-csv

This script will put all ec2 instances with their tags into a spreadsheet. One instance per row with the instance ID in col A. `tag-key`s are separated into columns. If a instance doesn't have a tag, the cell will be left blank. Otherwise the `tag-value` is placed into the corresponding cell.

```text
usage: tags [-h] -o OUTPUT_FILE [-r AWS_REGION] [-v]

Get instance tags in CSV format.

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT_FILE, --out OUTPUT_FILE
                        path to where the output should be written
  -r AWS_REGION, --region AWS_REGION
                        AWS region to use.
  -v, --version         show program's version number and exit
```

This script uses the boto3 library to make AWS API calls. So if you don't have it, do:

```text
pip install boto3
```

### Example usage:
```text
python tags.py -o tags.csv --region 'us-east-1'
```