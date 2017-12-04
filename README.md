# Meraki
Cisco Meraki tools written in Python

# Setup environment for the scripts

## Make sure Python libraries are installed
```
pip install -r requirements.txt
```

## API Key and Org Id

The Meraki API key must be provided to the script.  Optionally you
can also provide the organization id.  If no org id is provided, it
will be looked up.  But if your key is associated with more than one
organization, the script will exit.

There are several ways to pass the Meraki API key to the scripts.

1.  On Unix the scripts will look in `/usr/local/sbin/meraki.yaml`
for settings.
The YAML file should look like this:
```
apikey:
    'your-api-key-here'
orgid:
    'the-org-id-here'
```
2. Environmental variables MERAKI_APIKEY and MERAKI_ORGID.  For example, add this
to the bottom of your `~/.bashrc`:
```
export MERAKI_APIKEY="yourapikey"
export MERAKI_ORGID="theorgid"
```
3. The `--apikey` and `--orgid` options.

## Add bash completion

Assuming that `bash-completion` is installed, you can provide
tab completion to the script with the following:
```
sudo cp bash_completion.d/merakiapi /etc/bash_completion.d/
```

