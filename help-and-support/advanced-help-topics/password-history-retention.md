# Password history and retention

Access Manager allows you to store a history of previously used local admin passwords, so that if you recover a device from a backup, you can go back in time and get the local admin password that was active at the time the backup was taken.

AMS policies allow you to define both a minimum number of passwords to keep, as well as the minimum number of days a password should be retained for.

If both the `Number of previous passwords to keep` and `Number of days to keep previous passwords` setting is in use, then old passwords will not be removed until both thresholds have passed. For example, if you had a policy to generate a new password every day, to keep a minimum of 5 passwords, and to keep passwords for 365 days, you would have 365 passwords in your history. More examples are in the table provided below.

|Maximum age|Passwords to keep|Days to keep|Effective number of passwords|
|---|---|---|---|
|1|50|0|50|
|1|0|50|50|
|1|5|365|365|
|1|7|1|7|
|1|7|7|7|
