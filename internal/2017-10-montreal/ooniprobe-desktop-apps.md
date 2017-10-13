# OONI Probe desktop

Goal: Having simple wins for continuing to support Linux without much overhead.

Keep ooniprobe tests in command line interface (CLI). 

Build OONI Probe desktop app that communicates with the CLI --- > It will spawn a process for (a) running tests, (b) uploading measurements, etc.

There is an IPC layer that abstracts this cross-plaform and it is a parameter passed to the CLI. The IPC is the same used by Electron.

Using node for both desktop apps and CLI.

CLI is a fairly light wrapper around Measurement-Kit.

The core engine will be measurement-kit, where all the tests are implemented.

This architecture is inspired by exising projects (such as the project "Now").

If you're a CLI user, we want to ensure that the desktop doesn't use a different verson of CLI. The desktop and CLI components need to be separate, but know how to speak to each other. The desktop updates the CLI in a place that allows the user to also run it from the command line. This can help solve the problem of people having a different version of software installed on their laptops in comparison to what would be tested via the connection of CLI and the desktop apps.

We're building the apps primarily for Windows users, so design decisions should be Windows first.

Can we have OONI CLI, OONI daemon, etc all in one package? Potentially...

However, you could have the situation where the ooniprobe version installed is different to that in the desktop app... But perhaps these power users can figure it out for themselves and we can just have something in one package.

