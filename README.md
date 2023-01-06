# SRV-3193

Backfill the CPM DB with the Responding Version

- Given the study data from the VCSD database (see [this ticket](https://alidacxm.atlassian.net/browse/S3-38961)), this script:
  - aggregates nopatch results with patch results (patch result of an id overrides nopatch result if it exists) to generate a map of study id to responding ui version
  - uses this map to create SQL update statements
  - writes the update queries to a file for each pod, which can be run by the DBA team (see [this ticket](https://alidacxm.atlassian.net/browse/S3-39049))
