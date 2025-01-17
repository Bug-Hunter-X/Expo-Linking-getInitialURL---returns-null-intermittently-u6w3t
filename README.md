# Expo Linking.getInitialURL() Intermittent Null Return

This repository demonstrates a bug where `Linking.getInitialURL()` in Expo sometimes returns `null`, even when a deep link is used to open the application.  The problem is intermittent and hard to reproduce reliably.

## Bug Reproduction

(Steps to reproduce the bug)
1. Run the app.
2. Open a deep link URL (e.g., `exp://127.0.0.1:19000`).
3. Observe that `Linking.getInitialURL()` might return `null`, despite the app being opened via the deep link.

## Solution

The solution involves using `Linking.addEventListener` to listen for URL changes asynchronously. This method provides more consistent results and overcomes the timing-related issues involved in directly calling `getInitialURL()`.