---
layout: page
title: User guide
permalink: /
---

Form Sync – Copy, Version History & Backup for Jira Forms keeps a history of every Jira Forms template, copies forms to many projects at once, keeps the copies in sync with their source, brings back deleted forms, and moves forms between sites.

## Where to find it
Jira admins: ⚙ Settings → Apps → **Form Sync** (left menu, under "Apps").

## How it finds changes
Jira does not report changes of forms, so Form Sync checks the forms of every project once an hour and stores a new version whenever a form changed. **Settings › Check for changes now** runs the check right away. The first check after installation builds the starting point of the history.

## Version history and restore
Open a form and choose **Versions**. Every version shows when it was found and what changed (questions added, removed or renamed, required/optional, choices, linked Jira fields, conditions, lock and PDF settings). **View** shows the questions of a version; **Restore** saves the form with that version – its current state stays in the history. Jira does not record who changes a form, so changes found in Jira have no author; changes made with Form Sync show who made them.

## Deleted forms
**Deleted forms** lists forms deleted in Jira. Restoring one re-creates it in its project (as a new form) with its questions and publishing; linked copies follow it.

## Copy to many projects
Open a form, choose **Copy to projects**, pick the target projects and click **Copy**. Publishing (issue types for creating issues, request types and the customer portal) is matched by name in each project; what does not exist there is listed. Keep the copies **linked** to push later changes of the source to them.

## Linked copies
The **Copies** tab of a form shows its linked copies as *In sync* or *Outdated*. **Update** replaces the questions of a copy with the source's; the copy keeps its own name and publishing. Turn on **Settings › Update linked copies automatically** to do this after every change of the source.

## Move forms between sites
**Export** shows the form as JSON. On the other site (for example from a sandbox to production) paste it into **Import** and choose the project. Linked Jira fields are matched by field name; questions whose field does not exist there are unlinked and listed.

## Settings
- **Projects to skip** – not checked and not listed.
- **History** – always keep at least the last 5–100 versions of every form; delete older versions after 90 days to 5 years.
- **Activity log** – kept 90–730 days.

## Good to know
- Jira sometimes refuses a publishing setting (for example a question linked to the Description field on a request type that has no such field). Form Sync then saves the form without that publishing and tells you.
- Copies, updates and restores change forms through Jira's Forms API with the app's permissions; filled-in forms on issues are not changed.
