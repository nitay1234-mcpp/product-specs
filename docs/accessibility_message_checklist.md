# Accessibility Checklist for Success and Error Messages in UI

This checklist helps developers implement success and error messages in the user interface that comply with WCAG accessibility standards.

## Perceivable
- [ ] Use ARIA live regions (e.g., `aria-live="polite"` or `aria-live="assertive"`) to announce dynamic messages to screen reader users. (WCAG 2.1.1 - Keyboard, WCAG 3.2.2 - On Input)
- [ ] Provide text alternatives for any non-text content (icons, images) used in messages. (WCAG 1.1.1 - Non-text Content)
- [ ] Ensure sufficient color contrast between message text and background (minimum 4.5:1 contrast ratio). (WCAG 1.4.3 - Contrast Minimum)

## Operable
- [ ] Programmatically associate messages with relevant input fields using attributes like `aria-describedby`. (WCAG 4.1.2 - Name, Role, Value)
- [ ] Ensure messages in overlays or dialogs are keyboard accessible and can be dismissed or interacted with using keyboard. (WCAG 2.1.1 - Keyboard)
- [ ] Allow users sufficient time to read messages; avoid auto-dismissing messages too quickly. (WCAG 2.2.1 - Timing Adjustable)

## Understandable
- [ ] Use clear, concise, and jargon-free language in messages. (WCAG 3.1.5 - Reading Level)
- [ ] Provide actionable guidance in error messages to help users correct input errors. (WCAG 3.3.1 - Error Identification, WCAG 3.3.3 - Error Suggestion)
- [ ] Keep message formatting and placement consistent throughout the application.
- [ ] Use simple and direct confirmations for success messages.

## Robust
- [ ] Test message accessibility with popular screen readers and keyboard navigation. (WCAG 4.1.2 - Name, Role, Value)
- [ ] Use semantic HTML for alerts and messages, e.g., `role="alert"` for important notifications. (WCAG 4.1.2 - Name, Role, Value)
- [ ] Ensure messages are accessible across different browsers and devices.

---

Implementing this checklist will enhance accessibility compliance and improve user experience for all users.

---

### Examples:
- Use `<div role="alert" aria-live="assertive">Your refund was successful.</div>` to announce success immediately.
- Use `<span aria-live="polite">Error: Transaction ID is required.</span>` to politely notify errors without interrupting the user.
- Use `aria-describedby="error-id"` on input fields to link to error messages for focused context.
- Ensure color contrast like dark text (#000) on light backgrounds (#FFF) or use tools like the WebAIM Contrast Checker.