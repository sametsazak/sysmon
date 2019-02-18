# Sysmon - Wazuh Sigma Rules


Sysmon is a command line tool which allows us to monitor and track processes taking place in our computers. With the right configuration, suspicious behaviors can be detected by Sysmon and the detailed information will be stored in the generated log. For instance, the creation of a new process will be detected by Sysmon as “Event number 1”. This event will contain critical information that we could use to configure an active response or adopt other type of security measures.


# How to Install?

## Client Configuration

First, you should install Sysmon.

Download sysmon : https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon

Setup Sysmon: 

Sysmon64.exe -accepteula -i sysconfig.xml

Then, 

Copy below to your client's ossec.conf file
`

<localfile>
<location>Microsoft-Windows-Sysmon/Operational</location>
<log_format>eventchannel</log_format>
</localfile>

`
Save it and restart agent.

## Server Configuration

Copy sysmon_rules.xml to /var/ossec/etc/rules/local_rules.xml

Save it restart manager.

Finished!


Rules are generated from Rules from https://github.com/Neo23x0/sigma/tree/master/rules/windows/sysmon

Thanks.
