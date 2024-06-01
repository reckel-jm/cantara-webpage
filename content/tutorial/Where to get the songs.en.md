---
title: "Manage Songs"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 4
---

When using Cantara, you will need to collect, edit and distribute songs which can be used for presenting or exporting. If you start Cantara for the first time, you will notice that–depending on what you have chosen in the welcome assistent–you might only find one song available: "Amazing Grace". From that point on, you can start to get and add songs.

The folder which you choose two be your song repository will contain all the songs which you use in Cantara. That means that in order to add a new song, it is enough to just add a new file in that folder. Likewise you might proceed for editing or deleting songs. If you want to share all songs with someone else, just copy the files of your dictionary or share the folder itself. 
It has been also developed as a common pratice to create a Git repository in your repository folder which than can be shared via Github, Gitlab or other providers. 

## Understanding the way how songs are saved

Cantara supports two different song formats. One has the file ending `.song` and is very simply designed. It just contains the lyrics in the order as they should be presented along with some tags which describe the meta data of the songs. The other format is used by [CCLI Songselect](https://songselect.ccli.com/) and has the file endings `.txt` or `.ccli`. CCLI is a commercial database where you can download a lot of Christian songs for the use in churches or Christian groups.

{{% notice tip %}}
A lot of Christian church denominations and groups in Germany (including FeG, SMD as far as I know) provide member access to CCLI Songselect. You can find out whether you organization has already booked a subscription for you.
{{% /notice %}}

Cantara will automatically detect the correct song format and interpretate it in the way as stated below.

### The song file format

The song file format is a file which ends with `.song`. The lyrics there have to be printed in the same order as they should be shown including repetitions. Different slides are seperated with a double linebreak (an empty line). For example, if you would like to add the song "'Tis so sweet to trust in Jesus", add a new file `'Tis so sweet to trust in Jesus.song` with the following content:

{{%expand "Expand the file content " %}}
    'Tis so sweet to trust in Jesus
    Just to take Him at His word
    Just to rest upon His promise
    Just to know thus saith the Lord
    
    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
    
    O how sweet to trust in Jesus
    Just to trust His cleansing blood
    Just in simple faith to plunge me
    'Neath the healing cleansing flood
    
    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
    
    Yes 'tis sweet to trust in Jesus
    Just from sin and self to cease
    Just from Jesus simply taking
    Life and rest and joy and peace
    
    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
    
    I'm so glad I learned to trust Thee
    Precious Jesus Savior Friend
    And I know that Thou art with me
    Wilt be with me to the end
    
    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
{{% /expand%}}

The song consists of four stanzas with the chorus repeated after each one. Now, let's say that we would like to have a slightly different version of the song where we sing two stanzas together. A good convention fot this would be to copy the existing file `'Tis so sweet to trust in Jesus.song` to `'Tis so sweet to trust in Jesus [two stanzas together].song` and adjust the content:

{{%expand "Expand the file content " %}}
    'Tis so sweet to trust in Jesus
    Just to take Him at His word
    Just to rest upon His promise
    Just to know thus saith the Lord
    
    O how sweet to trust in Jesus
    Just to trust His cleansing blood
    Just in simple faith to plunge me
    'Neath the healing cleansing flood
    
    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
    
    Yes 'tis sweet to trust in Jesus
    Just from sin and self to cease
    Just from Jesus simply taking
    Life and rest and joy and peace
    
    I'm so glad I learned to trust Thee
    Precious Jesus Savior Friend
    And I know that Thou art with me
    Wilt be with me to the end
    
    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
{{% /expand%}}

Cantara will detect both song files and list them next to each other. While this approach seems to be a little bit complecated at the beginning, the practical usage has shown that it is much easier then using more complex file formats. You can always use your local text editor to adjust the lyrics as you like them to be. There will be no danger of missinterpretation or wrong order.

### CCLI Songselect

The CCLI songselect format will be used if you download a song from CCLI songselect. In opposite to the song format, the CCLI songselect lyrics format provides no clear information about the correct order of the different parts in a song (stanzas/choruses etc.). So, Cantara has to guess the order with an implemented algorithm. For **most of the songs**, Cantara will put the lyrics into the correct order. However, some of the CCLI song files lack consistency. In this case, you can convert the CCLI file to a song file and manually edit it according to your needs. 

{{% notice note %}}
Due to the lack of consitency, it is not recommended to edit a CCLI songselect file directly. Cantara will ask you to convert it to a song file first.
{{% /notice %}}

Here is some information about the parts which Cantara does understand:

  * "Vers/Strophe": a stanza which will be sung only once at the placed position
  * "Chorus": if available, the chorus will be sung at the placed position and afterwards repeated after every stanza or bridge. If an other chorus will come, it will replace the first one.
  * "Bridge": Will be treated like a stanza. A chorus will (most likely) follow if there has been one before.
  * "PreChorus": Will be sung before chorus (here the format is quite inconsistent!)
  * "Schluss": A closing part of the song. No chorus will follow.

{{% notice note %}}
The editor is capable of converting CCLI files to the song format. Just open a CCLi file in the editor and confirm that you would like to perform the conversion.
{{% /notice %}}

## Download songs from CCLI Songselect

As stated above, you can directly import songs from [CCLI Songselect](https://songselect.ccli.com/). Go to their webpage, login with your account and search for the song which you want to download. Press the speech bubble symbol right next to it (see picture below). After the text is shown, click at the third blue button from the left with the download symbol. Save the .txt-file directly into the Cantara song repository directory. Cantara should recognize the song and use the lyrics in the correct order.

![](/images/ccli-results.jpg?width=800) ![](/images/ccli-song-download.jpg?width=800)

{{% notice warning %}}
As stated before, it is your responsability to comply with the legal requirements of CCLI and the song copyright owners when using their services!
{{% /notice %}}

## Additional Song Lyrics Sources

  * [Hymnary.org](https://hymnary.org/): A very large hymn collection (mostly English)
  * [Evangeliums.net](https://www.evangeliums.net/lieder/): A German collection of Christian songs, some can not be accessed directly due to copyright restrictions
  * [The Cantara SongRepo at Github](https://github.com/reckel-jm/cantara_songrepo): Contains Public Domain Songs for free and direct use

## Edit and convert songs with the built-in editor

Cantara offers a built-in editor which provides an easy way to create songs, edit them or remove them. In addition, you can convert a CCLI song to the song format so that it might be adapted to your needs.