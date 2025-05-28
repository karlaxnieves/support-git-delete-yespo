---
title: iOS Links Handler
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
During a Mobile Push creation in the Reteno account you can specify the Link field in the form. It might be either some web page url, or deep link to the application.

<Image align="center" width="720px" src="https://files.readme.io/e9aefdd-add_link_to_push.png" />

By default Reteno SDK will open it via system method `UIApplication.shared.open(url, options: [:], completionHandler: nil)`

From Reteno SDK 1.5.5 onwards, you can add your own link handler:

```swift
Reteno.addLinkHandler { [weak self] url in
    guard
        let components = URLComponents(url: url, resolvingAgainstBaseURL: true),
        components.host == "example-app.esclick.me",
        let linkItem = UniversalLinkItem(rawValue: components.path)
    else {
        // if it's not a deep link, just open Safari
        UIApplication.shared.open(url)
        return
    }
    
    self?.applicationFlowCoordinator.handleUniversalLink(linkItem)
}
```

From Reteno SDK 1.7.2 onwards link handler has a new value in closure is `customData`. You can pass it from inApp `OPEN_URL` data sys action type.

```swift
Reteno.addLinkHandler { [weak self] url, customData in
    guard
        let components = URLComponents(url: url, resolvingAgainstBaseURL: true),
        components.host == "example-app.esclick.me",
        let linkItem = UniversalLinkItem(rawValue: components.path)
    else {
        // if it's not a deep link, just open Safari
        UIApplication.shared.open(url)
        return
    }

    self?.applicationFlowCoordinator.handleUniversalLink(linkItem)
}
```

Starting from Reteno SDK 2.0.2 onwards link handler has a single value in the closure `LinkHandler`. You can receive `url`, `customData`, and `source` - indicating from where the link handler was triggered. 

```swift
Reteno.addLinkHandler { [weak self] linkInfo in
    guard
        let components = URLComponents(url: linkInfo.url, resolvingAgainstBaseURL: true),
        components.host == "example-app.esclick.me",
        let linkItem = UniversalLinkItem(rawValue: components.path)
    else {
        // if it's not a deep link, just open Safari
        UIApplication.shared.open(url)
        return
    }

    // linkInfo.customData
    // linkInfo.source

    self?.applicationFlowCoordinator.handleUniversalLink(linkItem)
}
```

Using Universal links you have to provide your own link handler, since there is no way the link open in your app. For more information about Universal Links visit [Apple documentation](https://developer.apple.com/documentation/xcode/allowing-apps-and-websites-to-link-to-your-content).
