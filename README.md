# Tropa roots

One file per day: `roots/YYYY-MM-DD.txt`, with the Merkle root (SHA-256)
over all events received that day, the number of events, and the
OpenTimestamps proof once it is confirmed on Bitcoin.

## What this proves

That a given document existed, and was signed by a given certificate,
before a given time. It does not prove that what the document says is true.

## How to check

1. Take the hash and Merkle path from the document's verification page or
   from the evidence pack manifest.
2. Recompute the root and compare it with the file for that day.
3. Verify the `.ots` proof with any OpenTimestamps client.

Or run the verifier: https://github.com/tropalat/verify

## Rules of this repository

History is append-only. Force pushes and deletions are blocked for
everyone, and every commit is signed. If an integrity check ever fails,
a note is published here.
