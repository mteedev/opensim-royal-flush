# 👑 OpenSimulator Royal Flush

![OpenSimulator Royal Flush](assets/banner-horizontal.jpg)

**The cleanest hand in the metaverse.**

OpenSimulator Royal Flush is a WordPress plugin for OpenSimulator grids running [w4os](https://github.com/GuduleLapointe/w4os). It automatically identifies, emails, and queues no-avatar accounts for admin review and safe bulk deletion — keeping your grid database clean of bots, abandoned registrations, and dead weight.

> *Because every grid deserves a clean database.*

---

## 🃏 What It Does

When someone registers on your WordPress/w4os grid but never creates an avatar, they sit in your database forever — taking up space, skewing your user counts, and making it harder to find real residents. Royal Flush fixes that.

- **Day 30** — Sends a friendly reminder email with a link to create their avatar
- **Day 59** — Sends a final warning email — "your account will be removed tomorrow"
- **Day 60** — Flags the account in the admin review queue
- **Admin reviews** — You decide who gets flushed. Nothing is ever auto-deleted.

---

## ✨ Features

- **Safe by design** — No accounts are ever auto-deleted. Admin review and confirmation required for every flush
- **Avatar-aware** — Any account with a `w4os_uuid` is completely invisible to this plugin. Established residents are untouchable, always
- **Bot farm detection** — Automatically identifies suspect email domains with multiple no-avatar accounts
- **Trusted domain management** — Pre-populated with 38 legitimate providers (Gmail, Yahoo, Hotmail, Proton, iCloud, AOL and more) so real users never get flagged as bots
- **Color-coded review screen** — Red = disabled, orange = queued, yellow = pending. Spot the obvious ones instantly
- **Bulk select tools** — Select All, Select Queued, Select Disabled*, Deselect All
- **Email tracking** — D30 and D59 indicators show exactly which emails have been sent — never sent twice
- **Daily WP-Cron scan** — Runs automatically every day. Manual scan button available for immediate runs
- **Admin/Editor exempt** — Users with `edit_posts` capability are never flagged, ever
- **Clean deactivation** — Deactivating removes the cron schedule cleanly
- (Disabled Accounts Requires Disable User Log-In Plug-In https://wordpress.org/plugins/disable-user-login) 

---

## 📋 Requirements

- WordPress 5.0+
- [w4os — OpenSimulator Web Interface](https://github.com/GuduleLapointe/w4os) installed and configured
- (Disabled Accounts Requires Disable User Log-In Plug-In https://wordpress.org/plugins/disable-user-login) Optional!
- An OpenSimulator grid with WordPress-based registration
- PHP 7.4+

---

## 🚀 Installation

1. Download the latest release zip from the [Releases](https://github.com/mteedev/opensim-royal-flush/releases) page
2. In WordPress admin go to **Plugins → Add New → Upload Plugin**
3. Upload the zip and click **Install Now**
4. Click **Activate Plugin**
5. Navigate to **Users → 👑 Royal Flush**
6. Click **▶ Run Scan Now** to immediately populate the queue with existing no-avatar accounts
7. Review the list and flush at will

---

## ⚙️ Configuration

### Trusted Domains
Navigate to **Users → Royal Flush Settings** to manage your trusted domain list.

Trusted domains are **never** flagged as bot farm domains regardless of how many no-avatar accounts share them. The default list includes 38 common legitimate email providers. Add or remove domains as needed — one per line, lowercase.

To add a domain directly from the main screen, click the **"Add to trusted domains →"** link in the bot farm warning bar.

---

## 🖥️ Admin Screen

**Users → 👑 Royal Flush**

| Column | Description |
|--------|-------------|
| Username | Links to WP User Edit screen |
| Email | Full email address with trusted domain indicator |
| Registered | Account creation date |
| Days Old | Days since registration — bold red at 60+, amber at 30+ |
| Last Seen | Last active date |
| Status | Active or Disabled |
| Emails Sent | D30 / D59 sent indicators with timestamps on hover |
| Queue | Watching / Pending / Queued |

### Row Color Coding
| Color | Meaning |
|-------|---------|
| Red background | Account is disabled |
| Orange background | In delete queue (60+ days) |
| Yellow background | Pending (30+ days) |
| White | Recently registered, still watching |

---

## 📧 Email Content

### Day 30 — Friendly Reminder
Sent once to any no-avatar account registered for 30+ days. Includes a direct link to the avatar creation page.

### Day 59 — Final Warning
Sent once to any no-avatar account registered for 59+ days. Clearly states the account will be queued for removal with one final opportunity to create an avatar.

Both emails are sent **once per account, ever**. The timestamp is stored in user meta and the scan never sends that email again.

---

## 🔒 Safety Features

- **No auto-delete** — Ever. Admin must manually select and confirm every deletion
- **Double confirmation** — Dialog shows exact count before any deletion proceeds
- **Final server-side check** — At deletion time every account is re-verified: anyone with an avatar, admin privileges, or matching your own user ID is skipped
- **You cannot delete yourself** — Hardcoded protection
- **Admins and Editors are always exempt**

---

## 🗃️ User Meta Keys

| Key | Value |
|-----|-------|
| `orf_email_d30` | Datetime D30 email was sent |
| `orf_email_d59` | Datetime D59 email was sent |
| `orf_queued` | Datetime account was flagged for deletion queue |

---

## 📝 Changelog

See [CHANGELOG.md](CHANGELOG.md)

---

## 📄 License

GNU General Public License v3.0 — see [LICENSE](LICENSE)

---

## 👤 Author

**Gundahar Bravin** — [nerdypappy.com](https://nerdypappy.com)

Built for [NeverWorld Grid](https://neverworldgrid.com) — *Live. Love. Create.*

---

## 🤝 Contributing

Issues and pull requests welcome! If you run an OpenSimulator grid and hit a use case this plugin doesn't handle, open an issue and let's talk.

---

## ⭐ If This Helped You

Give the repo a star and tell your fellow grid operators. The OpenSimulator community is small — sharing tools makes everyone's grid better.

![OpenSimulator Royal Flush](assets/banner-vertical.jpg)
