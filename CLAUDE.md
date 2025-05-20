# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Time Counter (also referred to as "Time Fomo" in the README) is a web-based application that provides various time-related countdown features:

1. Daily countdown (time remaining until end of day)
2. Year countdown (days remaining until end of year)
3. Custom event countdown (days/time until a user-specified event)
4. Life hourglass visualization (a visual representation of age/life progression)

The application is built with vanilla JavaScript, HTML, and CSS (using Tailwind CSS for styling via CDN). It uses LocalStorage to persist user settings and preferences. All code is contained within a single HTML file (index.html).

## Development Commands

### Serve the Application

To serve the application locally using Python's built-in HTTP server:

```bash
# Python 3
python -m http.server

# Python 2
python -m SimpleHTTPServer
```

Or using Node.js with a package like `http-server`:

```bash
# Install http-server globally if not installed
npm install -g http-server

# Serve the current directory
http-server
```

### Open HTML File Directly

The application can also be opened directly in a browser without a server by opening the `index.html` file.

## Project Structure

- `index.html`: The main and only HTML file, containing all the application markup, styling, and JavaScript.

## Key Features

### Time-related Countdowns

1. **Daily Countdown**: Shows hours, minutes, and seconds remaining until the end of the current day.
2. **Year Countdown**: Shows days remaining until the end of the current year (optional display).
3. **Custom Event Countdown**: Allows users to set a custom event with a name and date, displaying the countdown to that event.

### Life Hourglass Visualization

A visual representation of life as a series of hourglasses representing years, with:
- Past years (empty hourglasses)
- Current year (hourglass with animated sand grains)
- Future years (full hourglasses)

## Application Architecture

The application follows a simple architecture:

1. **HTML Structure**: Defines the UI elements for the different features.
2. **CSS Styling**: Uses Tailwind CSS for layout and custom CSS for animations and specialized styling.
3. **JavaScript Logic**:
   - Element references and initialization
   - Event listeners for user interactions
   - Functions for updating and rendering the countdowns
   - LocalStorage integration for persistence

### Key JavaScript Components

- **Navigation System**: Handles switching between the "Countdowns" and "Life Hourglass" pages
- **Settings Modal**: Unified settings panel for all application features
- **Countdown Logic**: Functions for calculating and displaying time remaining
- **Life Hourglass Logic**: Visualization of age progression with SVG hourglasses
- **LocalStorage Integration**: Saves user preferences and settings

## Working with the Codebase

When working with this codebase, keep in mind:

1. All code is contained in a single HTML file with embedded CSS and JavaScript
2. User settings are stored in LocalStorage using these keys:
   - `customCountdownEvent`: Stores custom event data
   - `yearCountdownVisible`: Controls visibility of year countdown
   - `customEventDisplayFormat`: Format for displaying custom event countdown
   - `customEventMasterVisible`: Master toggle for custom event visibility
   - `fomoLifeCalendarAge`: User's current age for life hourglass
   - `fomoLifeCalendarMaxAge`: Target age for life hourglass

### JavaScript Code Structure

The JavaScript code is organized in the following sections:

1. **Global Variables and Constants** (lines 431-442): Defines localStorage keys and global state variables.
2. **DOM Element References** (lines 444-498): Organizes DOM elements by functionality (timers, life hourglass, navigation, modal).
3. **Navigation and Modal Functions** (lines 502-645): Handles page transitions and settings modal behavior.
4. **Timer Page Functions** (lines 649-783): Manages daily countdown, year countdown, and custom event countdown logic.
5. **Life Hourglass Functions** (lines 786-878): Handles the life visualization component with SVG hourglasses.
6. **Application Initialization** (lines 881-898): Sets up the application on page load.

When making changes, maintain this organizational structure and follow the existing coding patterns.

## Animation System

The application includes several animations:
- CSS transitions for page navigation (fade in/out effects)
- Sand grain animations in the current year's hourglass using CSS keyframes
- Hover effects on hourglasses and other UI elements

## Modal System

The settings interface uses a unified modal that:
- Provides settings for both Countdowns and Life Hourglass features
- Saves settings to LocalStorage
- Updates the UI dynamically when settings are changed

## Language Support

The application UI text is currently in Croatian. Key terms:
- "Odbrojavanja" = Countdowns
- "Životni Pješčani Sat" = Life Hourglass
- "Postavke" = Settings
- "Dana do kraja godine" = Days until end of year
- "Preostalo vrijeme do kraja dana" = Remaining time until end of day

## Common Tasks and Debugging

### Adding a New Feature

When adding a new feature to the application:

1. Locate the appropriate section in the HTML for UI elements
2. Add any needed CSS styles to the `<style>` section
3. Implement the JavaScript functionality in the appropriate section of the script
4. Update localStorage keys/handling if the feature requires persistence
5. Add any new modal settings to the unified settings modal

### Testing

To test the application:
1. Serve the application using one of the methods in the Development Commands section
2. Open the browser's console (F12 or Cmd+Option+I) to check for JavaScript errors
3. Test feature interactions, especially between pages and with the settings modal
4. Verify that localStorage persistence works by refreshing the page

### Common Issues

- **Settings not saving**: Verify localStorage key names and data formats match those in the constants section
- **Animations not working**: Check CSS transitions and class toggle logic in the JavaScript
- **Modal display problems**: Verify modal visibility toggling in the unified modal functions
- **Page transition issues**: Check the showPage function and content-enter/exit classes