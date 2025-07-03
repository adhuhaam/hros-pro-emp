# hrosproemp
This Mobile application for eployees of Human Resource Management system

made with react native and api from https://github.com/adhuhaam/hrospro.git backend, this app allows employees to login and see their details, payroll, leave, peronal details, documents, etc
# HRoS Pro Employee Mobile App 📱

> **Professional Human Resource Management System Mobile Application**

A modern, featurerich React Native mobile application for employees, built with Expo and inspired by professional design patterns. This app provides seamless access to HR services including attendance tracking, leave management, payroll, and employee selfservice features.

## 📸 App Preview

### **Dashboard & Employee ID Card**
<div align="center">
  <img src="https://cdn.rccmaldives.com/storage/app/images/dashboardpreview.png" alt="Dashboard with Animated Employee ID Card" width="300"/>
  <img src="https://cdn.rccmaldives.com/storage/app/images/employeecardflip.gif" alt="Employee Card Flip Animation" width="300"/>
</div>

### **Key Screens**
<div align="center">
  <img src="https://cdn.rccmaldives.com/storage/app/images/loginscreen.png" alt="Login Screen" width="250"/>
  <img src="https://cdn.rccmaldives.com/storage/app/images/attendancescreen.png" alt="Attendance Screen" width="250"/>
  <img src="https://cdn.rccmaldives.com/storage/app/images/leavescreen.png" alt="Leave Management" width="250"/>
</div>

### **Dark Theme Support**
<div align="center">
  <img src="https://cdn.rccmaldives.com/storage/app/images/dashboarddark.png" alt="Dark Theme Dashboard" width="300"/>
  <img src="https://cdn.rccmaldives.com/storage/app/images/profiledark.png" alt="Dark Theme Profile" width="300"/>
</div>

### **Design Inspiration (HRoS v3)**
<div align="center">
  <img src="https://cdn.rccmaldives.com/storage/app/images/hrosv3inspiration.png" alt="HRoS v3 Design Inspiration" width="600"/>
  <p><em>Professional design patterns and animations inspired by HRoS v3</em></p>
</div>

## ✨ Project Highlights

 **🎨 Professional Design**  Inspired by HRoS v3 with stunning animations and modern UI
 **📱 CrossPlatform**  Single codebase for iOS and Android using React Native  Expo
 **🌙 Dark/Light Themes**  Complete theming system with user preference persistence
 **🎯 EmployeeFocused**  Designed specifically for employee selfservice workflows
 **🔒 Secure Authentication**  JWTbased authentication with biometric support
 **🌍 MultiLanguage**  International support with i18next

## 🚀 Key Features

### 💼 Employee Management
 **Animated Employee ID Card**  Professional flip card with gradient backgrounds
 **Personal Profile**  View and edit employee information
 **Department & Role**  Complete organizational hierarchy
 **Document Management**  Access and manage personal documents
 **Contact Directory**  Companywide employee directory

### ⏰ Attendance & Time Tracking
 **OneTap Clock In/Out**  Simple attendance marking
 **RealTime Status**  Current attendance status display
 **Attendance History**  Calendar view with detailed tracking
 **Overtime Management**  Track and manage overtime hours
 **Location Verification**  GPSbased attendance validation

### 🏖️ Leave Management
 **Leave Applications**  Apply for different types of leave
 **Leave Balance**  Realtime balance tracking
 **Approval Workflow**  Track application status
 **Leave History**  Complete leave record with status
 **Calendar Integration**  Visual leave planning

### 💰 Payroll & Finance
 **Digital Payslips**  Monthly salary breakdown
 **Salary History**  Yearly overview and trends
 **Tax Information**  Detailed tax calculations
 **Bonus Records**  Track increments and bonuses
 **Export Options**  Download payslips as PDF

### 🗣️ Communication
 **Announcements**  Companywide notifications
 **Chat System**  Team communication features
 **Birthday Celebrations**  Team member birthdays
 **Company Handbook**  Digital policy access
 **Push Notifications**  Realtime alerts

### 📊 Dashboard & Analytics
 **Quick Access Grid**  3column tile navigation
 **Personal Analytics**  Attendance and leave trends
 **Company Holidays**  Colorcoded holiday calendar
 **Recent Activities**  Latest actions and updates
 **PulltoRefresh**  Realtime data synchronization

## 🛠️ Technology Stack

### **Core Framework**
 **React Native** 0.79  Crossplatform mobile development
 **Expo** ~53.0  Development platform and tooling
 **Expo Router**  Filebased navigation system
 **TypeScript**  Typesafe development

### **UI & Design**
 **React Native Paper**  Material Design components
 **Expo Linear Gradient**  Beautiful gradient backgrounds
 **React Native Reanimated** ~3.17  Smooth animations
 **Expo Vector Icons**  Comprehensive icon library
 **React Native Gesture Handler**  Touch interactions

### **State Management**
 **React Context**  User and theme management
 **AsyncStorage**  Persistent local storage
 **Axios**  HTTP client for API calls

### **Additional Libraries**
 **i18next  reacti18next**  Internationalization
 **React Native Toast Message**  User feedback
 **React Native Calendars**  Date components
 **Expo Notifications**  Push notifications
 **Lottie React Native**  Advanced animations

## 🏗️ Architecture

### **Project Structure**
```
src/
├── app/                    # Expo Router screens
│   ├── (auth)/            # Authentication group
│   │   ├── login.tsx
│   │   └── forgotpassword.tsx
│   ├── (tabs)/            # Main app tabs
│   │   ├── dashboard.tsx
│   │   ├── attendance.tsx
│   │   ├── leave.tsx
│   │   ├── profile.tsx
│   │   └── payroll.tsx
│   ├── _layout.tsx        # Root layout
│   ├── themecontext.tsx  # Theme management
│   ├── usercontext.tsx   # User state management
│   └── notfound.tsx     # 404 screen
├── components/            # Reusable components
│   ├── ui/               # UI components
│   ├── EmployeeCard.tsx   # Professional ID card
│   ├── DashboardTile.tsx  # Navigation tiles
│   └── AnnouncementCard.tsx
├── api/                   # API layer
│   ├── api.ts            # API functions
│   └── types.ts          # Type definitions
├── hooks/                # Custom hooks
├── constants/            # App constants
├── locales/              # Translation files
└── assets/               # Images, fonts, etc.
└── docs/                 # Documentation and images
    └── images/           # App screenshots and mockups
```

### **Backend Integration**
 **HRoS Pro API**  Node.js  Express  Prisma backend
 **MySQL Database**  Relational data storage
 **JWT Authentication**  Secure tokenbased auth
 **RESTful Endpoints**  Standard API architecture

## 🎨 Design System

### **Color Palette**
```typescript
Colors = {
  primary: '#006bad',      // Professional blue
  secondary: '#050027',    // Deep navy
  accent: '#004069',       // Medium blue
  
  light: {
    background: '#ffffff',
    surface: '#ffffff',
    text: '#000000',
    subtext: '#555555',
  },
  
  dark: {
    background: '#121212',
    surface: '#1e1e1e',
    text: '#ffffff',
    subtext: '#bbbbbb',
  }
}
```

### **Typography**
 **Title**: 32px, fontweight: 600
 **Subtitle**: 20px, fontweight: 600
 **Body**: 16px, lineheight: 24
 **Caption**: 12px, lineheight: 16

### **Components**
 **Tiles**: 30% width, 1:1 aspect ratio, 12px radius
 **Cards**: 16px padding, 10px radius, left border accent
 **Shadows**: Elevation 12 with proper shadow properties

## 🔧 Development Setup

### **Prerequisites**
 Node.js 18 
 Expo CLI
 React Native development environment
 iOS Simulator / Android Emulator

### **Installation**
```bash
# Clone the repository
git clone <repositoryurl>
cd hrosproemployeeapp

# Install dependencies
npm install

# Start development server
npx expo start devclient
```

### **Environment Variables**
```env
EXPO_PUBLIC_API_BASE_URL=https://yourbackendurl.com
EXPO_PUBLIC_APP_NAME=HRoS Pro Employee
```

### **Adding Screenshots**
To update the app preview images:

1. Create the `docs/images/` directory in your project root
2. Take screenshots of your app screens
3. Add them to the images folder with these names:
    `dashboardpreview.png`  Main dashboard screenshot
    `employeecardflip.gif`  Animated card flip
    `loginscreen.png`  Login interface
    `attendancescreen.png`  Attendance management
    `leavescreen.png`  Leave management
    `dashboarddark.png`  Dark theme dashboard
    `profiledark.png`  Dark theme profile
    `hrosv3inspiration.png`  Design inspiration comparison

## 📱 User Roles & Permissions

### **Employee**
 View personal profile and edit basic info
 Clock in/out functionality
 Apply for leaves and view leave history
 View personal payslips
 Access company directory
 View announcements

### **HR Manager**
 All employee permissions
 Manage employee records
 Approve/reject leave requests
 View department analytics
 Generate reports

### **Admin**
 All permissions
 User management
 System configuration
 Security settings

## 🚀 Development Phases

### **Phase 1 (Weeks 13): Foundation**
 ✅ Project setup with Expo  TypeScript
 ✅ Theme system implementation
 ✅ Navigation structure
 ✅ Employee ID card component
 ✅ API integration setup

### **Phase 2 (Weeks 46): Core Features**
 🔄 Authentication flow
 🔄 Dashboard implementation
 🔄 Employee management
 🔄 Profile management
 🔄 Theme switching

### **Phase 3 (Weeks 79): HR Features**
 📋 Attendance management
 📋 Leave management system
 📋 Announcements
 📋 Calendar integration
 📋 Document management

### **Phase 4 (Weeks 1012): Advanced Features**
 📋 Payroll integration
 📋 Chat features
 📋 Push notifications
 📋 Internationalization
 📋 Performance optimization

### **Phase 5 (Weeks 1316): Polish & Deployment**
 📋 Testing and bug fixes
 📋 Animation polish
 📋 Accessibility improvements
 📋 App store submission
 📋 Documentation

## 📊 Performance Goals

 **Launch Time**: < 3 seconds
 **Animation**: 60fps smooth transitions
 **Crash Rate**: < 0.1%
 **User Adoption**: 90% within 3 months
 **Rating**: 4.5 stars

## 🚀 Deployment

### **Development**
 **Expo Development Client** for testing
 **EAS Build** for development builds
 **OvertheAir Updates** for quick iterations

### **Production**
 **EAS Build** for production builds
 **App Store Connect** (iOS)
 **Google Play Console** (Android)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Write tests
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License  see the [LICENSE](LICENSE) file for details.

## 🔗 Related Projects

 **Backend API**: [HRoS Pro Backend](https://github.com/adhuhaam/hrospro.git)
 **Design Inspiration**: [HRoS v3](https://github.com/adhuhaam/hrosv3.git)

## 📞 Support

For support, email [youremail@company.com] or create an issue in this repository.



**Built with ❤️ for modern HR management**

