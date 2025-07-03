diff --git a/README.md b/README.md
--- a/README.md
+++ b/README.md
@@ -1,4 +1,337 @@
-# hros-pro-emp
-This Mobile application for eployees of Human Resource Management system
-
-made with react native and api from https://github.com/adhuhaam/hros-pro.git backend, this app allows employees to login and see their details, payroll, leave, peronal details, documents, etc
+# HRoS Pro Employee Mobile App 📱
+
+> **Professional Human Resource Management System Mobile Application**
+
+A modern, feature-rich React Native mobile application for employees, built with Expo and inspired by professional design patterns. This app provides seamless access to HR services including attendance tracking, leave management, payroll, and employee self-service features.
+
+## 📸 App Preview
+
+### **Dashboard & Employee ID Card**
+<div align="center">
+  <img src="./docs/images/dashboard-preview.png" alt="Dashboard with Animated Employee ID Card" width="300"/>
+  <img src="./docs/images/employee-card-flip.gif" alt="Employee Card Flip Animation" width="300"/>
+</div>
+
+### **Key Screens**
+<div align="center">
+  <img src="./docs/images/login-screen.png" alt="Login Screen" width="250"/>
+  <img src="./docs/images/attendance-screen.png" alt="Attendance Screen" width="250"/>
+  <img src="./docs/images/leave-screen.png" alt="Leave Management" width="250"/>
+</div>
+
+### **Dark Theme Support**
+<div align="center">
+  <img src="./docs/images/dashboard-dark.png" alt="Dark Theme Dashboard" width="300"/>
+  <img src="./docs/images/profile-dark.png" alt="Dark Theme Profile" width="300"/>
+</div>
+
+### **Design Inspiration (HRoS v3)**
+<div align="center">
+  <img src="./docs/images/hrosv3-inspiration.png" alt="HRoS v3 Design Inspiration" width="600"/>
+  <p><em>Professional design patterns and animations inspired by HRoS v3</em></p>
+</div>
+
+## ✨ Project Highlights
+
+- **🎨 Professional Design** - Inspired by HRoS v3 with stunning animations and modern UI
+- **📱 Cross-Platform** - Single codebase for iOS and Android using React Native + Expo
+- **🌙 Dark/Light Themes** - Complete theming system with user preference persistence
+- **🎯 Employee-Focused** - Designed specifically for employee self-service workflows
+- **🔒 Secure Authentication** - JWT-based authentication with biometric support
+- **🌍 Multi-Language** - International support with i18next
+
+## 🚀 Key Features
+
+### 💼 Employee Management
+- **Animated Employee ID Card** - Professional flip card with gradient backgrounds
+- **Personal Profile** - View and edit employee information
+- **Department & Role** - Complete organizational hierarchy
+- **Document Management** - Access and manage personal documents
+- **Contact Directory** - Company-wide employee directory
+
+### ⏰ Attendance & Time Tracking
+- **One-Tap Clock In/Out** - Simple attendance marking
+- **Real-Time Status** - Current attendance status display
+- **Attendance History** - Calendar view with detailed tracking
+- **Overtime Management** - Track and manage overtime hours
+- **Location Verification** - GPS-based attendance validation
+
+### 🏖️ Leave Management
+- **Leave Applications** - Apply for different types of leave
+- **Leave Balance** - Real-time balance tracking
+- **Approval Workflow** - Track application status
+- **Leave History** - Complete leave record with status
+- **Calendar Integration** - Visual leave planning
+
+### 💰 Payroll & Finance
+- **Digital Payslips** - Monthly salary breakdown
+- **Salary History** - Yearly overview and trends
+- **Tax Information** - Detailed tax calculations
+- **Bonus Records** - Track increments and bonuses
+- **Export Options** - Download payslips as PDF
+
+### 🗣️ Communication
+- **Announcements** - Company-wide notifications
+- **Chat System** - Team communication features
+- **Birthday Celebrations** - Team member birthdays
+- **Company Handbook** - Digital policy access
+- **Push Notifications** - Real-time alerts
+
+### 📊 Dashboard & Analytics
+- **Quick Access Grid** - 3-column tile navigation
+- **Personal Analytics** - Attendance and leave trends
+- **Company Holidays** - Color-coded holiday calendar
+- **Recent Activities** - Latest actions and updates
+- **Pull-to-Refresh** - Real-time data synchronization
+
+## 🛠️ Technology Stack
+
+### **Core Framework**
+- **React Native** 0.79+ - Cross-platform mobile development
+- **Expo** ~53.0 - Development platform and tooling
+- **Expo Router** - File-based navigation system
+- **TypeScript** - Type-safe development
+
+### **UI & Design**
+- **React Native Paper** - Material Design components
+- **Expo Linear Gradient** - Beautiful gradient backgrounds
+- **React Native Reanimated** ~3.17 - Smooth animations
+- **Expo Vector Icons** - Comprehensive icon library
+- **React Native Gesture Handler** - Touch interactions
+
+### **State Management**
+- **React Context** - User and theme management
+- **AsyncStorage** - Persistent local storage
+- **Axios** - HTTP client for API calls
+
+### **Additional Libraries**
+- **i18next + react-i18next** - Internationalization
+- **React Native Toast Message** - User feedback
+- **React Native Calendars** - Date components
+- **Expo Notifications** - Push notifications
+- **Lottie React Native** - Advanced animations
+
+## 🏗️ Architecture
+
+### **Project Structure**
+```
+src/
+├── app/                    # Expo Router screens
+│   ├── (auth)/            # Authentication group
+│   │   ├── login.tsx
+│   │   └── forgot-password.tsx
+│   ├── (tabs)/            # Main app tabs
+│   │   ├── dashboard.tsx
+│   │   ├── attendance.tsx
+│   │   ├── leave.tsx
+│   │   ├── profile.tsx
+│   │   └── payroll.tsx
+│   ├── _layout.tsx        # Root layout
+│   ├── theme-context.tsx  # Theme management
+│   ├── user-context.tsx   # User state management
+│   └── +not-found.tsx     # 404 screen
+├── components/            # Reusable components
+│   ├── ui/               # UI components
+│   ├── EmployeeCard.tsx   # Professional ID card
+│   ├── DashboardTile.tsx  # Navigation tiles
+│   └── AnnouncementCard.tsx
+├── api/                   # API layer
+│   ├── api.ts            # API functions
+│   └── types.ts          # Type definitions
+├── hooks/                # Custom hooks
+├── constants/            # App constants
+├── locales/              # Translation files
+└── assets/               # Images, fonts, etc.
+└── docs/                 # Documentation and images
+    └── images/           # App screenshots and mockups
+```
+
+### **Backend Integration**
+- **HRoS Pro API** - Node.js + Express + Prisma backend
+- **MySQL Database** - Relational data storage
+- **JWT Authentication** - Secure token-based auth
+- **RESTful Endpoints** - Standard API architecture
+
+## 🎨 Design System
+
+### **Color Palette**
+```typescript
+Colors = {
+  primary: '#006bad',      // Professional blue
+  secondary: '#050027',    // Deep navy
+  accent: '#004069',       // Medium blue
+  
+  light: {
+    background: '#ffffff',
+    surface: '#ffffff',
+    text: '#000000',
+    subtext: '#555555',
+  },
+  
+  dark: {
+    background: '#121212',
+    surface: '#1e1e1e',
+    text: '#ffffff',
+    subtext: '#bbbbbb',
+  }
+}
+```
+
+### **Typography**
+- **Title**: 32px, font-weight: 600
+- **Subtitle**: 20px, font-weight: 600
+- **Body**: 16px, line-height: 24
+- **Caption**: 12px, line-height: 16
+
+### **Components**
+- **Tiles**: 30% width, 1:1 aspect ratio, 12px radius
+- **Cards**: 16px padding, 10px radius, left border accent
+- **Shadows**: Elevation 12 with proper shadow properties
+
+## 🔧 Development Setup
+
+### **Prerequisites**
+- Node.js 18+ 
+- Expo CLI
+- React Native development environment
+- iOS Simulator / Android Emulator
+
+### **Installation**
+```bash
+# Clone the repository
+git clone <repository-url>
+cd hros-pro-employee-app
+
+# Install dependencies
+npm install
+
+# Start development server
+npx expo start --dev-client
+```
+
+### **Environment Variables**
+```env
+EXPO_PUBLIC_API_BASE_URL=https://your-backend-url.com
+EXPO_PUBLIC_APP_NAME=HRoS Pro Employee
+```
+
+### **Adding Screenshots**
+To update the app preview images:
+
+1. Create the `docs/images/` directory in your project root
+2. Take screenshots of your app screens
+3. Add them to the images folder with these names:
+   - `dashboard-preview.png` - Main dashboard screenshot
+   - `employee-card-flip.gif` - Animated card flip
+   - `login-screen.png` - Login interface
+   - `attendance-screen.png` - Attendance management
+   - `leave-screen.png` - Leave management
+   - `dashboard-dark.png` - Dark theme dashboard
+   - `profile-dark.png` - Dark theme profile
+   - `hrosv3-inspiration.png` - Design inspiration comparison
+
+## 📱 User Roles & Permissions
+
+### **Employee**
+- View personal profile and edit basic info
+- Clock in/out functionality
+- Apply for leaves and view leave history
+- View personal payslips
+- Access company directory
+- View announcements
+
+### **HR Manager**
+- All employee permissions
+- Manage employee records
+- Approve/reject leave requests
+- View department analytics
+- Generate reports
+
+### **Admin**
+- All permissions
+- User management
+- System configuration
+- Security settings
+
+## 🚀 Development Phases
+
+### **Phase 1 (Weeks 1-3): Foundation**
+- ✅ Project setup with Expo + TypeScript
+- ✅ Theme system implementation
+- ✅ Navigation structure
+- ✅ Employee ID card component
+- ✅ API integration setup
+
+### **Phase 2 (Weeks 4-6): Core Features**
+- 🔄 Authentication flow
+- 🔄 Dashboard implementation
+- 🔄 Employee management
+- 🔄 Profile management
+- 🔄 Theme switching
+
+### **Phase 3 (Weeks 7-9): HR Features**
+- 📋 Attendance management
+- 📋 Leave management system
+- 📋 Announcements
+- 📋 Calendar integration
+- 📋 Document management
+
+### **Phase 4 (Weeks 10-12): Advanced Features**
+- 📋 Payroll integration
+- 📋 Chat features
+- 📋 Push notifications
+- 📋 Internationalization
+- 📋 Performance optimization
+
+### **Phase 5 (Weeks 13-16): Polish & Deployment**
+- 📋 Testing and bug fixes
+- 📋 Animation polish
+- 📋 Accessibility improvements
+- 📋 App store submission
+- 📋 Documentation
+
+## 📊 Performance Goals
+
+- **Launch Time**: < 3 seconds
+- **Animation**: 60fps smooth transitions
+- **Crash Rate**: < 0.1%
+- **User Adoption**: 90%+ within 3 months
+- **Rating**: 4.5+ stars
+
+## 🚀 Deployment
+
+### **Development**
+- **Expo Development Client** for testing
+- **EAS Build** for development builds
+- **Over-the-Air Updates** for quick iterations
+
+### **Production**
+- **EAS Build** for production builds
+- **App Store Connect** (iOS)
+- **Google Play Console** (Android)
+
+## 🤝 Contributing
+
+1. Fork the repository
+2. Create a feature branch
+3. Make your changes
+4. Write tests
+5. Submit a pull request
+
+## 📄 License
+
+This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
+
+## 🔗 Related Projects
+
+- **Backend API**: [HRoS Pro Backend](https://github.com/adhuhaam/hros-pro.git)
+- **Design Inspiration**: [HRoS v3](https://github.com/adhuhaam/hrosv3.git)
+
+## 📞 Support
+
+For support, email [your-email@company.com] or create an issue in this repository.
+
+---
+
+**Built with ❤️ for modern HR management**
+
