---
id: instruction.editing_address
title: Editing Consultation Location/Address
taxonomy:
  - editing_address

module_dependencies:
  common:
    rules:
      - rule.address_management_access
    procedures:
      - procedure.viewing_addresses
      - procedure.editing_address
    ui:
      - ui.settings
      - ui.addresses
      - ui.consultation_location_card
      - ui.edit_address
      - ui.save_changes
      - ui.additional_information

  conditional:
    delegated_access:
      rules:
        - rule.delegated_address_permissions
      procedures:
        - procedure.troubleshooting_receptionist_address_calendar_access

related_instructions:
  - instruction.reordering_addresses
  - instruction.managing_delegated_access
---
# Editing Consultation Location/Address

## Intent

Guide users through updating the details of an existing consultation location, including supported supplementary address information.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for the requested edit and navigation guidance.
- Activate `delegated_access` only when the user's role, missing navigation, or permissions affect the task.
- Retrieve only the module entries necessary for the selected workflow.

## Decision logic

1. Identify the existing consultation location and the detail the user wants to change. Ask a targeted question only if the requested edit is unclear or its availability is not established.
2. Confirm the supported access point and guide the user through the editing procedure, using retrieved UI labels.
3. For supplementary location details covered by the procedure, direct the user to the relevant field. Do not extrapolate from this example to an unsupported list of editable fields.
4. Guide the user to save the change using the documented editing control.
5. If the user cannot find the relevant settings or edit control, apply the access-point rule and, when relevant, the delegated-access troubleshooting procedure. Escalate if the required capability or permission cannot be confirmed.
6. If the requested field or change is not supported by the retrieved knowledge, state the limitation rather than inventing a control or workflow.

## Scope and handoffs

This instruction covers changing existing consultation-location details. Reordering locations, adding or deleting addresses, calendar configuration, and patient booking setup are separate tasks.

For requests to change location order, use the related reordering instruction. For delegated-permission changes, use the delegated-access instruction. Route other intent changes according to the global instruction-routing policy.

Use `related_instructions` as optional discovery hints, not dependencies to load automatically.

## Response requirements

- Prioritize the user's requested edit and give concise, actionable steps from the retrieved procedure.
- Apply access-point and permission restrictions only where relevant.
- Use supported UI terminology; do not invent editable fields, controls, or configuration steps.
- Distinguish an unconfirmed capability from an unavailable one.
- Ask clarifying questions only when they materially affect the guidance.
- Follow `kraken-global-instructions.md` for localization, uncertainty, and escalation.

## Completion

Help the user verify that the edited details were saved, using the supported editing workflow. Do not assume the change is publicly visible immediately or claim to have saved it on the user's behalf.

Do not introduce address reordering, booking setup, or other workflows unless the user requests them.
