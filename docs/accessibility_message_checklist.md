# Accessibility Checklist for Success and Error Messages in UI

This checklist helps developers implement success and error messages in the user interface that comply with WCAG accessibility standards.

## Perceivable
- [ ] Use ARIA live regions (e.g., `aria-live="polite"` or `aria-live="assertive"`) to announce dynamic messages to screen reader users.
- [ ] Provide text alternatives for any non-text content (icons, images) used in messages.
- [ ] Ensure sufficient color contrast between message text and background (minimum 4.5:1 contrast ratio).

## Operable
- [ ] Programmatically associate messages with relevant input fields using attributes like `aria-describedby`.
- [ ] Ensure messages in overlays or dialogs are keyboard accessible and can be dismissed or interacted with using keyboard.
- [ ] Allow users sufficient time to read messages; avoid auto-dismissing messages too quickly.

## Understandable
- [ ] Use clear, concise, and jargon-free language in messages.
- [ ] Provide actionable guidance in error messages to help users correct input errors.
- [ ] Keep message formatting and placement consistent throughout the application.
- [ ] Use simple and direct confirmations for success messages.

## Robust
- [ ] Test message accessibility with popular screen readers and keyboard navigation.
- [ ] Use semantic HTML for alerts and messages, e.g., `role="alert"` for important notifications.
- [ ] Ensure messages are accessible across different browsers and devices.

---

Implementing this checklist will enhance accessibility compliance and improve user experience for all users.