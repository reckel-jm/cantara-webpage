---
title: "The General Roadmap of the Project"
date: 2023-02-01T16:11:42+01:00
draft: false
hidden: true
---

When I started Cantara six years ago (three years before I created this Github repository), I didn't except that I would continue the project for such a long time. Originally only designed for my personal purpose (having a simple song presentation program for church groups) it is now a widely used Open Source project. According to the snap store statistics (which is the only reliable one I have at the moment), Cantara is currently used by more then 120 individuals from 39 countries around the world. In addition to that, there are AUR, Flatpak and Windows users from which I don't have any statistical data. Cantara has been translated into Chinese, Italien, Spanish and German by the community and whenever when I get some feedback, I am really happy to see how this little program can be a tool to serve the church for the honor of God. 
With that being said, I would like to introduce some ideas and plans which I have for the future of the program and I am interested in your thoughts and suggestions as well:

### Cantara as a presentation program and presentation provider

A lot of churches have a complex presentation workflow for their church services/events which includes song presentations, presentations for the sermon (provided by the preacher), videos, Bible readings, announcements, etc. Although there are all-in-one-solutions who are designed for addressing all of this purposes, they are often lacking in functionality compared to the "original" ones. For example, a lot of sermons will be designed in PowerPoint, Libre Office Impress, LaTeX beamer or any other presentation software. It is unlikely that Cantara–even if we would try–could ever get the same functionality as these programs. However, Cantara could be a provider to such workflows if it allows to **export** the song presentations in these formats. Therefore I am planning to add an export functionality which allows to generate presentations which can be imported into other programs for getting a unified workflow experience. At the moment, my idea is as following:
- PowerPoint presentations can be easily created via the [PptxGenJS](https://gitbrent.github.io/PptxGenJS/)-library which is published under the MIT license. We could use the systems web browser to run the JavaScript and in that way keep Cantara leightweight. Cantara would need to export the presentations into some JavaScript code which can be used by the web browser + PptxGenJS to create a pptx.
- In addition to that, I would like to provide export options into [revealJs](https://revealjs.com/) and LaTeX Beamer slides which are also widely used **and** Open Source which is definitely an important reason to support these.
- I would love to use the Libre Office format (odp). However I don't know any library/framework which could be used to generate such files. If anyone has some hints for me, feel free to share.

This is all of course in addition to the presentation functionality and **not** as a replacement. The users will have the choice whether they would like to use Cantara as a song presentation tool *or* whether they would like to use it to generate the presentations which an be embedded into their presentation program of choice.

### Generate Sheets and Chords for the Musicians

An other long time desired feature would be to extend the musical functionality of Cantara so that the software could also generate sheets PDFs for the musicians. For that, I would prefer a combination of LuaLaTeX, [Lilypond](https://lilypond.org/index.de.html) and [lyluatex](https://github.com/jperon/lyluatex) which allows the generation of nice song books. The idea is that in addition to the song lyrics, song sheets (either an ly-file or a pdf file) can be managed as well. If a song presentation is created, Cantara would be also able to generate the sheets and put them into one PDF file so that the musicians don't need to look for the sheets by themselves. 

An alternative approach would be a JavaScript framework such as [OpensheetmusicDisplay](https://opensheetmusicdisplay.org/). This would require the source files to be in MusicXML instead of Liilypond and would not allow complete PDFs to be imported.

### Migrating to Flutter?

Pascal is an amazing programing language for development and Lazarus is very good for platform independent programing. However, with the time going forward there are other widely supported alternatives as well. One of them is Flutter which has been developed by Google. It would allow to create one application for all (Windows, Linux, Mac OS, Android, iOS). Whether it fits or not, could be evaluated in the future, so that maybe a long term migration to Flutter could be an option (but does not have to).

### Time Roadmap

Due to private circumstances, development will be continued after April 2023. Till that time, I have to finish my master thesis and collect more ideas and plans :-) 

**Any ideas, comments or thoughts?** [Continue the discussion on Github](https://github.com/reckel-jm/cantara/discussions/13)