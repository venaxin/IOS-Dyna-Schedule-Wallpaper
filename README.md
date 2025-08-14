# Dynamic Calendar Wallpaper for iOS

<img src="https://github.com/user-attachments/assets/de22be50-b329-4ac0-ad46-d59d3913f027" alt="Final Wallpaper Showcase" width="350"/>

A powerful, fully automated iOS Shortcut that generates a new lock screen wallpaper every day, displaying your upcoming schedule directly over a background image of your choice.

This project was born out of a desire to have a more productive and personalized iPhone lock screen. Instead of a static image, this shortcut provides an at-a-glance view of your week, ensuring you never miss an important event. It's designed to be both beautiful and functional, with a clean, readable layout and full customizability.

---

## Features

- **Fully Automated:** Set it once and get a new wallpaper every morning with your updated schedule.
- **Dynamic Schedule:** Pulls events directly from your iOS Calendar for the next 6 days.
- **Custom Backgrounds:** Automatically selects a random photo from a specified album in your Photos app.
- **Highly Customizable:** Easily change the font, text size, colors, and layout by editing simple CSS code within the shortcut.
- **Smart & Efficient:** Uses Base64 encoding to embed the background image directly into the HTML, creating a self-contained and reliable wallpaper generator.
- **Readable Design:** Implements a text shadow to ensure your schedule is legible over any background image, light or dark.

---

## Setup Guide

Follow these steps to get the Dynamic Calendar Wallpaper running on your iPhone.

### Step 1: Prerequisites

Before you install the shortcut, you need to have your calendar set up on your iPhone.

1.  **Sync Your Calendar:** If you use Google Calendar or another service, make sure it's synced to your iPhone. Go to **Settings > Calendar > Accounts** and add your account. Make sure the "Calendars" toggle is enabled.
2.  **Create a Photo Album:** Go to the **Photos** app and create a new album. Add all the pictures you want to use as potential backgrounds to this album.

### Step 2: Install the Shortcut

1.  Click the link below to download and add the shortcut to your Shortcuts app.
    *(https://www.icloud.com/shortcuts/39cb4da735d14c5ea922b2c6c695f5e0)*
    **[Download the Shortcut Here]**
2.  When prompted, tap **"Add Shortcut"**.

### Step 3: Configure the Shortcut

You need to tell the shortcut where to find your photos and calendar events.

1.  Open the **Shortcuts** app and find the "Dynamic Calendar Wallpaper" shortcut. Tap the three dots (**...**) on the shortcut to open the editor.
2.  **Select Your Photo Album:**
    -   Scroll down to the action that says **`Find Photos where Album is [Album Name]`**.
    -   Tap on the blue `[Album Name]` and select the photo album you created in Step 1.
3.  **Select Your Calendar:**
    -   Scroll further down to the action that says **`Find Calendar Events where Calendar is [Calendar Name]`**.
    -   Tap on the blue `[Calendar Name]` and select the specific calendar you want to pull events from (e.g., your Gmail account).
4.  Tap **"Done"** at the top right to save your changes.

### Step 4: Set Up the Daily Automation

This makes the shortcut run automatically every morning.

1.  In the Shortcuts app, tap the **"Automation"** tab at the bottom.
2.  Tap the **`+`** button at the top right and select **"Create Personal Automation"**.
3.  Choose **"Time of Day"** as the trigger.
4.  Set the time you want it to run (e.g., 7:00 AM) and make sure it's set to repeat **"Daily"**.
5.  Tap "Next".
6.  Tap **"Add Action"** and search for the **"Run Shortcut"** action.
7.  Tap on the blue `Shortcut` field and select your **"Dynamic Calendar Wallpaper"** shortcut.
8.  Tap "Next".
9.  **Important:** Turn **OFF** the toggle for **"Ask Before Running"** to make it fully automatic. Confirm by tapping "Don't Ask".
10. Tap **"Done"**.

Your setup is now complete! You will get a fresh, new wallpaper with your schedule every day.

---

## Customization

You can easily change the appearance of the text by editing the CSS code.

1.  Open the shortcut editor.
2.  Find the first **`Text`** action, which contains the `<style>` block.
3.  You can change values like:
    -   `font-size`: Make the text bigger or smaller.
    -   `color`: Change the text color (e.g., `black`, `#FF5733`).
    -   `text-shadow`: Adjust the shadow for readability.

---

## How It Works

This shortcut uses a self-contained HTML rendering method to create the wallpaper.

1.  It first finds a random background image, resizes it for performance, and encodes it into a Base64 text string.
2.  It then loops through the next 6 days, fetching calendar events for each day.
3.  This schedule information is formatted into an HTML list (`<ul>`).
4.  The Base64 image string and the schedule list are injected into a complete HTML document with CSS for styling.
5.  Finally, the shortcut uses the `Make Rich Text from HTML` and `Make PDF` actions to render this complete HTML file into a single, finished image, which is then set as the wallpaper.

This approach avoids common bugs with image overlays and transparency, providing a reliable and robust solution.
