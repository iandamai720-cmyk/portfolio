# A release that passed every automated check but failed on a real phone

[Polski](prewalk-release-acceptance.pl.md) · [Prewalk](../projects/prewalk/README.md)

**Project:** Prewalk website · **Date:** 29 October 2026 · **My role:** release acceptance on a real device

## Situation

A new version of the Prewalk homepage added an animated 3D floor plan at the top of the page. Before release, the build, 35 automated tests and 20 interface checks passed, including first-scroll checks on an emulated phone.

## What I found

On my Pixel 9, in several browsers, the first scroll on the page stuttered. It still happened after I waited 10 seconds for the page to load, so it was not just a slow connection. I did not accept the release.

## What happened next

The AI agent profiled the page and found heavy one-time graphics work that started at the first touch. The emulated tests had not measured it. The agent changed how the 3D scene loads and added regression tests.

I checked the new version on the same phone. The stutter was much better, but the floor plan still jumped for the first 1 to 1.5 seconds. I reported this as well, and a further fix was published the same day.

## Who did what

| Me | AI agent |
|---|---|
| Tested on a physical phone and several browsers | Profiled the page and found the cause |
| Described the symptom and what I had ruled out | Changed the code and added tests |
| Rejected the release and checked each fix | Documented each version |

## What I take from it

Passing tests do not guarantee a good experience on the customer's device. A useful report says which device and browser, when the problem happens, and what has already been ruled out. That is the same information I would give a developer in a support role.
