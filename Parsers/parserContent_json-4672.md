#### Parser Content
```Java
{
Name = json-4672
    Vendor = Microsoft
    Product = Microsoft Windows
    Lms = Direct
    DataType = "windows-privileged-access"
    TimeFormat = "yyyy-MM-dd HH:mm:ss" 
    Conditions = ["""4672""", """"PrivilegeList":""""]
    Fields = [
      """({event_name}Special privileges assigned to new logon)""", 
      """"EventReceivedTime":\s*({time}\d+)""",
      """"timestamp":\s*({time}\d+)""",
      """"EventTime":"({time}\d\d\d\d-\d\d-\d\d \d\d:\d\d:\d\d)""",
      """"(Hostname|MachineName)":"({host}[^"]*)""",
      """({event_code}4672)""",
      """"(Event|Entry)Type":"({outcome}[^"]+)""",
      """"SubjectUserName":"({user}[^"]*)""",
      """"SubjectDomainName":"({domain}[^"]*)""",
      """"SubjectLogonId":"({logon_id}[^"]*)""",
      """"PrivilegeList":"({privileges}[^"]*)""",
    ]
    DupFields = ["host->dest_host"]
  }
```