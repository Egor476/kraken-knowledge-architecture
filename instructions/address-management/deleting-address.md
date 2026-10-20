---
id: instruction.deleting_address
title: Deleting Consultation Location/Address
taxonomy:
  - deleting_address

module_dependencies:
  common:
    rules:
      - rule.address_management_access
      - rule.address_deletion_restrictions
    procedures:
      - procedure.viewing_addresses
      - procedure.deleting_address
    ui:
      - ui.settings
      - ui.addresses

  conditional:
    linked_calendar:
      rules:
        - rule.calendar_deletion_consequences
      procedures:
        - procedure.deleting_calendar
      ui:
        - ui.calendars
        - ui.calendar_options_menu
        - ui.delete_calendar

related_instructions:
  - instruction.recovering_address
  - instruction.managing_delegated_access
---
# Deleting Consultation Location/Address

## Intent

Guide users who want to delete an existing consultation location, including checking deletion restrictions and addressing a linked-calendar dependency safely.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for deletion restrictions, the core procedure, and navigation.
- Activate `linked_calendar` only when the address has a linked calendar or the user asks about removing that calendar.
- Retrieve only the module entries necessary for the user's situation.

## Decision logic

1. Identify the consultation location the user wants to delete. Distinguish deleting the address from deleting its calendar when the distinction affects the guidance.
2. Apply the retrieved deletion restrictions before providing removal steps. If a restriction blocks deletion, explain it using the relevant knowledge.
3. If the address has a linked calendar:

   - Explain that the calendar and address are separate objects and that the linked calendar blocks address deletion.
   - Retrieve the relevant calendar-deletion knowledge and explain potential consequences before any destructive steps.
   - Confirm the user's intent before recommending calendar deletion. If the consequences cannot be verified sufficiently for safe guidance, escalate rather than directing the user to proceed.
   - Do not assume that deleting an address automatically deletes its calendar.

4. If neither restriction applies, follow the address-deletion procedure. Do not invent the final deletion control or its location; acknowledge the gap if it prevents actionable guidance.
5. If access or permissions prevent progress, follow the global permissions and escalation policy without assuming that address-management access authorizes calendar deletion.

## Scope and handoffs

This instruction covers deleting an address, checking restrictions, and explaining a linked-calendar dependency. It is not a general calendar-management workflow.

For an already deleted address or a restoration request, route to the recovery instruction. For delegated-access changes, route to the delegated-access instruction.

For other changes of intent, follow the global instruction-routing policy. Use `related_instructions` as optional discovery hints, not automatic dependencies.

## Response requirements

- Prioritize the user's immediate question and explain blocking restrictions before steps.
- Give relevant destructive-action warnings before calendar-deletion guidance.
- Distinguish documented restrictions from unverified consequences and recovery claims.
- Use UI terminology from retrieved knowledge without inventing address-deletion controls or unsupported steps.
- Ask for confirmation before consequential actions when appropriate.
- Follow `kraken-global-instructions.md` for localization, permissions, uncertainty, and escalation.

## Completion

Help the user verify whether the intended address was removed using only supported knowledge; do not claim success without confirmation.

If deletion is blocked or cannot be guided safely, explain the restriction or verification gap and the appropriate next step. Do not promise restoration of the address or associated configuration.
