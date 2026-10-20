<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/hero-dark.png">
    <img src=".github/assets/hero.png" alt="heal.me.at landing page" width="880">
  </picture>
</p>

<h1 align="center">heal.me.at</h1>

<p align="center"><strong>Keep your own health record, and walk in with your questions ready.</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/status-in%20development-171717?style=flat-square" alt="Status: in development">
  <img src="https://img.shields.io/badge/license-source--available-404040?style=flat-square" alt="License: source-available">
  <img src="https://img.shields.io/badge/self--host-supported-525252?style=flat-square" alt="Self-host: supported">
  <img src="https://img.shields.io/badge/part%20of-me.at-737373?style=flat-square" alt="Part of me.at">
</p>

<p align="center">
  <a href="#features">Features</a> ·
  <a href="#how-it-works">How it works</a> ·
  <a href="#built-with">Built with</a>
</p>

A health history ends up scattered across portals, paper and memory, and the appointment is over before you remember the question you meant to ask. I built heal.me.at as a personal illness workbook: your conditions, symptoms, medications, visits and documents in one place, with an AI companion that reads your own records back to you, cites every entry it used, and drafts questions for your next appointment. It will not name a condition, work out a dose or recommend a treatment, and it refuses those questions before any model runs. It is self-hostable, with a local-model option so your records never leave your machine.

> **Not medical advice, and never a diagnosis.** This is an early build that has not been reviewed by a clinician or a regulator.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/overview-dark.svg">
    <img src=".github/assets/overview.svg" alt="heal.me.at at a glance: answers from your record, refusals before any model, sealed at rest, your machine and your model" width="880">
  </picture>
</p>

## Why heal.me.at

| The usual health app | heal.me.at |
| --- | --- |
| An AI that will guess at a diagnosis | Diagnosis, dosing and treatment questions are refused before any model runs |
| Answers you cannot trace | Every answer lists the entries it was drawn from |
| Your records on someone else's server | Self-host it with a local model, or run with no AI key at all |
| Scores, streaks and symptom charts | Nothing is scored, ranked or charted |
| Hard to leave | A lossless archive plus a FHIR-shaped bundle, restorable on any instance |

## Features

- **Ask your own record**: answers come only from your entries and list the entries they were drawn from. When the record does not support an answer, the companion says what is missing.
- **Questions for your next visit**: a prepare-visit mode drafts questions for your clinician, each tied to the entry that prompted it.
- **Refusals before any model**: questions about diagnosis, dosing, treatment choice or emergencies get fixed wording instead of an answer, and an activity trail logs every question and whether a model ran.
- **Local, hosted or no model**: point the companion at a model on your own machine, use a hosted one, or run with no AI key at all.
- **One searchable timeline**: conditions, allergies, journal entries, medications, visits and documents in one view, filterable by kind. Nothing is scored, ranked or charted.
- **Sealed documents and records**: every clinical field and uploaded file is encrypted before storage, and with no key configured the app refuses to write rather than storing plain text.
- **A printable Brief and calendar export**: a one-page summary to hand over at an appointment (no model involved), plus medication times and visits as a calendar file.
- **Households and care access**: keep separate records for a parent, child or partner, and let a clinician read one record through a one-time code you issue and can withdraw.
- **Export and restore**: one export produces a lossless archive and a FHIR-shaped bundle, and the archive restores into any record on any instance.

## How it works

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/flow-dark.svg">
    <img src=".github/assets/flow.svg" alt="How heal.me.at works: record, seal, ask, answer, prepare" width="880">
  </picture>
</p>

You record conditions, medications, visits and documents, and every clinical field and file is encrypted before it is stored. When you ask a question, the safety rails check it first: a refused question gets fixed wording and no model runs. Anything else is answered from your own entries, with citations, and the same record feeds the visit questions and the printable Brief.

## Built with

<p>
  <img src="https://img.shields.io/badge/Next.js-16-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16">
  <img src="https://img.shields.io/badge/React-19-171717?style=flat-square&logo=react&logoColor=white" alt="React 19">
  <img src="https://img.shields.io/badge/TypeScript-5-262626?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Tailwind%20CSS-4-404040?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS 4">
  <img src="https://img.shields.io/badge/Drizzle-Postgres-525252?style=flat-square&logo=drizzle&logoColor=white" alt="Drizzle ORM and Postgres">
  <img src="https://img.shields.io/badge/Cloudflare-R2-737373?style=flat-square&logo=cloudflare&logoColor=white" alt="Cloudflare R2">
</p>

- Next.js 16 (App Router), React 19, TypeScript
- Tailwind CSS 4
- Drizzle ORM + Postgres
- Better Auth (email and password, plus OAuth)
- oRPC + TanStack Query
- AES-256-GCM envelope encryption for records and documents
- S3-compatible object storage (Cloudflare R2) for sealed documents
- Pluggable AI driver: a local model, Anthropic, or an offline stand-in

## Part of the me.at family

heal.me.at is one of my [`*.me.at`](https://me.at) apps. They share one design system, account, and app shell. Development happens in a private monorepo; this repository is the project's public-facing home.

## License

Source-available. See [LICENSE](LICENSE).
