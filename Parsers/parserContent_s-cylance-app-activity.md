#### Parser Content
```Java
{
Name = s-cylance-app-activity
  Vendor = BlackBerry
  Product = BlackBerry Protect
  Lms = Splunk
  DataType = "app-activity"
  TimeFormat = "yyyy-MM-dd'T'HH:mm:ss.SSS"
  Conditions = [ """, Event Name:""", """, Message:""", """Event Type: AuditLog""" ]
  Fields = [
    """({time}\d\d\d\d-\d\d-\d\dT\d\d:\d\d:\d\d\.\d\d\d)[^\s]*\s+[^\s]+\s+({app}[^\s]+)\s""",
    """\w+\s+\d+ \d\d:\d\d:\d\d ({host}[a-fA-F\d.:]+)""",
    """\[({host}[\w\-.]+)\]\s*Event Type:""",
    """\sEvent Name:\s*({activity}[^,]+),""",
    """\sMessage:.+?[^,:]+(Assigned|Changed):\s*({additional_info}[^:,;]+)""",
    """\sUser:\s*(|({user_fullname}.+?))\s*\(({user_email}[^@\s\)]+@({email_domain}[^@\s\)]+))\)""",
    """\sSource IP:\s*({src_ip}[a-fA-F\d\.:]+)""",
    """\sProvider:\s*({login_type}[^,]+)""",
    """\sDevice:\s*({object}[^;]+)""",
  ]
  DupFields = [ "host->dest_host" ]
}
```