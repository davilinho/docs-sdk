---
id: introduction
title: Introduction
---

In this page you will find how to integrate our widget to your website quickly and easily. **It requires the registration of your patients beforehand** so that they can start using the widget.

You can check our [API Reference](/docs/patients) for more details on how to register your patients.

## Integration

In order to integrate the widget you will have to add the following scripts to your page.

```html
<script
  type="text/javascript"
  src="https://widget.mediquo.com/js/1.0.0/mediquo.js"
></script>
```

You will also have to initialize our widget with your Api Key and the access token of your patient.

```html
<script>
  window.onload = () => MediquoWidget.init({
    apiKey: <YOUR-API-KEY>,
    accessToken: <USER-ACCESS-TOKEN>,
  });
</script>
```

## Options

### `apiKey`

Required.
The API Key of your organization. [How to get an API Key](/docs/introduction#step-1-apply-and-receive-approval-for-your-organization)

### `accessToken`

Required.
Access Token issue by mediQuo server to authenticate your patient.

### `theme`

Optional. Default: {}
Use this option to customize the widget to match your organization colors. You can find more about widget [customization](/docs/sdk/widget/colors).

## Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title></title>
  </head>
  <body>
    <script
      type="text/javascript"
      src="https://widget.mediquo.com/js/1.0.0/mediquo.js"
    ></script>
    <script>
      window.onload = () => MediquoWidget.init({
        apiKey: <YOUR-API-KEY>,
        accessToken: <USER-ACCESS-TOKEN>,
      });
    </script>
  </body>
</html>
```