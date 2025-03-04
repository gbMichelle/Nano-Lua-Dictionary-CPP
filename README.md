## Nano Lua Dictionary

Nano Lua Dictionary (or nano_luadict) is a simple C snippet that facilitates (with some compromises) the creation of Lua tables composed of K/V's (or dictionaries) as specified [here](http://lua-users.org/wiki/TablesTutorial). I made this nano-project to to aid in the creation of an event system for a rather simple Game Engine, and because integrating a huge Lua binding framework such as Luabind just to fulfill this propose seemed to be too much overhead for my personal needs.

### C++ version

This is a fork of [this](https://github.com/Goles/Nano-Lua-Dictionary) library that is meant for C++. If you want a C version, go [here](https://github.com/Goles/Nano-Lua-Dictionary).

### Usage example

The project itself is self-explanatory, feel free to modify it to your needs, if you feel that a lot could be improved while maintaining simplicity and speed, just send a pull request :).

    #include "nanoluadict.h"

    luaDict(L                                           /* L is Lua State */
            , "sample_dictionary"                       /* Table name in global space */
            , 8                                         /* Number of kvs that we are including in our dictionary */
            , kvPairWithNumber("key1", 1)               /* Keys are always strings, this is a numeric value */
            , kvPairWithNumber("key2", 2)
            , kvPairWithString("key3", "string 3")      /* This is a string value */
            , kvPairWithNumber("key4", 4)
            , kvPairWithNumber("key5", 5)
            , kvPairWithNumber("key6", 6)
            , kvPairWithNumber("key7", 7)
            , kvPairWithCFunction("callback", c_function)); /* This is for a function callback */
