# Outline

1. <a href="#Overview">Overview</a>
1. <a href="#Getting Started with LaTeX">Getting Started with LaTeX</a>
1. <a href="#Getting Started with StatRep">Getting Started with StatRep</a>
1. <a href="#Example SESUG Paper">Example SESUG Paper</a>

<a name="Overview"/>

# Overview

The traditional method of including SAS code and corresponding results in a document is to copy and paste them manually. Which is fine if you do it perfectly the first time. But more often than not there is some iteration. You make small adjustments here and there. And all too often you end up with your code and output being out of sync.

When you use the StatRep LaTeX package, you follow a four-step process to create an executable document that guarantees that your code and output are in sync.

1. Create a LaTeX file that contains your text and SAS code.
1. Compile the LaTeX file to generate two new files.
   1. A PDF file with placeholders for your output.
   1. A SAS program containing the code that will generate the output.
1. Run the SAS program to generate output.
1. Compile the LaTeX file a second time to pull the SAS outputs back into the PDF.

The main advantage of this system is that you don't have to worry about your SAS code and outputs being out of sync. Because the SAS code is embedded within the document, it's definitely going to be the same code that generated your outputs.

SAS documentation for the StatRep package can be located [here](http://support.sas.com/rnd/app/papers/statrep.html). Or, if you want a more streamlined (but less complete) version of how to use StatRep, continue reading.

<a name="Getting Started with LaTeX"/>

# Getting Started with LaTeX (~30 minutes)

LaTeX, which is pronounced `Lah-tech` or `Lay-tech` (to rhyme with `blech` or `Bertolt Brecht`), is a document preparation system for high-quality typesetting. It is most often used for medium-to-large technical or scientific documents but it can be used for almost any form of publishing.

1. Install [MikTeX](https://miktex.org/download) (~5 minutes)
   1. This is the basic LaTeX software for Windows.
   1. During the install, change the following.
      1. Preferred paper = **Letter**
      1. Install missing packages on-the-fly = **Yes**
1. Install [TexMaker](http://www.xm1math.net/texmaker/download.html) (~5 minutes)
   1. This is an editor that makes it easier to edit LaTeX documents.
1. Watch [LaTeX Tutorial 1](https://www.youtube.com/watch?v=SoDv0qhyysQ) (~15 minutes).
   1. This is a quick way to gain basic familiarity with what LaTeX code looks like and how to interact with the software.

<a name="Getting Started with StatRep"/>

# Getting Started with StatRep (~20 minutes)

The download link for the StatRep package is located [here](http://support.sas.com/rnd/app/papers/statrep.html). Look for the link titled **_LaTeX package_**.

There are a lot of little details in what follows. Move slowly.

### Install SAS components (~2 minutes)

1. Extract the contents of `statrep.zip`. Copy the file `statrep_macros.sas` into a directory from which it can be accessed by the SAS Grid. For instance, `H:/statrep` would be a good choice.

### Install LaTeX components (~10 minutes)

1. Locate the directory in which LaTeX was installed.
   1. Likely here: `C:/Users/<user>/AppData/Roaming/MiKTeX/2.9/tex`
1. Under the `tex` folder, create subdirectories for `latex/statrep`.
   1. Thus forming `C:/Users/<user>/AppData/Roaming/MiKTeX/2.9/tex/latex/statrep`
1. Copy the following files into this new `statrep` folder.
   1. `statrep.dtx`
   1. `statrep.ins`
1. From a command prompt, navigate to the `statrep` folder.
   1. E.g., `cd C:/Users/<user>/AppData/Roaming/MiKTeX/2.9/tex/latex/statrep`
1. Enter the command `pdftex statrep.ins`.
   1. This should have created, at a minimum, `statrep.cfg`.
1. Open `statrep.cfg` in a text editor and edit as follows.
   1. Locate the line `\def\SRmacropath{statrep_macros.sas}`.
   1. Edit to point to where you saved `statrep_macros.sas`.
      1. E.g., `\def\SRmacropath{H:/statrep/statrep_macros.sas}`
      1. **Note**: You *must* use forward slashes (`/`) in the above file path.

### Use StatRep (~5 minutes)

1. Create a `myfirstpaper` folder under `H:/statrep` and copy `quickstart.tex` into this location.
   1. Thus creating `H:/statrep/myfirstpaper/quickstart.tex`.
1. Double-click to open `quickstart.tex` in TexMaker.
1. Insert a new line 3 that reads `\def\SRrootdir{H:/statrep/myfirstpaper}`.
   1. This line lets `statrep_macros.sas` know where to save things.
1. Compile the LaTeX file.
   1. This should create several files in `H:/statrep/myfirstpaper`.
      1. Examine `quickstart.pdf`. Note the placeholders such as `Missing File lst/tsta.lst`.
      1. Examine `quickstart_SR.sas`. Stare in amazement.
1. Run `quickstart_SR.sas` using Enterprise Guide (does not seem to work in batch).
   1. This should generate some folders with output (`lst`, `png`).
1. Compile the LaTeX file a second time.
   1. This should pull the `lst` and `png` outputs into the PDF file.
   1. Sometimes you have to compile an extra time to get the png labels to line up right. I do not know why. Just click the button twice and get over it.

<a name="Example SESUG Paper"/>

# Example SESUG Paper

An example LaTeX file is included in this repository. The file includes lots of customizations that are useful for SESUG formatting requirements. There are too many customizations to explain them all. Just make yourself a local copy and start editing away. Be sure to modify the 3rd line to correspond to where you save the LaTeX file.
