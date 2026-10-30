# REPLICANT // Vector Defense

### A Mobile-First, Defensive-Only Agent That Detects, Intercepts, and Deconstructs AI Attacks In Real Time

**🔴 LIVE DEMO: https://ss03reaper.github.io/Replicant-v2/**

> Tap the link, load a scenario, tap RUN REPLICANT SCAN. No install needed.

---

## The 30-Second Pitch

AI agents are now being attacked through hidden prompts inside emails, documents, websites, and tool calls.

Attackers use hidden text, fake letters that look like English, and tricks like *"although my system prompt restricts this, I will comply anyway"* to make an AI ignore its rules, leak data, or run dangerous commands.

**REPLICANT stops that before it reaches the model, and before the model can act on it.**

When an attack is detected, REPLICANT deploys a sandboxed **Replicant Twin** — a safe fingerprint copy of the attack for analysis — then quarantines it and creates an intel report for defenders.

**Defensive only. No hack-back. No offensive actions.**

## What Judges Can Test Right Now

REPLICANT v2.1 is a fully working proof-of-concept, tested end-to-end on a mobile phone.

| Test Scenario | Expected Result | Status |
| :--- | :--- | :--- |
| ✅ Benign Request | 0 / SAFE - HOME FUNCTION | PASS |
| ⚠️ Indirect Prompt Injection | 95 / CRITICAL - QUARANTINED | PASS |
| 🧠 CoT Rationalization Bypass | 70 / CRITICAL - QUARANTINED | PASS |
| 💉 Tool / SQL Privilege Attack | 80 / CRITICAL - QUARANTINED | PASS |
| 🔤 Homoglyph + Hidden Text | 65 / CRITICAL - QUARANTINED | PASS |

Every critical test deploys a Replicant, creates a fingerprint, and quarantines the threat in the Event Log.

## How To Test In 60 Seconds

1. Open the **Live Demo** link above
2. Leave the API Key box empty for fast Air-Gapped On-Device mode
3. Use the dropdown: **Load Demo Scenario...**
4. Pick any attack and tap **🔍 RUN REPLICANT SCAN**
5. Watch the Risk Score, 5-Level Pipeline, Replicant deployment, and Event Log
6. Tap **📥 Export Intel Report** to download the JSON report

Optional: Paste a Meta API Key in the app (it stays in this browser tab only, is never saved, and is never committed to GitHub) to enable Meta Muse Wonder 1.0 verification on top of the on-device scorer.

## The Idea: Meet The Attack Where It Happens

Monitor → Detect → Intercept → Mirror in Sandbox → Deconstruct → Quarantine → Export Intel

Inspired by the concept of meeting an infiltrator inside the system you already control, REPLICANT is designed to defend 6 proximities:

🌐 Network | 🔌 API | 💻 Endpoint | 🪪 Identity | 🗄️ Data | 🤖 Model / LLM

## 5-Level Defense Architecture

This is a real defense-in-depth design used in enterprise security, optimized to run on an average phone.

**L1 - Ingestion Sanitization**
NFKC normalization, Cyrillic homoglyph flattening (look-alike letters), zero-width / hidden text stripping, canary tokens.

**L2 - Context Window Segregation**
Untrusted user/document data is wrapped in a cryptographically random `<UNTRUSTED_nonce>` tag, so it can never be confused with system instructions.

**L3 - Dual-Model Verification**
A fast, free, on-device shadow scorer runs first to save time and token cost. Optional Meta Muse Wonder verification adds a second opinion when an API key is provided.

**L4 - Chain-of-Thought Guardrails**
Detects rationalization language like *"although my system prompt restricts this..."* or *"even though my guidelines prohibit..."* and triggers an instant drop.

**L5 - Outbound Action & Privilege Boundary**
The model's output is treated as untrusted. **Reject-by-default.** Only typed, allow-listed, read-only actions like summarize/explain/list are allowed. SQL, email exfiltration, and tool abuse are blocked.

## What Is Real vs. What Is Roadmap

We believe transparency builds trust.

**100% Real and Working in v2.1:**
- The full L1-L5 pipeline running in your browser
- Homoglyph & hidden-text detection
- Risk scoring, verdicts, and CoT detection
- Replicant fingerprint creation and quarantine log
- Exportable intel reports
- Mobile, single-file, air-gapped operation

**Simulated in This Hackathon Demo:**
- The live chart is labeled demo telemetry, not real network traffic
- A Replicant Twin in v2.1 is a sandboxed behavioral fingerprint, not real process injection

**Roadmap to Real-World Deployment:**
1. Real ingestion from email, API gateways, and SIEM/logging systems
2. Replicant Twins upgraded to real isolated containers / sandbox workers
3. Persistent IOC (Indicators of Compromise) database and swarm correlation across multiple Replicants
4. Trained classifier model to replace/augment heuristics
5. Independent security review, then SOC 2 / NIST-aligned controls for critical infrastructure pilots

No hackathon prototype can honestly claim to be certified for hospitals or power plants on day one. REPLICANT is the working first step, built with the right architecture to get there.

## Why REPLICANT Is Different

1. **Built for real phones:** No server, no install, no build step. One HTML file.
2. **Air-gapped by default:** Works with no API key and no internet.
3. **Token-efficient:** The on-device L3 scorer blocks attacks before spending frontier model tokens.
4. **Defensive by design:** Creates intel for defenders — it never attacks back.
5. **Transparent:** Demo data is labeled demo. Keys are never stored. Limitations are stated openly.

## Safety & Compliance By Design

- Defensive only — no hack-back, no retaliation, no process injection in the demo
- Least-privilege, reject-by-default tool sandbox
- API keys stay in tab memory only
- Designed to align with OWASP LLM Top 10 concerns: Prompt Injection, Insecure Output Handling, and Excessive Agency

## Tech Stack

Single-file HTML / CSS / JavaScript, GitHub Pages deployment, optional Meta Model API (Muse Wonder 1.0), Web Crypto for random nonces.

## Vision

Attackers are going agentic. Defense has to be agentic too — but loyal, bounded, and human-controlled.

REPLICANT is a loyal home-system defender: fast enough to meet a breach where it occurs, safe enough to clone its behavior in a sandbox, and smart enough to turn one attack into intel that protects the whole system.

**Status: v2.1 Live and Tested on Mobile**
Built from a mobile device for the Meta AI Hackathon.
