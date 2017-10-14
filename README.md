# codeAppareanceLatex

This is a config file to set:
   1. Style for listing package (could be use on any language)
   2. Julia syntax highlighting definition
   3. Command and environment to insert julia, python, and matlab code in your document easily.

       a. new commands: \juliaFile, \pythonFile, and \matlabFile
           All three are used like \juliaFile[folder_name]{file_name}
           folder_name is optional, and do it with the slash, e.g. "myFolder/". When no folder is provided, it is assumed that the code is in the same directory as your document.
           For file_name, do it without extension (it is assumed).
       Example:
           \juliaFile[codes/]{kMeans}
           \juliaFile{randomForest}

       b. new environments: if you want to write your code directly in your document. juliaText, pythonText, and matlabText are provided. Example:
           \begin{juliaText}{Write your caption here.}
           Write your code here
           \end{juliaText}
