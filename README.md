# Svelte + Vite

```
<application
  android:label="@string/app_name"
  ...
  android:usesCleartextTraffic="true">
```

```
php -S 127.0.0.1:8000
```

The following isn't really necessary:

Default port for emulator is 5554

telnet into emulator:

```
telnet localhost 5554

```

Above statement will generate .emulator_console_aut_token. Get the value then type:

```
auth emulator_console_aut_token
```

Then forward port:

```
redir add tcp:8000:8000
```
