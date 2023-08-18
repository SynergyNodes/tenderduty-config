# Example config that we are using for tenderduty (3 chains)

```
---

enable_dashboard: yes
listen_port: 8888
hide_logs: no
node_down_alert_minutes: 3

prometheus_enabled: no
prometheus_listen_port: 28686

pagerduty:
  enabled: yes
  api_key: <PagerDuty-Events-API-V2-Integration-Key>
  default_severity: alert

discord:
  enabled: no
  webhook: https://discord.com/api/webhooks/999999999999999999/zzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz

telegram:
  enabled: no
  api_key: '5555555555:AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA'
  channel: "-666666666"

chains:

  "01. Terra Mainnet":
    chain_id: phoenix-1
    valoper_address: <your-Terra-valoper-address>
    public_fallback: yes

    alerts:
      stalled_enabled: yes
      stalled_minutes: 10

      consecutive_enabled: yes
      consecutive_missed: 5
      consecutive_priority: critical

      percentage_enabled: yes
      percentage_missed: 10
      percentage_priority: warning

      alert_if_inactive: yes
      alert_if_no_servers: yes

      # Chain specific setting for pagerduty
      pagerduty:
        enabled: yes
        api_key: "" # uses default if blank

      # Discord settings
      discord:
        enabled: no
        webhook: "" # uses default if blank

      # Telegram settings
      telegram:
        enabled: no
        api_key: "" # uses default if blank
        channel: "" # uses default if blank

    nodes:
      # You can add multiple nodes here, like backup nodes, public endpoints, etc
      - url: tcp://<ip-address>:26657
        alert_if_down: yes  

      - url: tcp://<ip-address>:28657
        alert_if_down: no

      - url: https://rpc-terra2.synergynodes.com:443
        alert_if_down: yes     



  "02. Axelar":
    chain_id: axelar-dojo-1
    valoper_address: <your-Axelar-valoper-address>
    public_fallback: yes

    alerts:
      stalled_enabled: yes
      stalled_minutes: 10

      consecutive_enabled: yes
      consecutive_missed: 5
      consecutive_priority: critical

      percentage_enabled: yes
      percentage_missed: 10
      percentage_priority: warning

      alert_if_inactive: yes
      alert_if_no_servers: yes

      # Chain specific setting for pagerduty
      pagerduty:
        enabled: yes
        api_key: "" # uses default if blank

      # Discord settings
      discord:
        enabled: no
        webhook: "" # uses default if blank

      # Telegram settings
      telegram:
        enabled: no
        api_key: "" # uses default if blank
        channel: "" # uses default if blank

    nodes:
      # You can add multiple nodes here, like backup nodes, public endpoints, etc
      - url: tcp://<ip-address>:27657
        alert_if_down: yes 



  "03. Kujira":
    chain_id: kaiyo-1
    valoper_address: <your-Kujira-valoper-address>
    public_fallback: yes

    alerts:
      stalled_enabled: yes
      stalled_minutes: 10

      consecutive_enabled: yes
      consecutive_missed: 5
      consecutive_priority: critical

      percentage_enabled: yes
      percentage_missed: 10
      percentage_priority: warning

      alert_if_inactive: yes
      alert_if_no_servers: yes

      # Chain specific setting for pagerduty
      pagerduty:
        enabled: yes
        api_key: "" # uses default if blank

      # Discord settings
      discord:
        enabled: no
        webhook: "" # uses default if blank

      # Telegram settings
      telegram:
        enabled: no
        api_key: "" # uses default if blank
        channel: "" # uses default if blank

    nodes:
      # You can add multiple nodes here, like backup nodes, public endpoints, etc
      - url: tcp://<ip-address>:26657
        alert_if_down: no
```
