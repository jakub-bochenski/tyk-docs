---
date: 2023-08-15T09:37:14+01:00
title: How to Backup Tyk Dashboard Configurations Within A Tyk Cloud Deployment
menu:
  main:
    parent: "Frequently Asked Questions"
weight: 0 
---

#### What are the methods for backing up the configurations of the Tyk Dashboard, including Policies, Keys, and APIs. 

The dashboard configurations are managed by Tyk via environment variables and these will only change if you submit a [support ticket](https://support.tyk.io/hc/en-gb/articles/8671452599708-Ticket-Submission-Guide). There will be tickets like this one, as well as internal ones to track what was changed and what request brought about the change. Policies, API definitions and Keys are stored in MongoDB and Redis, which are managed by us. Per standard procedure, we take regular backups of these, but you can [request us](https://support.tyk.io/hc/en-gb/articles/8671452599708-Ticket-Submission-Guide) to take a backup for you at anytime.

Additionally, you can make use of Tyk-Sync to take a backup of Apis and Policies. Please be aware keys cannot be backed up this way.

#### It is crucial to track and audit changes made to the Tyk Dashboard configurations. How can I log and implement an audit trail for these changes? Are there specific tools or settings within Tyk Gateway that facilitate this process?

Tracking changes to Dashboard configurations will need to be done through submitting a [support ticket](https://support.tyk.io/hc/en-gb/articles/8671452599708-Ticket-Submission-Guide). As mentioned earlier, no configuration will change except on your request.

If you have a self-managed Tyk instance you can enable audit_logging. This tracks the actions performed by a user once they are logged into the dashboard. The logs are saved to a file on the Dashboard file system.

#### In the event of a configuration error or an undesirable change, is there a built-in mechanism to rollback to a previous configuration for an API or a Policy? Please advise on the available options or recommended approaches for performing rollbacks effectively.

For this, Tyk Sync can be used with the appropriate command to initiate a rollback. Only APIs and Policies can only be rolled back using this method. Keys are not accounted for. Additionally, a restoration from a database dump can be performed by submitting a [support ticket](https://support.tyk.io/hc/en-gb/articles/8671452599708-Ticket-Submission-Guide).
