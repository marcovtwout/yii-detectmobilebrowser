yii-detectmobilebrowser
=======================

Handles detecting mobile browsers.
Results are stored locally for caching calls within the same request, and
stored in a cookie for caching across requests.
Detection regex used from http://detectmobilebrowsers.com/

Install as an application component, in your config:

```
'components' => array(
   'detectMobileBrowser' => array(
       'class' => 'ext.yii-detectmobilebrowser.XDetectMobileBrowser',
    ),
),
```

You can get the current user preference like this:

```
if (Yii::app()->detectMobileBrowser->showMobile) {
    // do something
}
```

By default it will use the automatically detected value.
You can also set the preference yourself like this:

```
public function actionShowMobile() {
    Yii::app()->detectMobileBrowser->showMobile = true;
    $this->redirect(array('/site/index'));
}
```
