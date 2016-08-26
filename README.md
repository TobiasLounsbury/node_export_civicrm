# node_export_civicrm

This is a drupal module that interfaces with [node_export](https://www.drupal.org/project/node_export) and webform.
It does translation between CiviCRM Ids and names. 
On export it translates form keys such as 
`civicrm_1_contact_1_cg18_custom_67`
to an encoded format like 
`CIVICRM_NODE_EXPORT:CUSTOM:civicrm_1_contact_1:ExtraStudentData:StudentFavoriteSubject:18:67`

On import it attempts to do a lookup based on name and if found, returns the corresponding ids. If not found it returns the correctly formatted form key with the old ids.

##Currently Supported

- Custom Data
  - Contact Custom Data
  - Activity Custom Data
  - Relationship Custom Data
  - Any other Custom data that uses the `civicrm_.*_cg[0-9]_custom[0-9]` form key format (Though these are untested)
- Activity Types
- Relationship Types
- Case Types (Within an Activity)

## Known Limitations

1. It only works when you export a webform to JSON format.
2. It does not currently support:
  - Grants
  - Memberships
  - Contributions
  - Events
  - Creating Cases (As it's own Entity)
