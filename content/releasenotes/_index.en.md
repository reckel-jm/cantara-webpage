---
title: "Release Notes"
date: 2022-08-02T16:34:40+02:00
draft: false
weight: 2

---

This page contains information about the changes in different versions (releases) and plans for the future.

---

## Releases

### Version 2.6.0 (2024-05-31)

- Migrate to bgrabitmap for better handling and displaying of the presentation slides. In the future, further text effects like shadows etc. can be easily implemented.
- Redesign the multi screen presentation controller: In addition to the songs, every slide with content is listed and can be selected directly.
- Context menu of presentation window: Fullscreen and ending of presentation is now also selectable with that menu.
- Minor improvements of the song editor and full text search.
- Add "Select all Songs" under File menu in song selection.
- Bugfix: Wrong display of presentation when no specific font has been selected #24
- Bugfix: Drag and Drop exception in song selection window
- Bugfix: Wrong escaping of special characters in pptx-export
- A lot of minor bugfixes and corrections
- Translation update


### Version 2.5.0 (2023-08-21) 

- Complete rewriting of large parts of the source code including the internal structures for generating and painting presentation slides
- Improvement of the presentation layout
- Improvement of the song editor
- Implementation of a preview of the presentation in the settings menu
- Implementation of slide export to pptx (using PptxgenJs)
- Implementation of slide export to pictures
- Implementation of song lyrics export to markup text files
- Implementation of a full text search for browsing song lyrics
- Implementation of a two language song presentation
- Improvements of the presentation window and control (more keys and remote controls are supported)
- Fix [issue #17](https://github.com/reckel-jm/cantara/issues/17) 
- Cantara can now be directly opened with a ```.songtex```-file.

### Version 2.4.1 (2023-01-30) Italian and Spanish translation

The version 2.4.1. adds Italian and Spanish translation to Cantara. Despite that, there is no additional functionality compared to Version 2.4.0 which means that if you are not using one of the languages, you don't necessarily need to update to this version.

**Thank you to the translators!**


* The Italian translation has been provided by [@albanobattistella](https://github.com/albanobattistella)
* The Spanish translation has been provided by [@haggen88](https://github.com/haggen88)

Thank you for the effort!

### Version 2.4.0 (2023-01-06)

Version 2.4 is finally there! Beside new features, it also brings a lot of bug fixes. See the list below for details.

#### Improvements/Enhancements

* A new editor has been implemented which allows editing of the songs, converting CCLI songs into the song format, creating new songs, archiving them and cloning them (e.g. for different versions).
* A welcome assistant will guide new users after the first start of Cantara to setup and understand the program.
* Cantara can automatically break long slides into two pages if configured in the settings.
* The newly implemented SongTeX file format allows to export songs slides with the song lyrics and the order.

#### Bug Fixes

- Floating point errors when no background picture was selected
- Loading the slides took a long time if a background was selected

### Version 2.3.2 (2022-11-10)

This is a minor release which brings two small but useful improvements:

* Completion of traditional Chinese translation
* readiness for Flatpak

Check the corresponding [GitHub page](https://github.com/reckel-jm/cantara/releases/tag/v2.3.2) for details.

### Version 2.3.1 (2022-08-12)

This is a minor release and follow up on version 2.3

#### Improvements

- Version 2.3.1 brings support for background images. These can be adjusted and made transparent (towards the background color) or brighter.

#### Bug Fixes

- fix of spell mistake in CCLI license tag. It is now `ccli-licensenumber`
- complete German translation

### Version 2.3 (2022-08-02)

After testing and further development, version 2.3 can be released.

Improvements:

* Support of the CCLI songselect format*
* Support for Metadata which can be displayed dynamically during the song
* Improvements in source code
* Preparations for further development in source code, abstractions
* Bugfixes in displaying the songs

As always, I am looking forward to feedback, suggestions and bug reports.
Thank you!

[Go to Github page of the Release](https://github.com/reckel-jm/cantara/releases/tag/v2.3)
