---
id: jewnvemb5spnnqqrgwjkf2s
title: Cloud Sync Backup
desc: 'Cloud Sync Backup'
updated: 1673316172333
created: 1673313400266
tags: cat.tut
---
# Apps to sync multi cloud and backup

TIL the concept of syncing multi cloud and backup directly into cloud storage.

I already wrote a note related to some [[apps to sync multi cloud|notes.tutorial.cloud-storage-vs-online-backup#multi-cloud-management-app]]. This note is an expansion of the previous one.

## Rclone

[Rclone](https://rclone.org/) is a command-line program to manage files on cloud storage
- It is mature, open-source software originally inspired by rsync and written in Go
- Features:
    - Backup (and encrypt) / Restore (and decrypt) files to/from cloud storage
    - Mirror cloud data to other cloud services or locally
    - Migrate data to the cloud, or between cloud storage vendors
    - [Mount](https://rclone.org/commands/rclone_mount/) multiple, encrypted cloud storage as a disk
- [List](https://rclone.org/#providers) of supported cloud providers

## Kopia

[Kopia](https://kopia.io/) is a a fast and secure open-source backup/restore tool for Windows, Mac, and Linux.

- Kopia has both CLI (command-line interface) and GUI (graphical user interface) versions [^1]
- Kopia allows you to create encrypted snapshots of your data and save the snapshots to remote or cloud storage of your choice, to network-attached storage or server, or locally on your machine. 
- Kopia does not ‘image’ your whole machine. Rather, Kopia allows you to backup/restore any and all files/directories that you deem are important or critical.

A [discussion](https://news.ycombinator.com/item?id=27471945) in Hacker News.

[^1]: https://kopia.io/docs/installation/#two-variants-of-kopia

## Duplicati

[Duplicati](https://www.duplicati.com/) is a free backup software to store encrypted backups online.

This app [was discussed](https://news.ycombinator.com/item?id=33449574) in Hacker News. They don't recommend to use Duplicati. [^2]

[^2]: https://news.ycombinator.com/item?id=33450632

## Cryptomator

[Cryptomator](https://cryptomator.org/) encrypt files on your cloud storage.

![cryptomator](https://cryptomator.org/img/home/split-screenshots.png){max-width: 300px, display: block, margin: 0 auto}

## Related

- [List of alternatives](https://news.ycombinator.com/item?id=29210000)