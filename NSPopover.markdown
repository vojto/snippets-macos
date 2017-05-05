# Basic NSPopover

Setup:

1. Set up subclass of `NSViewController`

In a controller:

```swift
class PresentingController: NSViewController {
    var controller: PopoverController?
    var popover: NSPopover?

    func presentingAction() {
        if controller == nil {
            controller = PopoverController()
        }
        
        if popover == nil {
            popover = NSPopover()
            popover?.contentViewController = controller
            popover?.behavior = .transient
            popover?.animates = false
        }
        
        popover?.show(relativeTo: view.bounds, of: view, preferredEdge: .minY)
    }
}
```