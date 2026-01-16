# DNS Dig for Alfred

A power-user utility for performing DNS lookups directly from the Alfred search bar. It serves as a wrapper for the native `dig` command, offering smart detection for record types and IP addresses without requiring a terminal.

### Key Features

* **Smart Record Detection:** Automatically queries `A` records for domains, or specific types (MX, TXT, CNAME, etc.) if specified.
* **Auto Reverse Lookup:** Detects when you type an IP address (IPv4) and automatically performs a Reverse DNS lookup (PTR).
* **Instant Copy:** Press `Enter` to copy the result to your clipboard.
* **System Notifications:** Get a visual confirmation banner when a record is copied.
* **Clean Output:** Filters verbose `dig` output to show only the relevant answers (`+short`).
* **Full Debugging:** Hold `Cmd ⌘` + `Enter` to open a Terminal window with the full, verbose `dig` report.

### 🔍 Usage

The workflow uses the keyword `dig` (customizable).

#### 1. Standard Lookup (A Record)

Get the IP address for a domain.

> `dig google.com`

#### 2. Specific Record Types

Add the record type anywhere in the query (case insensitive). Supports **A, AAAA, MX, TXT, NS, CNAME, SOA, PTR, SRV, ANY**.

> `dig google.com mx`
> `dig txt yahoo.com`

#### 3. Reverse DNS Lookup

Simply type an IP address. The workflow detects the format and finds the hostname.

> `dig 8.8.8.8`
> *Result: dns.google.*

### Shortcuts & Modifiers

* `Enter`: Copy the selected result to the clipboard.
* `Cmd ⌘` + `Enter`: Open the full `dig` command in the Terminal for deep debugging.

### Configuration & Requirements

* **Dependencies:** Uses the default **Python 3** pre-installed on macOS. No external libraries required.
* **Network:** Uses your system's current DNS resolver settings (whatever is set in your Network Preferences).

### Notes

* The workflow parses input using standard `dig` functionality available on macOS.
* If no records are found, the workflow will display a "No records found" message.
* Timeout is set to 5 seconds to prevent hanging on slow connections.

---

**Created by Sylvester Kuisis**
