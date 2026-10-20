---
article_title: troubleshooting_consultation_location_management
article_id: location_troubleshooting
article_type: internal
language: en
audience: support_specialist
taxonomy:
- address_management
- calendar_management
source_dependencies:
  sections:
  - heading: Scope and initial diagnosis
    modules:
    - rule.address_management_access
    - rule.delegated_address_permissions
    - procedure.viewing_addresses
    - procedure.troubleshooting_receptionist_address_calendar_access
    - ui.settings
    - ui.addresses
    - ui.collapsible_navigation
    - ui.account_name_menu
  - heading: Address creation problems
    modules:
    - rule.physical_address_fields
    - rule.physical_address_quota
    - rule.online_consultation_eligibility
    - rule.subscription_limit_escalation
    - procedure.adding_physical_address
    - procedure.adding_online_consultation
    - procedure.checking_physical_address_limit
    - procedure.troubleshooting_online_location
    - ui.add_physical_consultation
    - ui.add_online_consultation
    - ui.address_limit_message
    - ui.general_add
  - heading: Booking unavailable at a new consultation location
    modules:
    - rule.online_booking_prerequisites
    - procedure.enabling_booking_at_address
  - heading: Address deletion blocked
    modules:
    - rule.address_deletion_restrictions
    - rule.calendar_deletion_consequences
    - procedure.deleting_address
    - procedure.deleting_calendar
    - ui.calendars
    - ui.calendar_options_menu
    - ui.delete_calendar
  - heading: Accidental deletion and restoration
    modules:
    - rule.deletion_recovery_limits
    - rule.address_recovery_support
    - rule.calendar_deletion_consequences
    - procedure.recovering_deleted_address
  - heading: Address changes not visible on the public profile
    modules:
    - rule.primary_address_order
    - procedure.reordering_addresses
    - procedure.checking_profile_updates
    - ui.address_drag_handle
    - ui.saved_successfully
  - heading: Delegated access issues
    modules:
    - rule.delegated_address_permissions
    - rule.address_management_access
    - procedure.troubleshooting_receptionist_address_calendar_access
    - ui.settings
    - ui.collapsible_navigation
    - ui.account_name_menu
  - heading: Escalation and handoff
    modules:
    - rule.subscription_limit_escalation
    - rule.address_recovery_support
    - rule.deletion_recovery_limits
    - rule.delegated_address_permissions
    - procedure.checking_physical_address_limit
    - procedure.recovering_deleted_address
    - procedure.troubleshooting_receptionist_address_calendar_access
---
# Troubleshooting Consultation Location Management

This article provides diagnostic guidance for resolving issues related to adding, editing, reordering, deleting, and restoring consultation locations on Doctoralia.

Use it to identify the cause of a reported issue, determine the appropriate next steps, and recognize cases that require assistance from Customer Care or another support specialist.

## Scope and initial diagnosis

### Initial Diagnosis

Before troubleshooting a consultation location issue, establish the user's intended action and access context.
1. **Identify the requested action.** Determine whether the user wants to add, edit, reorder, delete, or restore a consultation location.
2. **Identify the location type.** Confirm whether the issue concerns a physical consultation location or an online consultation.
3. **Confirm the access method.** Ask whether the user is accessing Doctoralia through the website or mobile app.
4. **Check navigation access.** Confirm whether the user can open **Settings** > **Addresses**.
5. **Identify the user's role.** Determine whether the person is managing their own professional profile or using a delegated account.

### Resolution

Adding, editing, deleting, and reordering consultation locations are supported through the Doctoralia website, not the mobile app.

If the user is accessing Doctoralia through the mobile app, direct them to the website and **Settings** > **Addresses**.

If the user is using the website but cannot access **Settings**, determine whether the issue concerns navigation visibility or delegated permissions. Continue with Delegated access issues for detailed troubleshooting when applicable.

Otherwise, proceed to the section corresponding to the user's intended action.

### Escalation

If the user cannot access the required section after completing the relevant access checks, refer the unresolved issue to the support team.

## Address creation problems

### Initial Diagnosis

Determine which creation problem the user is experiencing.

**Physical consultation location cannot be added**

Check the following:
- Confirm that the user is accessing **Settings** > **Addresses** on the website.
- Check whether **Add physical consultation** is available.
- Ask whether **You cannot add more addresses** appears.
- Determine whether the account-specific address limit needs clarification.

**Online consultation location cannot be added**

Check the following:
- Check whether the professional already has an online consultation location.
- Look for **Add online consultation** or a general Add control.
- Confirm whether the account has a paid subscription before applying the documented paid-plan allowance.

**Physical address form cannot be completed**

Check whether the user has entered the required address fields:
- Street name
- Street number
- Postal code

Floor, apartment, building, and entrance details are optional.

### Resolution

**Physical consultation location:** Explain that the number of locations permitted depends on the subscription plan. Do not provide an unconfirmed numerical limit.

**Online consultation location:** Explain that paid plans allow one online consultation location per professional. If one already exists, this may explain why the option to create another is unavailable.

**Incomplete physical address:** Guide the user to enter the required fields and, if relevant, additional location details. The source material does not establish other mandatory fields.

### Escalation

Refer the case to Customer Care when the account's physical-address limit is unclear or requires account-specific review.

Refer unresolved online consultation eligibility or creation issues to the support team.

## Booking unavailable at a new consultation location

### Initial Diagnosis

If patients cannot book appointments at a newly added consultation location, check the following:
- Confirm that the consultation location has been added to the professional's profile.
- Check whether **at least one service** is assigned to that location.
- Check whether **consultation hours** are configured for the location in its calendar.

### Resolution

If no service is assigned, instruct the user to configure at least one service for the location.

If consultation hours are missing, instruct the user to configure the relevant hours in the calendar.

Explain that both requirements must be met before patients can book appointments at the new location.

### Escalation

If both prerequisites are configured but booking remains unavailable, refer the issue to support for further investigation.

## Address deletion blocked

### Initial Diagnosis

If the user cannot delete a consultation location, the following restrictions may prevent deletion:
- The location is the only address on the professional's profile.
- A calendar is still linked to the location.

To identify the cause:
- Confirm that the user is managing the location through **Settings** > **Addresses** on the website.
- Determine whether the location is the only registered address.
- Determine whether the location has a linked calendar.

### Resolution

**If the location is the only address:**

Explain that the only address on a professional profile cannot be deleted. Do not suggest bypassing this restriction.

**If a calendar is linked to the location:**

Explain that the calendar must be deleted before the address can be removed.

Before proceeding, explain the consequences of deleting the calendar:
- Future appointments associated with the calendar are canceled.
- Affected patients are not notified automatically.
- Associated services and consultation hours are deleted.
- Past appointment history is preserved.
- Calendar deletion cannot be undone through the normal workflow.

Confirm that the user understands these consequences and wants to proceed.

If they choose to continue:
1. Open **Settings** > **Calendars** on the website.
2. Select the calendar linked to the consultation location.
3. Open the options menu in the upper-right corner.
4. Select **Delete calendar**.

After deleting the calendar, direct the user back to **Settings** > **Addresses** to continue removing the location, provided no other restriction applies.

### Escalation

If neither documented restriction explains why the address cannot be deleted, refer the issue to the support team.

## Accidental deletion and restoration

### Initial Diagnosis

If the user accidentally deleted a consultation location or its calendar, establish:
- Whether the address, its calendar, or both were deleted.
- Whether future appointments were associated with the deleted calendar.
- Whether services and consultation hours were configured for that location.

### Resolution

Explain that professionals cannot restore deleted addresses themselves. Restoration requires assistance from the support team.

The support team may be able to restore the deleted address and calendar. However, restoration does not automatically recover all associated information:
- Canceled future appointments must be booked again.
- Deleted services must be configured again.
- Deleted consultation hours must be configured again.

Do not promise that restoration will recover canceled appointments or deleted configuration.

### Escalation

Support team assistance is required for restoration requests.

Include the affected consultation location, the items reported as deleted, and whether the user needs assistance with appointments, services, or consultation hours.

## Address changes not visible on the public profile

### Initial Diagnosis

If the user reordered consultation locations but the public profile still shows the previous order, consider the following possible causes:
- The change has not yet appeared on the public profile.
- The patient-facing profile groups or prioritizes locations by consultation type.
- The reordering action was not saved successfully.

To investigate:
1. Confirm that the user reordered locations through **Settings** > **Addresses**.
2. Check whether they used the drag handle on the left side of the location card.
3. Ask whether **Saved successfully** appeared.
4. Confirm which location is now first in the **Addresses** list.
5. Ask the user to open their public profile in a private or incognito browser window.

### Resolution

Explain that the first location in the **Addresses** list is considered the primary address.

Public-profile changes may take time to appear. The patient-facing view may also group locations by consultation type, affecting their visible order.

Recommend waiting for the update and checking the public profile again in an incognito window.

Incognito mode helps verify what is publicly displayed; it does not accelerate the update.

### Escalation

If the change was saved but the expected result remains absent after allowing time for the update, refer the issue to the support team.

## Delegated access issues

### Initial Diagnosis

If a receptionist or delegated user cannot access **Settings** or manage consultation locations, check if:
- The user is accessing Doctoralia through the mobile app.
- The navigation menu is collapsed.
- **Settings** appears under the account-name menu.
- The delegated account lacks permission to edit basic profile information.

To investigate:
1. Confirm that the receptionist is using the Doctoralia website.
2. Check whether the navigation menu is collapsed.
3. Check whether **Settings** is available through the account-name menu.
4. Determine whether the delegated account has permission to edit basic profile information.

### Resolution

A receptionist with appropriate delegated permissions can manage consultation locations through the Doctoralia website.

If **Settings** is not visible, first check whether the navigation menu is collapsed or whether the option appears under the account-name menu.

If the delegated account lacks the necessary permissions, ask the person responsible for managing delegated access to review them.

The receptionist should use their own authorized delegated account rather than the professional's primary-account credentials.

### Escalation

If the required permissions appear to be present but access remains unavailable, refer the issue to the support team.

## Escalation and handoff

### Initial Diagnosis

Determine whether the case:
- Requires an account-specific subscription or eligibility review.
- Involves a deleted address or calendar requiring restoration.
- Remains unresolved after the documented troubleshooting checks.
- Requires a permissions review beyond the user's available access.

Before escalating, confirm which checks have already been completed and whether the issue falls outside the documented self-service procedures.

### Resolution

Use the appropriate routing guidance:

| Situation                                                                       | Recommended action                                        |
| :------------------------------------------------------------------------------ | :-------------------------------------------------------- |
| Physical consultation location limit is unclear                                 | Refer to Customer Care for account-specific clarification |
| Online consultation option remains unavailable after basic checks               | Refer to the support team for eligibility clarification  |
| Booking remains unavailable despite assigned services and consultation hours    | Refer to the support team for further investigation      |
| Address deletion remains blocked without a documented restriction               | Refer to the support team                                 |
| Address or calendar was deleted accidentally                                    | Request support-assisted restoration                      |
| Public-profile changes remain absent after saving and allowing time for updates | Refer to the support team                                 |
| Delegated user cannot access **Settings** despite appropriate permissions | Refer to the support team                                 |

When handing off a case, include the relevant details:
- The user's intended action and observed problem.
- Whether the affected location is physical or online.
- Whether the user is accessing the website or mobile app.
- Any visible error messages or unavailable controls.
- The troubleshooting checks already completed.
- Relevant subscription or delegated-permission questions.
- For deletion or restoration cases, the affected address, calendar, and reported impact on appointments or configuration.

### Escalation

Refer the case to the appropriate support team when self-service troubleshooting is insufficient or the required action cannot be performed by the professional.

Before guiding a user through a destructive action, explain its consequences and confirm that the user intends to proceed.

Do not promise an account-specific outcome, successful restoration, or an undocumented workaround.

When the available knowledge does not establish a complete resolution, explain the limitation and route the case to the support team.
