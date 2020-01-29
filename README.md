# Meraki

Cisco Meraki tools written in Python

Uses the Meraki [Dashboard API](https://dashboard.meraki.com/api_docs).

## Setup environment for the script

### Development

While developing, create a local environment.

```bash
python3 -m venv env
source env/bin/activate
pip3 install --upgrade pip
pip3 install -r requirements.txt
pip3 install pylint pytest rope
deactivate && source env/bin/activate
```

### Make sure Python libraries are installed

```bash
pip3 install -r requirements.txt
```

### API Key and Org Id

The Meraki API key must be provided to the script.  Optionally you
can also provide the organization id.  If no org id is provided, it
will be looked up.  But if your key is associated with more than one
organization, the script will exit.

There are several ways to pass the Meraki API key to the scripts.

1.  On Unix the scripts will look in `/usr/local/sbin/meraki.yaml`
for settings.
The YAML file should look like this:

```yaml
apikey:
    'your-api-key-here'
orgid:
    'the-org-id-here'
```

2. Environmental variables MERAKI_APIKEY and MERAKI_ORGID.  For example, add this
to the bottom of your `~/.bashrc`:

```bash
export MERAKI_APIKEY="yourapikey"
export MERAKI_ORGID="theorgid"
```

If on Windows:

```
setx MERAKI_APIKEY "yourapikey"
setx MERAKI_ORGID "theorgid"
```

3. The `--apikey` and `--orgid` options.

## Add bash completion

Assuming that `bash-completion` is installed, you can provide
tab completion to the script with the following:

```bash
sudo cp bash_completion.d/merakiapi /etc/bash_completion.d/
```

## Commands

Use the main `merakiapi` script to run various commands.

- cdp
- devices
- lldp
- organizations
- staticroutes
- clients
- l3firewallrules
- networks
- sitetositevpn

For example:

```csv
# merakiapi networks
MyNetwork1
MyNetwork2
MyNetwork3

# merakiapi staticroutes --network MyNetwork1
MyNetwork1,10.1.0.0/16,'Downstream main network',10.1.1.1,True,yes
MyNetwork1,10.2.8.0/27,'Users',10.1.1.1,True,yes

# merakiapi staticroutes --network MyNetwork1 --add --subnet 10.1.1.0/24 --name testing --gateway 10.2.8.2

# merakiapi clients --network MyNetwork1
MyNetwork1,LOC-EDI-LP2457,10.2.8.58,78:c9:86:ab:43:64,137,9
MyNetwork1,DudepleWatch,10.2.8.8,38:79:86:6b:a6:41,1,0
MyNetwork1,LOC-EDI-LP2457,10.2.8.6,4c:72:75:a2:ac:c5,10711,338597
```
