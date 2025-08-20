# 📂 Case 01: Valdoria – Queries
This file contains some important **KQL queries** I executed during the KC7 simulation exercise.  

## 🛜 Network and DNS Activity
OutboundNetworkEvents
| where src_ip == "10.10.0.22"
| distinct url
| count 

PassiveDns
| where domain contains "hire"
| distinct domain
| count

## 🗃️ File Creation Events
FileCreationEvents
| where filename == "Valdorian_Times_Editorial_Offer_Letter.docx"
| where hostname == "UL0M-MACHINE"

## ⚙️ Process Execution Events

ProcessEvents
| where hostname == "UL0M-MACHINE"
| where process_commandline contains "hacktivist_manifesto.ps1"

ProcessEvents
| where timestamp between (datetime(2024-01-21 07:00:00) .. datetime(2024-01-21 12:00:00))
| where hostname == "A37A-DESKTOP"
| order by timestamp asc

ProcessEvents
| where process_commandline contains ".7z"

## ⌨️ User Activity 

let mary_ips = 
Employees
| where name has "Mary"
| distinct ip_addr;
OutboundNetworkEvents
| where src_ip in (mary_ips)
| count

let mary_atmp = Employees
| where name has "Mary"
| distinct username;
AuthenticationEvents
| where username in (mary_atmp)
| count


