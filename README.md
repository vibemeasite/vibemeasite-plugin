# VibeMeASite plugin for Claude

Build and run a real, hosted website for a small business just by talking to Claude. VibeMeASite creates the pages and sections, sets the branding, adds appointment booking, a shop, a blog or a member directory, translates the site into other languages, and publishes it on its own hosting or a domain you already own.

This plugin bundles two things:

- **The VibeMeASite connector** — a remote MCP server at `https://mcp.vibemeasite.com/mcp/app` (declared in `.mcp.json`). It is the same connector listed in Claude's connector directory.
- **The `build-my-website` skill** — a short guide that helps Claude work in a sensible order: plan the site, offer the owner's own photos through a secure upload page, build and translate the sections, then publish.

## Getting started

1. Install the plugin.
2. The first time Claude uses VibeMeASite, a sign-in page opens. Enter your email address; there is no password — click the link we email you, or type the 6-digit code from the email.
3. Ask Claude something like: *"Set up a website for my plumbing business, Rivera Plumbing, with Home, Services and Contact pages."*

More examples and details: [vibemeasite.com/connector](https://vibemeasite.com/connector).

## What this plugin sends and where

- **Tool calls go to VibeMeASite only**, at `https://mcp.vibemeasite.com`. Each call carries just the details needed for that action (for example the text of a section you asked Claude to write). VibeMeASite never requests your chat history, memory or files.
- **Sign-in** uses OAuth. VibeMeASite receives your email address and issues an access token valid for one hour plus a refresh token valid for up to 90 days, which is replaced on every use.
- **Secrets never go through the chat.** API keys, passwords, payment setup, refunds and changes to who can edit your site happen on secure single-use pages on `mcp.vibemeasite.com` that Claude gives you a link to.
- **Your customers' details** (bookings, orders, sign-ups) are shown in chat with email addresses and phone numbers partly hidden.
- The plugin runs no local programs, hooks or scripts, and contains no compiled code.

Full details: [Privacy Policy](https://vibemeasite.com/privacy) (see "Connector update — October 4, 2026").

## Plan, billing and hosting

These are managed on your account page at [mcp.vibemeasite.com/account](https://mcp.vibemeasite.com/account), not inside Claude.

## Support

Email [admin@vibemeasite.com](mailto:admin@vibemeasite.com) or use [vibemeasite.com/contact](https://vibemeasite.com/contact).

## Links

- Documentation: [vibemeasite.com/connector](https://vibemeasite.com/connector)
- Terms of service: [vibemeasite.com/terms](https://vibemeasite.com/terms)
- Privacy policy: [vibemeasite.com/privacy](https://vibemeasite.com/privacy)
- Support: [vibemeasite.com/contact](https://vibemeasite.com/contact)

## License

MIT — see [LICENSE](LICENSE).
