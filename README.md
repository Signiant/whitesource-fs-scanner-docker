# whitesource-fs-scanner-docker
Lightweight Docker container to run the whitesource filesystem scanner (based on Alpine Linux)

# Running
The container just calls the whitesource file system scanner using the openjdk JRE v8.  As such, all of the command line arguments documented in the [Whitesource documentation](https://whitesource.atlassian.net/wiki/spaces/WD/pages/33718339/File+System+Agent) apply

When running, you will need to bind mount the whitesource config file as well as the content you wish to scan.  For example

```bash
docker run \
    -v "/path/to/my/whitesource-config-file:/whitesource.config \
    -v "/path/to/my/source/to/scan:/source" \
    signiant/whitesource-fs-scanner \
    -apiKey mykey -c /whitesource.config -d /source
```
