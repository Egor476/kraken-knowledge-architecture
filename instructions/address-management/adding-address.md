---
id: instruction.adding_address
title: Adding Consultation Location/Address
taxonomy:
  - adding_address

module_dependencies:
  common:
    rules:
      - rule.address_management_access
    procedures:
      - procedure.viewing_addresses
    ui:
      - ui.settings
      - ui.addresses

  branches:
    physical:
      rules:
        - rule.physical_address_fields
        - rule.physical_address_quota
      procedures:
        - procedure.adding_physical_address
      ui:
        - ui.add_physical_consultation
        - ui.additional_information

    online:
      rules:
        - rule.online_consultation_eligibility
      procedures:
        - procedure.adding_online_consultation
      ui:
        - ui.add_online_consultation

  conditional:
    physical_limit:
      procedures:
        - procedure.checking_physical_address_limit
      ui:
        - ui.address_limit_message

    online_control_missing:
      procedures:
        - procedure.troubleshooting_online_location
      ui:
        - ui.general_add

related_instructions:
  - instruction.enabling_online_booking
  - instruction.managing_delegated_access
---
# Adding Consultation Location/Address

## Intent

Guide users through adding a physical or online consultation location to their profile, including troubleshooting issues directly related to location creation.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for shared access and navigation requirements.
- Select the `physical` or `online` branch according to the user's intent.
- Activate `conditional` dependencies only when the corresponding creation issue arises.
- Retrieve only the module entries necessary for the selected workflow.

## Decision logic

1. Identify whether the user wants to create a physical or online consultation location. Ask for clarification only if the distinction is necessary and cannot be inferred from context.
2. Apply relevant shared access requirements and use common navigation knowledge when needed.
3. For a physical consultation location:

   - Select the `physical` branch.
   - Guide the user through the relevant creation procedure.
   - Explain required and optional address information using the retrieved rules.
   - If the user cannot add another physical location, activate `physical_limit` and follow the troubleshooting procedure.

4. For an online consultation location:

   - Select the `online` branch.
   - Apply the relevant eligibility and restriction rules.
   - Guide the user through the creation procedure.
   - If the creation control is unavailable, activate `online_control_missing` and follow the troubleshooting procedure.

## Scope and handoffs

This instruction covers creating consultation locations and troubleshooting their creation.

For requests outside this scope, follow the global instruction-routing policy.

Use `related_instructions` as optional discovery hints, not as dependencies to load automatically.

## Response requirements

- Prioritize the user's immediate question.
- Provide actionable steps from the selected procedure.
- Apply only rules relevant to the user's context.
- Use UI terminology from the retrieved knowledge.
- Do not invent product restrictions, plan limits, interface controls, or unsupported steps.
- Ask clarifying questions only when they materially affect the guidance.
- Follow `kraken-global-instructions.md` for localization, uncertainty, and escalation.

## Completion

Help the user verify that the consultation location was created, using only verification guidance supported by the retrieved knowledge.

Do not introduce booking setup or other related workflows unless the user requests them.
