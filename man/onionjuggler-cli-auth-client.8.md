% ONIONJUGGLER-CLI-AUTH-CLIENT(8) Manage onion service client side authorization
% Written by nyxnor (nyxnor@protonmail.com)
% default_date

# NAME

onionjuggler-cli-auth-client - Manage onion service client side authorization


# SYNOPSIS

**onionjuggler-cli-auth-client** [**--option**<=*ARGUMENT*>]\
**onionjuggler-cli-auth-client [--getconf]**\
**onionjuggler-cli-auth-client [--getopt]** [**--service** <*SERVICE*>]\
**onionjuggler-cli-auth-client** [**--on**] [**--client-priv-file** <*CLIENT_PRIV_FILE*>] [**--replace-file**]\
**onionjuggler-cli-auth-client** [**--on**] [**--client** <*CLIENT*>] [**--client-priv-config** <*CLIENT_PRIV_CONFIG*>] [**--replace-file**]\
**onionjuggler-cli-auth-client** [**--on**] [**--client** <*CLIENT*>] [**--client-priv-key** <*CLIENT_PRIV_KEY*>] [**--onion** <*ONION*>] [**--replace-file**]\
**onionjuggler-cli-auth-client** [**--off**] [**--client** <*CLIENT*>]\
**onionjuggler-cli-auth-client** [**--list**]\
**onionjuggler-cli-auth-client** [**-V**|**--version**]
**onionjuggler-cli-auth-client** [**-h**|**--help**]


# DESCRIPTION

**onionjuggler-cli-atuh-client** helps manage client side onion authorizations.


# OPTIONS

**--on** **--client-priv-file** <*CLIENT_PRIV_FILE*> **--replace-file**\
**--on** **--client** <*CLIENT*> **--client-priv-config** <*CLIENT_PRIV_CONFIG*> **--replace-file**\

**--on** **--client** <*CLIENT*> **--onion** <*ONION*> **--client-priv-key** <*CLIENT_PRIV_KEY*> **--replace-file**

: Authenticate as a client to an onion serivce. If the client private keys is not provided, a new key pair of public and private keys will be generated, keys are sent to stdout and you should send to the onion service operator. Add a $ONION.auth_private to ClientOnionAuthDir. File(s) modified: ClientOnionAuthDir.
```
onionjuggler-cli-auth-client --on --client-priv-file /home/user/alice.auth_private
onionjuggler-cli-auth-client --on --client alice --client-priv-config fe4avn4qtxht5wighyii62n2nw72spfabzv6dyqilokzltet4b2r4wqd:descriptor:x25519:UBVCL52FL6IRYIOLEAYUVTZY3AIOM
onionjuggler-cli-auth-client --on --client alice --onion fe4avn4qtxht5wighyii62n2nw72spfabzv6dyqilokzltet4b2r4wqd.onion --client-priv-key UBVCL52FL6IRYIOLEAYUVTZY3AIOMDI3AIFBAALZ7HJOHIJFVBIQ
onionjuggler-cli-auth-client --on --client alice --onion fe4avn4qtxht5wighyii62n2nw72spfabzv6dyqilokzltet4b2r4wqd.onion
```

**--off** **--client** <*CLIENT1,CLIENT2,...*>

: Deauthenticate from a remote onion serivce. Remove the $ONION.auth_private file from ClientOnionAuthDir. File(s) modified: ClientOnionAuthDir/.
```
onionjuggler-cli-auth-client --off --onion fe4avn4qtxht5wighyii62n2nw72spfabzv6dyqilokzltet4b2r4wqd.onion
onionjuggler-cli-auth-client --off --onion fe4avn4qtxht5wighyii62n2nw72spfabzv6dyqilokzltet4b2r4wqd.onion,yyyzxhjk6psc6ul5jnfwloamhtyh7si74b47a3k2q3pskwwxrzhsxmad.onion
```

**--list**

: List authentication files and the respective private keys from ClientOnionAuthDir.Useful when removing files and you want to see which onions you are already authenticated with.  File(s) modified: none.
```
onionjuggler-cli-auth-client --list
```

**-V**, **--version**

: Print version information.

**--getconf**

: Print configuration in the format **key**="*val*".

**--getopt**

: Print option parsing results.

**-h**, **--help**
: Display the script help message. Abscense of any parameter will also have the same effect.
```
onionjuggler-cli-auth-client -h
onionjuggler-cli-auth-client --help
```

**-R**, **--restart**, **-r**, **--reload**
: Signal tor daemon to restart or reload after the CLI edits tor's configuration files. (Default: reload)


# FILES

**/usr/share/onionjuggler/defaults.sh**

: Default library

**/etc/onionjuggler/onionjuggler.conf**

: Default system configuration file.

**/etc/onionjuggler/conf.d/\*.conf**

: Local configuration files that overrrite the default one.


# EXIT VALUE

**0**
: Success

**>0**
: Fail


# BUGS

Bugs you may find. First search for related issues on https://github.com/nyxnor/onionjuggler/issues, if not solved, open a new one.


# SEE ALSO

onionjuggler-tui(8), onionjuggler.conf(5), vitor(8), tor(1), sh(1), regex(7), sed(1), grep(1), shellcheck(1)


# COPYRIGHT

Copyright  ©  2021  OnionJuggler developers (MIT)
This is free software: you are free to change and redistribute it.  There is NO WARRANTY, to the extent permitted by law.