# Send Laptop Notification with Python
How to send laptop notification in python.

---

```python
from plier import notification

#send notification
notification.notify(
title="Reminder",                      #notification title
message="Take a break and stretch",    #notification message
app_name="Python Notifier",            #app name sending notification
timeout=10                             #notification duration in seconds
)
```

---

### Requirements 

- Python 3.x
- plyer 
  ```bash
  pip install plyer
  ```
