# Views and Modifiers

## Why SwiftUI Uses Structs for Views

SwiftUI uses structs for views rather than classes, primarily to align with the framework's focus on simplicity, immutability, and performance. Here’s why:

1. **Performance**: While performance isn’t the only reason, it’s a significant advantage. Structs are lightweight and don’t carry the overhead of inheritance, making SwiftUI views faster to create, copy, and dispose of as needed.

2. **Avoiding Inheritance**
   - In UIKit, views inherit from `UIView`, which means they come with over 200 properties and methods, many of which might not be relevant to a specific view.
   - SwiftUI opts for a composition-based approach, where structs contain only the properties and methods needed, without inheriting unnecessary functionality.

3. **Value Types over Reference Types**
   - Structs in Swift are value types, meaning each view is a copy of the data rather than a shared reference.
   - This is more efficient for SwiftUI's declarative design, where views are frequently recreated based on state changes. Each new struct view is a fresh copy with the latest data, avoiding complex memory management issues tied to references.

By using structs, SwiftUI embraces immutability and simplicity, which aligns with Swift’s language philosophy and makes the UI code easier to read and manage.
