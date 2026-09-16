---
layout: default
title: "Expired Domain Workflow for Local SEO"
description: "Finding, qualifying, purchasing, and developing expired domains for local SEO projects."
---

# Expired Domain Workflow for Local SEO

## Document Overview

- **Process owner:** [Name or team]
- **Last updated:** [YYYY-MM-DD]
- **Status:** Draft
- **Related resources:** [Links to tools, templates, and reference documents]

### Purpose

Document the process for finding expired domains, evaluating their suitability, purchasing qualified domains, and preparing them for use in local SEO projects.

### Scope

This workflow covers domain discovery, qualification, purchase, setup, content production, and link building.

### Workflow Summary

Discovery → Availability check → Qualification → Baserow → Purchase → Setup → Content → Link building

### Process Standards

For each domain:

- Maintain a single record in Baserow.
- Record the source and date of each qualification check.
- Document decisions, costs, ownership, and next actions.
- Store credentials in the approved password manager.
- Use accurate business information and publish reviewed content.

## 1. Finding Domains

### 1.1. Fetching Expired Domain Lists

**Objective:** Collect candidate domains from approved sources.

**Sources and tools:**

- [Source or provider]
- [Export method or API]
- [Collection frequency]
- [Storage location]

**Procedure:**

1. Retrieve the latest domain lists.
2. Record the source and retrieval date.
3. Normalize domain names and remove duplicates.
4. Apply initial filters.
5. Save candidates for availability checks.

**Initial filters:**

- Target locations: [Criteria]
- Relevant industries or topics: [Criteria]
- Accepted extensions: [Criteria]
- Naming requirements: [Criteria]
- Exclusions: [Criteria]

**Output:** A deduplicated candidate list with source information.

### 1.2. Verifying Domain Availability

**Objective:** Confirm how each candidate can be acquired and at what cost.

**Procedure:**

1. Check the domain using [registrar, provider, or API].
2. Record its acquisition status.
3. Record the purchase price, renewal cost, and any additional fees.
4. Record relevant auction or drop deadlines.
5. Flag uncertain results for manual review.
6. Recheck availability immediately before purchase.

**Acquisition statuses:**

- Available to register
- Auction
- Backorder or pending drop
- Aftermarket purchase
- Unavailable
- Requires manual verification

**Output:** Candidates with verified acquisition paths and estimated costs.

### 1.3. Checking Backlinks and Domain History

**Objective:** Evaluate the relevance and quality of the domain's existing history.

**Tools:**

- Backlink analysis: [Tool]
- Historical website review: [Tool]
- Additional checks: [Tools]

**Review checklist:**

- [ ] Review referring domains and representative backlinks.
- [ ] Check topical and geographic relevance.
- [ ] Review anchor text distribution.
- [ ] Identify the strongest linked pages and their original URLs.
- [ ] Review live, lost, and recently acquired links.
- [ ] Inspect historical website content and previous uses.
- [ ] Flag spam, suspicious redirects, or unrelated topic changes.
- [ ] Flag potential trademark or identity conflicts.
- [ ] Record findings and supporting evidence.

**Qualification criteria:**

| Criterion | Requirement | Rejection condition |
| --- | --- | --- |
| Topical relevance | [Requirement] | [Condition] |
| Geographic relevance | [Requirement] | [Condition] |
| Backlink quality | [Requirement] | [Condition] |
| Anchor text profile | [Requirement] | [Condition] |
| Historical use | [Requirement] | [Condition] |
| Acquisition cost | [Budget] | [Condition] |

**Output:** A preliminary qualification decision with review notes.

### 1.4. Retrieving Additional Data for Qualifying Domains

**Objective:** Enrich promising candidates before making a purchase decision.

**Data to collect:**

- Available domain history and registration dates
- Referring domain and backlink counts
- Authority metrics, including provider and check date
- Estimated organic traffic and keyword visibility
- Relevant historical pages and linked URLs
- Local and topical relevance
- Acquisition and renewal costs
- Proposed project and intended use

**Procedure:**

1. Retrieve data from [tools or APIs].
2. Record the provider and timestamp for each metric.
3. Flag missing or conflicting data.
4. Apply the qualification rubric.
5. Assign a decision and document the rationale.

**Decision options:**

- Qualified
- Rejected
- Needs further review

**Output:** An enriched candidate record with a documented decision.

### 1.5. Pushing Qualified Domains into Baserow

**Objective:** Maintain a central record of qualified domains and their progress.

**Baserow configuration:**

- Workspace: [Workspace]
- Database: [Database]
- Table: [Table]
- Import method: [Manual, CSV, or API]
- Unique record key: [Normalized domain name]

**Suggested fields:**

| Field | Purpose |
| --- | --- |
| Domain | Normalized domain name |
| Source | Discovery source |
| Discovered date | Date first collected |
| Availability checked | Most recent verification timestamp |
| Acquisition method | Registration, auction, backorder, or aftermarket |
| Purchase estimate | Expected acquisition cost |
| Renewal cost | Expected recurring cost |
| Target location | Relevant geographic market |
| Niche | Relevant industry or topic |
| Qualification metrics | Selected metrics and their sources |
| Review notes | Findings, concerns, and evidence |
| Qualification decision | Qualified, rejected, or further review |
| Workflow status | Current stage |
| Assigned owner | Responsible person |
| Intended project | Planned use |
| Next action | Next task and due date |

**Procedure:**

1. Map collected data to Baserow fields.
2. Check for an existing domain record.
3. Create or update the record.
4. Attach supporting evidence or reference links.
5. Assign an owner and next action.
6. Verify that the import completed successfully.

**Output:** A complete, deduplicated Baserow record.

### 1.6. Purchasing Qualified Domains

**Objective:** Acquire approved domains and record ownership details.

**Purchase checklist:**

- [ ] Confirm qualification is complete.
- [ ] Recheck availability and final pricing.
- [ ] Confirm the intended project and budget.
- [ ] Obtain approval from [owner], if required.
- [ ] Purchase through the approved account.
- [ ] Confirm the domain appears in the registrar account.
- [ ] Configure renewal preferences and account security.
- [ ] Record the actual cost, purchase date, registrar, and expiration date.
- [ ] Save the receipt and update Baserow.

**Output:** A purchased domain ready for setup.

## 2. Domain Setup

### 2.1. Configuring DNS

**Objective:** Connect the domain to the required hosting and services.

**Procedure:**

1. Select the DNS provider.
2. Configure nameservers.
3. Add the required website and service records.
4. Choose the canonical hostname.
5. Verify DNS resolution.
6. Record the configuration in Baserow or linked technical documentation.

**Completion checklist:**

- [ ] Nameservers resolve correctly.
- [ ] Website records point to the intended host.
- [ ] Required verification records are present.
- [ ] DNS configuration is documented.

### 2.2. Configuring Email

**Objective:** Establish the email services required by the project.

**Procedure:**

1. Select the email provider.
2. Create required mailboxes or aliases.
3. Configure MX, SPF, DKIM, and DMARC records as appropriate.
4. Configure website transactional email.
5. Test sending, receiving, and contact form delivery.
6. Record account ownership and credential references.

**Output:** Working, tested email services.

### 2.3. Configuring Address and Business Details

**Objective:** Establish accurate business and contact information for the site.

**Required details:**

- Business or organization name: [Name]
- Relationship to the website: [Description]
- Physical address, if applicable: [Address]
- Service area, if applicable: [Locations]
- Phone number: [Number]
- Contact email: [Email]
- Business hours, if applicable: [Hours]

**Procedure:**

1. Confirm which business or organization the site represents.
2. Verify the contact details and permission to publish them.
3. Define where those details should appear.
4. Apply consistent information across relevant pages and settings.

**Output:** An approved set of business and contact details.

### 2.4. Setting Up Hosting

**Objective:** Provision hosting for the website.

**Procedure:**

1. Create the hosting account or site instance.
2. Attach the domain.
3. Configure HTTPS.
4. Configure backups and recovery access.
5. Configure monitoring and required security settings.
6. Verify that the site is accessible.

**Output:** A working hosting environment with HTTPS and backups.

### 2.5. Installing and Configuring WordPress

**Objective:** Prepare WordPress for content production.

**Configuration checklist:**

- [ ] Install WordPress.
- [ ] Create named administrator accounts.
- [ ] Set the site title, language, and timezone.
- [ ] Configure permalink structure.
- [ ] Configure HTTPS and canonical redirects.
- [ ] Configure search visibility for the current development stage.
- [ ] Remove default content.
- [ ] Configure media and discussion settings.
- [ ] Define a plan for relevant historical URLs.
- [ ] Verify backups and administrative access.

**Output:** A configured WordPress installation.

### 2.6. Installing Core Plugins and Theme

**Objective:** Apply the approved site foundation.

| Component | Approved tool | Configuration reference |
| --- | --- | --- |
| Theme | [Theme] | [Reference] |
| SEO | [Plugin] | [Reference] |
| Caching and performance | [Plugin or host feature] | [Reference] |
| Security | [Plugin or host feature] | [Reference] |
| Backups | [Plugin or host feature] | [Reference] |
| Forms | [Plugin] | [Reference] |
| Email delivery | [Plugin or service] | [Reference] |
| Redirects | [Plugin or host feature] | [Reference] |

**Completion checklist:**

- [ ] Install and configure approved components.
- [ ] Activate required licenses.
- [ ] Remove unused themes and plugins.
- [ ] Confirm updates and compatibility.
- [ ] Test forms, navigation, and mobile layouts.
- [ ] Record the installed components.

**Output:** A site ready for content creation.

## 3. Content Creation

### 3.1. Automated Content Research

**Objective:** Produce research briefs for relevant, useful content.

**Inputs:**

- Site purpose and audience
- Target locations and topics
- Keyword research
- Relevant historical content
- Approved sources

**Procedure:**

1. Collect topic and search intent data using [workflow].
2. Group related topics.
3. Identify local information and source material.
4. Create a content brief for each proposed page.
5. Review and prioritize the briefs.

**Brief requirements:**

- Proposed title and URL
- Intended audience and search intent
- Primary topic and related questions
- Outline
- Sources and supporting evidence
- Internal linking opportunities
- Required local details

**Output:** A reviewed content backlog.

### 3.2. Content Creation

**Objective:** Produce drafts that satisfy the approved briefs.

**Procedure:**

1. Assign a brief to [writer or automation].
2. Draft the page using the editorial guidelines.
3. Verify factual and location-specific claims.
4. Add relevant images and source references.
5. Draft metadata and internal links.
6. Submit the draft for review.

**Editorial guidelines:** [Link]

**Output:** A complete draft ready for review.

### 3.3. Content Review

**Objective:** Confirm that content is accurate, useful, and ready to publish.

**Review checklist:**

- [ ] Addresses the intended audience and search intent.
- [ ] Contains accurate, supported claims.
- [ ] Uses verified local details.
- [ ] Contains no invented business details, experiences, or testimonials.
- [ ] Provides useful, original information.
- [ ] Follows the editorial guidelines.
- [ ] Uses clear headings and readable formatting.
- [ ] Includes relevant, working links.
- [ ] Uses approved images and appropriate alt text.
- [ ] Has a final title, URL, and metadata.

**Review outcomes:**

- Approved
- Revisions required
- Rejected

**Output:** An approved draft or documented revision request.

### 3.4. Content Posting

**Objective:** Publish approved content and verify the live page.

**Procedure:**

1. Add the approved content to WordPress.
2. Apply headings, media, and page formatting.
3. Set the URL, metadata, and relevant page settings.
4. Add internal links.
5. Preview the page on desktop and mobile.
6. Publish or schedule the page.
7. Verify the live page and links.
8. Record the published URL and publication date.

**Output:** A verified live page recorded in the content tracker.

## 4. Link Building

### 4.1. Identifying Linking Targets

**Objective:** Identify relevant websites and destination domains for potential links.

**Target criteria:**

- Topical relevance: [Criteria]
- Geographic relevance: [Criteria]
- Audience usefulness: [Criteria]
- Quality requirements: [Criteria]
- Exclusions: [Criteria]

**Procedure:**

1. Identify potential target websites.
2. Review their relevance and quality.
3. Record the proposed relationship and purpose of the link.
4. Prioritize qualified opportunities.

**Output:** A reviewed list of linking targets.

### 4.2. Identifying Specific Pages for Linking

**Objective:** Select appropriate source and destination pages.

**Procedure:**

1. Identify the source page where a link could be added.
2. Identify the most relevant destination page.
3. Confirm that the destination is live and useful.
4. Define the editorial reason for the link.
5. Draft natural anchor text and placement.
6. Record the proposed link for review.

**Fields to record:**

- Source domain and URL
- Destination domain and URL
- Relevance rationale
- Proposed anchor text
- Proposed placement
- Required disclosure or link attributes
- Review status

**Output:** A page-level linking plan.

### 4.3. Adding Backlinks

**Objective:** Publish approved links and verify their implementation.

**Procedure:**

1. Confirm the placement is approved.
2. Add the link within relevant page content.
3. Apply appropriate link attributes and disclosures.
4. Publish the change.
5. Verify the destination, anchor text, and surrounding content.
6. Record the live placement and date.
7. Schedule a follow-up check.

**Completion checklist:**

- [ ] The link serves a clear reader need.
- [ ] The source and destination are relevant.
- [ ] The anchor text reads naturally.
- [ ] The destination loads correctly.
- [ ] Required attributes and disclosures are present.
- [ ] The placement is recorded in the link tracker.

**Output:** A verified link placement with a maintenance record.

## 5. Ongoing Maintenance

### Review Schedule

| Activity | Frequency | Owner |
| --- | --- | --- |
| Domain renewal review | [Frequency] | [Owner] |
| DNS, hosting, and email checks | [Frequency] | [Owner] |
| WordPress updates and backup checks | [Frequency] | [Owner] |
| Content accuracy review | [Frequency] | [Owner] |
| Broken link and placement checks | [Frequency] | [Owner] |
| Project performance review | [Frequency] | [Owner] |

### Exceptions and Troubleshooting

For each issue, record:

- Domain and affected workflow step
- Issue description
- Supporting evidence
- Assigned owner
- Resolution and date
- Any required process changes

## 6. Reference Materials

- [Approved tools and accounts]
- [Domain qualification rubric]
- [Baserow schema and field mapping]
- [Automation workflows]
- [WordPress configuration checklist]
- [Editorial guidelines]
- [Content brief template]
- [Link placement tracker]
