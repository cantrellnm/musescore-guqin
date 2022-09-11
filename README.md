# Guqin for Musescore

**NOT A PLUGIN!** This repository contains the files and instructions to get an okay-ish version of a "guqin" instrument working in MuseScore. The result is basically a 7-string guitar with 正調/ZhengDiao tuning (C D F G A c d) where the tablature staff will show 徽/Hui numbers instead of fret numbers. No JianZiPu or fingering information!

![Screenshot of linked staff and tabs with hui numbers](https://github.com/cantrellnm/musescore-guqin/blob/main/screenshot.png?raw=true)

---

## Part 1 - Instrument

You *could* re-create the instrument for each new score by editing the string data of a 7-string guitar in "Staff/Part Properties". But it's easier in the long run to use an `instruments.xml` file with the instrument information. If you don't already have a custom `instruments.xml` file, you can:

1. Download the `instruments.xml` file from this repository and save it somewhere on your computer. I recommend keeping it close to wherever MuseScore keeps its files. For example, mine is saved in `C:\Users\[USER]\Documents\MuseScore3\Extensions`.
2. In MuseScore go to Edit > Preferences and open the Scores tab. For "Instrument list 2" locate and select the `instruments.xml` file you just downloaded. Click OK.
3. You may need to restart MuseScore, but you should now find the Guqin & Guqin (Tablature) instruments in the Strings - Plucked group.

But the instrument is still just a guitar with guqin tuning.

## Part 2 - Tab Hui Numbers

This next part is a total hack. We can't change the behavior of the tabs to switch from frets to hui, but we can "translate" frets to hui numbers with a custom font. Except we can't use custom fonts for the tabs! So as suggested in [a comment from MuseScore Issue #268399](https://musescore.org/en/node/268399#comment-1111872) we're going to override one of MuseScore's built-in fonts. **Don't do this if you already use the non-standard tabs font!**

1. Download the `MScoreTabulature.ttf` file from this repository and install it to your computer.
2. In MuseScore (you may need to close & re-open), right-click the Guqin tablature staff and click "Staff/Part Properties".
3. Click the "Advanced Style Properties..." button and choose any of the fonts for Fret Marks except MuseScore Tab Sans or MuseScore Tab Serif.
4. Increase the font size (and maybe line distance) until it's legible and click OK.

Tada! It's still just a guitar with guqin tuning but now you'll see hui numbers on the tab staff. And you can uninstall the `MScoreTabulature.ttf` font at any time to switch back to the default behavior.

## Limitations

1. Because this relies on a font that's installed on your system, another computer without the font installed will just see regular fret numbers when viewing a `.mscz`/`.xml` file of your music. (But a pdf/printing should work!)
2. There's a decent number of hui positions in this font (36 positions from hui 1 to 13+) but the numbers must match up with frets (in semi-tone intervals like a guitar) so it is more limited than the actual instrument (which has no frets).
3. I did my best to match hui numbers with fret numbers, but there was rounding involved for all except the octaves and a guitar is an equal temperamant instrument (a guqin is not!) so it's not going to be exact. Use your ear and be prepared to adjust a little.

---

**Issues and pull requests welcome.**