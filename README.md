yii-detectmobilebrowser
=======================

Handles detecting mobile browsers. Results are stored locally for caching calls within the same request, and
stored in a cookie for caching across requests.

Detection regex used from http://detectmobilebrowsers.com/

## Requirements

Tested on Yii 1.1.8 - 1.1.14, should work on all versions.

## Installation

Install as an application component, in your config:

```php
'components' => array(
   'detectMobileBrowser' => array(
       'class' => 'ext.yii-detectmobilebrowser.XDetectMobileBrowser',
    ),
),
```

## Usage

You can get the current user preference like this:

```php
if (Yii::app()->detectMobileBrowser->showMobile) {
    // do something
}
```

By default it will use the automatically detected value.
You can also set the preference yourself like this:

```php
public function actionShowMobile() {
    Yii::app()->detectMobileBrowser->showMobile = true;
    $this->redirect(array('/site/index'));
}
```
