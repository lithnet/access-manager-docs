# Setting up just-in-time access

Lithnet Access Manager supports granting access to computers and groups using a simple, just-in-time (JIT) access model.

Rather than administrators having permanent access to computers or groups, they can use Access Manager to grant themselves access on a temporary as-needed basis.

By reducing permanent administrators, you can rapidly increase the difficulty of a successful lateral-movement based attack in your environment.

Access Manager supports two forms of JIT:

* [JIT for Computers](jit/setting-up-jit-for-computers.md) allows you to configure administrators to request just-in-time access to specific machines.
* [JIT for Roles](jit/setting-up-jit-for-roles.md) allows you to define a role, based on an Active Directory group, that users are allowed to request access to on a temporary basis.