# Time Fomo

**Live Demo:** [https://gerrix90.github.io/time-fomo/](https://gerrix90.github.io/time-fomo/)

An elegant web application for tracking remaining time until end of day, year-end, and special events, with life span visualization through hourglasses.

## Features

### Daily Countdown
Displays hours, minutes, and seconds remaining until the end of the current day with a clean, modern interface. The timer updates in real-time with a sleek display.

### Year Countdown
Shows the number of days remaining until the end of the current year (optional display that can be toggled in settings).

### Custom Event Countdown
Create a personalized countdown to any important date:
- Set a custom event name
- Choose a future date 
- Select display format (days only or days plus hours/minutes/seconds)
- See real-time updates until your special event arrives

### Life Hourglass Visualization
A unique visual representation of life as a series of hourglasses representing years:
- Past years displayed as empty hourglasses
- Current year shown with an animated hourglass (sand grains in motion)
- Future years represented as full hourglasses
- Customizable current age and target age settings

## Getting Started

### No Installation Required!
This application is built with vanilla JavaScript, HTML, and CSS with no external dependencies or build process. Just clone and run!

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- That's it!

### Running Locally

You can run the application in multiple ways:

**1. Open the HTML file directly**
Simply open the `index.html` file in your web browser.

**2. Use Python's built-in server**
```bash
# Python 3
python -m http.server

# Python 2
python -m SimpleHTTPServer
```
Then navigate to `http://localhost:8000` in your browser.

**3. Use Node.js http-server**
```bash
# Install http-server globally if not installed
npm install -g http-server

# Serve the current directory
http-server
```
Then navigate to the URL displayed in the terminal (typically `http://localhost:8080`).

## How to Use

### Navigation
Use the navigation buttons at the top of the page to switch between:
- "Countdowns" - Shows all time countdowns
- "Life Hourglass" - Displays the life visualization

### Settings
Click the gear icon in the top right corner to access settings for both features:

**Countdown Settings:**
- Toggle the year countdown visibility
- Enable/disable custom event countdown
- Set custom event name and date
- Choose display format (days only or full time)

**Life Hourglass Settings:**
- Set your current age
- Set your target age (maximum display)

### Hover Interactions
- Hover over the daily countdown or year countdown to see their labels
- Click on them to "pin" the label (stays visible)
- Hover over hourglasses in the Life Hourglass visualization to see them enlarge slightly

## Technical Details

### Technologies Used
- HTML5
- CSS3 (with Tailwind CSS via CDN)
- Vanilla JavaScript
- LocalStorage API for saving user preferences

### Key Implementation Features
- Responsive design that works on mobile and desktop
- CSS animations for interactive elements
- SVG graphics for the hourglasses
- LocalStorage for persistence between sessions
- No external libraries or frameworks required (besides Tailwind CSS)

### Using Tailwind CSS in production
The project relies on the Tailwind Play CDN for quick setup. Browsers display a
warning that the CDN build is not meant for production use. If you plan to use
the app offline or want to avoid this warning, compile Tailwind locally:

```bash
npx tailwindcss -i ./input.css -o ./tailwind.min.css --minify
```

Replace the `<script src="https://cdn.tailwindcss.com"></script>` tag in
`index.html` with a `<link rel="stylesheet" href="tailwind.min.css">` reference.

### Localization
The UI is available in English. The application was originally created in Croatian - the translations were provided for the following key terms:
- "Countdowns" (originally "Odbrojavanja")
- "Life Hourglass" (originally "Životni Pješčani Sat")
- "Settings" (originally "Postavke")
- "Days until year-end" (originally "Dana do kraja godine")
- "Time remaining until end of day" (originally "Preostalo vrijeme do kraja dana")

## Customization

### Adjusting the Appearance
You can modify the appearance by editing the CSS in the `<style>` section of the HTML file:
- Colors and gradients
- Animation timing and effects
- Layout and spacing
- Font sizes and weights

### Adding More Features
The codebase is designed to be easy to extend. Potential additions could include:
- Additional countdown types
- Different visualization styles
- Dark/light theme toggle
- Support for multiple languages
- Audible alerts when countdowns reach zero

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Tailwind CSS for the utility classes
- Inter font family for the typography
- Inspiration from various time tracking and life visualization tools