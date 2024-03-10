# celeste_on_arm64

## Celeste rebuilt for arm64

FMOD doesn't support arm64 until version 2.02, and Celeste is on 1.10.x

This patch adds FMOD 2.02 bindings, use bsdiff to apply the appropriate patch to the appropriate binary (one for win32 for local testing, one for the linux binary)

NOTE there is a bug with music for bside levels, when you quit the music will carry on until it ends. I've tried a bunch of things to fix it, but I suspect it was something that magically didn't happen under FMOD 1.x because EventInstances were classes (passed by reference and GCed) but are structs from 2.0 onward.
