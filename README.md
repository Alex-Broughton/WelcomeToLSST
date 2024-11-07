Steps to run Batch Processing Service on LSST Data

1. Login to USDF

2. Make setup.sh script:

```
source /sdf/group/rubin/sw/w_latest
setup lsst_sitcom -t w_latest
```
(May need to run `chmod +x setup.sh` first

3. bps submit `bps-thing.yaml` -> Save the run ID!

4. `allocateNodes.py -v --dynamic -n 16 -m 0-01:00:00 -q milano -g 120 s3df`

5. To check up on the status of the run: `bps report --id #######.0`

6. To cancel: run `bps cancel --id ######.0`  or `bps cancel --user {username}`  and then run `scancel -u {username}`

7. To check up on the state of the jobs running nodes/cpus: `squeue -u {username}`
