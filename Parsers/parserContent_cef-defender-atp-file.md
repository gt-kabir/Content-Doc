#### Parser Content
```Java
{
Name = cef-defender-atp-file
  DataType = "file-operations"
  Conditions = ["""CEF""", """SkyFormation Cloud Apps Security""", """requestClientApplication=""", """AdvancedHunting-DeviceFileEvents"""]
  Fields = ${MicrosoftParserTemplates.cef-defender-atp.Fields} [
     """"FileName"+:\s*"+({process_name}[^"]+)""",
     """"FolderPath"+:\s*"+({file_path}({file_parent}[^"]*?[\\\/]+)?({file_name}[^"\\\/]+?(\.({file_ext}\w+))?))"""",
     """DeviceName"+:\s*"+({dest_host}[^"]+)""",
     """MD5"+:"+({md5}[^"]+)""",
]
}
```