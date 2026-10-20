# nostr-relays

A short list of public Nostr relays that currently accept application data
(kind 30078, NIP-78) from a new key, at the size of a small document, and
return it when asked: `relays.json`.

```json
{ "updated": "YYYY-MM-DD", "relays": ["wss://...", "..."] }
```

Used by the chess tournament pages at https://chessprograms.mwolf.net/ to
choose relays when a new live link is made; they keep a list of their own
as a fallback, so this file is a convenience, not a dependency.

The list is checked about once a week by publishing a test message (which
asks to be deleted after an hour, NIP-40) to each relay three times and
reading it back; a relay is listed when that works at least twice. Relays
that refuse unknown keys some of the time are left out.

Fetch it from
`https://raw.githubusercontent.com/mwolf-net/nostr-relays/main/relays.json`.
