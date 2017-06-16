In your NSView subclass:

```swift
var trackingArea: NSTrackingArea?

override open func updateTrackingAreas() {
    if let area = trackingArea {
        removeTrackingArea(area)
    }
    
    trackingArea = NSTrackingArea(rect: bounds, options: [.mouseMoved, .mouseEnteredAndExited, .activeInKeyWindow], owner: self, userInfo: nil)
    self.addTrackingArea(trackingArea!)
}
```