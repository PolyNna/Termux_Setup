TERMUX — PHONE AS A LAPTOP

A Practical, Step-by-Step Guide to Building a Linux Desktop on Android

By NNANNA POLYCARP
your Android phone into a surprisingly capable Linux desktop environment using Termux, Termux:X11, PRoot-Distro, Debian, Ubuntu, and XFCE.

This project documents the actual process I followed — not just the commands that worked, but also the errors I encountered, what caused them, how I fixed them, and how I verified that everything was working.

---

📖 Read the Guide

"Open TERMUX — PHONE AS A LAPTOP" (./index.html)

The guide is designed to work directly in a web browser and can also be printed or saved as a PDF.

---

🖥️ What This Guide Covers

- Installing Termux correctly
- Setting up Termux:X11
- Preparing Android for long-running Linux sessions
- Installing Debian with PRoot-Distro
- Installing and configuring XFCE
- Connecting XFCE to Termux:X11
- Installing Firefox as the first GUI test
- Understanding and fixing the "Process completed (signal 9)" problem
- Setting up ADB and Android Wireless Debugging
- Configuring PulseAudio for Linux desktop audio
- Installing LibreOffice
- Installing Python 3
- Creating Python virtual environments
- Installing NumPy, pandas and Matplotlib
- Installing and configuring Thonny
- Creating a Linux desktop startup script
- Automating startup with Termux:Widget
- Exploring Ubuntu with PRoot-Distro
- Working with Android shared storage
- Understanding Termux:API and camera access
- Understanding the difference between Android camera access and a Linux webcam
- Working with Bluetooth
- Troubleshooting common X11, DBus, ADB and desktop errors
- Useful commands and recovery procedures

---

🧠 What Makes This Guide Different?

I didn't want to create another tutorial that simply says:

«"Run this command, then run this command."»

Instead, every important stage explains:

Where am I?
What environment or terminal am I currently using?

What am I doing?
What is the purpose of the next step?

What does the command mean?
The important parts of the command are explained in simple language.

What should I see?
Expected output is shown whenever useful.

What if it fails?
The problem is addressed at the stage where it can actually happen.

Where do I go next?
Each major section makes it clear where the process continues.

---

⚠️ Real Problems, Real Solutions

This project includes problems that actually appeared during my setup, including:

Process completed (signal 9)

CANNOT LINK EXECUTABLE "adb":
cannot locate symbol "_ZNSt6__ndk113__hash_memoryEPKvm"

cannot connect to daemon at tcp:5037:
Connection refused

Cannot open display

Failed to get system bus

and other X11, DBus, ADB and Linux desktop issues.

Rather than hiding these problems, I documented where they occurred, what I discovered, how I fixed them, and how I verified the fixes.

---

🏗️ The Basic Architecture

┌─────────────────────────────┐
│          ANDROID            │
│       Your Phone            │
└──────────────┬──────────────┘
               │
               ▼
┌──────────────TERMUX — PHONE AS A LAPTOP

A Practical, Step-by-Step Guide to Building a Linux Desktop on Android

By NNANNA POLYCARP

Turn your Android phone into a surprisingly capable Linux desktop environment using Termux, Termux:X11, PRoot-Distro, Debian, Ubuntu, and XFCE.

This project documents the actual process I followed — not just the commands that worked, but also the errors I encountered, what caused them, how I fixed them, and how I verified that everything was working.

---

📖 Read the Guide

"Open TERMUX — PHONE AS A LAPTOP" (./index.html)

The guide is designed to work directly in a web browser and can also be printed or saved as a PDF.

---

🖥️ What This Guide Covers

- Installing Termux correctly
- Setting up Termux:X11
- Preparing Android for long-running Linux sessions
- Installing Debian with PRoot-Distro
- Installing and configuring XFCE
- Connecting XFCE to Termux:X11
- Installing Firefox as the first GUI test
- Understanding and fixing the "Process completed (signal 9)" problem
- Setting up ADB and Android Wireless Debugging
- Configuring PulseAudio for Linux desktop audio
- Installing LibreOffice
- Installing Python 3
- Creating Python virtual environments
- Installing NumPy, pandas and Matplotlib
- Installing and configuring Thonny
- Creating a Linux desktop startup script
- Automating startup with Termux:Widget
- Exploring Ubuntu with PRoot-Distro
- Working with Android shared storage
- Understanding Termux:API and camera access
- Understanding the difference between Android camera access and a Linux webcam
- Working with Bluetooth
- Troubleshooting common X11, DBus, ADB and desktop errors
- Useful commands and recovery procedures

---

🧠 What Makes This Guide Different?

I didn't want to create another tutorial that simply says:

«"Run this command, then run this command."»

Instead, every important stage explains:

Where am I?
What environment or terminal am I currently using?

What am I doing?
What is the purpose of the next step?

What does the command mean?
The important parts of the command are explained in simple language.

What should I see?
Expected output is shown whenever useful.

What if it fails?
The problem is addressed at the stage where it can actually happen.

Where do I go next?
Each major section makes it clear where the process continues.

---

⚠️ Real Problems, Real Solutions

This project includes problems that actually appeared during my setup, including:

Process completed (signal 9)

CANNOT LINK EXECUTABLE "adb":
cannot locate symbol "_ZNSt6__ndk113__hash_memoryEPKvm"

cannot connect to daemon at tcp:5037:
Connection refused

Cannot open display

Failed to get system bus

and other X11, DBus, ADB and Linux desktop issues.

Rather than hiding these problems, I documented where they occurred, what I discovered, how I fixed them, and how I verified the fixes.

---

🏗️ The Basic Architecture

┌─────────────────────────────┐
│          ANDROID            │
│       Your Phone            │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│           TERMUX            │
│   Linux-like terminal       │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│       PROOT-DISTRO          │
│ Linux distribution manager  │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│           DEBIAN            │
│       Linux userspace       │
└──────────────┬──────────────┘
               │
        ┌──────┴──────┐
        ▼             ▼
   ┌─────────┐   ┌───────────┐
   │  XFCE   │   │ PulseAudio│
   │ Desktop │   │   Audio   │
   └────┬────┘   └───────────┘
        │
        ▼
┌─────────────────────────────┐
│       TERMUX:X11            │
│       Display Server        │
└──────────────┬──────────────┘
               │
               ▼
       ┌───────────────┐
       │ Linux Desktop │
       │ on Android    │
       └───────────────┘

---

🧰 Software Covered

Software| Purpose
Termux| Linux terminal environment on Android
Termux:X11| Graphical display server
PRoot-Distro| Linux distribution management
Debian| Main Linux environment
Ubuntu| Optional additional Linux environment
XFCE| Graphical desktop environment
Firefox ESR| GUI/browser testing
PulseAudio| Desktop audio
LibreOffice| Office productivity
Python| Programming and data work
Thonny| Python development environment
Termux:Widget| Home-screen automation
Termux:API| Android feature access
ADB| Android debugging and configuration

---

📱 My Goal

The goal was simple:

Can I take an Android phone and build something that feels much closer to a Linux laptop?

The answer turned out to be yes — with limitations.

This project is about understanding how far that setup can realistically go, what works well, what requires workarounds, and where Android remains different from a conventional Linux computer.

---

⚠️ Important

This guide is based on a real Android/Termux setup.

Your Android version, device manufacturer, chipset, Termux version, Linux distribution version and available packages may be different.

Commands and package versions can change over time.

Always read the output of your terminal before assuming that your result should look exactly like mine.

---

 Official Resources

- "Termux — F-Droid" (https://f-droid.org/packages/com.termux/)
- "Termux — GitHub" (https://github.com/termux/termux-app)
- "Termux:X11 — GitHub" (https://github.com/termux/termux-x11)
- "Termux:X11 Releases" (https://github.com/termux/termux-x11/releases/tag/nightly)
- "Termux:API — F-Droid" (https://f-droid.org/packages/com.termux.api/)
- "Termux:API — GitHub" (https://github.com/termux/termux-api)
- "Termux:Widget — F-Droid" (https://f-droid.org/packages/com.termux.widget/)
- "PRoot-Distro Documentation" (https://github.com/termux/proot-distro/blob/master/README.md)
- "Android Phantom/Cached/Empty Processes Documentation" (https://github.com/agnostic-apollo/Android-Docs/blob/master/en/docs/apps/processes/phantom-cached-and-empty-processes.md)

---

👤 Author

NNANNA POLYCARP

B.Tech. Industrial Mathematics

This project grew out of my own attempt to get more computing capability from the Android phone I already had instead of immediately buying another computer.

---

 If This Helps You

If you use this guide to build your own Android Linux desktop, consider starring the repository and sharing what worked — especially if your device required a different solution.

Learn → Install → Break → Understand → Fix → Build.￼Enter───────────────┐
│           TERMUX            │
│   Linux-like terminal       │
└──────────────┬──────────────┘
