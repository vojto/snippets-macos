In `AppDelegate`'s `didFinishLaunching`, set up the menubar item:

```swift
let item = NSStatusBar.system().statusItem(withLength: 50)
self.statusItem = item
```

To change the item, we can work with its `button` property:

```swift
item.button?.image = // ...
item.button?.title = "button title"
item.button?.imagePosition = .imageLeading
```

We can assign a menu for the button:

```swift
let menu = NSMenu()
menu.addItem(NSMenuItem(title: "item", action: nil, keyEquivalent: ""))

item.menu = menu
```
