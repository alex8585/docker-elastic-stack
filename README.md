# Docker elastic stack configs
## install
- 1). Install and start rsyslog: Ensure rsyslog is installed and running on your system.
- 2). Edit the rsyslog configuration file: Open the configuration file, typically located at /etc/rsyslog.conf or /etc/rsyslog.d/50-default.conf.
  - Add a template: \
  ```` $template RemoteFormat,"<%pri%>%timestamp:::date-rfc3339% %HOSTNAME% %syslogtag%%msg%\n" ````
  - Add a forwarding rule:  (Replace logstage-ip with the IP address or hostname of your Logstage server.)\
   ````*.* @@logstage-ip:514````
- 3). docker compose  up


