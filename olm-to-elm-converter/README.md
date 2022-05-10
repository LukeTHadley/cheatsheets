## OLM to EML Converter

For no apparent reason other than to annoy me and make things difficult, versions of Microsoft Outlook for Mac (e.g. Microsoft Entourage 2006, Microsoft Outlook 2011 (although this guide was used on exported data from the 2011 version)), can only export your data to a `.OLM` type.

This type can only be imported into other mac-types of Outlook, unless you use a payed converters.

If you wanted to, say, oh i don't know, export your email data and use it in another application or export your data to a PC, you can't.

However, with a small bit of Python code and messing about with file extentions you can convert your data to `.EML` type that can be imported into most email clients.

This code was originally taken from a [Gist - convert_olm_to_eml.py](https://gist.github.com/tennantje/f04f54871db5e7a0507331f69648f7f4)

#### Prerequisits

You will need a command line that can run Python 3

You need to export your data from outlook to an OLM type form outlook.

#### Using the tool

Step 1: Rename your exported `.olm` file to `.zip` file extention.
An OLM is just a zip file with documents inside, we will parse the content inside of it.

Step 2: Unzip your zip file

Step 3: Go into your now unzipped folder and place the `olmconverter.py` file into the folder that should have the following files.

```shell
Accounts/
Categories.xml
Local/
```

Step 4: In your local folder, delete all folders apart from `.com/microsoft.__Messages` that has your emails in.
All other files are not your emails and will break this current version of the converter.

Step 5: Run the python file from the command line with no given arguemtns.

The program shoudl start running, outputting the filepath of each email as it converts them.

Step 6: After the program has finished running, all files will have been duplicated and converted with the `.EML` file type which can now be imported.

Step 7: Import your xml..

Thunderbird Specific - Use the Thunderbird extention (ImportExportTools-NG) to import your XML email files.