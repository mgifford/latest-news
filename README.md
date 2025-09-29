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

## ✨ Features

### 🎵 Advanced Audio Controls
- **Global Speed Control** (0.5x to 2x) - Set playback speed for all episodes
- **Sleep Timer** (15min to 1 hour) - Gradual volume fade for bedtime listening
- **Auto-pause others** - Starting one episode pauses all others
- **Progress preservation** - Audio controls remember your preferences

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
- **CORS proxy fallback** - Multiple proxy services for reliable RSS access
- **Browser-like headers** - Improved compatibility with RSS feeds
- **Error handling** - Graceful degradation when feeds are unavailable
- **Caching** - localStorage for improved performance
- **Audio detection** - Only displays true podcast feeds (filters out articles)

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
- **Commuting** - Speed control for time-efficient listening
- **News comparison** - Multiple perspectives on current events
- **Accessibility** - Screen reader friendly with proper ARIA labels

## 🔄 RSS Feed Processing

The application intelligently processes various RSS feed formats:

- **Audio detection** - Filters out article-only feeds
- **Image extraction** - Episode artwork → Channel artwork → Fallback
- **Duration parsing** - Handles seconds, MM:SS, and HH:MM:SS formats
- **Description cleaning** - Removes HTML tags, normalizes whitespace
- **Date parsing** - Multiple timestamp formats with timezone handling
- **CORS handling** - Multiple proxy fallbacks for reliable access

## 🎨 Design Principles

- **Information hierarchy** - Important details prominently displayed
- **Minimal cognitive load** - Clean, uncluttered interface
- **Progressive disclosure** - Details available but not overwhelming
- **Consistent interaction** - Global controls, predictable behavior
- **Accessibility first** - Proper contrast, keyboard navigation, screen reader support

## 🔮 AI Prompt That Could Generate This Project

If you wanted to recreate this project using a single AI prompt, here's what you might use:

---

**"Create a modern, single-file HTML podcast news aggregator with the following specifications:**

**Core Functionality:**
- Aggregate RSS feeds from BBC, CBC (5 shows), ABC Australia, Al Jazeera, NPR, and Democracy Now
- Add French feeds: News in Slow French and France Inter
- Parse RSS/XML using DOMParser with multiple CORS proxy fallbacks
- Display latest episodes with date sorting (newest first)
- Progressive loading - show cards as feeds load individually

**Audio Features:**
- Global speed control (0.5x-2x) and sleep timer (15min-1hr) at top of page
- Sleep timer with 2-minute gradual volume fade before auto-pause
- Auto-pause other episodes when starting new one
- Apply global settings to newly played audio

**Interface Requirements:**
- Dark/light theme toggle with localStorage persistence
- English/French/Both language switching
- Responsive CSS Grid layout with 280px minimum card width
- Each card shows: source, episode image, title (14pt), time + duration, Play button
- Expandable episode summaries (hide for NPR/ABC/Al Jazeera - no useful summaries)
- 80x80px podcast images with fallback handling

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

Use modern JavaScript (async/await, fetch, CSS custom properties) in a single HTML file with embedded CSS and JavaScript."**

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
