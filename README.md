# Guess the Flag

**Guess the Flag** is a fun SwiftUI-based quiz app where players identify country flags from a selection. Built as part of the [100 Days of SwiftUI](https://www.hackingwithswift.com/100/swiftui) by Paul Hudson, this project introduces and reinforces fundamental SwiftUI concepts, including Stack layouts, Gradients, Buttons, and Alerts.

## Overview

The app features:

- **Randomized Flags**: A shuffled set of flags to choose from each round.
- **Score Tracking**: Gain or lose points based on correct or incorrect answers.
- **Game Limits**: The game resets after 8 rounds.
- **Feedback Alerts**: Alerts display feedback and scores after each attempt.

---

## Key Concepts and Code Examples

### 1. **Stacks for Layout**

SwiftUI `VStack` and `ZStack` are used to create the main layout, layering elements for structure and background.

```swift
ZStack {
  RadialGradient(stops: [
    .init(color: Color(red: 0.1, green: 0.2, blue: 0.45), location: 0.3),
    .init(color: Color(red: 0.76, green: 0.15, blue: 0.26), location: 0.3)
  ], center: .top, startRadius: 200, endRadius: 700)
  .ignoresSafeArea()
  
  VStack {
    Text("Guess the Flag")
      .font(.largeTitle.bold())
      .foregroundStyle(.white)
    // Game content
  }
}
```

### 2. **Gradients for Backgrounds**

A `RadialGradient` is applied as a background to create a visually appealing effect.

```swift
RadialGradient(
  stops: [
    .init(color: Color(red: 0.1, green: 0.2, blue: 0.45), location: 0.3),
    .init(color: Color(red: 0.76, green: 0.15, blue: 0.26), location: 0.3)
  ],
  center: .top,
  startRadius: 200,
  endRadius: 700
)
```

### 3. **Buttons with Action and Labels**

Each flag is presented as a button, and selecting a flag triggers the `flagTapped` function.

```swift
Button {
  flagTapped(number)
} label: {
  Image(countries[number])
    .clipShape(.capsule)
    .shadow(radius: 5.0)
}
```

### 4. **Alerts for User Feedback**

Alerts provide feedback on each selection, including whether the answer was correct, the correct flag when an incorrect choice is made, and a game-over message.

```swift
.alert(scoreTitle, isPresented: $showingScore) {
  Button(gameAttempts == 7 ? "Play Again" : "Continue", action: askQuestion)
} message: {
  Text(scoreMessage)
}
```

---

### 5. **Screenshots**

| Demo                           |
| ------------------------------ |
| ![ss01](screenshots/ss01.jpeg) |
| ![ss02](screenshots/ss02.jpeg) |
| ![ss03](screenshots/ss03.jpeg) |
| ![ss04](screenshots/ss04.jpeg) |

---

## Commit Log

Here’s a progression of the changes in this project:

1. **e2f4987** - Improved the text messages for the last alert.
2. **db0b062** - Added a message for game completion.
3. **1aeb9ef** - Set a game limit to 8 rounds before resetting.
4. **c235935** - Show which flag was selected on an incorrect answer.
5. **0dcdca6** - Updated score based on correct or incorrect answers.
6. **b2e93b0** - Adjusted spacing and view arrangement.
7. **17f6af4** - Improved color scheme for instructions.
8. **409ea11** - Displayed game title and score.
9. **7b803be** - Styled game content with a material background.
10. **fb5064a** - Adjusted radial gradient colors for a better visual effect.
11. **b5614df** - Enhanced the background with a radial gradient.
12. **6378475** - Styled flags to be more prominent.
13. **48d654b** - Improved font styling for instructions.
14. **851b066** - Experimented with a linear gradient background.
15. **9a12af3** - Displayed an alert.
16. **45c0029** - Added a method to restart the game.
17. **b328e0a** - Implemented correct/wrong answer validation.
18. **bca696b** - Shuffled countries for random flags on each round.
19. **7f77efa** - Adjusted text color for readability against the blue background.
20. **ea8953a** - Added a blue background.

---

## Usage

1. The app shows three random flags, and the player must tap the correct one.
2. Each correct answer awards points, while incorrect selections deduct points.
3. Alerts show feedback on each answer, and the game resets after 8 rounds.

---

## Notes

This project provides an excellent introduction to layout management with stacks, background customization with gradients, interactive buttons, and feedback with alerts.
