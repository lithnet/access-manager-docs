# Using variables in HTML and JSON templates
Access Manager provides a [comprehensive set of variables](audit-variables.md) you can use in your HTML and JSON audit templates.

Access Manager uses the [Handlebars](https://handlebarsjs.com/guide/) language to allow you to insert variables into templates, and even perform conditional rendering of your template, based on the contents of the audit data.

## HTML example
In this simple example, we can see reference to the `Response.Target` attribute, and some conditional rendering based on the value of `Response.IsSuccess`.

```html
<html>
<div>
    <p>Access to {{Response.Target}} was {{#if Response.IsSuccess}}granted{{else}}denied{{/if}} for {{user.FullyQualifiedName}}</p>
</div>
</html>
```
## JSON example
In this example, we can see examples of conditional rendering inside the summary and title elements, as well as the conditional addition of the `computer` section.

```json
{
  "@type": "MessageCard",
  "@context": "http://schema.org/extensions",
  "summary": "{{#if Response.IsSuccess}}✅ Access to a {{Response.TargetType}} was granted{{else}}❌ Access to a {{Response.TargetType}} was denied{{/if}}",
  "title": "{{#if Response.IsSuccess}}✅ Access to a {{Response.TargetType}} was granted{{else}}❌ Access to a {{Response.TargetType}} was denied{{/if}}",
  "sections": [
    {
      "text": "{{Response.message}}"
    },
    {
      "title": "Details",
      "facts": [
        {
          "name": "Requested access",
          "value": "{{Response.AccessTypeDescription}}"
        },
        {
          "name": "Name",
          "value": "{{user.DisplayName}}"
        },
        {
          "name": "User name",
          "value": "{{user.FullyQualifiedName}}"
        },
        {{#if Computer}}
        {
          "name": "Computer",
          "value": "{{computer.FullyQualifiedName}}"
        },
        {{/if}}
        {{#if Response.IsSuccess}}
        {
          "name": "Access expiry",
          "value": "{{Response.AccessExpiryDate}}"
        },
        {
          "name": "Matched rule",
          "value": "{{Response.MatchedRuleDescription}}"
        },
        {{/if}}
        {
          "name": "Request reason",
          "value": "{{Request.Reason}}"
        }
      ]
    }
  ]
}

```