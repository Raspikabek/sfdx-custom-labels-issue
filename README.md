# Salesforce Custom Labels deployment issue

**NOTE**: All commands running `-c` flag for check-only

# Steps to reproduce (source deploy)


## Option A (auto):
* Run `npm run build` (creates Scratch Org > Geneartes manifest > tries to deploy with destructive changes)

## Option B (manual):
* Create a Manifest with the source metadata:

```bash
sfdx force source manifest create -p force-app -o temp
```
* Deploy the manifest with Destructive Changes:
```bash
sfdx force source deploy --manifest temp/package.xml --predestructivechanges destructiveChangesPre.xml --postdestructivechanges ackage.xml --predestructivechanges destructiveChangesPre.xml --postdestructivechanges destructiveChangesPost.xml -g -c -u TARGET_ORG_ALIAS
```


# MDAPI usage

Run `npm run mdapi:build` (converts metadata into temp_metadata > copies destructiveChanges into temp_metadata > performs deployment)