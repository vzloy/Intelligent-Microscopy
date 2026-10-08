<p align="center">
  <strong>🔬 Intelligent-Microscopy</strong><br>
  <em>LLM-assisted experiment planning for advanced bioimaging and tissue imaging</em>
</p>

<p align="center">
  <a href="#quick-start">Quick Start</a> •
  <a href="#systems">Systems</a> •
  <a href="#what-can-the-llm-help-with">Capabilities</a> •
  <a href="#try-it-now">Try It Now</a> •
  <a href="#methodology">Methodology</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/systems-4_microscopes-blue" alt="Systems">
  <img src="https://img.shields.io/badge/vendors-Leica_%7C_Nikon_%7C_Zeiss-green" alt="Vendors">
  <img src="https://img.shields.io/badge/licence-CC_BY_4.0-lightgrey" alt="Licence">
  <img src="https://img.shields.io/badge/platform-any_LLM-orange" alt="Platform">
</p>

---

Every microscope session starts with the same questions: *Which objective? Which laser lines? Will this even work on this system?*

**Intelligent-Microscopy** gives you structured reference files that describe the complete hardware configuration of advanced imaging systems — every objective, laser, detector, filter and acquisition module. Upload a file to any LLM and get answers grounded in the actual hardware before you sit down at the microscope.

> [!NOTE]
> This is a planning tool, not a replacement for hands-on training or facility staff. It helps you arrive at your session better prepared.

---

## Quick Start

```mermaid
flowchart LR
    A["📥 Download\n.md file"] --> B["🤖 Upload to\nany LLM"]
    B --> C["💬 Ask about\nyour experiment"]
    C --> D["🔬 Book your\nsession"]
    style A fill:#4A90D9,color:#fff,stroke:none
    style B fill:#7B61FF,color:#fff,stroke:none
    style C fill:#E5A100,color:#fff,stroke:none
    style D fill:#2ECC71,color:#fff,stroke:none
```

**1.** Pick a microscope below and download its `.md` reference file

**2.** Upload it to [Claude](https://claude.ai), [ChatGPT](https://chat.openai.com), [Gemini](https://gemini.google.com) or any other LLM

**3.** Ask your question — the LLM will cross-check your plan against the real hardware

> [!TIP]
> Upload **all** the reference files at once and ask *"Which system is best for my experiment?"* — the LLM will compare across microscopes and recommend one.

---

## Systems

Reference files are organised by vendor:

```
Intelligent-Microscopy/
├── Leica/
│   ├── HCF2.md — STELLARIS 8 (confocal)
│   └── HCF3.md — STELLARIS 8 Tau-STED FALCON (FLIM / STED nanoscopy)
├── Nikon/
│   └── HCF4.md — AX R MP NSPARC (confocal / multiphoton)
└── Zeiss/
    └── HSR1.md — Lattice SIM 5 (super-resolution SIM)
```

| System | Vendor | Modalities | File |
|--------|--------|-----------|------|
| **HCF2** — STELLARIS 8 | Leica | Confocal, spectral detection | [✅ Download](Leica/HCF2.md) |
| **HCF3** — STELLARIS 8 Tau-STED FALCON | Leica | Confocal, STED super-resolution, FLIM | [✅ Download](Leica/HCF3.md) |
| **HCF4** — AX R MP NSPARC | Nikon | Confocal, resonant, multiphoton, FLIM, FRET, SHG, ISM super-resolution | [✅ Download](Nikon/HCF4.md) |
| **HSR1** — Lattice SIM 5 | Zeiss | Lattice SIM, SIM Apotome, widefield | 🔜 Coming soon |

---

## Living Documents

These reference files are **not static spec sheets**. Every file carries a version timestamp (date and time) and is updated continuously to reflect:

- 🧑‍🔬 **Real-world experience** — lessons from student training sessions, facility projects and day-to-day use shape what goes into the files: common mistakes, non-obvious settings, practical tips that don't appear in any manual
- 🔬 **Instrument behaviour** — hardware changes, filter swaps, new objectives, firmware updates and observed instrument quirks are recorded as they happen
- 🤖 **LLM model development** — as language models evolve, we revise file structure, terminology and level of detail to get the most reliable reasoning from current-generation models

> [!IMPORTANT]
> Always download the latest version before starting a new project. Check the version timestamp at the top of each file — if your copy is more than a few weeks old, it may not reflect the current state of the instrument.

---

## What can the LLM help with?

### 🟢 Before your session
> Design the experiment before you book
- Check feasibility on a particular microscope
- Choose objectives, laser lines and detection paths for your fluorophores
- Estimate acquisition time for tiling, Z-stacks and time-lapse
- Design automated acquisition workflows
- Compare two microscopes for your application

### 🟡 During your session
> Quick answers while you're at the microscope
- Troubleshoot dim or noisy images
- Look up filter specs, detector ranges or laser lines
- Identify unexpected signals — autofluorescence? bleed-through?

### 🔵 After your session
> Process, document and publish
- Plan an analysis pipeline for your data
- Draft a methods section describing your acquisition
- Calculate scale bars from acquisition metadata

---

## Try It Now

Copy and paste any of these into your LLM after uploading a reference file:

<details>
<summary><strong>🟢 Getting started</strong> — any experience level</summary>

```
I have a tissue section stained with DAPI and Alexa Fluor 488.
Which system should I use and how do I set it up?
```
</details>

<details>
<summary><strong>🟡 Tiling experiment</strong> — planning acquisition time</summary>

```
Can I tile a whole mouse kidney section at 20× on HCF2 with
a Z-stack, and how long will it take?
```
</details>

<details>
<summary><strong>🔴 Advanced</strong> — multiphoton FLIM</summary>

```
I want to do two-photon FLIM of NAD(P)H and FAD on HCF4.
Which detector path gives me the best photon budget for
phasor analysis?
```
</details>

<details>
<summary><strong>🔵 Comparing systems</strong> — choosing between microscopes</summary>

```
I need to image live organoids deeper than 200 µm with
subcellular resolution. Compare HCF4 multiphoton and
HSR1 lattice SIM for this application.
```
</details>

---

## Methodology

This project follows four principles for building instrument reference files that LLMs can reliably reason over:

| Principle | Rule |
|-----------|------|
| **Precision over assumption** | Specifications are never inferred. If verified data is unavailable, the field is left blank. |
| **Source priority** | The equipment quotation reflecting the installed configuration takes precedence over manufacturer websites. |
| **Completeness over token economy** | Reference files are as comprehensive as possible. Context-window cost is negligible compared to failed experiments and wasted samples. |
| **Explicit limitations** | Every file flags what the system *cannot* do — critical for correct LLM reasoning across instruments. |

---

## Limitations

> [!CAUTION]
> Responses may contain errors, omit important constraints or suggest inappropriate settings. Always verify recommendations against the original documentation and discuss with facility staff when in doubt.

- The LLM **cannot control any microscope** or acquire images
- It does **not know the live state** of the hardware (mounted objectives, incubator status, laser warm-up)
- It **cannot replace training** — especially for laser safety, alignment and system-specific procedures
- It does **not have access** to your sample's actual brightness or labelling efficiency

---

## Collaboration

This is a methodological and research project exploring how LLMs can serve as advisory tools in advanced imaging environments.

We are particularly interested in collaboration with **Nikon** on extending LLM-assisted workflows for the AX R MP NSPARC platform and related systems.

We welcome contributions from:
- 🏛️ **Microscopy facilities** — adapt these reference files for your own instruments
- 🔧 **Instrument manufacturers** — improve accuracy and coverage
- 🧪 **Researchers** — share use cases, report errors, suggest improvements

To contribute, please [open an issue](../../issues) or get in touch.

---

## Acknowledgements

Developed at the **Facility for Imaging by Light Microscopy (FILM)**, Imperial College London.

---

## Licence

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to share and adapt this material for any purpose, including commercial use, provided you give appropriate credit.

---

<sub>All outputs are advisory only. Experimental decisions remain the responsibility of trained facility staff and researchers. Pricing, personal identifiers and contact information have been removed from all reference material.</sub>
