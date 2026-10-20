---
id: instruction.managing_delegated_access
title: Managing delegated access to address and calendar settings
taxonomy:
  - receptionist

module_dependencies:
  common:
    rules:
      - rule.delegated_address_permissions
    procedures:
      - procedure.troubleshooting_receptionist_address_calendar_access
    ui:
      - ui.settings
      - ui.collapsible_navigation
      - ui.account_name_menu

related_instructions:
  - instruction.adding_address
  - instruction.editing_address
  - instruction.deleting_address
---
# Managing Delegated Access

## Intent

Help users diagnose delegated-access problems affecting address or calendar management, especially when an authorized staff member cannot find or access the relevant settings.

## Knowledge selection

Use `module_dependencies` in the YAML front matter as the candidate knowledge pool.

- Retrieve relevant `common` dependencies for supported delegated-access rules, troubleshooting, and navigation.
- Retrieve only the module entries necessary for the user's access issue.

## Decision logic

1. Identify the user's role, intended management task, and access problem only to the extent needed for accurate guidance.
2. Apply the retrieved permission rules and troubleshooting procedure to distinguish navigation or access-point issues from insufficient delegated permissions.
3. If the issue concerns calendar access, use only the calendar-related guidance actually supported by the retrieved procedure; do not assume address permissions also authorize calendar operations.
4. If the user asks to grant, modify, or create delegated access, explain the supported next step or responsible party without inventing an account-management workflow.
5. If access cannot be established safely, follow the global permissions and escalation policy.

## Scope and handoffs

This instruction covers diagnosing delegated-access problems and identifying appropriate permission-review next steps. It does not provide undocumented steps for creating accounts, granting permissions, or performing the underlying address or calendar task.

For a request to complete a separate product task, follow the global instruction-routing policy. Use `related_instructions` as optional discovery hints, not automatic dependencies.

## Response requirements

- Prioritize the access problem preventing the user's task.
- Distinguish supported address-management permissions from unspecified permissions for other operations.
- Use only documented navigation guidance and avoid inventing permission settings or administrative controls.
- Do not suggest sharing primary-account credentials or bypassing access controls.
- Follow `kraken-global-instructions.md` for localization, permissions, uncertainty, and escalation.

## Completion

Help the user identify whether the issue is resolved or requires a permission review or escalation. Do not claim that permissions were changed or access was granted without confirmation.
