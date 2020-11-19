---
title: Auth service
sidebar: Docs
showTitle: true
---
## Introduction

The auth service provides a form for keep the different users of ecosystem,
the general idea is **share users through of all apps**.

### Requirements:

1. We need to add a **Initial client** with a command like (Infrastructure Task):

Maybe is required for Auth admin Web/App

```sh
aqueduct auth add-client --id com.local.test \
    --secret mysecret \
    --connect postgres://postgres:postgres@localhost:5432/on_watch_auth
```

### Hierarchy

1. **Initial client** for Register new Clients
2. **New Users**:
    - **General users**: Ex: Agents, Dispatchers, etc
    - **Users representing external applications**: A user who creates apis
3. **Roles**: Roles created for manage information
3. **APIs:**: Each application that can authenticate
4. **Permissions for api**: A list of permissions for an specific API
5. **Role with permission**: Association between Roles and API Permissions

### Flow

1. Create and API
2. Add Roles
3. Add a Client for the API (credentials used on external APP): Getting a `client ID` and `secret`
4. Add Permission for API
5. Add Permission/API to Role
6. Add Roles to Users

### Flow users

1. Register a user using Basic authentication credentials (Flow step 3) `POST /v1/register`
   and getting a new User.
2. Login with your new credentials `POST /v1/login` and getting a Bearer token. In the process of login, the system detects your user, the basic credentials of your client/app (secret values), and show your roles bases on this params.

```json
 {
    "id": 1,
    "company": null,
    "username": "pepito@company.com",
    "authorization": {
    "access_token": "asdsdasds",
    "token_type": "bearer",
    "expires_in": 89999,
    "refresh_token": "sdasdasdasd"
    },
    "roles": [
        {
            "role": {"id": 1, "name": "Admin sales"},
            "api": {"id": 2, "name": "Marketing module"}
        }
    ]
 }
```







