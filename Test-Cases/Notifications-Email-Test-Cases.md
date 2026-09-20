# Notifications & Email Test Cases

## Scope
Positive, negative, preference, delivery, duplicate prevention, deep-link, read/unread, email, push, in-app notification, and error-handling test cases.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| NOTIF-001 | In-app notification generated | 1. Perform notification-triggering action<br>2. Open notifications | Valid trigger | Correct notification is created for intended user | — | Not Run | High | — | Positive |
| NOTIF-002 | Email notification generated | 1. Perform email-triggering action<br>2. Check inbox | Valid email | Correct email is delivered according to notification rules | — | Not Run | High | — | Email |
| NOTIF-003 | Push notification generated | 1. Enable push<br>2. Trigger notification<br>3. Check device | Registered device | Correct push notification is delivered | — | Not Run | High | — | Mobile |
| NOTIF-004 | Correct notification recipient | 1. Trigger user-specific event<br>2. Check relevant accounts | User A / User B | Notification is sent only to intended recipient(s) | — | Not Run | High | — | Data isolation |
| NOTIF-005 | Notification content accuracy | 1. Trigger notification<br>2. Review title/body/details | Known event | Notification displays correct event information | — | Not Run | High | — | Data accuracy |
| NOTIF-006 | Notification timestamp | 1. Trigger event<br>2. Review notification | Known event time | Timestamp is displayed correctly according to product/timezone rules | — | Not Run | Medium | — | Data accuracy |
| NOTIF-007 | Open notification | 1. Receive notification<br>2. Click/tap it | Existing notification | Correct destination or detail view opens | — | Not Run | High | — | Navigation |
| NOTIF-008 | Notification deep link | 1. Receive notification<br>2. Open from notification link | Valid notification | User lands on correct record/page | — | Not Run | High | — | Deep link |
| NOTIF-009 | Deep link while logged out | 1. Logout<br>2. Open protected notification link<br>3. Authenticate | Protected link | Authentication is required and post-login navigation follows requirements | — | Not Run | High | — | Authorization |
| NOTIF-010 | Unauthorized notification deep link | 1. Login as different user<br>2. Open another user's notification link | Restricted link | Unauthorized data is not exposed | — | Not Run | High | — | Security-focused |
| NOTIF-011 | Mark notification as read | 1. Open unread notification | Unread notification | Notification becomes read according to requirements | — | Not Run | Medium | — | State |
| NOTIF-012 | Mark notification as unread | 1. Select read notification<br>2. Mark unread | Read notification | Notification returns to unread state | — | Not Run | Medium | — | State |
| NOTIF-013 | Mark all as read | 1. Have multiple unread notifications<br>2. Select Mark All Read | Multiple notifications | All eligible notifications become read | — | Not Run | Medium | — | Bulk action |
| NOTIF-014 | Unread count accuracy | 1. Generate multiple notifications<br>2. Read some<br>3. Check badge/count | Multiple notifications | Unread count matches actual unread notifications | — | Not Run | High | — | Data accuracy |
| NOTIF-015 | Duplicate notification prevention | 1. Trigger one event once<br>2. Check notifications | Single event | Unintended duplicate notifications are not created | — | Not Run | High | — | Duplicate prevention |
| NOTIF-016 | Rapid repeated event | 1. Trigger same event rapidly according to supported flow<br>2. Check notifications | Repeated event | Notifications follow configured deduplication/frequency rules | — | Not Run | Medium | — | Edge case |
| NOTIF-017 | Notification ordering | 1. Generate notifications at different times<br>2. Open list | Multiple notifications | Notifications appear in defined order | — | Not Run | Medium | — | Sorting |
| NOTIF-018 | Notification preference OFF | 1. Disable notification type<br>2. Trigger corresponding event | Preference OFF | Disabled notification channel/type is suppressed according to requirements | — | Not Run | High | — | Preferences |
| NOTIF-019 | Notification preference ON | 1. Enable notification type<br>2. Trigger corresponding event | Preference ON | Eligible notification is delivered | — | Not Run | High | — | Preferences |
| NOTIF-020 | Preference persists after refresh | 1. Change notification setting<br>2. Save<br>3. Refresh | ON/OFF | Selected preference persists | — | Not Run | Medium | — | Persistence |
| NOTIF-021 | Preference persists after re-login | 1. Change preference<br>2. Logout<br>3. Login | ON/OFF | Saved preference remains applied | — | Not Run | Medium | — | Persistence |
| NOTIF-022 | Unsubscribe from email | 1. Open supported unsubscribe control<br>2. Unsubscribe<br>3. Trigger eligible email | Subscribed user | User is unsubscribed according to applicable notification rules | — | Not Run | High | — | Email preference |
| NOTIF-023 | Email suppressed after unsubscribe | 1. Unsubscribe<br>2. Trigger non-mandatory email | Unsubscribed user | Suppressed email is not sent | — | Not Run | High | — | Email preference |
| NOTIF-024 | Re-subscribe to email | 1. Re-enable supported email preference<br>2. Trigger eligible event | Re-subscribed user | Eligible email delivery resumes according to requirements | — | Not Run | High | — | Email preference |
| NOTIF-025 | Transactional email behavior | 1. Disable optional marketing/notification preferences<br>2. Trigger required transactional event | Transactional event | Transactional email follows product/legal requirements independently of optional preferences | — | Not Run | High | — | Business rules |
| NOTIF-026 | Email subject accuracy | 1. Trigger email<br>2. Review subject | Known event | Subject accurately represents the event | — | Not Run | Medium | — | Email |
| NOTIF-027 | Email recipient accuracy | 1. Trigger user-specific email<br>2. Inspect recipient | User email | Email is sent to correct intended address | — | Not Run | High | — | Data accuracy |
| NOTIF-028 | Email content accuracy | 1. Trigger email<br>2. Review content | Known event | Email contains correct user/event information | — | Not Run | High | — | Email |
| NOTIF-029 | Email links | 1. Receive email<br>2. Open supported links/buttons | Valid email | Links navigate to correct and authorized destination | — | Not Run | High | — | Navigation |
| NOTIF-030 | Expired email action link | 1. Open time-limited link after expiration | Expired link | Expired action is rejected with appropriate recovery flow | — | Not Run | High | — | Negative |
| NOTIF-031 | Email layout on mobile | 1. Open email on supported mobile client/device | Notification email | Content remains readable and actions usable | — | Not Run | Medium | — | Responsive |
| NOTIF-032 | Broken/missing email image | 1. Trigger email containing images<br>2. Review rendering | Email with images | Images follow expected rendering/fallback behavior without breaking core content | — | Not Run | Medium | — | Email UI |
| NOTIF-033 | Email variables/placeholders | 1. Trigger templated email<br>2. Review personalized fields | Known user/event | Template variables are populated correctly; raw placeholders are not shown | — | Not Run | High | — | Template |
| NOTIF-034 | Push notification while app open | 1. Keep app foregrounded<br>2. Trigger push | Registered device | Foreground notification follows defined app behavior | — | Not Run | Medium | — | Mobile |
| NOTIF-035 | Push notification while app backgrounded | 1. Background app<br>2. Trigger push | Registered device | Push is delivered according to requirements | — | Not Run | High | — | Mobile |
| NOTIF-036 | Push notification after app termination | 1. Close app<br>2. Trigger push | Registered device | Push behavior matches platform/product requirements | — | Not Run | High | — | Mobile |
| NOTIF-037 | Push permission denied | 1. Deny OS notification permission<br>2. Trigger push | Permission denied | App handles denied permission correctly without misleading notification state | — | Not Run | Medium | — | Mobile |
| NOTIF-038 | Push permission later enabled | 1. Initially deny permission<br>2. Enable through supported flow/settings<br>3. Trigger push | Permission enabled | Push delivery resumes after device registration/settings update | — | Not Run | Medium | — | Mobile |
| NOTIF-039 | Notification for deleted/unavailable record | 1. Receive notification<br>2. Remove referenced record according to test setup<br>3. Open notification | Deleted record | Application handles unavailable destination gracefully | — | Not Run | Medium | — | Edge case |
| NOTIF-040 | Notification service failure | 1. Trigger event while notification service failure is simulated | Valid event | Core action remains consistent and notification failure is handled according to requirements | — | Not Run | High | — | Integration |
| NOTIF-041 | Delayed notification delivery | 1. Trigger event<br>2. Observe delayed delivery scenario | Valid event | Delayed notification does not create incorrect duplicates or stale state | — | Not Run | Medium | — | Edge case |
| NOTIF-042 | Notification timezone | 1. Trigger scheduled/time-based notification<br>2. Verify delivery/display time | Configured timezone | Timing follows configured timezone rules | — | Not Run | High | — | Scheduling |
| NOTIF-043 | Scheduled notification | 1. Configure scheduled notification<br>2. Wait until scheduled time | Future schedule | Notification is generated at intended time according to requirements | — | Not Run | High | — | Scheduling |
| NOTIF-044 | User changes email address | 1. Change verified email according to supported flow<br>2. Trigger notification | New email | Future eligible emails use the correct verified address | — | Not Run | High | — | Integration |
| NOTIF-045 | Notification across supported environments | 1. Verify core notification flows across supported web/mobile environments | Valid events | Notification functionality behaves consistently where supported | — | Not Run | Medium | — | Cross-platform |
