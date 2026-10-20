# Kraken Product Facts

> **Evidence status:** This inventory records product behavior described in the supplied Doctor–Kraken video. It is not independently verified against product code, documentation, or a live environment.

## Product rules and limitations

Subscription quotas, restrictions, permissions, dependencies:

* PR-01 | When registering a physical consultation location, adding street name, street number, and postal code is required.
* PR-02 | When registering a physical consultation location, adding floor, apartment, building, or entrance is optional.
* PR-03 | The number of physical locations per account is limited by subscription plan.
* PR-04 | One online consultation location per professional is allowed on a paid plan.
* PR-05 | Booking appointments at a new consultation location for patients is unavailable if the address has no assigned services.
* PR-06 | Booking appointments at a new consultation location for patients is unavailable if the address has no consultation hours configured in the calendar.
* PR-07 | Deleting an address is unavailable if this address has a linked calendar.
* PR-08 | Deleting an address is unavailable if this address is the only one on the profile.
* PR-09 | The consultation location in the first position in the Addresses section is considered the primary address.
* PR-10 | Changes to the public profile, including changes to the order of consultation locations, may not be updated immediately.
* PR-11 | A patient-facing profile may prioritize or filter locations by tabs according to consultation type.
* PR-12 | Only the website allows adding, editing, deleting, or reordering addresses.
* PR-13 | Calendar color can be changed through the mobile app.
* PR-14 | Turning a consultation location into a clinic requires a medical center profile.
* PR-15 | A medical center profile allows linking other doctors to the profile.
* PR-16 | A medical center profile allows administrators to coordinate the schedules of linked doctors.
* PR-17 | A medical center profile allows administrators to coordinate the calendars of linked doctors.
* PR-18 | A clinic has its own institutional profile and address.
* PR-19 | A clinic administrator can send medical facility invitation emails to doctors to link them to the clinic facilities and shared schedule.
* PR-20 | Doctors can accept clinic invitations through a link in the invitation email.
* PR-21 | An unaccepted invitation from the medical facility does not establish a clinic association.
* PR-22 | A receptionist with an appropriately permissioned delegated account can manage addresses through the website.
* PR-23 | Missing Settings access may result from insufficient delegated permissions.
* PR-24 | Reception or administration can manage calendars from a central panel.
* PR-25 | Professionals can maintain their own working hours within a clinic.
* PR-26 | Individual professional profiles are intended for one professional.
* PR-27 | A doctor already linked to a clinic cannot unlink themselves from their individual profile.
* PR-28 | Professionals cannot restore deleted addresses themselves.

## Procedures and Workflows

User actions required to accomplish tasks:

* PW-01 | To see location addresses, select Settings > Addresses.
* PW-02 | To add a physical location address, select Add physical consultation in the Addresses section.
* PW-03 | To edit an existing physical location address, locate the card for the consultation location in the Addresses section, and then select Edit Address.
* PW-04 | To add an online consultation location, select Add online consultation in the Addresses section.
* PW-05 | To update the floor number, enter the floor number in the Additional Information (Optional) field in the consultation location card.
* PW-06 | To remove an address with an active calendar, go to Settings > Calendars, select the calendar for the consultation location, select the menu at the upper right corner, and then select Delete Calendar.
* PW-07| To change the order of consultation locations, go to the Addresses section, hold down the icon on the left side of the consultation location card, and drag it to the desired position.
* PW-08 | If changes are not visible on the public profile, wait briefly and check the profile in an incognito browser window.
* PW-09 | A clinic administrator can remove the association with a doctor through the facility administration settings.
* PW-10 | After editing an address, select Save changes to save the updated details.
* PW-11 | If Add physical consultation is missing, check whether the account has reached its subscription-plan address limit and whether You cannot add more addresses appears.
* PW-12 | If Add online consultation is missing, check whether an online consultation is already registered or whether the general Add control has a different label.
* PW-13 | If patients cannot book at a new address, check whether at least one service is assigned and consultation hours are configured in its calendar.
* PW-14 | If a receptionist cannot find Settings, check whether they are using the website, whether their delegated account has permission to edit basic profile information, and whether the navigation menu is collapsed.
* PW-15 | If a doctor does not want to join a clinic and has not accepted the invitation, they can leave the invitation unaccepted.
* PW-16 | If a doctor is already linked to a clinic and wants to leave, the clinic administrator must remove the association through facility administration settings.
* PW-17 | If an address was deleted accidentally, contact support to request restoration of the address and calendar. Explain that canceled future appointments, services, and consultation hours cannot be restored automatically.

## UI elements

Navigation paths, buttons, fields, and messages:

* UI-01 | Settings | Navigation item (may appear as a gear icon or under the account name)
* UI-02 | Addresses | Navigation section
* UI-03 | Add physical consultation | Button
* UI-04 | You cannot add more addresses | Message
* UI-05 | Consultation location card | Card
* UI-06 | Edit address | Button
* UI-07 | Save changes | Button
* UI-08 | Add online consultation | Button
* UI-09 | Additional information (optional) | Field
* UI-10 | Calendars | Navigation section
* UI-11 | Gear icon | Icon associated with Settings
* UI-12 | Delete calendar | Menu action
* UI-13 | Drag handle on the left side of a consultation location card | Icon
* UI-14 | Saved successfully | Message
* UI-15 | Calendar options menu (upper right) | Menu
* UI-16 | Add (general control; label may vary) | Button
* UI-17 | Collapsible navigation menu | Navigation component
* UI-18 | Account-name menu | Menu (possible location for Settings)

## Outcomes and Side Effects

Cancellations, data loss, saved changes, recovery limitations:

* OS-01 | Selecting Save Changes in the consultation location card saves changes to an existing physical location address.
* OS-02 | Selecting Delete Calendar in the calendar menu of the Calendars section deletes this calendar.
* OS-03 | Deleting a calendar cancels future appointments.
* OS-04 | Calendar deletion does not notify affected patients.
* OS-05 | Calendar deletion removes associated services.
* OS-06 | Calendar deletion removes associated consultation hours.
* OS-07 | The history of past appointments associated with a calendar remains after deleting the calendar.
* OS-08 | The deletion of a calendar cannot be reversed.
* OS-09 | Changing the order of consultation locations results in the Saved successfully message.
* OS-11 | Future appointments canceled through calendar deletion cannot be automatically restored and must be booked again.
* OS-12 | Deleted configured services cannot be restored and must be entered again.
* OS-13 | Deleted consultation hours cannot be restored and must be entered again.

## Escalation Triggers

Cases requiring Customer Care or specialized teams:

* ET-01 | If a professional needs clarification about their account-specific address limit, Customer Care may review the account and provide guidance.
* ET-02 | Creating a medical center profile requires activation by the specialized team.
* ET-03 | The support team can restore the deleted address and its calendar.