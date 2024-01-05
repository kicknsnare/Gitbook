---
description: https://corelight.com/products/zeek-data/
---

# Zeek Logs

Each log output consists of multiple fields, and each field holds a different part of the traffic data. Correlation is done through a unique value called "UID". The "UID" represents the unique identifier assigned to each session.

Zeek logs in a nutshell;

| <p>Category<br></p>             | <p>Description<br></p>                                                              | Log Files                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------- | ----------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>Network<br></p>              | <p>Network protocol logs.<br></p>                                                   | <p><em>conn.log, dce_rpc.log, dhcp.log, dnp3.log, dns.log, ftp.log, http.log, irc.log, kerberos.log, modbus.log, modbus_register_change.log, mysql.log, ntlm.log, ntp.log, radius.log, rdp.log, rfb.log, sip.log, smb_cmd.log, smb_files.log, smb_mapping.log, smtp.log, snmp.log, socks.log, ssh.log, ssl.log, syslog.log, tunnel.log.</em><br></p> |
| <p>Files<br></p>                | <p>File analysis result logs.<br></p>                                               | <p><em>files.log, ocsp.log, pe.log, x509.log.</em><br></p>                                                                                                                                                                                                                                                                                           |
| <p>NetControl<br></p>           | <p>Network control and flow logs.<br></p>                                           | <p><em>netcontrol.log, netcontrol_drop.log, netcontrol_shunt.log, netcontrol_catch_release.log, openflow.log.</em><br></p>                                                                                                                                                                                                                           |
| <p>Detection<br></p>            | <p>Detection and possible indicator logs.<br></p>                                   | <p><em>intel.log, notice.log, notice_alarm.log, signatures.log, traceroute.log.</em><br></p>                                                                                                                                                                                                                                                         |
| <p>Network Observations<br></p> | <p>Network flow logs.<br></p>                                                       | <p><em>known_certs.log, known_hosts.log, known_modbus.log, known_services.log, software.log.</em><br></p>                                                                                                                                                                                                                                            |
| <p>Miscellaneous<br></p>        | <p>Additional logs cover external alerts, inputs and failures.<br></p>              | <p><em>barnyard2.log, dpd.log, unified2.log, unknown_protocols.log, weird.log, weird_stats.log.</em><br></p>                                                                                                                                                                                                                                         |
| <p>Zeek Diagnostic<br></p>      | <p>Zeek diagnostic logs cover system messages, actions and some statistics.<br></p> | <p><em>broker.log, capture_loss.log, cluster.log, config.log, loaded_scripts.log, packet_filter.log, print.log, prof.log, reporter.log, stats.log, stderr.log, stdout.log.</em><br></p>                                                                                                                                                              |

\
Some of the most commonly used logs are explained in the given table.

| Update Frequency       | <p>Log Name<br></p>   | <p>Description<br></p>                           |
| ---------------------- | --------------------- | ------------------------------------------------ |
| Daily                  | _known\_hosts.log_    |  List of hosts that completed TCP handshakes.    |
| Daily                  | _known\_services.log_ |  List of services used by hosts.                 |
| Daily                  | _known\_certs.log_    |  List of SSL certificates.                       |
| Daily                  | _software.log_        |  List of software used on the network.           |
| Per Session            | _notice.log_          |  Anomalies detected by Zeek.                     |
| <p>Per Session<br></p> | _intel.log_           |  Traffic contains malicious patterns/indicators. |
| <p>Per Session<br></p> | _signatures.log_      |  List of triggered signatures.                   |

Brief log usage primer table;

<table><thead><tr><th width="139">Overall Info</th><th width="164">Protocol Based</th><th width="150">Detection</th><th>Observation</th></tr></thead><tbody><tr><td><em>conn.log</em></td><td><em>http.log</em></td><td><em>notice.log</em></td><td><em>known_host.log</em></td></tr><tr><td><em>files.log</em></td><td><em>dns.log</em></td><td><em>signatures.log</em></td><td><em>known_services.log</em></td></tr><tr><td><em>intel.log</em></td><td><em>ftp.log</em></td><td><em>pe.log</em></td><td><em>software.log</em></td></tr><tr><td><em>loaded_scripts.log</em></td><td><em>ssh.log</em></td><td><em>traceroute.log</em></td><td><em>weird.log</em></td></tr></tbody></table>

\


