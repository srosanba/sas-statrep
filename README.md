1. <a href="#Overview">Overview</a>
1. <a href="#Getting Started with LaTeX">Getting Started with LaTeX</a>
1. <a href="#Getting Started with StatRep">Getting Started with StatRep</a>
1. <a href="#Example SESUG Paper">Example SESUG Paper</a>

<a name="Overview"/>

## Overview

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

## Getting Started with LaTeX

To get started with LaTeX you need to install two different pieces of software.

1. [MikTeX](https://miktex.org/download)
   1. This is the basic LaTeX software for Windows.
1. [TexMaker](http://www.xm1math.net/texmaker/download.html)
   1. This is an editor that makes it easier to edit LaTeX documents.

Once both pieces of software have been installed, you'll want to go to YouTube and watch one of Michelle Krummel's *excellent* tutorials. Start with [LaTeX Tutorial 1](https://www.youtube.com/watch?v=SoDv0qhyysQ). This is a quick way to gain basic familiarity with what LaTeX code looks like and how to interact with the software.

<a name="Getting Started with StatRep"/>

## Getting Started with StatRep

The download link for the StatRep package is located [here](http://support.sas.com/rnd/app/papers/statrep.html). Look for the link titled **_LaTeX package_**.

There are two pieces to the StatRep package: the SAS components and the LaTeX components. These two pieces have separate setup requirements. 

<a name="Example SESUG Paper"/>

## Example SESUG Paper
