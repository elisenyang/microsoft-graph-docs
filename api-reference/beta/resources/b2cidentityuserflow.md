---
title: "b2cIdentityUserFlow resource type"
description: "Represents a user flow within an Azure Active Directory B2C tenant."
localization_priority: Priority
doc_type: resourcePageType
ms.prod: "microsoft-identity-platform"
author: "jkdouglas"
---

# b2cIdentityUserFlow resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a user flow within an Azure Active Directory B2C tenant.

To help you set up the most common identity tasks for your applications, Azure Active Directory B2C includes predefined, configurable policies called [user flows](/azure/active-directory-b2c/user-flow-overview). A user flow lets you determine how users interact with your application when they do things like sign in, sign up, edit a profile, or reset a password. You can create many user flows of different types in your tenant and use them in your applications as needed. With user flows, you can control the following capabilities:

- Account types used for sign-in, such as social accounts like a Facebook or local account
- Attributes to be collected from the consumer, such as first name, postal code, and shoe size
- Azure Multi-Factor Authentication
- Customization of the user interface
- Information that the application receives in the token

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List user flows](../api/identitycontainer-list-b2cuserflows.md)|b2cIdentityUserFlow collection|Retrieve all B2C user flows.|
|[Get user flow](../api/b2cidentityuserflow-get.md)|b2cIdentityUserFlow|Retrieve properties of a B2C user flow.|
|[Create user flow](../api/identitycontainer-post-b2cuserflows.md)|b2cIdentityUserFlow|Create a new B2C user flow.|
|[Delete user flow](../api/b2cidentityuserflow-delete.md)|None|Delete a B2C user flow.|
|[List identity providers](../api/b2cidentityuserflow-list-identityproviders.md)|[identityProvider](../resources/identityProvider.md) collection|Retrieve all identity providers in a B2C user flow.|
|[Add identity provider](../api/b2cidentityuserflow-post-identityproviders.md)|None|Add an identity provider to a B2C user flow.|
|[Remove identity provider](../api/b2cidentityuserflow-delete-identityproviders.md)|None|Remove an identity provider from a B2C user flow.|

## Properties

|Property|Type|Description|
|:---------------|:--------|:----------|
|id|String|The name of the user flow. This is a required value and is immutable after it's created. The name will be prefixed with the value of `B2C_1_` after creation.|
|userFlowType|String|The [type of user flow](/azure/active-directory-b2c/user-flow-versions). The supported values for **userFlowType** are:<br/><ul><li>`signUp`</li><li>`signIn`</li><li>`signUpOrSignIn`</li><li>`passwordReset`</li><li>`profileUpdate`</li><li>`resourceOwnerPasswordCredentialSignIn`</li>|
|userFlowTypeVersion|Single|The version of the user flow.|

## Relationships

| Relationship       | Type  |Description|
|:---------------|:--------|:----------|
|identityProviders|[identityProvider](../resources/identityprovider.md) collection|The identity providers included in the user flow.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.b2cIdentityUserFlow",
  "optionalProperties": [],
  "keyProperty": "id"
} -->

```json
{
    "id": "String (identifier)",
    "userFlowType": "String",
    "userFlowTypeVersion": "Single",
    "identityProviders": [{"@odata.type": "microsoft.graph.identityProvider"}]
}
```