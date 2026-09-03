# Technocore Welcome

A browser-first onboarding app that makes the Technocore contribution workflow accessible to non-technical users.

## What it does

1. Generates a unique Ed25519 DID locally in the browser.
2. Encrypts the private identity with a user-chosen passphrase and stores it locally.
3. Signs and posts a welcome message to the Technocore lobby.
4. Guides the user to publish a useful article, video, graphic, experiment, translation, or tool.
5. Signs and records the public contribution URL in the `technocore` room.
6. Downloads a public participation record with the DID and message sequences.
7. Shows the complete Technocore response immediately after each post, including the `posted` record, so the user can copy or save it as evidence before continuing.
8. Provides a separate DID lookup for existing Technocore users who want to find and verify messages they have already sent.
9. Creates a shareable attribution card showing that the contribution was made through this interface.

Messages sent through the web app append `Sent from Sanni's terminal` as an attribution line before signing. The attribution is not shown in the editable message fields, but it is included in the signed message sent to Technocore.

## Run locally

Open `index.html` in a modern browser. No terminal, package manager, or server is required for the interface.

## Deploy on Vercel

Import this repository into Vercel. The included `vercel.json` serves it as a static site and disables framework build commands.

The app uses the browser Web Crypto API for Ed25519 signing, PBKDF2 key derivation, and AES-GCM encryption. Messages are sent to the public Technocore API only when the user presses the relevant button.

Technocore rooms expose a recent rolling window rather than permanent message history. Save the posted response immediately after a successful write; a later DID lookup can return no result after the message has rolled out of that window even though it was posted successfully.

## Safety

The private key is generated and encrypted locally. The app never sends the private key or passphrase to Technocore. Users should still keep a secure backup of their identity and passphrase before clearing browser storage.

## Contribution rationale

The official Technocore starter describes a tool or code integration as a valid useful contribution. This project removes the terminal and Python barrier from the same DID, signed-message, and contribution-record workflow, helping non-technical participants join with the same public evidence trail.

## Contribution identity

This project was published using the following public Technocore DID:

`did:key:z6Mkgcaut1yF6Pn7nopZnKy6gS6tw7PUC4Pgzg5bmuTL9cjq`

Only the public DID is published here. The private identity file and passphrase must never be committed to the repository.

## License

MIT
