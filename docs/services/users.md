# Users

**Services**  
Users

![Users](assets/images/services/users.png)

*Image: User management (placeholder).*

The **Users** service manages local user accounts: list users, create, delete, reset password. It dispatches actions that the system manager fulfills (e.g. accountsservice or useradd/passwd).

## What you see

- **State** (`UsersState`) — List of users (`UserState`: username, etc.).
- **Actions** — `UsersSetUsersAction`, `UsersCreateUserAction`, `UsersDeleteUserAction`, `UsersResetPasswordAction`.
- **Events** — May emit when user list or state changes.
- **Implementation** — `ubo_app/services/050-users/`: reducer, setup, ubo_handle; system manager handles privileged operations.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → Users](../home/settings/users.md)
- [Architecture → System](../architecture/system.md)
