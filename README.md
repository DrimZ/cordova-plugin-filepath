# Repository Notice

This repository is a forked version of [hiddentao/cordova-plugin-filepath](https://github.com/hiddentao/cordova-plugin-filepath) to support the latest Android permissions, including:

- `android.permission.READ_MEDIA_IMAGES`
- `android.permission.READ_MEDIA_VIDEO`
- `android.permission.READ_MEDIA_AUDIO`

<br>

## Installation

```bash
$ cordova plugin add @dhrimz/cordova-plugin-filepath
```

<br>

---

<br><br><br>

# cordova-plugin-filepath

**PLEASE NOTE: This plugin is no longer actively maintained.**

This plugin allows you to resolve the native filesystem path for Android content
URIs and is based on code in the [aFileChooser](https://github.com/iPaulPro/aFileChooser/blob/master/aFileChooser/src/com/ipaulpro/afilechooser/utils/FileUtils.java) library.

Original inspiration [from StackOverflow](http://stackoverflow.com/questions/20067508/get-real-path-from-uri-android-kitkat-new-storage-access-framework).

## Installation

```bash
$ cordova plugin add cordova-plugin-filepath
```

## Supported Platforms

* Android

## Usage

Once installed the plugin defines the `window.FilePath` object. To resolve a
file path:

```js
window.FilePath.resolveNativePath('content://...', successCallback, errorCallback);
```

##### successCallback
Returns the ``file://`` file path.

##### errorCallback
Returns the following object:
```js
{ code: <integer>, message: <string> }
```
Possible error codes are:
* ``-1`` - describes an invalid action
* ``0`` - ``file://`` path could not be resolved
* ``1`` - the native path links to a cloud file (e.g: from Google Drive app)

## LICENSE

Apache (see LICENSE.md)
