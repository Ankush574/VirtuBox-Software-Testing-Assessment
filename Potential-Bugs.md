# Potential Bugs / Risk Areas

The following are potential bugs or risk areas identified without executing the application. They are based on expected production behaviour and are not confirmed defects.

## 1. Unauthorized access to another user's tasks
**Severity:** Critical

A user may potentially access another user's task by changing an ID or request parameter.

**Impact:** Private task data could be exposed. This is a serious authorization issue.

## 2. Unauthorized editing or deletion of another user's task
**Severity:** Critical

A user may potentially edit or delete a task that belongs to another account.

**Impact:** This could cause unauthorized modification or permanent data loss.

## 3. Duplicate task creation
**Severity:** Major

Clicking Save multiple times quickly may create duplicate task records.

**Impact:** Users may get duplicate tasks and the database may contain unnecessary data.

## 4. Deleted task returns after refresh
**Severity:** Major

A task may disappear from the screen but come back after the page is refreshed.

**Impact:** This can indicate that the UI changed but the database deletion failed.

## 5. UI shows a change as saved when the database update failed
**Severity:** Major

The application may update the screen before the backend operation has actually succeeded.

**Impact:** Users may believe their work is saved when it is not.

## 6. Extremely long input causes application failure
**Severity:** Major

Very large input may not be handled correctly.

**Impact:** This can produce errors, poor performance or instability.

## 7. Same email can be registered more than once
**Severity:** Major

The application may fail to enforce email uniqueness during registration.

**Impact:** This could create account conflicts and login problems.

## 8. Session remains active after logout
**Severity:** Major

Protected pages may still be accessible after the user logs out.

**Impact:** Someone using the same device could access private tasks.

## 9. Unclear error messages
**Severity:** Minor

Server, database or validation errors may be presented using unclear technical messages.

**Impact:** Users may not understand the problem or what action they should take.

## 10. Leading/trailing spaces are handled incorrectly
**Severity:** Minor

Spaces may not be trimmed correctly in fields such as email or task names.

**Impact:** This can cause confusing validation or login behaviour.
