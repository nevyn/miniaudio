# NaN kills all audio on Big Sur until process quits

A single NaN in an audio buffer sent to coreaudio mutes all audio
in all programs running on the computer until the process quits.

Repro'd with a MacBook Air running Big Sur and a pair of AirPods Pro.
Doesn't happen with internal speakers, only with bluetooth audio.

## Build

```
    cd examples/build
    mkdir -p bin
    gcc ../nan_repro.c -o bin/nan -ldl -lm -lpthread; and ./bin/nan
```