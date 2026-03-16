# 🌐 NEXUS — Connect & Create

A modern, full-featured social media platform built with vanilla HTML, CSS, and JavaScript. NEXUS empowers users to connect, share, and collaborate in a beautiful, intuitive interface inspired by industry-leading social platforms.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation & Setup](#installation--setup)
- [Usage Guide](#usage-guide)
- [Project Structure](#project-structure)
- [Key Features Explained](#key-features-explained)
- [Demo Accounts](#demo-accounts)
- [Architecture](#architecture)
- [Browser Support](#browser-support)
- [Contributing](#contributing)
- [Roadmap](#roadmap)
- [License](#license)
- [Author](#author)

---

## 🎯 Overview

**NEXUS** is a modern social media platform designed to showcase best practices in web development. It combines a sleek UI with powerful functionality, allowing users to:

- Create and share posts with rich media
- Discover trending topics and connect with people
- Engage through reactions, comments, and shares
- Watch reels and video content
- Explore job opportunities
- Send direct messages
- Build and grow communities

The entire platform is built with **zero external dependencies** (except Google Fonts), making it lightweight, fast, and perfect for learning modern web development patterns.

---

## ✨ Features

### 📱 Core Features

- **Authentication System**
  - Secure login/register flow
  - Session management with localStorage
  - Demo accounts for quick access
  - Password validation

- **Feed & Discovery**
  - Dynamic feed with infinite scroll capability
  - Stories (temporary content)
  - Trending topics widget
  - People recommendations
  - Search functionality

- **Post Types**
  - Text posts with hashtag/mention detection
  - Photo posts (single or multi-image grid)
  - Video posts with native player controls
  - Article posts with preview cards
  - Polls with live voting

- **Engagement**
  - Rich reaction system (6 emoji reactions)
  - Comments with nested interactions
  - Like/Save functionality
  - Share posts to networks
  - Reaction picker with hover preview

- **Content Discovery**
  - 🎬 **Reels** - Short-form video content feed
  - 💼 **Jobs** - Job listings with filtering
  - 📅 **Events** - Upcoming tech events
  - 🔖 **Saved** - Bookmark posts for later
  - 🔥 **Trending** - Hashtag trends

- **Social Features**
  - Follow/Unfollow users
  - Detailed profile pages
  - User statistics (posts, followers, following)
  - Edit profile bio
  - Profile banners with gradient colors

- **Messaging**
  - Real-time chat interface
  - Conversation list
  - Message history
  - Status indicators
  - Responsive chat bubble design

- **Notifications**
  - Real-time notification panel
  - Unread notification badges
  - Different notification types (likes, comments, follows)
  - Mark as read functionality

### 🎨 Design Features

- **Modern UI/UX**
  - Glassmorphism authentication screen
  - Smooth animations & transitions
  - Gradient backgrounds & overlays
  - Responsive design (mobile-first)
  - Accessibility-conscious color contrasts

- **Interactive Elements**
  - Hover effects & state changes
  - Modal interactions (stories, lightbox)
  - Toast notifications
  - Dropdown menus
  - Drag-friendly UI

---

## 🛠️ Tech Stack

| Technology | Purpose | Notes |
|------------|---------|-------|
| **HTML5** | Structure & Markup | Semantic HTML |
| **CSS3** | Styling & Layout | Custom properties, Grid, Flexbox |
| **JavaScript (Vanilla)** | Logic & Interactivity | No frameworks, ES6+ |
| **LocalStorage API** | Data Persistence | In-browser database simulation |
| **Google Fonts** | Typography | Plus Jakarta Sans, Clash Display |

### Key Libraries & APIs

- **Native Web APIs**: Fetch, LocalStorage, localStorage events
- **CSS Features**: CSS Grid, Flexbox, Custom Properties, Animations, Gradients
- **JavaScript Patterns**: Module pattern, Event delegation, Functional programming

---

## 💻 Installation & Setup

### Prerequisites

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Code editor (VS Code recommended)
- Basic understanding of HTML/CSS/JS

### Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/NEXUS.git
   cd NEXUS
   ```

2. **Open in Browser**
   ```bash
   # Option 1: Direct file open
   open index.html

   # Option 2: Use Live Server (VS Code Extension)
   # Right-click → Open with Live Server

   # Option 3: Python simple server
   python3 -m http.server 8000
   # Visit: http://localhost:8000
   ```

3. **No Build Process Required**
   - The platform runs entirely in the browser
   - No npm install or build step needed
   - Just open `index.html` and you're good to go!

### Project Structure

```
NEXUS/
├── index.html          # Main application file
├── README.md           # Documentation
├── LICENSE             # MIT License
└── assets/             # (Optional) Images, icons
    ├── logo.png
    └── screenshots/
```

---

## 📖 Usage Guide

### Getting Started

1. **Sign Up / Login**
   - Click "Join Now" to create a new account
   - Or use demo credentials to explore immediately
   - Passwords are validated (minimum 4 characters)

2. **Navigate the Platform**
   - **Home** - Your main feed with stories and posts
   - **Reels** - Watch short-form video content
   - **Jobs** - Browse tech job opportunities
   - **Messages** - Direct messaging with other users
   - **Alerts** - Notifications dashboard

3. **Create Content**
   - Click the compose box at the top
   - Choose post type: Post, Article, or Video
   - Add media, polls, or text
   - Click "Share ✦" to publish

### Interactive Features

- **Stories**: Click on story rings to view, navigate with arrows or wait for auto-advance
- **Reactions**: Hover over "Like" button to see reaction picker
- **Comments**: Click "Comment" to open comment thread, reply and like comments
- **Messages**: Select a conversation and type to message friends
- **Search**: Use top search bar to find people and topics

---

## 🏗️ Project Structure & Architecture

### Component Hierarchy

```
NEXUS Application
├── Auth Screen
│   ├── Login Form
│   ├── Register Form
│   └── Demo Login Links
│
├── App Shell
│   ├── Navigation Bar
│   │   ├── Logo
│   │   ├── Search Bar
│   │   ├── Nav Tabs
│   │   └── Profile Avatar
│   │
│   ├── Notification Panel
│   │
│   ├── Views (Tab-based routing)
│   │   ├── Feed View
│   │   │   ├── Left Sidebar (Profile Card + Menu)
│   │   │   ├── Center Feed
│   │   │   │   ├── Stories Bar
│   │   │   │   ├── Compose Card
│   │   │   │   └── Posts Container
│   │   │   └── Right Sidebar (Widgets)
│   │   │       ├── Trending Widget
│   │   │       ├── Suggestions Widget
│   │   │       └── Jobs Mini Widget
│   │   │
│   │   ├── Reels View
│   │   ├── Jobs View
│   │   ├── Messages View
│   │   ├── Profile View
│   │   ├── Saved View
│   │   └── Events View
│   │
│   └── Modals
│       ├── Story Modal
│       ├── Lightbox
│       └── Toast Notifications
```

### Data Flow

```
User Action → Event Handler → DB Update → Re-render UI
```

### Database Schema (LocalStorage)

```javascript
localStorage["nx_users"] = {
  username: {
    username,
    name,
    headline,
    bio,
    colorIdx,
    password,
    followers: [],
    following: [],
    joinedAt,
    saved: []
  }
}

localStorage["nx_posts"] = [
  {
    id,
    author,
    type,           // "post" | "article" | "video" | "photo"
    body,
    photos,         // optional
    videoUrl,       // optional
    articleTitle,   // optional
    poll,           // optional
    likes,
    reactions,
    comments,
    saves,
    time
  }
]

localStorage["nx_messages"] = {
  "user1|user2": [  // Alphabetically sorted users
    {
      from,
      text,
      time
    }
  ]
}

localStorage["nx_stories"] = [
  {
    u,              // username
    text,
    emoji,
    bg              // gradient background
  }
]
```

---

## 🎯 Key Features Explained

### 1. **Authentication & Session Management**

```javascript
// Session persists across browser refreshes
DB.setSession(username) → stored in localStorage
DB.session() → retrieves current user
```

**Features:**
- Registration with validation
- Secure password storage (hashed in production)
- Auto-login if session exists
- Logout clears session

### 2. **Dynamic Feed Rendering**

Posts render with conditional layouts based on type:
- Text posts → Body text with formatting
- Photo posts → Grid layout (1, 2, or 3+ images)
- Videos → Native video player with controls
- Articles → Preview card with title
- Polls → Interactive voting interface

### 3. **Rich Reactions System**

- Hover reaction picker with 6 emoji options
- Quick-react with single click
- Toggle reactions (click again to remove)
- Reaction count aggregation
- Visual feedback with animations

### 4. **Comments & Engagement**

- Nested comment threads
- Comment likes/replies
- Real-time comment count updates
- User mentions & hashtag detection
- Formatted text rendering

### 5. **Stories Feature**

```javascript
// Auto-advance: 4 seconds per story
// Manual navigation: click left/right
// Progress bar shows completion
// Smooth transitions between stories
```

### 6. **Search & Discovery**

- Real-time search with user matching
- Trending hashtags widget
- People recommendations with follow buttons
- Job listings with filtering
- Upcoming events calendar

### 7. **Notifications System**

```javascript
// 5 notification types:
// ❤️ Reaction notifications
// 💬 Comment replies
// 👥 New followers
// 🔁 Share/retweet
// 💼 Profile view alerts
```

### 8. **Messaging Platform**

- Conversation list with last message preview
- Real-time chat interface
- Message history with timestamps
- Status indicators (online/offline)
- Unread message badges

---

## 👥 Demo Accounts

Quick access without registration:

| Username | Password | Bio |
|----------|----------|-----|
| `alex_v` | `demo` | Full-Stack Developer · Open Source |
| `sara_m` | `demo` | UX Designer · Product Enthusiast |
| `dev_mike` | `demo` | Backend Engineer · Cloud Architect |

**Or create your own account** to explore fully!

---

## 🔧 Customization Guide

### Change Brand Colors

Edit CSS variables in `:root` selector:

```css
:root {
  --primary: #0a66c2;        /* Main brand color */
  --accent2: #e91e8c;        /* Secondary accent */
  --gradient: linear-gradient(135deg, #ff6b6b, #feca57); /* Gradients */
}
```

### Modify Seed Data

Edit the `seedDB()` function:

```javascript
const us = [
  {
    u: 'username',
    n: 'Full Name',
    h: 'Headline',
    b: 'Bio',
    ci: 0,           // color index (0-5)
    pw: 'password'
  }
];
```

### Add New Post Types

1. Add type to post object
2. Create rendering logic in `renderPost()`
3. Update compose interface

### Extend Features

- **Add real backend**: Replace localStorage with API calls
- **Add image upload**: Use FormData API
- **Add notifications**: Implement WebSocket/SSE
- **Add dark mode**: Toggle theme CSS class

---

## 🏛️ Architecture Details

### State Management

```javascript
// Global state variables
let CU = null;              // Current User
let currentView = 'feed';   // Active view
let currentPostType = 'post'; // Compose type
let currentConv = null;     // Active conversation
let notifOpen = false;      // Notif panel state
```

### View Routing

```javascript
showView('feed') → Display feed-view
showView('reels') → Display reels-view
showView('jobs') → Display jobs-view
showView('messages') → Display messages-view
// etc...
```

### Event Delegation

```javascript
// Click handlers use function calls, not listeners
onclick="doLogin()"
onclick="createPost()"
onclick="addReaction(postId, emoji)"
```

### Helper Functions

| Function | Purpose |
|----------|---------|
| `DB.get(key)` | Retrieve from localStorage |
| `DB.set(key, value)` | Save to localStorage |
| `initials(username)` | Get user initials for avatar |
| `getBg(username)` | Get user's gradient color |
| `ta(timestamp)` | Format time ago (e.g., "2m ago") |
| `formatBody(text)` | Add hashtag/mention styling |

---

## 🌐 Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | Latest | ✅ Full Support |
| Firefox | Latest | ✅ Full Support |
| Safari | 13+ | ✅ Full Support |
| Edge | Latest | ✅ Full Support |
| IE 11 | - | ❌ Not Supported |

### Required Features

- ES6 JavaScript support
- CSS Grid & Flexbox
- CSS Custom Properties
- LocalStorage API
- Fetch API

---

## 🚀 Performance Optimizations

- **Zero Dependencies**: No npm packages = minimal bundle size
- **CSS Animations**: GPU-accelerated transitions
- **Event Delegation**: Efficient event handling
- **LocalStorage Caching**: Fast data retrieval
- **Lazy Rendering**: Posts render only in view
- **Minifiable**: Can be minified to ~50KB

---

## 🔐 Security Notes

**Current Implementation (Development):**
- Passwords stored in plain text (for demo purposes)
- No encryption on stored data
- Session in localStorage

**Production Recommendations:**
- Hash passwords with bcrypt
- Implement JWT tokens
- Use HTTPS only
- Server-side session management
- Input validation & sanitization
- XSS/CSRF protection

---

## 🐛 Known Limitations & Future Enhancements

### Current Limitations

- Single-device sessions (localStorage)
- No persistent backend storage
- Local data resets on browser clear
- No real-time notifications
- No file upload (demo images only)

### Roadmap v2.0

- [ ] Backend API integration (Node.js/Python)
- [ ] Real-time WebSocket messaging
- [ ] Database persistence (PostgreSQL/MongoDB)
- [ ] Image/file uploads to cloud
- [ ] Dark mode theme
- [ ] Mobile app (React Native)
- [ ] Push notifications
- [ ] Advanced analytics
- [ ] Admin dashboard
- [ ] Content moderation tools

---

## 🤝 Contributing

We welcome contributions! Follow these steps:

1. **Fork the Repository**
   ```bash
   git clone https://github.com/yourusername/NEXUS.git
   cd NEXUS
   git checkout -b feature/your-feature
   ```

2. **Make Your Changes**
   - Keep code clean and commented
   - Follow existing code style
   - Test thoroughly in browser

3. **Commit & Push**
   ```bash
   git add .
   git commit -m "feat: add new feature description"
   git push origin feature/your-feature
   ```

4. **Open a Pull Request**
   - Describe changes in detail
   - Link any related issues
   - Provide screenshots if UI changes

### Code Style Guidelines

- Use vanilla JavaScript (no frameworks)
- Keep functions focused and pure
- Add comments for complex logic
- Use meaningful variable names
- Mobile-first responsive design

### Report Issues

Found a bug? Please open an issue with:
- Browser & version
- Steps to reproduce
- Expected vs actual behavior
- Screenshots/videos if applicable

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 NEXUS Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, and/or sell copies of the
Software...
```

---

## 👨‍💻 Author

**Dharun Kumar M** [@dharun](https://github.com/dharu_kumar)

- 🚀 Full-Stack Developer
- 💡 Web Technology Enthusiast
- 📚 Open Source Contributor

### Connect With Me

- GitHub: [@dharun]([https://github.com/mdharunmdharun175-tech])
- Twitter: [@dharun46](https://x.com/Dharun_046)
- LinkedIn: [dharun-kumar](www.linkedin.com/in/dharun-kumar-m-691a04351)
- Portfolio: [dharunkumar.dev](https://yoursite.com)

---

## 🙏 Acknowledgments

- Design inspiration from LinkedIn, Twitter, and Instagram
- Font: Google Fonts (Plus Jakarta Sans, Clash Display)
- Community feedback and contributions
- Open source community support

---

## 📞 Support & Contact

Have questions or suggestions?

- **Issues**: [GitHub Issues](https://github.com/yourusername/NEXUS/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/NEXUS/discussions)
- **Email**: contact@mdharunmdharun175@gmail.com/Dharun-9342659272
- **Discord**: [Join Server](https://discord.gg/nexus)

---

## 📊 Project Statistics

- **Code Lines**: 2,000+ (HTML/CSS/JS)
- **Features**: 20+
- **Post Types**: 4
- **Views**: 7
- **Demo Users**: 5
- **Database Collections**: 4
- **CSS Variables**: 20+

---

## 🎓 Learning Resources

This project is perfect for learning:

- ✅ DOM manipulation with Vanilla JS
- ✅ CSS Grid & Flexbox layouts
- ✅ LocalStorage & Web APIs
- ✅ Event handling & delegation
- ✅ Component-based architecture
- ✅ Responsive design patterns
- ✅ UI/UX best practices
- ✅ State management without frameworks

---

## 📈 Get Started

```bash
# Clone and run
git clone https://github.com/yourusername/NEXUS.git
cd NEXUS
open index.html

# Login with demo account
Username: alex_v
Password: demo
```

---

<div align="center">

### ⭐ If you find this project useful, please consider giving it a star!

**[⬆ back to top](#-nexus--connect--create)**

</div>

---

**Last Updated**: March 2025 | **Version**: 1.0.0 | **Status**: ✅ Active Development
