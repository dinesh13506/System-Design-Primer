# Online offline indicator

## System Requirements

1. User should be able to see if other users are online or offline.
2. System should be scalable, Daily Active users is 1M.
3. A user is said to be online if his/her latest online time is in range of X seconds (configrable) with current time. If difference between current time and his/her latest online time is more than X seconds (configrable) then user is considered to be offline.
4. System should support bulk api to fetch user's status.

