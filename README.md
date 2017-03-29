The traditional method of including SAS code and corresponding results in a document is to copy and paste them into Word. Which is fine if you do it perfectly the first time. But more often than not there is some iteration. You make small adjustments here and there. And all too often you end up with your code and output being out of sync.

When you use the StatRep LaTeX package, you follow a four-step process to create an executable document that guarantees that your research results are reproducible.

1. Create a LaTeX file that contains your text and SAS code. 
1. Compile the LaTeX file to generate two new files. 
   1. A PDF file with placeholders for your SAS output.
   1. A SAS program containing the code embedded in the LaTeX file. 
1. Run the SAS program to generate output. 
1. Compile the LaTeX file a second time to pull the SAS outputs back into the PDF.

The main advantage of this system is that you don't have to worry about your SAS code and outputs being out of sync. Because the SAS code is embedded within the document, it's definitely going to be the same code that generated your outputs. 

SAS documentation for the StatRep package can be located [here](http://support.sas.com/rnd/app/papers/statrep.html). Or, if you want a more streamlined (but less complete) version of how to use StatRep, continue reading. 

## Install MiKTeX

There are a lot of different versions of the TeX language. It is recommended that you install [MikTeX](https://miktex.org/download). 

Once this software has been installed, open the file xxx. 
