# PURECAST (Proof of Concept)
<img width="150" alt="notube" src="https://github.com/user-attachments/assets/175e566b-32c7-42b3-8baa-696b08304950" />

PURECAST is a lightweight Site-Specific Browser (SSB) engine optimized for constrained mobile web playback workflows.

The project explores an alternative architectural approach for long-term playback stability by minimizing dependency on fragile frontend patching techniques and delegating all network filtering to the local AdGuard stack.

Rather than modifying YouTube binaries, injecting complex scripts, or relying on UI-specific selectors, PURECAST constrains the playback environment itself through a hardened and minimal browser shell.



https://github.com/user-attachments/assets/caa27367-9045-4592-8530-c98f2c3a58e2



https://github.com/user-attachments/assets/790bfd0c-eac4-4570-8740-082bcfc22e92



## Core Principles

**Minimal Surface Architecture**
The application intentionally minimizes interaction with volatile frontend components in order to reduce breakage caused by frequent UI updates or anti-adblock changes.

**Externalized Filtering**
PURECAST contains no internal ad-blocking engine. All filtering operations are delegated exclusively to the local AdGuard VPN/Proxy environment. The application is designed to operate as a tightly coupled client-side companion, requiring the active AdGuard filtering stack to function correctly.

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

## Disclaimer

PureCast does not modify proprietary binaries, circumvent DRM systems, or host/provide proprietary media content.

The project operates exclusively as a constrained browser runtime and depends entirely on third-party web services and the local AdGuard filtering environment.

This repository and its associated binaries are provided strictly for technical evaluation, architectural research, and experimental purposes only.
