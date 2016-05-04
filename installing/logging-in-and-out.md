# Logging in and out

## Creating a user and Logging In

To publish a package, you must have a user on the npm registry. If you don't have one,
you can create it 2 ways:
  - On the npm website
  - Using `npm adduser`

Note: If you created one on the site, use `npm login` to store the credentials on the client.

Once you have created a user and logged in, you can use `npm config ls` to ensure that the
credentials are stored on your client. You can also check that your user has been added to
the registry by going to [https://npmjs.com/~](https://npmjs.com/~)username.

### npm whoami

To see what username you are logged in as, you can enter:

    npm whoami [--registry <registry>]

## Logging Out

To log out, use the `npm logout` command:

    npm logout [--registry=<url>] [--scope=<@scope>]

When logged into a registry that supports token-based authentication, this
command will tell the server to end this token's session. This will invalidate
the token everywhere you're using it, not just for the current environment.

When logged into a legacy registry that uses username and password authentication,
this will clear the credentials in your user configuration. In this case, it will
 _only_ affect the current environment.

If `--scope` is provided, this will find the credentials for the registry
connected to that scope, if set.

### Configuration

You can configure the `logout` command 2 ways:

|             | Description                                                                                   | Default                         |
|------------ |---------------------------------------------------------------------------------------------  |-------------------------------  |
| `registry`  | The base URL of the npm package registry. If `scope` is also specified,it takes precedence.   | `https://registry.npmjs.org/`   |
| `scope`     | If specified, you will be logged out of the specified scope.                                  | none                            |
