---
name: build-my-website
description: Guides building or updating a small-business website with the VibeMeASite tools — planning the pages, adding the owner's photos through the upload page, writing sections, translating, and publishing. Use when someone asks to create, redesign, translate or launch their business website with VibeMeASite.
---

# Build a website with VibeMeASite

VibeMeASite builds and hosts a real website for the Site Owner through the VibeMeASite tools. This skill is the recommended working order. Follow it unless the Site Owner asks for something different.

## 1. Understand the business first

Before creating anything, find out:

- the business name and what it does;
- which pages it needs (for example Home, Services, About, Contact) and whether a single scrolling page or separate pages suits it better;
- which languages the site should be in, and which one is the main language (it can't be changed later);
- whether it needs booking, a shop, a blog, or a member directory.

Then call `create_site`. If the account already has a site, work on that one instead.

## 2. Offer photos early

Real photos make the biggest difference. As soon as a section would benefit from a photo or video, ask whether the Site Owner wants to add their own. If they do, call `get_media_upload_page_url` and share the link: they upload from their own device, and `list_pending_uploads` then returns keys for `generate_block`. Don't ask them to paste or attach images in the chat. If they don't have photos, `stock_media_search` finds freely licensed ones.

## 3. Build the site

1. `set_branding`: colors, logo, site name and tagline, contact details.
2. `generate_block` for each section, page by page. Use the branding color variables in the CSS. Each call replaces the whole section.
3. `set_menu_structure` and `set_footer`.
4. `set_page_seo` for the important pages.
5. Widgets as needed: `add_booking_widget` (then `connect_calendar`), `add_shop_widget`, `add_map`, `add_carousel`, `add_floating_widget`, `set_cookie_banner`.

When editing an existing page, read it first with `get_page_content`, change only what was asked, and publish the same slot again.

## 4. Translate

Build the main language completely first. Then `add_site_languages` if needed, and translate each section with `generate_block` and `lang`, plus `set_header_translations`. `list_translation_status` shows what is still missing.

## 5. Publish

`go_live` puts the site online. `add_domain` connects a domain the Site Owner already owns; pass on both setup options exactly as returned.

## Things that happen outside the chat

Never ask the Site Owner to type an API key, password, or payment detail into the conversation. For email sending, spam protection, payments, refunds, team access changes and full customer records, call `get_settings_link`. It returns a secure, single-use page where they do it themselves. Plan, billing and hosting are managed on vibemeasite.com.

## Before anything destructive

Say exactly what will be deleted or replaced (which section, page, booking or order) before calling a tool that deletes, cancels or overwrites, and wait for the Site Owner to agree.
