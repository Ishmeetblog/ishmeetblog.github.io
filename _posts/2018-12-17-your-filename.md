---
layout: post
title: Uses of firebase
---
uses of firebase

### Monitor your usage


When you create a Firebase project, you're also creating a project in the Google Cloud Platform. Use the App Engine Quotas page in the Cloud Platform Console to monitor your project's Cloud Firestore usage and storage costs.


### Beta limits


Maximum writes per second per database (at beta)	= 10,000 (up to 10 MiB per second)
Maximum concurrent connections for mobile/web clients per database (at beta)	 =  1,000,000

### Free quota

Cloud Firestore offers free quota that allows you to get started at no cost. The free quota amounts are listed below. If you need more quota, you must enable billing for your Cloud Platform project.

Quotas are applied daily and reset around midnight Pacific time.



### Standard limits


Constraints on collection IDs	
- Must be valid UTF-8 characters
- Must be no longer than 1,500 bytes
- Cannot contain a forward slash (/)
- Cannot solely consist of a single period (.) or double periods (..)
- Cannot match the regular expression __.*__


