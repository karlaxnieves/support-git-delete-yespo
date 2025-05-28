---
title: Unity User Management
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity User Management | Yespo Guide
  description: >-
    The User Management module manages user data and permissions, allowing the
    setting of attributes for both registered and anonymous users through
    specific methods.
  robots: index
next:
  description: ''
---
The User Management module handles user data and permissions. It allows you to set attributes for both registered and anonymous users.

## How It Works

- **SetUserAttributes**: Use this method to assign attributes to a registered user.
- **SetAnonymousUserAttributes**: Use this method for users that are not registered.

## Code Sample

```csharp
using Reteno.Core;
using Reteno.Users;
using System.Collections.Generic;
public class UserExample : MonoBehaviour
{
    void Start()
    {
        // For a registered user:
        User registeredUser = new User
        {
            UserAttributes = new UserAttributes
            {
                // Add key-value pairs for user attributes
            },
            SubscriptionKeys = new List<string> { "news", "offers" },
            GroupNamesInclude = new List<string> { "beta_testers" },
            GroupNamesExclude = new List<string> { "trial_users" }
        };
        RetenoSDK.SetUserAttributes("external_user_id_123", registeredUser);
        // For an anonymous user:
        var anonymousAttributes = new UserAttributesAnonymous
        {
            // Set attributes for anonymous users
        };
        RetenoSDK.SetAnonymousUserAttributes(anonymousAttributes);
    }
}
```

### Additional Tips:

- Unique Identifier: Always provide a unique external user ID for registered users.
- Attribute Management: Keep user attributes up to date to improve personalization and analytics.