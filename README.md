# codeAppearanceLatex

These are config files to insert pretty code inside LaTeX documents. Two options are available, both of them supporting Julia language syntax highlighting. To use them, place one of the files in your directory and write in the preamble:
```
\input{codeListingConfig.tex}
```
or:
```
\input{juliaMintedConfig.tex}
```
depending on which one you want to use.

An example document is provided in main.tex, which uses both approaches to show the code "leastSquares.jl", and whose output is shown in exmple.pdf. The Listing package is less prone to installation errors, but at least in ShareLatex both of them work well. Note that the Minted package needs a floating environment to support captions and labels.

*************************************************************
## codeListingConfig.tex ---- Listing package approach
*************************************************************

This is a config file to set:
   1. Style for listing package (could be used on any language)
   2. Julia syntax highlighting definition
   3. Command and environment to insert julia, python, and matlab code in your document easily.

       a. New commands: \juliaFile, \pythonFile, and \matlabFile
       
        All three are used like
        ```
        \juliaFile[folder_name]{file_name}
        ```
        folder_name is optional, and do it with the slash, e.g. "myFolder/". When no folder is provided, it is assumed that the code is in the same directory as your document.

        For file_name, do it without extension (it is assumed). Example:
        ```
        \juliaFile[codes/]{kMeans}
        \juliaFile{randomForest}
        ```

       b. New environments: if you want to write your code directly in your document. juliaText, pythonText, and matlabText are provided. Example:
        ```
        \begin{juliaText}{Write your caption here.}
            Write your code here
        \end{juliaText}
        ```


*************************************************************
## juliaMintedConfig.tex ---- Minted package approach
*************************************************************

 This is a config file to set:
   1. Style for minted package, using Julia language as a default.
   2. A command to insert julia code. Note that to have caption and label, a floating environment is needed.
   Example without caption: 
   ```
   \juliaFileMinted{randomForest.jl}
   ```
   Example with float environment:
   ```
   \begin{listing}[h!]   
      \caption{My Caption}      
      \label{code:myLabel}
      \juliaFileMinted{randomForest.jl}
   \end{listing}
   ```
