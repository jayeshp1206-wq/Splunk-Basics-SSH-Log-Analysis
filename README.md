#  Splunk Basics – SSH Log Analysis



## ⚙️ Steps to Upload SSH Log into Splunk

1. Go to Splunk Web → **Settings > Add Data**.
2. Choose **Upload** and select `synthetic_zeek_ssh.json`.
3. Set Source type: `json` or create a new one `zeek:ssh`.
4. Index: Choose `main` or create a new index like `ssh_lab`.
5. Finish the upload and confirm indexing.

---

## 🔍 Lab Tasks

Use SPL queries to complete the following analysis:

### ✅Task 1: List the top 10 endpoints with failed SSH login attempts
```spl
index=ssh_lab sourcetype="json" auth_success=false
| stats count by "id.orig_h"
| head 10
```
### ✅Task 2: Find the number of total SSH connections
```spl
index=ssh_lab sourcetype="json"
| stats count as total_ssh_connections
```
### ✅Task 3: Count all event types (successful, failed, no-auth, multiple-failed) seen in the logs
```spl
index=ssh_lab sourcetype="json"
| stats count by event_type
```

## 📸Submission
Submit a screenshot for each of the following:
-Task 1 =>
<img width="1906" height="848" alt="task1" src="https://github.com/user-attachments/assets/fc1f5ba4-2dee-497e-8169-9193ab4620bb" />



- Task 2=>
- <img width="1913" height="615" alt="task2" src="https://github.com/user-attachments/assets/a306a9df-edb2-42aa-8010-3fc3f792a640" />




- Task 3=>
- <img width="1920" height="621" alt="task3" src="https://github.com/user-attachments/assets/d2a7a717-ac38-446a-8370-572dc9db5fe1" />

