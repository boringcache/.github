# BoringCache – Vision

BoringCache exists to reduce wasted work in software builds.

Modern builds repeatedly reinstall dependencies, rebuild binaries, and re-download artifacts across CI runs, machines, and environments—even when nothing meaningful has changed.

The core belief is simple:

> If something was already built, installed, or downloaded, it should be reused.

BoringCache is not a build system.
It is not a workflow engine.
It does not try to be clever.

It provides a universal cache layer that lets developers reuse expensive parts of their build—dependencies, toolchains, and build outputs—across CI, Docker, and local machines.

Speed comes from reuse.
Clarity comes from explicit control.
Trust comes from verification.
