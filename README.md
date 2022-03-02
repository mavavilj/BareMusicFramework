# BareMusicFramework

This is a repository created for fueling discussion and development around a public domain "barebones DAW framework". The background for this comes from a set of personally recognized issues with conventional DAWs and development APIs.

# Background:

## Finished DAWs:

* Are closed source code.
* Are large software projects so that even if their code was open it could be difficult to reuse because there's so much of it already.
* Are not necessariy designed for modularity in mind. So if one wanted to design some custom music program that uses some code of a finished DAW, then this may not be possible, if the DAW's API is not designed modularly.
* Are not necessarily designed for customization. Compare e.g. Cubase (at most user macros?) to Reaper (SDK and JSFX).
* Are fundamentally quite similar software, so that the technical features of DAW A and DAW B are not as big as one may imagine. Most of it is in GUI layouts and bundled FX etc. But all DAW programs could in principle share a "common base".

## DAW users:

* Are happy with their commercial DAW.

or

* Use multiple programs, because they have different strenghts and weaknesses.

or

* Would like to change things in their programs, workflows, etc., but have no means to change things.

## Existing DAW frameworks:

* Are scattered and unstandardized. Every "DAW house" might construct their own framework or at least select their own toolchains.

## Developers:

* May want to develop new types of programs or new components to new programs, but get lost as how to achieve it, if there's no "common base framework" of DAWs, which can be studied like JUCE or WDL-OL can be studied for plug-ins.
* May want to write or modify only particular parts of programs, like rewriting a fader class or a "VST rack" class or something.
* May want to share creations, but may not have conventions for doing so.
* May want to write different sorts of musical applications, and may not want to rethink the framework choice everytime they do so.
* May want to develop in new languages, which might then require that the lower level API is written in some nice language, e.g. C, for which it's easy to create bindings.

# Motive:

Based on the given background it would seem that having a framework of C code that allows development of "all sorts of DAW programs" like JUCE or WDL-OL allows writing "all sorts of plug-in" could be nice.

# Some proposed features of such framework:

* It's written in C, since this allows most freedom in choosing to e.g. develop in other languages, while still leaving options for C-compatability and high performance.
* It has a modular architecture, which means that it contains "generic classes" that define what a DAW generally has or may have. The framework is meant to operate like Qt operates for GUIs. That is, when a developer wants to write DAW or a music program, then the framework has the essential parts for this and ways to extend them.
* It's FLOSS, because this allows it to be retained in public domain use, so that anyone can use it.
