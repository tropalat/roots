# Tropa roots

Two files per day:

- `roots/YYYY-MM-DD.txt`: the Merkle root (SHA-256) over every event
  received that day, and the number of events.
- `roots/YYYY-MM-DD.txt.ots`: the OpenTimestamps proof for that file.
  It is added a few hours later, once the timestamp is confirmed on Bitcoin.

## What this proves

That a given document existed, and was signed by a given certificate,
before a given time. It does not prove that what the document says is true.

## How to check

1. Take the hash and Merkle path from the document's verification page or
   from the evidence pack manifest.
2. Recompute the root and compare it with the file for that day.
3. Verify the timestamp with any OpenTimestamps client:
   `ots verify roots/YYYY-MM-DD.txt.ots`

Or run the verifier: https://github.com/tropalat/verify

## Rules of this repository

History is append-only. Force pushes and deletions are blocked for
everyone, with no exceptions. Only the publishing bot can add commits, and
every commit after this README must be signed. If an integrity check ever
fails, a note is published here.
