# Education / Learning Management System (LMS) Test Cases

## Scope
Domain-specific student enrollment, courses, lessons, assignments, quizzes, grading, progress tracking, certificates, instructor permissions, deadlines, learning content, and education workflow testing.

| ID | Scenario | Test Steps | Test Data | Expected Result | Actual Result | Status | Priority | Evidence | Notes |
|---|---|---|---|---|---|---|---|---|---|
| LMS-001 | Student enrolls in available course | 1. Login as student<br>2. Open available course<br>3. Click Enroll | Available course | Student is successfully enrolled | — | Not Run | High | — | Enrollment |
| LMS-002 | Enrolled course appears on dashboard | 1. Enroll in course<br>2. Open student dashboard | Enrolled course | Course appears in student's enrolled courses | — | Not Run | High | — | Integration |
| LMS-003 | Duplicate course enrollment | 1. Enroll in course<br>2. Attempt to enroll again | Same course | Duplicate enrollment is prevented | — | Not Run | High | — | Data integrity |
| LMS-004 | Enrollment in unavailable course | 1. Open unavailable/closed course<br>2. Attempt enrollment | Closed course | Enrollment is prevented according to course rules | — | Not Run | High | — | Negative |
| LMS-005 | Enrollment capacity limit | 1. Fill course to configured capacity<br>2. Attempt another enrollment | Full course | Capacity/waitlist rules are correctly enforced | — | Not Run | High | — | Boundary |
| LMS-006 | Student withdraws from course | 1. Open enrolled course<br>2. Select Withdraw<br>3. Confirm | Enrolled course | Enrollment status changes according to withdrawal rules | — | Not Run | High | — | Enrollment |
| LMS-007 | Student accesses enrolled course | 1. Login as enrolled student<br>2. Open course | Enrolled student | Course content permitted to student is accessible | — | Not Run | High | — | Authorization |
| LMS-008 | Non-enrolled student accesses restricted course | 1. Login as non-enrolled student<br>2. Attempt direct course access | Restricted course | Restricted content is not exposed | — | Not Run | High | — | Authorization |
| LMS-009 | Student cannot access instructor controls | 1. Login as student<br>2. Attempt instructor/admin page access | Student account | Instructor controls remain inaccessible | — | Not Run | High | — | RBAC |
| LMS-010 | Instructor accesses assigned course | 1. Login as instructor<br>2. Open assigned course | Assigned course | Instructor can access permitted management features | — | Not Run | High | — | RBAC |
| LMS-011 | Instructor cannot manage unrelated course | 1. Login as Instructor A<br>2. Attempt to manage Instructor B course | Unassigned course | Unauthorized course management is denied | — | Not Run | High | — | Authorization |
| LMS-012 | Course details display correctly | 1. Open course | Known course | Title, description, instructor and other configured details are correct | — | Not Run | Medium | — | Data accuracy |
| LMS-013 | Lesson opens successfully | 1. Open enrolled course<br>2. Select available lesson | Published lesson | Correct lesson content opens | — | Not Run | High | — | Learning content |
| LMS-014 | Locked lesson access | 1. Attempt to open lesson before prerequisite/unlock condition | Locked lesson | Access follows configured lesson-lock rules | — | Not Run | High | — | Business rules |
| LMS-015 | Complete lesson | 1. Open lesson<br>2. Complete required activity<br>3. Mark/finish lesson | Available lesson | Lesson is recorded as completed | — | Not Run | High | — | Progress |
| LMS-016 | Course progress calculation | 1. Complete known number of lessons<br>2. Review progress | Known completion data | Progress percentage/count is calculated correctly | — | Not Run | High | — | Data accuracy |
| LMS-017 | Progress persists after re-login | 1. Complete lesson<br>2. Logout<br>3. Login again | Student account | Saved progress remains correct | — | Not Run | High | — | Persistence |
| LMS-018 | Video lesson playback | 1. Open video lesson<br>2. Play/pause/seek where supported | Test video | Video controls and playback function according to requirements | — | Not Run | Medium | — | Media |
| LMS-019 | Resume video lesson | 1. Watch part of video<br>2. Leave lesson<br>3. Reopen | Partially watched video | Playback position follows configured resume behavior | — | Not Run | Medium | — | Persistence |
| LMS-020 | Download permitted learning material | 1. Open lesson resources<br>2. Download allowed file | Test PDF | Correct file downloads successfully | — | Not Run | Medium | — | Documents |
| LMS-021 | Restricted material access | 1. Obtain/open protected material link as unauthorized user | Restricted resource | Unauthorized access is denied | — | Not Run | High | — | Security-focused |
| LMS-022 | Submit assignment | 1. Open assignment<br>2. Upload/enter valid submission<br>3. Submit | Test assignment | Submission is saved for correct student and assignment | — | Not Run | High | — | Assignment |
| LMS-023 | Assignment required file missing | 1. Open file-required assignment<br>2. Submit without file | No file | Submission is prevented with appropriate validation | — | Not Run | High | — | Validation |
| LMS-024 | Unsupported assignment file type | 1. Upload unsupported file<br>2. Submit | Unsupported file | File is rejected according to assignment rules | — | Not Run | Medium | — | Validation |
| LMS-025 | Oversized assignment file | 1. Upload file exceeding configured limit | Oversized test file | File is rejected with appropriate feedback | — | Not Run | Medium | — | Boundary |
| LMS-026 | Assignment submitted before deadline | 1. Submit valid assignment before deadline | Valid submission | Submission is accepted and correct timestamp/status is recorded | — | Not Run | High | — | Deadline |
| LMS-027 | Assignment submitted after deadline | 1. Attempt submission after deadline | Late submission | Late submission follows configured acceptance/penalty rules | — | Not Run | High | — | Deadline |
| LMS-028 | Replace assignment before deadline | 1. Submit assignment<br>2. Replace/resubmit before deadline | Updated file | Latest submission/version follows configured resubmission rules | — | Not Run | High | — | Assignment |
| LMS-029 | Student views own assignment only | 1. Login as Student A<br>2. Attempt to access Student B submission | Student B submission | Access is denied | — | Not Run | High | — | Privacy |
| LMS-030 | Instructor grades assignment | 1. Login as instructor<br>2. Open submission<br>3. Enter grade<br>4. Save | Valid grade | Grade is saved for correct student/assignment | — | Not Run | High | — | Grading |
| LMS-031 | Grade outside allowed range | 1. Enter grade above/below configured range<br>2. Save | Invalid grade | Invalid grade is rejected | — | Not Run | High | — | Boundary |
| LMS-032 | Student views released grade | 1. Instructor releases grade<br>2. Login as student<br>3. Open assignment | Released grade | Correct grade and permitted feedback are visible | — | Not Run | High | — | Grading |
| LMS-033 | Unreleased grade visibility | 1. Save grade without releasing it<br>2. Login as student | Unreleased grade | Grade visibility follows configured release rules | — | Not Run | High | — | Authorization |
| LMS-034 | Instructor feedback | 1. Grade assignment<br>2. Add feedback<br>3. Release<br>4. View as student | Test feedback | Correct feedback appears to intended student | — | Not Run | High | — | Grading |
| LMS-035 | Start quiz | 1. Open available quiz<br>2. Click Start | Published quiz | Quiz attempt starts correctly | — | Not Run | High | — | Quiz |
| LMS-036 | Quiz question display | 1. Start quiz<br>2. Navigate questions | Test quiz | Correct questions and supported answer controls are displayed | — | Not Run | High | — | Quiz |
| LMS-037 | Submit quiz | 1. Answer questions<br>2. Submit quiz<br>3. Confirm | Completed attempt | Quiz is submitted once and attempt status updates | — | Not Run | High | — | Quiz |
| LMS-038 | Quiz score calculation | 1. Submit known answers<br>2. Review score | Known correct/incorrect answers | Score is calculated according to configured grading rules | — | Not Run | High | — | Data accuracy |
| LMS-039 | Unanswered required quiz question | 1. Leave required question unanswered<br>2. Submit | Incomplete attempt | Application follows configured validation/submission rules | — | Not Run | Medium | — | Validation |
| LMS-040 | Timed quiz expiration | 1. Start timed quiz<br>2. Reach configured time limit | Timed quiz | Attempt follows configured auto-submit/expiration behavior | — | Not Run | High | — | Timer |
| LMS-041 | Quiz timer after refresh | 1. Start timed quiz<br>2. Refresh/reopen | Active attempt | Timer remains accurate and cannot be unintentionally reset | — | Not Run | High | — | Edge case |
| LMS-042 | Quiz attempt limit | 1. Use configured number of attempts<br>2. Attempt another | Attempt limit reached | Additional attempt is prevented according to rules | — | Not Run | High | — | Business rules |
| LMS-043 | Network failure during quiz | 1. Start quiz<br>2. Enter answers<br>3. Lose network during supported save/submit action | Active attempt | App handles failure according to requirements without falsely reporting submission | — | Not Run | High | — | Error handling |
| LMS-044 | Duplicate quiz submission | 1. Submit quiz<br>2. Rapidly click Submit repeatedly | Completed quiz | Duplicate attempts/submissions are prevented | — | Not Run | High | — | Duplicate prevention |
| LMS-045 | Overall course grade calculation | 1. Create known assignment/quiz grades<br>2. Review total grade | Known grade values | Overall grade follows configured weighting/calculation rules | — | Not Run | High | — | Calculation |
| LMS-046 | Course completion | 1. Complete all required course activities<br>2. Review status | Completed requirements | Course is marked complete according to completion rules | — | Not Run | High | — | Completion |
| LMS-047 | Certificate generation | 1. Complete certificate-eligible course<br>2. Open certificate | Eligible student | Certificate is generated with correct student/course information | — | Not Run | Medium | — | Certificate |
| LMS-048 | Certificate before course completion | 1. Attempt certificate access before requirements are met | Incomplete course | Certificate is unavailable according to eligibility rules | — | Not Run | Medium | — | Authorization |
| LMS-049 | Course announcement | 1. Instructor publishes announcement<br>2. Login as enrolled student | Test announcement | Announcement reaches/displays to intended course audience | — | Not Run | Medium | — | Communication |
| LMS-050 | Course notification recipient isolation | 1. Trigger course-specific notification<br>2. Check enrolled and unrelated users | Two student groups | Notification reaches only intended eligible recipients | — | Not Run | High | — | Data isolation |
| LMS-051 | Discussion post creation | 1. Open course discussion<br>2. Create valid post | Test content | Post is created under correct student/course | — | Not Run | Medium | — | Discussion |
| LMS-052 | Delete own discussion post | 1. Create post<br>2. Delete using supported flow | Own post | Post is deleted according to requirements | — | Not Run | Medium | — | Discussion |
| LMS-053 | Student edits another student's post | 1. Login as Student B<br>2. Attempt to edit Student A post | Another user's post | Unauthorized modification is denied | — | Not Run | High | — | Authorization |
| LMS-054 | Instructor publishes course content | 1. Login as instructor<br>2. Create content<br>3. Publish | Test lesson | Published content becomes available to eligible students | — | Not Run | High | — | Instructor |
| LMS-055 | Draft course content visibility | 1. Create draft lesson<br>2. Login as student | Draft lesson | Draft content is hidden according to publishing rules | — | Not Run | High | — | Authorization |
| LMS-056 | Course schedule timezone | 1. Configure dated activity<br>2. View schedule in supported timezone context | Known date/time | Dates and deadlines follow configured timezone rules | — | Not Run | High | — | Scheduling |
| LMS-057 | Concurrent assignment grading | 1. Open same submission in two authorized instructor sessions<br>2. Save conflicting grades | Same submission | Conflict follows defined rules without silent data corruption | — | Not Run | High | — | Concurrency |
| LMS-058 | Failed grade save | 1. Enter grade<br>2. Cause request failure<br>3. Save | Valid grade | False success is not shown and stored grade remains consistent | — | Not Run | High | — | Error handling |
| LMS-059 | Student data isolation | 1. Login as Student A<br>2. Attempt direct access to Student B private academic data | Student B data | Private academic information is not exposed | — | Not Run | High | — | Privacy |
| LMS-060 | LMS across supported environments | 1. Test core student/instructor flows across supported browsers/devices | Test accounts | Core LMS functionality behaves consistently | — | Not Run | Medium | — | Cross-platform |
