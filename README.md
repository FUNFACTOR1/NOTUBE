# NOTUBE (Proof of Concept)
<img width="150" alt="notube" src="https://github.com/user-attachments/assets/175e566b-32c7-42b3-8baa-696b08304950" />

NOTUBE is a lightweight Site-Specific Browser (SSB) engine optimized for the YouTube Mobile web experience.

The project explores an alternative architectural approach for long-term playback stability by minimizing dependency on fragile frontend patching techniques and delegating all network filtering to the local AdGuard stack.

Rather than modifying YouTube binaries, injecting complex scripts, or relying on UI-specific selectors, NOTUBE constrains the playback environment itself through a hardened and minimal browser shell.


https://github.com/user-attachments/assets/0d401aff-9abb-4c54-9284-9383a5ad293b



https://github.com/user-attachments/assets/f6b2623d-477d-432f-a286-be4a214d322d



## Core Principles

**Minimal Surface Architecture**
The application intentionally minimizes interaction with volatile frontend components in order to reduce breakage caused by frequent UI updates or anti-adblock changes.

**Externalized Filtering**
NOTUBE contains no internal ad-blocking engine. All filtering operations are delegated exclusively to the local AdGuard VPN/Proxy environment. The application is designed to operate as a tightly coupled client-side companion, requiring the active AdGuard filtering stack to function correctly.

**Zero-Privilege Model**
The APK operates as a pure UI sandbox:
- 0 Android permissions
- no background services
- no wake locks
- no telemetry
- no accessibility hooks
- no persistent tasks

---

## Technical Direction

The project focuses on:
- stable WebView-driven rendering
- constrained execution environments
- reduced maintenance overhead
- native-like responsiveness
- minimal runtime complexity

No binary patching, reverse engineering, or API spoofing is performed.

---

## Current Limitations

To preserve the strict zero-permission architecture, `MediaSession` and Picture-in-Picture (PiP) background handling were intentionally removed from this Proof of Concept.

Achieving seamless PiP state persistence without foreground-service privileges remains an open technical challenge.

---

## Status

This repository currently provides:
- demonstration videos
- demonstration APKs
- architectural Proof of Concept
- experimental runtime design exploration

The project is intended for technical evaluation and research purposes.
