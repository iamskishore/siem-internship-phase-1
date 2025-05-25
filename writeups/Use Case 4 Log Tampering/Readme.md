# Log Tampering Simulation

## What is Log Tampering?

  Log tampering, a technique used to modify or delete log entries, can be simulated to practice log analysis and incident response. This simulation can help organizations understand the impact of log tampering and develop effective detection and prevention strategies.

**Signs of Log Tampering**

- **Unexpected Gaps or Inconsistencies:**
    
    - _Description:_ Missing log entries or irregular time stamps may indicate deletion or alteration.
    - _Example:_ A sudden absence of logs during a critical period when an incident is suspected.
- **Altered Log Timestamps (Timestomping):**
    
    - _Description:_ Manipulating timestamps to mislead forensic analysis.
    - _Example:_ Log entries showing times that don't align with system clocks or expected event sequences.
- **Corrupted or Unreadable Log Files:**
    
    - _Description:_ Logs that cannot be opened or have been intentionally damaged.
    - _Example:_ Receiving errors when attempting to access or read log files.
- **Discrepancies Between Related Logs:**
    
    - _Description:_ Inconsistencies between logs that should correlate.
    - _Example:_ Authentication logs indicating a login without corresponding entries in application access logs.
##  wevtutil

  Wevtutil.exe an administrator command line utility used primarily **to register your event provider on the computer**. It provides metadata information about the provider, its events, and the channels to which it logs events, and to query events from a channel or log file.[more info](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/wevtutil)

## Detection Log Tampering

###  event code:
   **Event ID 1102** indicates that the Windows Security audit log was cleared. This event is logged regardless of whether the "Audit System Events" audit policy is enabled or disabled. It provides information about the user who cleared the log, including their Security ID, Account Name, Account Domain, and Logon ID[more info](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/auditing/event-1102)
   ![Log Tempering](screenshots/Log-temp.png)
   **Rule add**
   ![Rule add](screenshots/addrulelog.png)
   