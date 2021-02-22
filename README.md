Linked issue: https://issuetracker.google.com/u/1/issues/180884668

### Description

If multiple permissions are requested using `RequestMultiplePermissions` and one of them is permanently denied, the map returned by `registerForActivityResult` does not contain all the requested permissions.

#### How to reproduce it
- Launch the app
- Click the button
- Allow the location permission and deny the SMS permission
- Click the button again
- Permanently deny the SMS permission (do not ask again)

The callback will be invoked only with the SMS permission.

You can also check the logcat filtering it with the tag `PermissionsResult`.