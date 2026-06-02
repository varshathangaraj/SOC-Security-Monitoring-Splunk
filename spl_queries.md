# SPL Queries Used

## 1. Brute Force Detection
source="security_logs_v2.log" "Failed password"
| rex "from (?P<src_ip>\d+\.\d+\.\d+\.\d+)"
| stats count by src_ip
| sort -count

## 2. Failed vs Accepted Logins
source="security_logs_v2.log"
| rex "(?P<status>Failed|Accepted) password"
| stats count by status

## 3. Top Targeted Usernames
source="security_logs_v2.log" "Failed password"
| rex "for (invalid user )?(?P<username>\w+) from"
| stats count by username
| sort -count

## 4. Attack Timeline
source="security_logs_v2.log"
| timechart count

## 5. Port Scanning Detection
source="security_logs_v2.log" "Firewall"
| rex "SRC=(?P<src_ip>\d+\.\d+\.\d+\.\d+)"
| rex "DPT=(?P<port>\d+)"
| stats count by src_ip port
| sort -count

## 6. Windows Security Events
source="security_logs_v2.log" "EventID"
| rex "EventID (?P<event_id>\d+)"
| stats count by event_id
| sort -count

## 7. DNS Anomaly Detection
source="security_logs_v2.log" "DNS"
| rex "from (?P<src_ip>\d+\.\d+\.\d+\.\d+)"
| stats count by src_ip
