This is a simple, informational app that displays a grid of Apple's development frameworks. Tapping on a framework opens a detail screen with a description and a "Learn More" button. This button opens the framework's official webpage in an in-app Safari browser.

**Key technologies and patterns used:**

* **Architecture & State Management:**
    * The app is built entirely with **SwiftUI**.
    * It follows the **MVVM** (Model-View-ViewModel) architectural pattern.
    * **`@StateObject`** is used to create and manage the ViewModel's lifecycle.
    * **`@Binding`** is used to pass state back from the detail view (via the dismiss button) to the main view.
    * A **`didSet`** property observer on the `selectedFramework` variable in the ViewModel is used to automatically trigger the presentation of the detail view.

* **UI and Layout:**
    * **`NavigationView`** is used for the main screen's title bar.
    * A **`LazyVGrid`** inside a **`ScrollView`** creates an efficient, scrollable grid of items.
    * The project is built with **reusable components**, including `AFButton` (a custom button), `XDismissButton`, and `FrameworkTitleView`.

* **Navigation & Presentation:**
    * The **`.sheet()`** modifier is used to present modal views for both the framework details and the Safari web view.

* **UIKit Integration:**
    * **`UIViewControllerRepresentable`** is used to wrap and display UIKit's `SFSafariViewController`, allowing web pages to be shown inside the SwiftUI app.

---
