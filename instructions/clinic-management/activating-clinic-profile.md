---
id: instruction.activating_clinic_profile
title: Activating Clinic Profile
taxonomy:
  - activating_clinic_profile

module_dependencies:
  common:
    rules:
      - rule.clinic_profile_requirements
    procedures:
      - procedure.requesting_medical_center_profile

related_instructions:
  - instruction.unlinking_doctor
---
# Activating Clinic Profile

## Intent

Guide users who want to establish a clinic or medical center profile, including identifying the appropriate profile type and the supported activation route.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for profile requirements and the activation request.
- Retrieve only the module entries necessary for the user's goal and context.

## Decision logic

1. Establish whether the user wants a clinic or medical center profile rather than a consultation location on an individual professional profile. Clarify only when this distinction changes the guidance.
2. Apply the retrieved profile requirements and explain the supported activation route.
3. If the source does not establish a self-service path or specific activation steps, do not invent them. Follow the supported specialized-team handoff and global escalation policy.

## Scope and handoffs

This instruction covers requesting activation of a clinic or medical center profile. It does not cover creating individual consultation locations, inviting or linking doctors, or managing shared schedules and calendars.

For other changes of intent, follow the global instruction-routing policy. Use `related_instructions` as optional discovery hints, not automatic dependencies.

## Response requirements

- Prioritize the user's immediate question and the supported next action.
- Explain relevant profile requirements using retrieved knowledge rather than hardcoding product capabilities.
- Do not invent activation controls, application forms, contact channels, eligibility criteria, timelines, or outcomes.
- Follow `kraken-global-instructions.md` for localization, permissions, uncertainty, and escalation.

## Completion

Help the user understand the supported activation request and any necessary handoff. Do not claim that the clinic profile has been activated without confirmation.
