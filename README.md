# Meraki
Cisco Meraki tools written in Python

# Setup environment for the scripts

## Make sure Python libraries are installed
```
pip install -r requirements.txt
```

## API Key

On Unix the scripts will look in `/usr/local/sbin/meraki.yaml`
for settings.

The YAML file should look like this:

```
apikey:
    'your-api-key-here'
```

Without the YAML file, the `--apikey` option must be used.

