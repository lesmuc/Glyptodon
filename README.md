> 🚧🚧🚧 This is work in progress 🚧🚧🚧

# Glyptodon, a UI widget for displaying 'no content' message in iOS

This is a UI element for iOS that shows a 'no content' message over an existing view. It can be used to show a missing content message and suggest an action.

For example, consider we have an ecommerce app with a shopping cart screen that shows a list of products. If the user goes to the empty cart screen we can show a "Cart is empty" message and a "Search" button.

<img src='https://raw.githubusercontent.com/exchangegroup/Glyptodon/master/Graphics/screenshots/glyptodon_ios_screenshot_2.png' width='320' alt='Glyptodon iOS message view example'>


## Setup

There are three ways you can add Glyptodon to your project.

**Add source (iOS 7+)**

Simply add [GlyptodonDistrib.swift](https://github.com/exchangegroup/Glyptodon/blob/master/Distrib/GlyptodonDistrib.swift) file into your Xcode project.

**Setup with Carthage (iOS 8+)**

Add `github "exchangegroup/Glyptodon" ~> 2.0` to your Cartfile and run `carthage update`.

**Setup with CocoaPods (iOS 8+)**

If you are using CocoaPods add this text to your Podfile and run `pod install`.

    use_frameworks!
    pod 'Glyptodon', '~> 2.0'

## Usage

Add `import Glyptodon` to your source code if you used Carthage or CocoaPods setup methods.

Glyptodon is an extension of UIView class. You can reach it by using using the `glyptodon` property in any instance of UIView or its subclass. It can be, for example, the `view` property of your view controller.


### Show and hide message view


```Swift
view.glyptodon.show("No new messages")
view.glyptodon.hide()

// Show message with a button
view.glyptodon.show("Cart is empty", withButton: "Go shopping") {
  // Do something when the button is tapped.
}
```

### Styling

Set `glyptodon.style` property to style the view **before** it is shown. See the [styling manual](https://github.com/exchangegroup/Glyptodon/wiki/Styling) for the complete list of configuration options.

```Swift
// Set the view background color
view.glyptodon.style.view.backgroundColor = GlyptodonColor.fromHexString("#EEEEEE")

// Set the title font
view.glyptodon.style.title.font = UIFont.preferredFontForTextStyle(UIFontTextStyleTitle1)

// Set the title color
view.glyptodon.style.title.color = GlyptodonColor.fromHexString("#666666")

// Set the button font
view.glyptodon.style.button.font = UIFont.preferredFontForTextStyle(UIFontTextStyleBody)

// Set the button color
view.glyptodon.style.button.color = GlyptodonColor.fromHexString("#007AFF")

// Set the button color
view.glyptodon.style.button.colorHighlighted = GlyptodonColor.fromHexString("#007AFF33")
```

### Unit testing

Sometimes it is useful to verify the presence of the message view and its content in the unit test. The library provides the following helper properties to make unit testing easier.

```Swift
// Indicates if the view is currently visible
view.glyptodon.visible

// Returns the currently displayed title label
view.glyptodon.title

// Returns the currently displayed button
view.glyptodon.button
```

## Demo

This project includes a demo iOS app.

<img src='https://raw.githubusercontent.com/exchangegroup/Glyptodon/master/Graphics/screenshots/glyptodon_demo_ios_app.png' alt='Glyptodon demo iOS app' width='320'>

## License

Glyptodon library is released under the [MIT License](LICENSE).


<img src='https://raw.githubusercontent.com/exchangegroup/Glyptodon/master/Graphics/Drawings/Glyptodon_Riha2000.jpg' alt='UI widget for displaying 'no results' message in iOS' width='450'>

*Drawing of a Glyptodon by Pavel Riha. Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Glyptodon_(Riha2000).jpg).*