# Mobile App Test Cases

## Scope
Installation, launch, permissions, navigation, interruptions, network behavior, background/foreground states, orientation, notifications, deep links, session handling, updates, device compatibility, and mobile-specific edge cases for Android and iOS applications.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| MOB-001 | Install application | 1. Install app on supported device<br>2. Complete installation | Supported device | App installs successfully without errors | — | Not Run | High | — | Installation |
| MOB-002 | First application launch | 1. Install app<br>2. Launch app | Fresh install | App launches successfully and expected first-launch flow appears | — | Not Run | High | — | Smoke |
| MOB-003 | Relaunch application | 1. Open app<br>2. Close app<br>3. Reopen | Existing installation | App launches normally without corrupted state | — | Not Run | High | — | Smoke |
| MOB-004 | App launch while offline | 1. Disable internet<br>2. Launch app | Offline device | App handles offline state according to requirements without crashing | — | Not Run | High | — | Network |
| MOB-005 | Login on mobile app | 1. Open app<br>2. Enter valid credentials<br>3. Login | Valid credentials | User logs in successfully | — | Not Run | High | — | Authentication |
| MOB-006 | Session persists after app restart | 1. Login<br>2. Close app<br>3. Reopen | Logged-in user | Session persists according to authentication requirements | — | Not Run | High | — | Session |
| MOB-007 | Logout | 1. Login<br>2. Tap Logout | Logged-in user | User is logged out and protected content becomes inaccessible | — | Not Run | High | — | Authentication |
| MOB-008 | Protected screen after logout | 1. Login<br>2. Open protected screen<br>3. Logout<br>4. Attempt to reopen protected content | Protected content | Authentication is required and protected data is not exposed | — | Not Run | High | — | Security-focused |
| MOB-009 | App navigation | 1. Navigate through primary screens/tabs | N/A | Navigation opens correct screens without unexpected state loss | — | Not Run | High | — | Navigation |
| MOB-010 | Android system Back button | 1. Navigate through multiple screens<br>2. Press system Back | Android device | App follows expected navigation hierarchy | — | Not Run | Medium | — | Android |
| MOB-011 | Back gesture/navigation on iOS | 1. Navigate to child screen<br>2. Use supported back gesture/control | iOS device | Previous screen opens correctly | — | Not Run | Medium | — | iOS |
| MOB-012 | App sent to background | 1. Open app<br>2. Send app to background | Active session | App preserves/handles state according to requirements | — | Not Run | High | — | Lifecycle |
| MOB-013 | Return app to foreground | 1. Background app<br>2. Reopen it | Active session | App resumes correctly without broken/stale UI | — | Not Run | High | — | Lifecycle |
| MOB-014 | Long background duration | 1. Login<br>2. Background app for configured session period<br>3. Reopen | Active session | Session and screen state follow timeout/security requirements | — | Not Run | High | — | Session |
| MOB-015 | Force close and reopen | 1. Use app<br>2. Force close<br>3. Reopen | Existing session | App recovers without corrupted state or crash | — | Not Run | High | — | Lifecycle |
| MOB-016 | Incoming call interruption | 1. Use app<br>2. Receive/simulate incoming call<br>3. Return to app | Active workflow | App resumes safely and entered/saved state follows requirements | — | Not Run | Medium | — | Interruption |
| MOB-017 | Notification interruption | 1. Use app<br>2. Receive another notification<br>3. Return to app | Active workflow | App remains stable and current workflow is preserved appropriately | — | Not Run | Medium | — | Interruption |
| MOB-018 | Screen lock/unlock | 1. Open app<br>2. Lock device<br>3. Unlock | Active session | App follows expected security/session behavior | — | Not Run | High | — | Security-focused |
| MOB-019 | Network switches Wi-Fi to mobile data | 1. Use app on Wi-Fi<br>2. Switch to mobile data<br>3. Continue action | Active session | App handles network transition without incorrect state | — | Not Run | High | — | Network |
| MOB-020 | Network switches mobile data to Wi-Fi | 1. Use app on mobile data<br>2. Switch to Wi-Fi | Active session | App continues/reconnects correctly | — | Not Run | Medium | — | Network |
| MOB-021 | Network lost during request | 1. Start data operation<br>2. Disable network before completion | Valid action | Error/retry state is displayed and false success is avoided | — | Not Run | High | — | Error handling |
| MOB-022 | Network restored | 1. Lose connection<br>2. Restore network<br>3. Retry/continue | N/A | App recovers according to requirements | — | Not Run | High | — | Recovery |
| MOB-023 | Slow network | 1. Use app under slow network conditions<br>2. Perform data operation | Slow connection | Loading states appear correctly and app remains usable | — | Not Run | Medium | — | Performance |
| MOB-024 | Camera permission allowed | 1. Trigger camera feature<br>2. Allow permission | Camera permission | Camera-dependent feature works correctly | — | Not Run | Medium | — | Permission |
| MOB-025 | Camera permission denied | 1. Trigger camera feature<br>2. Deny permission | Permission denied | App handles denial gracefully and provides appropriate guidance | — | Not Run | Medium | — | Permission |
| MOB-026 | Photo/media permission | 1. Trigger image/file selection<br>2. Allow required permission | Media permission | User can select supported media successfully | — | Not Run | Medium | — | Permission |
| MOB-027 | Location permission allowed | 1. Trigger location feature<br>2. Allow permission | Location permission | Location-dependent feature works according to requirements | — | Not Run | Medium | — | Permission |
| MOB-028 | Location permission denied | 1. Trigger location feature<br>2. Deny permission | Permission denied | App remains usable and handles unavailable location appropriately | — | Not Run | Medium | — | Permission |
| MOB-029 | Notification permission denied | 1. Deny notification permission<br>2. Continue using app | Permission denied | App handles denial without blocking unrelated functionality | — | Not Run | Medium | — | Permission |
| MOB-030 | Permission permanently denied | 1. Deny permission according to OS flow<br>2. Trigger feature again | Permission denied | App follows platform requirements and provides settings guidance when appropriate | — | Not Run | Medium | — | Permission |
| MOB-031 | Portrait orientation | 1. Open supported screen in portrait | Portrait | UI displays correctly without clipping/overlap | — | Not Run | Medium | — | UI |
| MOB-032 | Landscape orientation | 1. Rotate device to landscape where supported | Landscape | UI adapts correctly according to product requirements | — | Not Run | Medium | — | UI |
| MOB-033 | Orientation change during data entry | 1. Enter unsaved data<br>2. Rotate device | Partial form data | Data/state is not unexpectedly lost | — | Not Run | Medium | — | Edge case |
| MOB-034 | Keyboard appearance | 1. Tap text input | N/A | Keyboard appears without incorrectly hiding active input/actions | — | Not Run | Medium | — | UI |
| MOB-035 | Keyboard dismissal | 1. Open keyboard<br>2. Dismiss using supported method | N/A | Keyboard closes correctly and screen remains usable | — | Not Run | Low | — | UI |
| MOB-036 | Different screen sizes | 1. Open app on supported small and large screens<br>2. Review core screens | Multiple devices | Content remains readable and controls accessible | — | Not Run | High | — | Compatibility |
| MOB-037 | Dynamic text/font scaling | 1. Increase OS text size<br>2. Open core screens | Large text setting | UI follows accessibility/product requirements without critical clipping | — | Not Run | Medium | — | Accessibility |
| MOB-038 | Dark mode | 1. Enable device dark mode<br>2. Open app | Dark mode | App follows supported theme behavior with readable content | — | Not Run | Medium | — | UI |
| MOB-039 | Light mode | 1. Enable light mode<br>2. Open app | Light mode | Content displays correctly | — | Not Run | Medium | — | UI |
| MOB-040 | Push notification while app foregrounded | 1. Keep app open<br>2. Trigger push | Valid notification | Foreground notification follows defined behavior | — | Not Run | Medium | — | Push |
| MOB-041 | Push notification while backgrounded | 1. Background app<br>2. Trigger push | Valid notification | Notification is delivered according to requirements | — | Not Run | High | — | Push |
| MOB-042 | Tap push notification | 1. Receive push<br>2. Tap notification | Valid notification | Correct app screen/content opens | — | Not Run | High | — | Deep link |
| MOB-043 | Push notification after logout | 1. Logout<br>2. Trigger/open protected notification | Protected notification | Private content remains protected | — | Not Run | High | — | Security-focused |
| MOB-044 | Deep link while app installed | 1. Open supported deep link | Valid deep link | Correct app screen opens | — | Not Run | High | — | Deep link |
| MOB-045 | Deep link to restricted content | 1. Open restricted deep link as unauthorized user | Restricted link | Access is denied without exposing protected data | — | Not Run | High | — | Authorization |
| MOB-046 | App update preserves user data | 1. Install previous supported version<br>2. Create/login with data<br>3. Update app | Existing app data | Update completes and intended user data/settings remain intact | — | Not Run | High | — | Upgrade |
| MOB-047 | App version update | 1. Update to latest build<br>2. Launch<br>3. Test smoke flow | Updated build | App launches and core flow works after update | — | Not Run | High | — | Regression |
| MOB-048 | Low storage condition | 1. Use device/test environment with limited storage<br>2. Perform storage-dependent action | Low storage | App handles storage failure appropriately without data corruption | — | Not Run | Medium | — | Edge case |
| MOB-049 | Rapid repeated taps | 1. Rapidly tap primary action multiple times | Valid action | Duplicate unintended actions/records are prevented | — | Not Run | High | — | Edge case |
| MOB-050 | App remains stable during repeated navigation | 1. Navigate repeatedly between core screens<br>2. Perform common actions | N/A | App remains responsive without crashes or corrupted navigation state | — | Not Run | Medium | — | Stability |
| MOB-051 | Sensitive data in app switcher | 1. Open sensitive screen<br>2. Send app to background<br>3. View recent-app preview | Sensitive screen | Sensitive information follows product security/privacy requirements | — | Not Run | High | — | Security-focused |
| MOB-052 | Sensitive data after logout | 1. Login and view private data<br>2. Logout<br>3. Navigate/reopen app | Private data | Previously authenticated private data is not improperly accessible | — | Not Run | High | — | Security-focused |
| MOB-053 | Android supported OS versions | 1. Install/run app across supported Android versions<br>2. Execute smoke flow | Supported Android versions | Core functionality works across supported Android versions | — | Not Run | Medium | — | Android |
| MOB-054 | iOS supported OS versions | 1. Install/run app across supported iOS versions<br>2. Execute smoke flow | Supported iOS versions | Core functionality works across supported iOS versions | — | Not Run | Medium | — | iOS |
| MOB-055 | App behavior after device restart | 1. Login/use app<br>2. Restart device<br>3. Open app | Existing installation | App/session behaves according to persistence/security requirements | — | Not Run | Medium | — | Lifecycle |
