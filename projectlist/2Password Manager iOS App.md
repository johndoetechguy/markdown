# 🔐 Password Manager iOS App

A secure iOS application for managing passwords and credit card information with comprehensive local storage, advanced validation, modern UI features, and beautiful SwiftUI design.

## ✨ Features

### 🔑 Password Management
- **Add Passwords**: Store passwords with context, username, expiry dates, and notes
- **Edit Passwords**: Full edit and delete functionality for existing passwords
- **View Passwords**: List all saved passwords with username, expiry date, and notes preview
- **Data Persistence**: Passwords are saved locally using UserDefaults with JSON serialization
- **Expiry Tracking**: Monitor password expiration dates with smart date filtering
- **Notes Support**: Add detailed notes for each password entry
- **Username Field**: Store usernames separately from passwords for better organization
- **Password Generation**: Generate strong random passwords with one tap

### 💳 Credit Card Management
- **Add Credit Cards**: Store comprehensive card details with bank name and notes
- **Edit Credit Cards**: Full edit and delete functionality for existing cards
- **View Credit Cards**: List all saved cards with masked numbers, bank name, and card type
- **Card Type Detection**: Automatic identification of card types (Visa, Mastercard, Amex, etc.)
- **Luhn Algorithm Validation**: Real-time card number validation with visual feedback
- **CVV Masking**: Secure CVV input with show/hide toggle functionality
- **Bank Name & Notes**: Optional fields for additional card information
- **Smart Expiry Date Selection**: Dynamic month filtering based on selected year
- **Beautiful Card Design**: Modern rounded cards with clean borders and proper spacing

### 🛡️ Security Features
- **Local Storage**: Data encrypted in UserDefaults with JSON serialization
- **Card Number Masking**: Privacy protection for credit cards in lists
- **CVV Protection**: Masked CVV input with visibility toggle
- **Input Validation**: Comprehensive validation for all forms
- **Unique ID Generation**: UUID-based unique identifiers for all entries
- **Data Integrity**: Graceful handling of missing fields in existing data
- **Face ID/Touch ID**: Biometric authentication for secure access
- **Master Password**: SHA-256 hashed master password protection

### 🎨 User Interface
- **SwiftUI**: Modern SwiftUI components throughout
- **Navigation**: Smooth navigation-based navigation
- **Responsive Layouts**: Optimized layouts for different screen sizes
- **Visual Feedback**: Color-coded validation messages and status indicators
- **Smart Spinners**: Dynamic expiry date selection with current date awareness
- **Tabbed Navigation**: The main screen features a tabbed layout for easy navigation between Cards and Passwords
- **Unified Design**: The entire app uses a consistent design language for a sleek and modern look
- **Custom Header**: The main screen has a custom header with the app title and subtitle
- **Exit Button**: An exit button has been added to the header to close the app
- **Theme Support**: Light and dark theme compatibility

## 🚀 Getting Started

### Prerequisites
- Xcode 15.0 or later
- iOS 17.0 or later
- Swift 5.9 or later

### Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd PasswordManagerApp
   ```

2. **Open in Xcode**
   - Open Xcode
   - Select "Open a project or file"
   - Navigate to the project folder and select `PasswordManagerApp.xcodeproj`

3. **Build and Run**
   - Select your target device or simulator
   - Press `Cmd + R` to build and run the app
   - Or click the "Play" button in Xcode

## 📱 Usage

### First Time Setup
1. Launch the app
2. You'll be prompted to set up a master password
3. Enter and confirm your master password (minimum 6 characters)
4. The app will now be secured with your master password

### Authentication
- **Master Password**: Enter your master password to access the app
- **Face ID/Touch ID**: Use biometric authentication if available on your device
- **Auto-Logout**: The app will automatically log out after inactivity for enhanced security

### Managing Passwords
1. **Add Password**: Tap the "+" button in the Passwords tab
2. **Fill Details**: Enter context, username, password, expiry date, and notes
3. **Generate Password**: Use the "Generate Strong Password" button for secure passwords
4. **Save**: Tap "Save" to store the password

### Managing Credit Cards
1. **Add Credit Card**: Tap the "+" button in the Cards tab
2. **Fill Details**: Enter card number, holder name, bank, expiry date, and CVV
3. **Auto-Detection**: Card type is automatically detected from the card number
4. **Validation**: Card number is validated using the Luhn algorithm
5. **Save**: Tap "Save" to store the credit card

### Features
- **Search**: Use the search bar to find specific passwords or credit cards
- **Copy**: Tap the copy icon to copy passwords or card numbers to clipboard
- **Edit**: Tap on any entry to edit its details
- **Delete**: Swipe left on entries or use the delete button in edit mode
- **Show/Hide**: Toggle password and CVV visibility with the eye icon

## 🏗️ Architecture

### Data Models
- **PasswordEntry**: Represents a password entry with context, username, password, expiry date, and notes
- **CreditCardEntry**: Represents a credit card entry with all card details

### Core Components
- **PasswordRepository**: Manages data persistence using UserDefaults and JSON serialization
- **BiometricManager**: Handles Face ID and Touch ID authentication
- **ContentView**: Main app coordinator that manages authentication flow

### Views
- **LoginView**: Authentication screen with master password and biometric options
- **SetupMasterPasswordView**: First-time setup for master password
- **MainView**: Tabbed interface with passwords and credit cards
- **PasswordListView**: Displays and manages password entries
- **CreditCardListView**: Displays and manages credit card entries
- **AddPasswordView**: Form for adding new passwords
- **AddCreditCardView**: Form for adding new credit cards
- **EditPasswordView**: Form for editing existing passwords
- **EditCreditCardView**: Form for editing existing credit cards

## 🔒 Security

### Data Protection
- All sensitive data is stored locally on the device
- Master password is hashed using SHA-256
- Credit card numbers are masked in the UI
- CVV is always masked and requires explicit show/hide action

### Authentication
- Master password required for app access
- Face ID/Touch ID integration for biometric authentication
- Auto-logout functionality for enhanced security

### Validation
- Comprehensive input validation for all forms
- Credit card number validation using Luhn algorithm
- Password strength requirements
- Required field validation

## 🎨 UI/UX Design

### Design Principles
- **Modern**: Clean, minimalist design using SwiftUI
- **Accessible**: Support for VoiceOver and other accessibility features
- **Responsive**: Adapts to different screen sizes and orientations
- **Intuitive**: Easy-to-use interface with clear navigation

### Color Scheme
- **Primary**: Blue accent color for interactive elements
- **Secondary**: Gray for supporting text and backgrounds
- **Success**: Green for positive actions
- **Warning**: Orange for expiry dates
- **Error**: Red for destructive actions

### Typography
- **Headlines**: Large, bold text for titles
- **Body**: Standard text for content
- **Captions**: Small text for secondary information
- **Monospace**: Used for passwords and card numbers

## 🛠️ Technical Details

### Dependencies
- **SwiftUI**: Modern declarative UI framework
- **LocalAuthentication**: Biometric authentication
- **CryptoKit**: Password hashing
- **Foundation**: Core functionality

### Data Persistence
- **UserDefaults**: Local storage for app data
- **JSON**: Data serialization format
- **Codable**: Swift's built-in serialization protocol

### Platform Support
- **iOS 17.0+**: Minimum deployment target
- **iPhone**: Optimized for iPhone screens
- **iPad**: Universal app with iPad support
- **Dark Mode**: Full dark mode support

## 🔄 Migration from Android

This iOS app is a direct conversion of the Android Password Manager app with the following adaptations:

### Platform-Specific Features
- **SwiftUI**: Replaces Android's XML layouts and ViewBinding
- **UserDefaults**: Replaces Android's SharedPreferences
- **Face ID/Touch ID**: Replaces Android's BiometricPrompt
- **NavigationView**: Replaces Android's Navigation Component
- **TabView**: Replaces Android's TabLayout

### Equivalent Components
| Android | iOS |
|---------|-----|
| MainActivity | ContentView + MainView |
| LoginActivity | LoginView |
| PasswordListFragment | PasswordListView |
| CreditCardListFragment | CreditCardListView |
| AddPasswordFragment | AddPasswordView |
| AddCreditCardFragment | AddCreditCardView |
| EditPasswordFragment | EditPasswordView |
| EditCreditCardFragment | EditCreditCardView |
| SetupMasterPasswordActivity | SetupMasterPasswordView |
| PasswordRepository | PasswordRepository |
| BiometricManager | BiometricManager |

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📞 Support

If you encounter any issues or have questions, please:
1. Check the existing issues
2. Create a new issue with detailed information
3. Include device information and iOS version

## 🔮 Future Enhancements

- [ ] iCloud sync support
- [ ] Password strength analyzer
- [ ] Data export/import functionality
- [ ] Password sharing between devices
- [ ] Advanced search filters
- [ ] Password history tracking
- [ ] Secure notes feature
- [ ] Two-factor authentication codes
- [ ] Password breach monitoring
- [ ] Custom categories/tags 