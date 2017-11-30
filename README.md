# Meraki
Cisco Meraki tools written in Python

# Setup environment for the scripts

## Make sure Python libraries are installed
```
pip install -r requirements.txt
```

## API Key

There are several ways to pass the Meraki API key to the scripts.

1.  On Unix the scripts will look in `/usr/local/sbin/meraki.yaml`
for settings.
The YAML file should look like this:
```
apikey:
    'your-api-key-here'
```
2. Environmental variable MERAKI_APIKEY
3. The `--apikey` option.

