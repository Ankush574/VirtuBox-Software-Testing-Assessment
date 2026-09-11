# Test Cases - Task Management Application

## 1. Registration

| TC ID | Test Scenario | Test Steps / Test Data | Expected Result | Type |
|---|---|---|---|---|
| REG-01 | Register with valid details | Enter valid name, email and password and click Register | Account should be created successfully | Positive |
| REG-02 | Register with all fields empty | Click Register without entering data | Required field validation should be displayed | Negative |
| REG-03 | Register with invalid email | Enter `ankush@` or `ankush.com` | Invalid email message should be displayed | Negative |
| REG-04 | Register with already registered email | Use an email that already exists | Registration should be rejected with a clear message | Negative |
| REG-05 | Password below minimum length | Enter a password shorter than the allowed minimum | Password validation should be displayed | Negative |
| REG-06 | Password at minimum length | Enter a password exactly at the minimum limit | Registration should be allowed if other details are valid | Edge |
| REG-07 | Very long input | Enter values near and beyond the maximum field length | Application should validate the limit without breaking | Edge |
| REG-08 | Password confirmation mismatch | Enter different values in password and confirmation | User should be told that passwords do not match | Negative |
| REG-09 | Leading/trailing spaces | Enter spaces before/after name or email | Unnecessary spaces should be handled correctly | Edge |
| REG-10 | Valid name with normal spacing | Enter a normal name such as `Ankush Kumar` | Name should be accepted | Positive |

## 2. Login

| TC ID | Test Scenario | Test Steps / Test Data | Expected Result | Type |
|---|---|---|---|---|
| LOG-01 | Login with valid credentials | Enter registered email and correct password | User should be logged in successfully | Positive |
| LOG-02 | Wrong password | Enter correct email and incorrect password | Login should fail with an appropriate error | Negative |
| LOG-03 | Unregistered email | Enter an email that is not registered | Login should not be allowed | Negative |
| LOG-04 | Both fields empty | Click Login without entering credentials | Required field validation should appear | Negative |
| LOG-05 | Email empty | Enter password only | Email validation should be displayed | Negative |
| LOG-06 | Password empty | Enter email only | Password validation should be displayed | Negative |
| LOG-07 | Invalid email format | Enter an invalid email such as `abc@` | Application should reject the format | Negative |
| LOG-08 | Password case sensitivity | Enter the correct password with different capitalization | Login should fail if passwords are case-sensitive | Edge |
| LOG-09 | Repeated failed attempts | Enter an incorrect password several times | Application should handle repeated failures safely | Edge |
| LOG-10 | Refresh after login | Login successfully and refresh | Session should remain active when persistent sessions are expected | Edge |

## 3. Create Task

| TC ID | Test Scenario | Test Steps / Test Data | Expected Result | Type |
|---|---|---|---|---|
| TASK-C01 | Create task with valid data | Enter a valid task title/details and save | Task should be created and appear in the list | Positive |
| TASK-C02 | Create task with empty title | Leave title empty and save | Task should not be created and validation should appear | Negative |
| TASK-C03 | Minimum valid title | Enter the smallest allowed valid title | Task should be created successfully | Edge |
| TASK-C04 | Very long title | Enter a title beyond the allowed limit | Application should validate the limit safely | Edge |
| TASK-C05 | Create multiple tasks | Create several valid tasks | All tasks should appear correctly | Positive |
| TASK-C06 | Special characters | Enter `Fix login #1 & test` | Task should be stored and displayed correctly | Edge |

## 4. View Task List

| TC ID | Test Scenario | Test Steps / Test Data | Expected Result | Type |
|---|---|---|---|---|
| TASK-V01 | View existing tasks | Login and open task list | User's saved tasks should be displayed | Positive |
| TASK-V02 | User with no tasks | Login with a new account | A useful empty-state message should be displayed | Edge |
| TASK-V03 | Many tasks | Create many tasks and open the list | No missing or duplicate records should appear | Positive |
| TASK-V04 | Refresh task list | Create a task and refresh the page | Saved task should still be present | Positive |
| TASK-V05 | Different user | Login as another user | User should only see their own tasks | Negative/Security |

## 5. Edit Task

| TC ID | Test Scenario | Test Steps / Test Data | Expected Result | Type |
|---|---|---|---|---|
| TASK-E01 | Edit successfully | Open an existing task, change data and save | Updated information should be displayed | Positive |
| TASK-E02 | Edit with empty title | Remove the title and save | Application should prevent saving and show validation | Negative |
| TASK-E03 | Maximum allowed input | Enter data at the maximum supported length | Changes should save successfully | Edge |
| TASK-E04 | Cancel editing | Change a task and cancel | Original task data should remain unchanged | Positive |
| TASK-E05 | Refresh after editing | Edit and save, then refresh | Updated information should remain saved | Positive |

## 6. Delete Task

| TC ID | Test Scenario | Test Steps / Test Data | Expected Result | Type |
|---|---|---|---|---|
| TASK-D01 | Delete existing task | Click Delete on a task | Selected task should be removed | Positive |
| TASK-D02 | Cancel deletion | Choose Delete and then Cancel | Task should remain unchanged | Positive |
| TASK-D03 | Delete one task from many | Delete one task while several exist | Only the selected task should be removed | Positive |
| TASK-D04 | Verify after refresh | Delete a task and refresh | Deleted task should not return | Positive |
| TASK-D05 | Unauthorized deletion | Attempt to delete another user's task | Application should prevent the operation | Negative/Security |

## 7. Input Validation and Error Handling

| TC ID | Test Scenario | Expected Result | Type |
|---|---|---|---|
| VAL-01 | Submit required form fields empty | Clear required-field validation should appear | Negative |
| VAL-02 | Enter only spaces | Application should not accept spaces as meaningful input where inappropriate | Negative |
| VAL-03 | Extremely large input | Input should be rejected or safely handled | Edge |
| VAL-04 | Special characters | Valid characters should work and unsafe input should be handled safely | Edge |
| VAL-05 | Server/database unavailable | User should see a meaningful error instead of a stack trace | Negative |
| VAL-06 | Double-click Submit/Save | Duplicate accounts or tasks should not be created accidentally | Edge |
| VAL-07 | Network interruption during save | User should be informed that the save failed; data should not be falsely shown as saved | Negative |
| VAL-08 | Invalid API response | Application should handle the response without crashing | Negative |
| VAL-09 | Session expiry | User should be redirected to login or asked to authenticate again | Edge |
| VAL-10 | Refresh after an operation | UI and database state should remain consistent | Positive |
