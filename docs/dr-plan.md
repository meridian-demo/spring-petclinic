---
rto_minutes: 120
rpo_minutes: 30
last_reviewed: 2026-01-15
approver: engineering@meridian.dev
---

# Disaster Recovery Plan — Spring PetClinic

## Overview

This document describes the disaster recovery procedures for the Spring PetClinic service. It covers failure scenarios, recovery steps, and escalation procedures to ensure service continuity.

## Recovery Steps

1. **Detect** — Automated alerting triggers via PagerDuty on error rate spike or health check failure
2. **Assess** — On-call engineer evaluates scope of impact and determines if DR activation is needed
3. **Activate** — Follow runbook to initiate failover to secondary region or restore from backup
4. **Verify** — Confirm service health via synthetic checks and dashboard metrics
5. **Communicate** — Update status page and notify stakeholders via Slack #incidents channel

## Contact List

- **Primary On-Call**: Rotates weekly (see PagerDuty schedule)
- **Engineering Manager**: engineering@meridian.dev
- **VP Engineering**: cto@meridian.dev
- **Security Team**: security@meridian.dev

## Dependencies

- PostgreSQL (primary datastore)
- Redis (caching layer)
- External API integrations