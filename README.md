# sf-extension-permission
This extension is to manage Android permissions on Smartface more easly.
## Install
```shell
npm i -S https://github.com/alperozisik/sf-extension-permission.git
```
## Require
```javascript
const permission = require('sf-extension-permission');
```
## Simple usage
```javascript
permission.checkPermission(Application.android.Permissions.WRITE_EXTERNAL_STORAGE, function(err) {
    if(!err) {
        //Do your work after permission is granted
    }
});
```

## Require multiple permissions once
```javascript
var requiredPermissions = [
Application.android.Permissions.WRITE_EXTERNAL_STORAGE,
Application.android.Permissions.BODY_SENSORS
];
permission.checkPermission(requiredPermissions, function(err) {
    if(!err) {
        //Do your work after permission is granted
    }
});
```

## Display custom rationale
By default this library shows rationale if user does not grant permission. This rationle text is embedded. If you want to use a different one, it is possible to provide it as second argument.
```javascript
var requiredPermissions = [
Application.android.Permissions.WRITE_EXTERNAL_STORAGE,
Application.android.Permissions.BODY_SENSORS
];
permission.checkPermission(requiredPermissions, "Your Rationale Text", function(err) {
    if(!err) {
        //Do your work after permission is granted
    }
});
```


## Localization
By default this library checks some values on the global lang variable. If they do not present, default English texts are used.
- about Display Rationale:
    - lang.**permissionRequiredTitle**
    - lang.**permissionRequiredMessage**

## Peer Dependencies
Alerts used in this extension are based on the [sf-extension-alert](https://github.com/alperozisik/sf-extension-alert)