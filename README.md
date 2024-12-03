# LongTouchButton
🎯 A reusable SwiftUI button component that supports both short tap and long press actions, providing a flexible and user-friendly interaction.

🚀 Features
- 🖱️ Short Tap: Triggers a default action with a quick tap.
- ✋ Long Press: Executes a different action after holding the button for a configurable duration.
- 🖼️ Custom Labels: Design your button with any SwiftUI View.
- ✨ Visual Feedback: Subtle opacity change during interaction.
- ♻️ Reusable: Easy to integrate across multiple SwiftUI views.
  
## 📦 Installation
Copy the LongTouchButton and LongTouchButtonStyle components into your project.
`import SwiftUI`

## 📝 Usage
Here’s an example of how to use `LongTouchButton` in your SwiftUI views:

```
import SwiftUI

struct ContentView: View {
    var body: some View {
        LongTouchButton(
            {
                print("Short tap action triggered")
            },
            longAction: {
                print("Long press action triggered")
            }
        ) {
            Text("Press Me")
                .padding()
                .background(Color.blue)
                .foregroundColor(.white)
                .cornerRadius(8)
        }
    }
}
```

## 🖼 Result
- Short Tap: Executes action.
- Long Press: Executes longAction after holding for 0.6 seconds.

## ⚙️ Customization
### 1. Adjust Long Press Duration
Modify the withTimeInterval in LongTouchButtonStyle to change the required hold time:

```
Timer.scheduledTimer(withTimeInterval: 1.0, repeats: false) { _ in
    longAction()
}
```
### 2. Add Haptic Feedback
Enhance the user experience by adding haptic feedback during the long press:

```
if configuration.isPressed {
    let generator = UIImpactFeedbackGenerator(style: .medium)
    generator.impactOccurred()
}
```
### 3. Dynamic Labels
Use a dynamic SwiftUI View as the button label:

```
LongTouchButton(
    { print("Short Action") },
    longAction: { print("Long Action") }
) {
    VStack {
        Image(systemName: "hand.tap")
        Text("Tap or Hold")
    }
}
```

## ⭐ Support
If you like this component, please give it a star ⭐ to show your support!
