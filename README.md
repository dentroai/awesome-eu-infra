# Awesome European Infrastructure [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

> European infrastructure tools for building, deploying, and scaling software - categorized by sovereignty level.

<sup>Built and maintained by Dentro - we run <a href="https://dentro.chat">DentroChat</a> entirely on sovereign European infrastructure.</sup>

---

The US CLOUD Act allows US law enforcement to compel data access from US-owned infrastructure, regardless of where the data physically sits. Using an EU SaaS hosted on AWS Frankfurt still carries this exposure. This list makes that distinction visible so you can make informed infrastructure decisions.

### Sovereignty Tiers

| | Tier | Meaning |
|---|---|---|
| 🟢 | EU Sovereign | EU/EFTA company running on EU-owned infrastructure |
| 🟡 | EU Company, US Cloud (EU region) | EU/EFTA company on AWS/GCP/Azure, but data processed in EU data centers |
| 🔴 | EU Company, US Cloud (US region) | EU/EFTA company on US cloud infrastructure with data processed outside the EU |
| 🔵 | Self-Hostable | Open-source - deploy on your own EU infrastructure for full sovereignty |

## Contents

- [Hosting and Compute](#hosting-and-compute)
- [GPU Compute](#gpu-compute)
- [Deployment and Orchestration](#deployment-and-orchestration)
- [Payments](#payments)
- [Email Delivery](#email-delivery)
- [Email Hosting](#email-hosting)
- [AI and LLM Inference](#ai-and-llm-inference)
- [LLM Observability](#llm-observability)
- [Web Search APIs](#web-search-apis)
- [Image Generation](#image-generation)
- [Analytics](#analytics)
- [Authentication](#authentication)
- [Automation](#automation)
- [Backups](#backups)

## Hosting and Compute

- 🟢 [Hetzner](https://www.hetzner.com/) (DE) - Bare-metal servers, VPS, and block storage. Unbeatable price-to-performance ratio. Owns and operates its own data centers in Germany and around the world. We use it.
- 🟢 [Scaleway](https://www.scaleway.com/) (FR) - Full cloud ecosystem with instances, S3-compatible object storage, managed databases, and serverless. Owns its infrastructure and easy to use. We use it.
- 🟢 [OVHcloud](https://www.ovhcloud.com/) (FR) - Enterprise-grade dedicated servers and public cloud built on OpenStack. One of the largest EU-owned cloud providers, operating its own global data center network.


## GPU Compute

- 🟢 [Hetzner](https://www.hetzner.com/gpu-server) (DE) - Dedicated GPU servers at aggressive pricing. However, small GPUs (GEX44, GEX131) and setup fee required.
- 🟢 [Scaleway](https://www.scaleway.com/en/gpu-instances/) (FR) - Widest and most accessible EU-native GPU variety (H100, B300) with hourly rental.
- 🟢 [Nebius](https://nebius.com/) (NL) - Large-scale GPU clusters (H100, H200, L40S) with own infrastructure.


## Deployment and Orchestration

- 🔵 [Coolify](https://coolify.io/) - Self-hosted PaaS alternative to Heroku/Vercel. One-click install on any VPS, auto-deploy on git push, built-in SSL. The simplest way to get a fully European deployment pipeline - rent a Hetzner server, install Coolify, deploy everything from there. We use it.

## Payments

> **A note on card payments and sovereignty:** Online card payments usually flow through global card schemes (Visa, Mastercard, Amex, and others). There is currently no EU-wide card network alternative with comparable coverage. These schemes are run by non-EU entities, so EU-only processing cannot be guaranteed and CLOUD Act exposure can still apply, regardless of which EU payment provider you use. For the strongest EU-only posture, prefer [SEPA Direct Debit](https://www.europeanpaymentscouncil.eu/what-we-do/sepa-direct-debit) and other European account-to-account rails.

### Payment Service Providers

Payment Service Providers (PSPs) process payments on behalf of your company. You remain the merchant of record and handle tax/VAT yourself.

- 🟢 [Adyen](https://www.adyen.com/) (NL) - Huge EU native payment processor. However, only works with big clients (they turned us down).
- 🟡 [Frisbii](https://frisbii.com/) (DK) - Subscription billing and payment gateway. Most similar to Stripe functionality wise. Monthly fee required. Runs on AWS.
- 🟡 [Mollie](https://www.mollie.com/) (NL) - Payment and subscription billing platform popular with EU SMBs. Runs on Google Cloud. Solid pricing, less primitives than Stripe or Frisbii. We use it.
- 🟡 [Pay.nl](https://www.pay.nl/) (NL) - Dutch PSP with four own data centers in the Netherlands. All payment products developed in-house. Uses Google Cloud to facilitate the actual payment transactions. Unfortunately even smaller feature set than Mollie, doesn't handle subscriptions natively.

### Merchants of Record

Merchants of Record (MoRs) become the legal seller of your product. They handle international tax, VAT, and compliance — you receive payouts. Convenient, but adds a dependency layer.

- 🔴 [Polar](https://polar.sh/) (SE) - Open-source MoR platform for developers selling SaaS and digital products. Uses Stripe under the hood for payment processing. Because Stripe cannot guarantee EU-only processing, data can be transferred outside Europe.
- 🔴 [Creem](https://creem.io/) (EE) - MoR for SaaS and AI-native startups. Built on top of Stripe Connect for payment processing and payouts. Same constraint as above: EU-only processing cannot be guaranteed.

## Email Delivery

- 🟢 [Lettermint](https://lettermint.co/) (NL) - Transactional and marketing email API and SMTP relay, built entirely on OVHcloud. Cracked and responsive founder team. Great deliverability and pricing. We use it.
- 🟡 [Brevo](https://www.brevo.com/) (FR) - Marketing + transactional email, CRM, and SMS. Uses OVH for primary hosting but Google Cloud for backups/storage in Belgium. Has a global suppression list across domains, making it unusable for us.
- 🟡 [Mailjet](https://www.mailjet.com/) (FR) - Transactional and marketing email. Runs on Google Cloud in EU regions (Frankfurt + St. Ghislain).
- 🟡 [MailerLite](https://www.mailerlite.com/)  [MailerSend](https://www.mailersend.com/) (LT) - Email marketing / Transactional email platform. Runs on Google Cloud.

## Email Hosting

- 🟢 [Migadu](https://migadu.com/) (CH) - Practical multi-domain email hosting at flat pricing. DNS lookups resolve to OVH IP ranges in France. Great value for managing many domains and receiving emails and sending emails manually - an email inbox.
- 🟢 [Proton Mail](https://proton.me/mail) (CH) - Privacy-focused email with end-to-end encryption. Strong brand and security posture. We had issues with our email deliverability early on though.

## AI and LLM Inference

- 🟢 [Nebius AI Studio](https://nebius.com/ai-studio) (NL) - Inference platform for open-source models on Nebius-owned GPU clusters. Use a public inference endpoint or deploy your own model to the their cloud. We use it.
- 🟡 [Mistral AI](https://mistral.ai/) (FR) - The only competitive LLMs trained by a European company. Couldn't really find out what infra they run their inference on, but some sources point to Azure. We use it.
- 🟢 [Scaleway AI](https://www.scaleway.com/en/model-as-a-service/) (FR) - Managed inference on Scaleway's own GPU infra. But model quality as well as context window size is currently lackluster.

## LLM Observability

- 🔵 [Phoenix](https://phoenix.arize.com/) - Open-source LLM tracing and evaluation by Arize. Single-container deployment, lightweight and simple. Self-host on your EU cloud. We use it.
- 🔵 [Langfuse](https://langfuse.com/) - Open-source LLM tracing platform with tracing. Powerful feature set, but much heavier to self-host than Phoenix.


## Web Search APIs


- 🟡 [Linkup](https://www.linkup.so/) (FR) - Search API for AI apps with strong developer experience and top factuality benchmarks. Built on Azure. We use it.
- 🟢 [Staan](https://staan.ai/) (FR) -Search API for AI apps built by Qwant and Ecosia with its own proprietary index. Developer experience was very poor, and can't just sign up and use it. 

## Image Generation

- 🟡 [Black Forest Labs](https://blackforestlabs.ai/) (DE) - Creators of FLUX, with dedicated EU endpoint (`api.eu.bfl.ai`). EU routing is available, but underlying cloud vendor is not publicly disclosed. They didn't answer our email about their infra.

## Analytics

- 🟢 [Plausible](https://plausible.io/) (EE) - Privacy-first website analytics, hosted on Hetzner in Germany with EU-owned CDN (Bunny). Also available as self-hosted Community Edition. No cookies, no personal data collection, GDPR-compliant out of the box.

## Authentication

- 🔵 [better-auth](https://www.better-auth.com/) (US) - Open-source TypeScript authentication framework. Use with popular web frameworks such as nextjs or sveltekit. Self-host on EU infrastructure for full sovereignty - the practical alternative to Auth0/Clerk without giving up features.

## Automation

- 🟡 [Make](https://www.make.com/) (CZ) - Visual no-code automation platform. Infrastructure runs on AWS.
- 🔵 [n8n](https://n8n.io/) (DE) - Visual no-code automation platform. The cloud version runs on Azure, so self-hosting is the play here.

## Backups

- 🔵 [Duplicati](https://www.duplicati.com/) - Open-source encrypted backup to any S3-compatible storage. Pair with EU object storage (Hetzner Storage Box, Scaleway Object Storage, OVHcloud Object Storage).

## Footnotes

- Sovereignty tiers are based information available to us as of February 2026. Always verify current infrastructure details with the provider directly.
- Where possible, choose 🟢 EU Sovereign providers. Even when data stays in EU data centers, US-owned infrastructure remains subject to the CLOUD Act. Full sovereignty means your data is governed exclusively by EU law.
- Yes, we are promoting EU infrastructure on a US-owned platform. GitHub is still where European developer eyes are - so we meet the community where it is, while advocating for the stack behind it to be European.
- Contributions welcome! Read the [contributing guidelines](contributing.md) first.
