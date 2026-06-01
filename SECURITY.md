# Security Policy

At LearnaSub, we take the security of our infrastructure and our clients' intellectual property seriously. This document outlines our security practices, supported versions, and the protocol for reporting vulnerabilities.

## Supported Versions

LearnaSub is a fully managed, cloud-based SaaS platform. All active workspaces and enterprise clients are automatically maintained on the latest, most secure version of the platform.

| Platform Component | Supported          |
| ------------------ | ------------------ |
| Web Application    | :white_check_mark: |
| Telegram Bot API   | :white_check_mark: |
| Backend Services   | :white_check_mark: |

## Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.** 

If you believe you have found a security vulnerability in LearnaSub, please report it to us privately so we can patch it immediately before public disclosure. 

1. Email your findings to: **[tsukimapodcast@gmail.com]**
2. Include a brief description of the vulnerability and the steps to reproduce it.
3. We will acknowledge your report within 24-48 hours and provide an estimated timeline for the fix.

## Infrastructure & Data Protection

While LearnaSub's source code is proprietary and closed-source, we believe in transparency regarding how we protect your data.

### 1. Workspace Isolation
We utilize strict Row-Level Security (RLS) within our PostgreSQL database architecture. Project files, translation memories, and AI refinements are strictly isolated at the `workspace_id` level. Users can only access data explicitly shared within their authorized team workspace.

### 2. Secure Cloud Storage
Subtitle assets (`.srt`, `.ass`) and translation artifacts are stored in encrypted object storage (Supabase). Access requires authenticated, time-limited presigned URLs, ensuring your pre-release content cannot be scraped or accessed publicly.

### 3. Payment Processing
LearnaSub does not store sensitive financial information. 
*   **Global Payments:** Managed via secure, decentralized blockchain transaction routing (Binance Pay / USDT).
*   **Localized Payments:** Handled by CBM-compliant gateways (Myan Myan Pay), passing only randomized, length-restricted Order IDs to the gateway to ensure transaction integrity.

### 4. AI & Vector Processing
AI memory and context generation are handled via transient processing streams using Edge Functions. Data vectorized for our internal RAG (Retrieval-Augmented Generation) knowledge base is strictly limited to LearnaSub's public documentation and does not ingest proprietary user subtitle files.

---
*LearnaSub is developed and maintained by Tsukima.*
