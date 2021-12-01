# Shortcut - AHA Integration
This solution relies on separate Engineering and Product Stories in Shortcut.
As related Engineering Stories are completed, Product Stories are automatically updated.

A link is made between Aha Records and Shortcut Records based on (paramterized) name.
Certain Aha and Shortcut Data can even sync when the force_update flag is set.


## Instructions:
Create a personal `.env` from supplied `.env-template` and configure where appropriate

In Aha, navigate to Account Settings / Account / Customizations / Custom Fields.
Create two custom fields each, detailed below, for Release, Epic and Feature.
> Type: URL/Email Field // In Show Advanced Options - set key as `link`
> Type: Predefined Choice List // Add choices of `Yes` and `No` // In Show Advanced Options - set key as `force_update`

### Expected Behaviours
- Features in Aha with no corresponding equivalent in Shortcut, with `force_update` set to `Yes`, will be automatically created in Shortcut
- Descriptions of Releases, Epics, Features and Feature Requirements, with `force_update` set to `Yes`, will automatically overwite their equivalents in Shortcut


#### Notes:
- This integration relies on AHA Progress being measured via by AHA Feature completion. As a result, overall completion is not "true to size" and does not reflect effort accomplishment, and should only be used as an indicitive measure.
- If there is no Shortcut label to distinguish product tickets, one will be automatically created.
- Progress and Workflow Updates are not designed to reverse, and if that occurs may not be properly reported.

## AHA mapping to Shortcut:
- Release:Milestone
- Epic:Epic
- Feature:Story
  - url:app_url
  - Description(body):Description 
  - Requirements:Tasks
 
## AHA to Shortcut (optional):
- All Record Types
- All Record Information

## Shortcut to AHA:
- Workflow Status
