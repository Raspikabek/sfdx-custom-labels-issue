# Salesforce Custom Labels deployment issue

# Steps to reproduce

* Clone repository.
* Create a Manifest with the source metadata:

```bash
sfdx force source manifest create -p force-app -o temp
```
* Deploy the manifest with Destructive Changes:
```bash
sfdx force source deploy --manifest temp/package.xml --predestructivechanges destructiveChangesPre.xml --postdestructivechanges ackage.xml --predestructivechanges destructiveChangesPre.xml --postdestructivechanges destructiveChangesPost.xml -g -c -u TARGET_ORG_ALIAS
```
