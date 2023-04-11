# issue3885
### Summary
- User remains in invalid authentication state (zombie state)
### Steps to repro
- Click the `EMAIL/PW` button
- Click the `ANONYMOUSLY` button
### Expected Behavior
- Since the user is already signed in, anonymous sign in should not work.
### Actual Behavior
- The anonymous sign in will sign OVER the current "real" account. The newly created anon account will contain 1 provider: firebase.
### Summary
-  Since the logic checks is: You can only log in / sign in, if FirebaseUser.isAnonymous is TRUE. The user can never sign in again, without logging out the user first.
