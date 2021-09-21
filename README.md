# o365-graph-api-md
A Markdown-based read-only client for the Microsoft Graph API (Office 365 API)

Goal 1: speak to the Microsoft Graph API to read calendar meetings, and output them as Markdown files.

Goal 2: read Markdown files and be able to react to changes within them. Changes to Markdown files marked with an item UID corresponding to a known O365 meeting should write those changes to the cloud unless the ETag changed in the meantime (in which case do the default Palm thing and duplicate, or just ask the user). If a Markdown file describing an item UID for a known O365 meeting disappears (or has a property like "Deleted: true" appended to it), the cloud sync should detect that and ask the user to confirm the deletion (nicely in a bulk list, if the user does a lot of deleting so we don't end up with a hundred popups one after another). Maybe store some cloud-specific data, ETags, timestamps and other metadata beyond the basics that's immediately useful into a SQLite database (or make the SQLite the master store, and the export/import/change process only projects the data onto Markdown outputs/inputs).
