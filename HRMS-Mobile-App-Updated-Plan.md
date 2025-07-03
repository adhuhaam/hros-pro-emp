# HRMS Mobile App Development Plan (Updated)
## Based on HRoS v3 Styling and Features

### Project Overview
Building a comprehensive HRMS mobile application using React Native and Expo, inspired by the excellent design patterns and features from the hrosv3 project. This app will consume the HRoS Pro backend API while implementing modern, professional styling and user experience.

### Design Inspiration Analysis
From the hrosv3 project, we identified these key design elements and features:

#### **Standout Features We'll Implement:**
1. **Animated Employee ID Card** - Professional flip card with gradient backgrounds
2. **Grid-based Dashboard** - Clean tile navigation with proper shadows
3. **Dark/Light Theme System** - Complete theming with AsyncStorage persistence
4. **Smooth Animations** - React Native Reanimated for professional transitions
5. **International Support** - Multi-language capabilities
6. **Professional Color Scheme** - Blue primary (#006bad) with clean whites/grays
7. **Context-based Architecture** - User and theme management
8. **Toast Notifications** - User-friendly feedback system

### Technology Stack (Inspired by hrosv3)

#### **Core Framework:**
- **React Native** 0.79+ with **Expo** (~53.0)
- **Expo Router** for file-based routing
- **TypeScript** for type safety

#### **UI & Styling:**
- **React Native Paper** for Material Design components
- **Expo Linear Gradient** for beautiful gradient backgrounds
- **React Native Reanimated** (~3.17) for smooth animations
- **Expo Vector Icons** for comprehensive icon library
- **React Native Gesture Handler** for touch interactions

#### **State Management:**
- **React Context** for user and theme management
- **AsyncStorage** for persistent storage
- **Axios** for API calls

#### **Additional Features:**
- **i18next** + **react-i18next** for internationalization
- **React Native Toast Message** for notifications
- **React Native Calendars** for date components
- **Expo Notifications** for push notifications
- **Lottie React Native** for animations

### Project Structure (Following hrosv3 Pattern)
```
src/
├── app/                    # Expo Router screens
│   ├── (auth)/            # Authentication group
│   │   ├── login.tsx
│   │   └── forgot-password.tsx
│   ├── (tabs)/            # Main app tabs
│   │   ├── dashboard.tsx
│   │   ├── attendance.tsx
│   │   ├── leave.tsx
│   │   ├── profile.tsx
│   │   └── payroll.tsx
│   ├── _layout.tsx        # Root layout
│   ├── theme-context.tsx  # Theme management
│   ├── user-context.tsx   # User state management
│   └── +not-found.tsx     # 404 screen
├── components/            # Reusable components
│   ├── ui/               # UI components
│   │   ├── ThemedText.tsx
│   │   ├── ThemedView.tsx
│   │   ├── LoadingScreen.tsx
│   │   └── AnimatedCard.tsx
│   ├── EmployeeCard.tsx   # Professional ID card
│   ├── DashboardTile.tsx  # Navigation tiles
│   └── AnnouncementCard.tsx
├── api/                   # API layer
│   ├── api.ts            # API functions
│   └── types.ts          # Type definitions
├── hooks/                # Custom hooks
│   ├── useThemeColor.ts
│   └── useAuth.ts
├── constants/            # App constants
│   ├── Colors.ts
│   └── Layout.ts
├── locales/              # Translation files
│   ├── en.json
│   └── es.json
└── assets/               # Images, fonts, etc.
    ├── logo.png
    ├── bg.jpg
    └── card_logo.png
```

### Key Features Implementation

#### **1. Professional Employee ID Card**
```typescript
// Animated flip card with gradient background
const EmployeeCard = () => {
  const flipAnim = useRef(new Animated.Value(0)).current;
  
  return (
    <Pressable onPress={flipCard}>
      <Animated.View style={[styles.cardFace, frontStyle]}>
        <LinearGradient
          colors={['#006bad', '#050027', '#004069', '#006bad']}
          start={{ x: 0, y: 0 }}
          end={{ x: 1, y: 1 }}
          style={styles.card}
        >
          {/* Employee photo, name, designation, contact */}
        </LinearGradient>
      </Animated.View>
    </Pressable>
  );
};
```

#### **2. Dashboard Grid Layout**
```typescript
const DashboardGrid = () => {
  const { theme } = useTheme();
  const tileBg = theme === 'dark' ? '#1e1e1e' : '#fff';
  
  return (
    <View style={styles.grid}>
      <DashboardTile
        icon="business-time"
        title="Attendance"
        onPress={() => router.push('/attendance')}
        backgroundColor={tileBg}
      />
      // More tiles...
    </View>
  );
};
```

#### **3. Theme System**
```typescript
// Theme Context with AsyncStorage persistence
export const ThemeProvider = ({ children }) => {
  const [theme, setTheme] = useState<'light' | 'dark'>('light');
  
  useEffect(() => {
    const loadTheme = async () => {
      const storedTheme = await AsyncStorage.getItem('theme');
      if (storedTheme) setTheme(storedTheme);
    };
    loadTheme();
  }, []);
  
  const toggleTheme = async () => {
    const newTheme = theme === 'light' ? 'dark' : 'light';
    setTheme(newTheme);
    await AsyncStorage.setItem('theme', newTheme);
  };
  
  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};
```

### Screen Designs (Following hrosv3 Patterns)

#### **Dashboard Screen Features:**
- **Animated Employee ID Card** with flip animation
- **Quick Access Grid** (3 columns, professional tiles)
- **Announcements Section** with card-based layout
- **Holidays Section** with color-coded past/future events
- **Pull-to-refresh** functionality
- **Professional shadows and elevations**

#### **Authentication Flow:**
- **Clean login form** with company branding
- **Professional logo placement**
- **Themed input fields** with proper placeholders
- **Toast notifications** for feedback
- **Forgot password** functionality

#### **Profile Screen:**
- **Employee details** with photo
- **Contact information**
- **Department and role** information
- **Edit profile** capabilities
- **Settings access**

#### **Attendance Screen:**
- **Clock in/out** with one-tap functionality
- **Current status** display
- **Attendance history** calendar
- **Time tracking** analytics

#### **Leave Management:**
- **Apply for leave** with date picker
- **Leave history** with status indicators
- **Leave balance** display
- **Approval workflow** tracking

### Styling Guidelines (Inspired by hrosv3)

#### **Color Palette:**
```typescript
export const Colors = {
  primary: '#006bad',
  secondary: '#050027',
  accent: '#004069',
  
  light: {
    background: '#ffffff',
    surface: '#ffffff',
    text: '#000000',
    subtext: '#555555',
    border: '#E0E0E0',
  },
  
  dark: {
    background: '#121212',
    surface: '#1e1e1e',
    text: '#ffffff',
    subtext: '#bbbbbb',
    border: '#333333',
  }
};
```

#### **Typography System:**
```typescript
export const Typography = {
  title: {
    fontSize: 32,
    fontWeight: '600',
    lineHeight: 32,
  },
  subtitle: {
    fontSize: 20,
    fontWeight: '600',
  },
  body: {
    fontSize: 16,
    lineHeight: 24,
  },
  caption: {
    fontSize: 12,
    lineHeight: 16,
  }
};
```

#### **Component Styles:**
```typescript
const styles = StyleSheet.create({
  tile: {
    width: '30%',
    aspectRatio: 1,
    backgroundColor: '#fff',
    borderRadius: 12,
    marginBottom: 14,
    justifyContent: 'center',
    alignItems: 'center',
    elevation: 12,
    shadowColor: '#000000',
    shadowOffset: { width: 0, height: 3 },
    shadowOpacity: 0.19,
  },
  
  card: {
    backgroundColor: '#fff',
    padding: 16,
    borderRadius: 10,
    marginBottom: 8,
    borderLeftWidth: 6,
    borderLeftColor: '#006bad',
    elevation: 12,
    shadowColor: '#000000',
    shadowOffset: { width: 0, height: 3 },
    shadowOpacity: 0.19,
  }
});
```

### API Integration (Connecting to HRoS Pro Backend)

#### **API Service Layer:**
```typescript
export const api = {
  login: async (username: string, password: string) => {
    const response = await axios.post(`${API_BASE_URL}/api/auth/login`, {
      email: username,
      password
    });
    return response.data;
  },
  
  getEmployees: async () => {
    const response = await axios.get(`${API_BASE_URL}/api/employees`);
    return response.data;
  },
  
  getDashboardAnalytics: async () => {
    const response = await axios.get(`${API_BASE_URL}/api/dashboard/analytics`);
    return response.data;
  }
};
```

#### **User Context with API Integration:**
```typescript
export const UserProvider = ({ children }) => {
  const [user, setUserState] = useState(null);
  const [loading, setLoading] = useState(true);
  
  const setUser = async (userData) => {
    setUserState(userData);
    await AsyncStorage.setItem('user', JSON.stringify(userData));
  };
  
  const logout = async () => {
    setUserState(null);
    await AsyncStorage.removeItem('user');
    await AsyncStorage.removeItem('token');
  };
  
  return (
    <UserContext.Provider value={{ user, setUser, logout, loading }}>
      {children}
    </UserContext.Provider>
  );
};
```

### Animation Implementations

#### **Card Flip Animation:**
```typescript
const useCardFlip = () => {
  const flipAnim = useRef(new Animated.Value(0)).current;
  const [isFlipped, setIsFlipped] = useState(false);
  
  const flipCard = () => {
    const toValue = isFlipped ? 0 : 180;
    Animated.timing(flipAnim, {
      toValue,
      duration: 600,
      useNativeDriver: true,
    }).start(() => setIsFlipped(!isFlipped));
  };
  
  const frontInterpolate = flipAnim.interpolate({
    inputRange: [0, 180],
    outputRange: ['0deg', '180deg'],
  });
  
  const backInterpolate = flipAnim.interpolate({
    inputRange: [0, 180],
    outputRange: ['180deg', '360deg'],
  });
  
  return { flipCard, frontInterpolate, backInterpolate };
};
```

### Development Phases

#### **Phase 1 (Weeks 1-3): Foundation & Styling**
- **Project Setup** with Expo and TypeScript
- **Theme System** implementation
- **Navigation Structure** with Expo Router
- **Employee ID Card** component with animations
- **Dashboard Grid** layout
- **API Integration** setup

#### **Phase 2 (Weeks 4-6): Core Features**
- **Authentication Flow** with backend integration
- **Dashboard Analytics** implementation
- **Employee Management** screens
- **Profile Management** with photo upload
- **Theme Switching** functionality

#### **Phase 3 (Weeks 7-9): HR Features**
- **Attendance Management** with clock in/out
- **Leave Management** system
- **Announcements** and notifications
- **Calendar Integration** for holidays
- **Document Management**

#### **Phase 4 (Weeks 10-12): Advanced Features**
- **Payroll Integration** and payslip viewing
- **Chat/Communication** features
- **Push Notifications** setup
- **Internationalization** implementation
- **Performance Optimization**

#### **Phase 5 (Weeks 13-16): Polish & Deployment**
- **Testing** and bug fixes
- **Animation Polish** and micro-interactions
- **Accessibility** improvements
- **App Store** preparation and submission
- **Documentation** and maintenance guide

### Key Implementation Details

#### **File-based Routing (Expo Router):**
```typescript
// app/_layout.tsx
export default function RootLayout() {
  return (
    <ThemeProvider>
      <UserProvider>
        <Stack screenOptions={{ headerShown: false }}>
          <Stack.Screen name="(auth)" />
          <Stack.Screen name="(tabs)" />
        </Stack>
      </UserProvider>
    </ThemeProvider>
  );
}
```

#### **Professional Toast System:**
```typescript
const showToast = (type: 'success' | 'error' | 'info', message: string) => {
  Toast.show({
    type,
    text1: type === 'success' ? 'Success' : type === 'error' ? 'Error' : 'Info',
    text2: message,
    visibilityTime: 3000,
  });
};
```

### Performance Considerations

1. **Image Optimization:** Use Expo's optimized image components
2. **List Performance:** FlatList with proper keyExtractor and getItemLayout
3. **Animation Performance:** useNativeDriver for all animations
4. **Memory Management:** Proper cleanup of listeners and timers
5. **Bundle Optimization:** Tree shaking and lazy loading

### Deployment Strategy

#### **Development:**
- **Expo Development Client** for testing
- **EAS Build** for creating development builds
- **Over-the-Air Updates** for quick iterations

#### **Production:**
- **EAS Build** for production builds
- **App Store Connect** (iOS) and **Google Play Console** (Android)
- **Expo Application Services** for CI/CD

### Success Metrics

1. **Performance:** < 3 second app launch time
2. **User Experience:** Smooth 60fps animations
3. **Reliability:** < 0.1% crash rate
4. **Adoption:** 90%+ employee usage within 3 months
5. **Satisfaction:** 4.5+ star rating

This updated plan incorporates all the beautiful design patterns and professional features from the hrosv3 project while adapting them for the HRoS Pro backend API. The result will be a modern, professional HRMS mobile application with stunning visuals and smooth user experience.