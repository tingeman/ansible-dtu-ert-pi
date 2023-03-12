# ToDo list

- [ ] **implement a lock to prevent scheduled shutdown/reboot during service**
  - if lock-file is present, prevent shutdown/reboot
  - we should be able to override the lock, e.g. argument "force"
  - should the lock file have a timeout feature? e.g. xx hours since creation?
  - should the 04:00 am forced reboot override the lock?
  - should the lock be able to explicitly state that 04:00 am reboot should or shouldn't be blocked?
- [ ] **Implement local sqlite database to store alive messages**
  - Use local db to store all messages
  - Use a flag to indicate which ones have been submitted
  - When submitting a new message online, first check for and submit any unsubmitted messages
  - Schedule regular submission of any stored messages
  - Only try submitting online, when network is available
  - When trying to submit, launch separate process, which regularly checks for connection, and submits if possible.
  - Should such a service run in the background always? Can we make it a service that restarts when it fails/faults?
- [ ] **Implement flags for send_alive.py**
  -  so that we can choose which messages to collect and send
-  [ ] **Implement testing mode for reboot_now.sh and shutdown_now.sh**
   - Should perform all tasks, except the shutdown command


