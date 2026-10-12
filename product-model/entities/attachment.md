---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/attachment/upload.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/storage/controller/attachment.php#handle_attachment"
    }
  ]
}
---

# Attachment

An uploaded file, initially unattached, which may be bound to a forum contribution or private message.

## Information kept

- **Filename** — The supplied display name and stored-file association.
- **File content** — The uploaded bytes delivered on an admitted download.
- **Size** — The kept file size used by upload limits and presentation.
- **Media classification** — The extension/media/thumbnail classification used in file handling.
- **Comment** — The file caption persisted with accepted parent submission or editing.
- **Uploader** — The associated poster identity, including the shared anonymous identity.
- **Uploaded at** — When the file was uploaded.
- **Use** — Whether the file serves a post or private message.
- **Binding** — The contribution or message to which an uploaded file is attached.
- **Downloads** — The counter updated by the ordinary download branch.

## States

### Uploaded

The file is stored without a bound parent contribution.

### Attached

The file is bound to its parent contribution.
