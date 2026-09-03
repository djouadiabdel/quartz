---
title: Privacy Policy
---

*This page covers **Reel Uploader**, a personal command line tool used by the author of this site to manage his own YouTube videos. It is not a product, it has no users other than the author, and nothing here describes the essays on the rest of the site.*

## What the tool is

Reel Uploader is a script that runs on one laptop. It reads a list of video titles, descriptions and tags from a local file and writes them onto videos that already exist on the author's own YouTube channel. There is no website, no server, no account system and no way for anyone else to run it.

## What data it touches

The tool authenticates with Google using OAuth and requests one scope, `https://www.googleapis.com/auth/youtube`. With that scope it does exactly two things:

1. Lists the videos on the authenticated user's own channel, to find which video matches which entry in the local file.
2. Updates the title, description, tag list and category on those same videos.

It reads no other Google service. It does not touch Gmail, Drive, Contacts, Calendar or Photos, and it never requests a scope for them.

## Where that data goes

Nowhere. The OAuth access token is written to a single file on the author's own computer, readable only by his user account. Video titles and descriptions are read from a local file and sent directly to the YouTube Data API over HTTPS.

The tool has no analytics, no telemetry, no logging service and no database. It transmits nothing to any third party. No data is sold, shared, transferred or used for advertising, and none of it is used to train any model.

## Retention and deletion

The only stored artefact is the local OAuth token. Deleting that file ends the tool's access immediately. Access can also be revoked at any time from [Google Account permissions](https://myaccount.google.com/permissions), which invalidates the token whether or not the file still exists.

## Limited use

Reel Uploader's use of information received from Google APIs adheres to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including the Limited Use requirements.

## Contact

Questions about this policy go to the address listed as the developer contact on the OAuth consent screen for the application.

*See also [[terms|Terms of Service]].*
