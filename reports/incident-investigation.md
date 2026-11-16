
# Incident Investigation Report
## SSH Brute Force Activity

### 1. Incident Summary

An SSH brute-force simulation was conducted against an Ubuntu Linux system from a Kali Linux machine in a controlled lab environment.

Authentication logs were collected and investigated using Splunk SIEM.

### 2. Detection Details

- Event Type: Failed SSH Authentication
- Target Service: SSH
- Log Source: Ubuntu auth.log
- SIEM: Splunk
- Total Failed Login Events: 857
- Identified Source IPs: 1
- Targeted Account: ubuntu

### 3. Investigation

The authentication logs were analyzed using SPL queries to identify repeated failed login attempts.

The investigation focused on:

- Source IP identification
- Targeted account identification
- Authentication failure frequency
- Event timeline
- Suspicious login patterns

### 4. Findings

Repeated failed SSH authentication attempts were identified from one source IP targeting the ubuntu account.

A three-panel dashboard was created to visualize the attack timeline, source IP activity, and targeted usernames.

### 5. Recommended Response

- Review SSH authentication logs.
- Investigate the source IP and associated activity.
- Review SSH access permissions.
- Disable password-based SSH authentication where operationally appropriate.
- Prefer SSH key authentication.
- Implement rate limiting or tools such as Fail2ban.
- Monitor repeated authentication failures.

### 6. Conclusion

The lab demonstrated how SIEM tools can be used to identify suspicious authentication activity, investigate potential brute-force behavior, and visualize security events.

