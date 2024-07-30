Adding User-Defined DNS Entries

If you want to add specific DNS entries (like mapping a particular hostname to an IP address), you typically do this in the /etc/hosts file. However,

for more complex configurations, you might want to use systemd-resolved's configuration files.

For instance, you can configure static DNS entries by creating or editing a configuration file in /etc/systemd/resolved.conf.d/.

Here's an example of how to set it up:

    Create a new configuration file:

```bash

sudo mkdir -p /etc/systemd/resolved.conf.d
sudo nano /etc/systemd/resolved.conf.d/dns_entries.conf
```

```ini
[Resolve]
DNS=8.8.8.8 8.8.4.4
Domains=example.com
```

Restart systemd-resolved to apply the changes:

```
bash
sudo systemctl restart systemd-resolved
```
