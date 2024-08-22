# zabbix-pihole-template
Zabbix Template for a Pi-Hole Server

Download the template and import it to Zabbix Server. It's for 7.0+. It's simple though and should be fine to backport.

The template just grabs the output of `pihole status`, parses it to JSON, and alerts when DNS isn't running or blocking is disabled.

Apply the template to the Host running Pi-Hole. Modify that server's Zabbix Agent configuration to include the following line:

```AllowKey=system.run[/usr/local/bin/pihole status,*]```

I run Pi-Hole on RHEL 9.4, and I don't remember having to make any SELinux policies.
