---
id: instruction.enabling_online_booking
title: Enabling Online Booking
taxonomy:
  - enabling_online_booking

module_dependencies:
  common:
    rules:
      - rule.online_booking_prerequisites
    procedures:
      - procedure.enabling_booking_at_address

related_instructions:
  - instruction.adding_address
---
# Enabling Online Booking

## Intent

Help users understand why patients cannot book appointments at a consultation location and identify the supported prerequisites for enabling booking.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for booking prerequisites and the supported diagnostic procedure.
- Retrieve only the module entries necessary for the user's question.

## Decision logic

1. Identify the consultation location and whether the user wants to enable patient booking or troubleshoot unavailable booking. Clarify only when the distinction affects the guidance.
2. Apply the retrieved prerequisites and guide the user through the supported checks.
3. If a prerequisite is missing, explain what needs to be configured without inventing controls or a configuration workflow not present in the knowledge.
4. If the prerequisites appear satisfied but booking remains unavailable, or the user needs exact setup steps not documented in the knowledge, acknowledge the gap and follow the global escalation policy.

## Scope and handoffs

This instruction covers patient-booking prerequisites and related troubleshooting at a consultation location. It does not cover creating consultation locations, configuring services or consultation hours step by step, or assuming that online consultations and patient online booking are the same feature.

For other changes of intent, follow the global instruction-routing policy. Use `related_instructions` as optional discovery hints, not automatic dependencies.

## Response requirements

- Prioritize the user's immediate question and the next supported check.
- Distinguish documented prerequisites from unverified setup or activation behavior.
- Do not invent interface labels, configuration steps, eligibility requirements, or booking outcomes.
- Follow `kraken-global-instructions.md` for localization, permissions, uncertainty, and escalation.

## Completion

Help the user determine whether the documented prerequisites are satisfied. Do not claim that patient booking is enabled without supported confirmation.
