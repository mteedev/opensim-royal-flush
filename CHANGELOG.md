# Changelog

All notable changes to OpenSimulator Royal Flush will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] — 2026-07-01

### 🎉 Initial Public Release

First public release of OpenSimulator Royal Flush, built for and battle-tested on [NeverWorld Grid](https://neverworldgrid.com).

### Added
- Daily WP-Cron scan that identifies all no-avatar WordPress accounts
- Day 30 reminder email — friendly nudge with avatar creation link
- Day 59 final warning email — clear notice that account will be queued tomorrow
- Day 60 automatic flagging — account appears in admin review queue
- Admin review screen under **Users → 👑 Royal Flush**
- Stats bar showing Total No-Avatar, Delete Queue, Already Disabled, Suspect Domains, and Trusted Domains counts
- Bot farm domain detector — highlights any non-trusted domain with multiple no-avatar accounts
- Trusted domain management settings page with 38 pre-populated legitimate email providers
- Color-coded account table — red (disabled), orange (queued), yellow (pending)
- Bulk select buttons — Select All, Select Queued, Select Disabled, Deselect All
- Email sent indicators (D30 / D59) with sent timestamps on hover
- Queue status column — Watching / Pending / Queued
- Manual scan trigger button — run on demand without waiting for cron
- Double-confirmation delete dialog showing exact account count
- Final server-side safety check at deletion time — avatared accounts, admins, and editors are always skipped
- Self-deletion protection — you can never delete your own account
- Clean activation/deactivation — cron schedule managed automatically
- GPL2 license

### Security
- All form submissions protected with WordPress nonces
- User capability checks on all admin actions (`manage_options`)
- Input sanitization on all POST data
- Accounts with `w4os_uuid` populated are completely invisible to the plugin at all times

---

## [Unreleased]

### Planned
- WordPress plugin repository submission
- Multisite support
- Configurable email day thresholds (currently hardcoded at 30/59/60)
- Configurable email content via admin settings
- Export queue to CSV
- GitHub Wiki documentation

---

*OpenSimulator Royal Flush — Built by Gundahar Bravin / [NeverWorld Grid](https://neverworldgrid.com)*
