#### Parser Content
```Java
{
Name = cef-azure-event-hub-security
  DataType = "alert"
  Conditions = [""""category":"Security"""", """"eventName""""]
  Fields = ${MSParserTemplates.cef-azure-event-hub.Fields}[
    """compromisedEntity":"({user_upn}[^"]+)"""",
    """userName":"(({domain}[^\\"]+)\\+)?({user}[^"]+)"""",
    """clientIPAddress":"({src_ip}[^",]+)""",
    """severity":"({alert_severity}[^"]+)"""",
    """operationId":"({alert_id}[^"]+)"""",
    """category":"({azure_category}[^"]+)"""",
    """attackedResourceType":"({azure_resource_type}[^"]+)"""",
    """\Wext_properties_eventProperties_attackers_0_=({src_ip}[a-fA-F\d.:]+)""",
    """\Wext_properties_eventProperties_previousIPAddress=(|({last_known_ip}.+?))(\s+\w+=|\s*$)""",
    """eventName":"({alert_type}.+?[^\\])"""",
    """\Wext_properties_eventProperties_malwareName=(|({alert_type}.+?))(\s+\w+=|\s*$)""",
    """resultDescription":"({alert_name}.+?[^\\])"""",
    """detailDescription":"({additional_info}.+?[^\\])"""",
    """Namespace:\s*(|({azure_event_hub_namespace}[^\]]+?))\s*[\];]""",
    """EventHub name:\s*(|({azure_event_hub_name}[^\]]+?))\s*\]"""
  ]
}
```