# 🎙️ Latest News Podcasts

A modern, responsive web application for aggregating and listening to the latest news podcasts from major international sources. Features real-time RSS feed parsing, advanced audio controls, and a clean, accessible interface.

## 📻 Featured News Sources

### English Podcasts
- **BBC Global News Podcast** - Breaking international news coverage
- **CBC** (5 shows) - Canadian perspective on world events
  - World Report - Daily international news
  - The House - Weekly politics
  - The World This Hour - Hourly updates
  - Your World Tonight - Evening news
  - At Issue - Political panel discussions
- **ABC (Australia) AM** - Australian morning news program
- **Al Jazeera Updates** - Middle Eastern perspective
- **NPR News Now** - American public radio updates
- **Democracy Now!** - Independent daily news program

### French Podcasts
- **News in Slow French** - French language learning with current events
- **France Inter - L'invité 8h20** - Daily interviews with newsmakers
- **InnerFrench Podcast** - Advanced French learning with cultural topics

## ✨ Features

### 🎵 Advanced Audio Controls
- **Global Speed Control** (0.5x to 2x) - Set playback speed for all episodes
- **Sleep Timer** (5-25 minutes in 5min intervals) - Gradual volume fade for bedtime listening
- **30-Second Skip Controls** - Forward/backward buttons + keyboard shortcuts (←/→/Space)
- **Auto-pause others** - Starting one episode pauses all others
- **Smart button states** - Skip buttons disabled at episode boundaries
- **Keyboard shortcuts** - Global hotkeys for active audio (arrows + spacebar)

### 📱 Modern Interface
- **Responsive design** - Works on desktop, tablet, and mobile
- **Dark/Light themes** - Toggle between themes with persistent settings
- **Progressive loading** - Episodes appear as feeds load (no waiting)
- **Date sorting** - Latest news always appears first
- **Language switching** - English ↔ French ↔ Both views

### 📰 Rich Episode Information
- **Episode images** - Artwork from RSS feeds when available
- **Duration display** - See episode length at a glance (⏱️ 32:24)
- **Publication times** - "2 hours ago" with timezone awareness
- **Expandable summaries** - Detailed episode descriptions (where meaningful)
- **Metadata** - Author and duration information

### 🔧 Technical Features
- **Duplicate Detection** - Prevents same episodes from multiple sources using GUID/audio URL tracking
- **CORS proxy fallback** - Multiple proxy services for reliable RSS access
- **Browser-like headers** - Improved compatibility with RSS feeds
- **Error handling** - Graceful degradation when feeds are unavailable
- **Smart caching** - localStorage with version control and manual cache clearing
- **Audio detection** - Only displays true podcast feeds (filters out articles)
- **Cache management** - Clear cache button with automatic version updates

### ♿ Accessibility Features (WCAG 2.2 AA Compliant)
- **Semantic HTML** - Proper heading hierarchy, landmarks, and roles
- **Screen reader support** - ARIA labels, live regions, and descriptive text
- **Keyboard navigation** - Full keyboard access with skip links and focus management
- **Color contrast** - 4.5:1 contrast ratio in both dark and light themes
- **Touch targets** - Minimum 44px for mobile accessibility
- **Alternative text** - Proper image descriptions and button labels

## 🚀 Quick Start

1. **Clone or download** this repository
2. **Start a local server** (required for CORS):
   ```bash
   cd news
   python3 -m http.server 8091
   ```
3. **Open browser** to `http://localhost:8091/podcasts-en.html`
4. **Set preferences** - Choose your preferred speed and sleep timer
5. **Browse episodes** - Click "📖 Show Details" for full descriptions
6. **Start listening** - Click "Play" on any episode

## 📁 Project Structure

```
news/
├── podcasts-en.html          # Main application (single file)
├── podcasts-en-fixed.html    # Backup version
└── README.md                 # This documentation
```

## 🛠️ Technology Stack

- **Pure HTML5/CSS3/JavaScript** - No external dependencies
- **CSS Custom Properties** - For theming system
- **Fetch API** - For RSS feed retrieval with timeout handling
- **DOMParser** - For XML/RSS parsing
- **localStorage** - For preferences and caching
- **CSS Grid** - For responsive card layouts
- **Modern ES6+** - Arrow functions, async/await, template literals

## 🎯 Use Cases

- **Morning news briefing** - Quick scan of latest global events
- **Bedtime listening** - Use sleep timer for gradual fade-out
- **Language learning** - French podcasts with adjustable speed
- **Commuting** - Speed control and skip functions for time-efficient listening
- **Ad skipping** - 30-second forward jumps to skip commercials quickly
- **News comparison** - Multiple perspectives on current events without duplicates
- **Accessibility needs** - Full WCAG 2.2 AA compliance for all users
- **Keyboard users** - Complete keyboard navigation with shortcuts

## 🔄 RSS Feed Processing

The application intelligently processes various RSS feed formats:

- **Duplicate prevention** - Uses GUID → audioUrl → link → title hierarchy for unique identification
- **Audio detection** - Filters out article-only feeds using enclosure validation
- **Image extraction** - Episode artwork → Channel artwork → Fallback with error handling
- **Duration parsing** - Handles seconds, MM:SS, and HH:MM:SS formats from different sources
- **Description cleaning** - Removes HTML tags, normalizes whitespace, selective hiding for non-descriptive feeds
- **Date parsing** - Multiple timestamp formats with timezone handling and "hours ago" display
- **CORS handling** - Multiple proxy fallbacks with User-Agent spoofing for reliable access
- **Cache versioning** - Automatic cache invalidation when deduplication logic updates

## 🎨 Design Principles

- **Information hierarchy** - Important details prominently displayed with 14pt minimum font
- **Minimal cognitive load** - Clean, uncluttered interface with progressive loading
- **Progressive disclosure** - Details available but not overwhelming (expandable summaries)
- **Consistent interaction** - Global controls, predictable behavior, unified skip controls
- **Accessibility first** - WCAG 2.2 AA compliance, proper contrast, keyboard navigation, screen reader support
- **Performance focused** - Duplicate detection, smart caching, progressive rendering
- **Multi-modal input** - Mouse, touch, and keyboard interaction patterns

## 🔮 AI Prompt That Could Generate This Project

If you wanted to recreate this project using a single AI prompt, here's what you might use:

---

**"Create a modern, single-file HTML podcast news aggregator with the following specifications:**

**Core Functionality:**
- Aggregate RSS feeds from BBC, CBC (5 shows), ABC Australia, Al Jazeera, NPR, and Democracy Now
- Add French feeds: News in Slow French, France Inter, and InnerFrench
- Parse RSS/XML using DOMParser with multiple CORS proxy fallbacks and User-Agent spoofing
- Implement duplicate detection using GUID → audioUrl → link → title hierarchy
- Display latest episodes with date sorting (newest first) and no duplicate episodes
- Progressive loading - show cards as feeds load individually with fade-in animations

**Audio Features:**
- Global speed control (0.5x-2x) and sleep timer (5-25min in 5min intervals) at top of page
- 30-second skip controls (⏪/⏩ buttons) on each episode with smart boundary detection
- Keyboard shortcuts: ← (skip back), → (skip forward), Space (play/pause) for active audio
- Sleep timer with 2-minute gradual volume fade before auto-pause
- Auto-pause other episodes when starting new one
- Apply global settings to newly played audio with real-time speed adjustment

**Interface Requirements:**
- Dark/light theme toggle with localStorage persistence and WCAG AA 4.5:1 contrast
- English/French/Both language switching with cache management
- Responsive CSS Grid layout with 280px minimum card width
- Each card shows: source, episode image, title (14pt), time + duration, Play button, skip controls
- Expandable episode summaries (hide for NPR/ABC/Al Jazeera - no useful summaries)
- 80x80px podcast images with fallback handling and error states
- Clear cache button with manual cache clearing functionality
- Keyboard shortcut hints displayed in global controls area

**Technical Details:**
- Handle duration formats: seconds (BBC), MM:SS (Democracy Now), HH:MM:SS (CBC)
- Extract images from itunes:image, media:thumbnail, or channel image
- Use browser-like headers for better RSS access
- Filter out non-podcast feeds (must have audio enclosures)
- Handle CBC contentLink audio elements
- Progressive loading with fade-in animations
- CORS proxies: corsproxy.io, api.codetabs.com, cors-anywhere.herokuapp.com

**Styling:**
- CSS custom properties for theming
- Dark theme: #0b0c0d background, #15171a cards, #79b8ff accent
- Light theme: white background, #f8f9fa cards, #0366d6 accent
- Loading spinner with minimal animation
- Clean typography with system fonts
- Proper hover states and accessibility

**Error Handling:**
- Graceful degradation when feeds fail
- Multiple CORS proxy attempts
- Console logging for debugging
- Error messages for users when all feeds fail

## AI Prompt

I need a single HTML file that creates a fully accessible podcast aggregator. It should:

1. **Fetch and Parse RSS**: Aggregate 15+ podcast RSS feeds (English and French news/politics)
2. **Display Cards**: Show episodes in reverse chronological order with podcast source, image, title, time/duration
3. **Audio Controls**: 30-second skip forward/backward buttons, keyboard shortcuts (←/→/Space), HTML5 player integration
4. **Accessibility**: WCAG 2.2 AA compliant with semantic HTML, ARIA labels, keyboard navigation, 4.5:1 contrast ratios
5. **Responsive Design**: CSS Grid layout, dark/light themes with accessible colors, expandable summaries
6. **Language Filter**: Switch between English, French, or Both languages with cache management
7. **Duplicate Prevention**: Track seen episodes using GUID → audioUrl → link → title hierarchy
8. **Data Processing**: Parse pubDate, handle various RSS formats, manage images and fallbacks
9. **Performance**: Progressive loading with fade animations, cache versioning, manual cache clearing

Key feeds to include: CBC, BBC, NPR, PBS, Al Jazeera, France Info, RFI, Radio Canada, InnerFrench, etc.

Technical requirements: Vanilla HTML/CSS/JS, localStorage for themes and cache, CORS proxy fallbacks, comprehensive error handling, semantic HTML landmarks, ARIA live regions for dynamic content.

Use modern JavaScript (async/await, fetch, CSS custom properties) in a single HTML file with embedded CSS and JavaScript.

---

This prompt would generate approximately 90% of the current functionality, though refinements would likely be needed for the specific feed handling and advanced features.

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Feel free to submit issues, feature requests, or pull requests. Areas for potential enhancement:

- Additional news sources
- Playlist functionality  
- Offline caching
- Keyboard shortcuts
- Social sharing
- Export/import settings
- PWA capabilities

---

*Last updated: September 29, 2025*