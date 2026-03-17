topic_id: SERVICE-SEARCH-01
title: service-search: Sovereign Inverted Index
tier: Tier-5-Service
category: Service-Logic
tags: [search, inverted-index, tantivy, darp, files-over-databases]
abstract: |
  A static, binary indexing engine built in Rust (Tantivy). Provides microsecond search retrieval across millions of files without utilizing active database software, guaranteeing DARP compliance.
details:
  human_narrative: |
    Instead of using heavy databases that lock your data into a vendor's system, we use an Inverted Index. It acts like the index at the back of a textbook: a tiny, highly compressed map that tells the system exactly which file contains the word you are looking for, allowing the entire archive to be copied to a USB drive and searched instantly on any machine.
links: [TOTEBOX-01, OS-WORKPLACE-01, SYS-CONTRACTS-01]
