# msoak

Subscribe to different MQTT brokers and topics simultaneously, and soak up what they have to offer.

## startup

Launch _msoak_ with the example configuration file:

```console
$ msoak example.config
```

Then publish a message:

```bash
mosquitto_pub -t tests/sponge/1 -m "$(jo name=Jane number=42)"
```

you should see the payload as formatted by Lua. The word `loc` at start of output is the _id_ of the connection as specified in `example.config`.

```
loc tests/sponge/1 Hello Jane -> now=18:12:50Z
```

## requirements

You will require:

* [libmosquitto](http://mosquitto.org)
* [libconfig](http://www.hyperrealm.com/libconfig/)
* [Lua](http://www.lua.org)

#### macos

```console
$ brew install lua libconfig
$ make
```

#### freebsd

```console
# pkg install lua53 libconfig mosquitto
$ make
```

#### openbsd

```console
# pkg_add libconfig lua-5.3.5
$ make
```

#### debian

```console
# apt-get install libconfig-dev liblua5.3-dev libmosquitto-dev libbsd-dev
$ make
```

## see also

* [mqttwarn](https://github.com/jpmens/mqttwarn)
