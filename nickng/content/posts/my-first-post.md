---
title: "My First Post"
date: 2022-03-16T22:30:27+08:00
draft: false
toc: false
images:
tags:
  - untagged
---

# Azure file snapshot

## What is it? 
Azure Files provides the capability to take share snapshots of file shares. Share snapshots capture a point-in-time, read-only copy of your data.

Share snapshot capability is provided at the file share level. Retrieval is provided at the individual file level, to allow for restoring individual files. You cannot delete a share that has share snapshots unless you delete all the share snapshots first.

Share snapshots are incremental in nature. Only the data that has changed after your most recent share snapshot is saved. Incremental snapshots minimizes the time required to create the share snapshot and saves on storage costs. Even though share snapshots are saved incrementally, you need to retain only the most recent share snapshot in order to restore the share.


## When to use share snapshots
-   *Protection against application error and data corruption*
	-   Applications that use file shares perform operations such as writing, reading, storage, transmission, and processing. When an application is misconfigured or an unintentional bug is introduced, accidental overwrite or damage can happen to a few blocks. To help protect against these scenarios, you can take a share snapshot before you deploy new application code. When a bug or application error is introduced with the new deployment, you can go back to a previous version of your data on that file share.
-   *Protection against accidental deletions or unintended changes*
	-   Imagine that you're working on a text file in a file share. After the text file is closed, you lose the ability to undo your changes. In these cases, you then need to recover a previous version of the file. You can use share snapshots to recover previous versions of the file if it's accidentally renamed or deleted.
-   *General backup purposes*
	-   After you create a file share, you can periodically create a share snapshot of the file share to use it for data backup. A share snapshot, when taken periodically, helps maintain previous versions of data that can be used for future audit requirements or disaster recovery.


---
## Reference:
- https://docs.microsoft.com/en-gb/learn/modules/configure-azure-files-file-sync/4-create-file-share-snapshots
- www.nickng.life