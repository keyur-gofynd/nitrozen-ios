# Nitrozen-SwiftUI

## Elements
### 1. Button Previews

| Preview1 | Preview2 | Preview3 | Preview4 | Preview5 |
| ---      | ---       | ---       | ---       | ---       |
| <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/buttons1.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/buttons2.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/buttons3.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/buttons4.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/buttons5.png" width="300"> |

### Button code snippets
Primary button
```swift
	Button(action: {}) {
		Text("Click me")
			.frame(maxWidth: .infinity)
	}
	.primaryButton()
```
Primary Disable button
```swift
	Button(action: {}) {
		Text("Click me")
			.frame(maxWidth: .infinity)
	}
	.disabled(true)
	.primaryButton()
```
Primary loading button
```swift
	@State var isButtonLoading: Bool = false //declare state boolean at view level
	
	Button(action: {}) {
		Text("Click me")
			.frame(maxWidth: .infinity)
	}
	.primaryButton(isLoading: $isButtonLoading)
```
Primary button with custom appearance
```swift
	Button(action: {}) {
		HStack{
			Text("Custom font")
		}
	}
	.primaryButton(
		appearance: NitrozenAppearance.shared
			.primaryButton.copy
			.font(.system(size: 10).italic())
			.titleColor(.white)
			.backgroundColor(.black),
		viewPadding: .custom(paddingToAdd: .init(top: 20, leading: 80, bottom: 20, trailing: 80))
	)
```
Bordered button
```swift
	Button(action: {}) {
		Text("Click me")
	}
	.borderedButton()
```
Tertiary button
```swift
	Button(action: {}) {
		Text("Click me")
	}
	.tertiaryButton()
```


### 2. Text/Label/Font (will add code snippet here)
| Preview1 | Preview2 | Preview3 | Preview4 | Preview5 |
| ---      | ---       | ---       | ---       | ---       |
| <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/textLabelFont1.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/textLabelFont2.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/textLabelFont3.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/textLabelFont4.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/textLabelFont5.png" width="300"> |

### Text/Label/Font code snippets
All font variants applied on label/text
```swift
struct TextLabels: View {

	@State var isLoading: Bool = false
	
	var body: some View {
		List{
			
			Section {
				
				HStack{
					Text("Loading")
					Toggle("", isOn: $isLoading)
				}
				
				Text("With love, from Nitrozen-SwiftUI")
					.body(isLoading: $isLoading, size: .m, weight: .regular)
			}
			
			Section("Body XXS") {
				Text("With love, from Nitrozen-SwiftUI /bold")
					.body(size: .xxs, weight: .bold)
				
				Text("With love, from Nitrozen-SwiftUI /regular")
					.body(size: .xxs, weight: .regular)
				
				Text("With love, from Nitrozen-SwiftUI /link")
					.body(size: .xxs, weight: .link, color: .blue)
				
				Text("With love, from Nitrozen-SwiftUI /useDefault(medium)")
					.body(size: .xxs, weight: .useDefault)
			}
			
			Section("Body XS") {
				Text("With love, from Nitrozen-SwiftUI /bold")
					.body(size: .xs, weight: .bold)
				
				Text("With love, from Nitrozen-SwiftUI /regular")
					.body(size: .xs, weight: .regular)
				
				Text("With love, from Nitrozen-SwiftUI /link")
					.body(size: .xs, weight: .link, color: .blue)
				
				Text("With love, from Nitrozen-SwiftUI /useDefault(medium)")
					.body(size: .xs, weight: .useDefault)
			}
			
			Section("Body S") {
				Text("With love, from Nitrozen-SwiftUI /bold")
					.body(size: .s, weight: .bold)
				
				Text("With love, from Nitrozen-SwiftUI /regular")
					.body(size: .s, weight: .regular)
				
				Text("With love, from Nitrozen-SwiftUI /link")
					.body(size: .s, weight: .link, color: .blue)
				
				Text("With love, from Nitrozen-SwiftUI /useDefault(medium)")
					.body(size: .s, weight: .useDefault)
			}
			
			Section("Body M") {
				Text("With love, from Nitrozen-SwiftUI /bold")
					.body(size: .m, weight: .bold)
				
				Text("With love, from Nitrozen-SwiftUI /regular")
					.body(size: .m, weight: .regular)
				
				Text("With love, from Nitrozen-SwiftUI /link")
					.body(size: .m, weight: .link, color: .blue)
				
				Text("With love, from Nitrozen-SwiftUI /useDefault(medium)")
					.body(size: .m, weight: .useDefault)
			}
			
			Section("Body L") {
				Text("With love, from Nitrozen-SwiftUI /bold")
					.body(size: .l, weight: .bold)
				
				Text("With love, from Nitrozen-SwiftUI /regular")
					.body(size: .l, weight: .regular)
				
				Text("With love, from Nitrozen-SwiftUI /link")
					.body(size: .l, weight: .link, color: .blue)
				
				Text("With love, from Nitrozen-SwiftUI /useDefault(medium)")
					.body(size: .l, weight: .useDefault)
			}
			
			Section("Headings") {
				Text("With love, from Nitrozen-SwiftUI .xxs)")
					.heading(size: .xxs)
				
				Text("With love, from Nitrozen-SwiftUI .xs)")
					.heading(size: .xs)
				
				Text("With love, from Nitrozen-SwiftUI .s)")
					.heading(size: .s)
				
				Text("With love, from Nitrozen-SwiftUI .m)")
					.heading(size: .m)
				
				Text("With love, from Nitrozen-SwiftUI .l)")
					.heading(size: .l)
				
				Text("With love, from Nitrozen-SwiftUI .xl)")
					.heading(size: .xl)
			}
			
			Section {
				Text("Custom Appearance")
				
				Text("This is text/label with purple title color and custom font")
					.heading(size: .m, color: .purple)
			}
		}
	}
}
```


### 3. TextField (will add code snippet here)
| Preview1 | Preview2 |
| ---      | ---       |
| <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/textfield1.png" width="300"> | <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/textfield2.png" width="300"> |

### 4. Checkbox (will add code snippet here)

| Preview1 |
| ---      |
| <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/checkbox1.png" width="300"> |

### 5. Radio (will add code snippet here)

| Preview1 |
| ---      |
| <img src="https://raw.githubusercontent.com/hitendra-gofynd/nitrozen-ios/master/Example-Nitrozen-SwiftUI/Example-Nitrozen-SwiftUI/Preview%20Content/radio1.png" width="300"> |
