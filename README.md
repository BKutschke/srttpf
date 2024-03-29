# I. Authorship
The tool "AnalyzeSrttpf" was jointly developed by Beate Kutschke and Tobias Bachmann. Tobias coded the tool.

# II. Short description of the tool "AnalyzeSrttpf"
The tool "AnalyzeSrttpf" finds the small rounded two/three-part form in larger corpora of monophonic songs and dances as they were published in popular music collections in Europe between 1650 and the early 19th century. 
To this end, SRTTPF identifies all repeated note sequences (defined by pitch and duration). Most importantly, it also shows repeated note sequences that 'compete' with each other because they overlap. For more information on the tool and its function: 
- https://smc2020torino.it/adminupload/file/SMCCIM_2020_paper_189.pdf
- https://github.com/BKutschke/srttpf/blob/main/OMR-SMC-paper_189.mp4


For a description of the music-historical research project motivating the development of the AnalyzeSrttpf:
- https://github.com/BKutschke/srttpf/file/Description_of_music-historical_project.pdf

# III. Instructions for installing and running ‚AnalyzeSrttpf‘
The instructions focus on Windows. In section 1 and 2, the instructions operate with a preconfigured version of the tool suitable for a test run. The test run provides a first idea of the tool. Instructions for the tool’s individual configurations follow in section 3.

# 1. Installation of Music21 and Python
- Download python-3.6.0 (or a newer version) from https://www.python.org/downloads/. (You need a version of python-3, not of python-2.) Unzip the folder. You will receive python-3.6.0.exe. Install the program.
- To download music21-3.1.0.win32.zip (or a newer version or a version for MacOS or Linux) go to http://web.mit.edu/music21/ and klick on releases (https://github.com/cuthbertLab/music21/releases). Unzip the folder. You will receive music21-3.1.0.win32.exe and install the program.
- Run Python. (If the Windows Start menu shows you four items of Python, do not click on ‚Python module docs‘, IDLE or ‚Python manuals‘, but ‚Python‘ without additional label. Clicking on Python opens the windows console. Type: „from music21 import *“ (without quotation marks).

# 2. Installation of additional tools („libraries“) for visual presentation of results and writing analytical results into EXCEL table
- Install matplotlib (available in this repository): Open the windows console via „Windows R“ –> „cmd.exe“ and type „py -3 -m pip install -U pip setuptools“, then „py -3 -m pip install matplotlib“ (for visual representation)
- Install openpyxl: In the windows console type „py -3 -m pip install openpyxl“ (for writing analytical results into EXCEL table).
- Install natsort: Download the package ’natsort‘ for Python from https://github.com/SethMMorton/natsort; on this page, click on releases (https://github.com/SethMMorton/natsort/releases) and choose the latest zip-folder for download). Type in the windows console: „py -3 -m pip install natsort“ (without quotation marks).
- Installation of MuseScore3.0 (or higher): Go to the page of Musescore (https://musescore.org/en/download) and download MuseScore 3.0 (or higher). Install the software. (Linux users might receive different visual results because of some platform dependant behaviour of the exported files.)
- Further customization in the context of MuseScore3.0: In order to make Tobias’ software operate MuseScore3.0, users have to add the path that leads to MuseScore, to the computer’s system. They do so by open „Control panel“, then „system“, then „Advanced system settings“, then „Extended“, then „Environment variables“. In „System variables“ select „Path“ (double click) and then copy&paste the path of the “bin” file of MuseScore3.0 into the current window by clicking on „new“ on the right side of the window: for instance „C:\Program Files\MuseScore 3\bin“- Close both windows by clicking on „o.k.“ (otherwise the program will not run).
- Customize size of pngs: The PNGs displaying the score together with the analytical results achieved by by ‚AnalyzeSrttpf‘ on an infinite html need to be enlarged in order to avoid that python produces scores in PNG format with numerous ‚line breaks‘. To this end, change the format of the PNGs. You do so by opening the printer options: right click on a printer; select „Printer options“; select „Layout“; select „Customize page size“; type „40 cm“ for width and give the new size a recognizable name; save. (There should be somewhere the option “Apply to all printers” which I cannot find at the moment.)
- Install notepad++: Go to https://notepad-plus-plus.org/download/v7.6.6.html.
- Download AnalyzeSrttpf.py and the ancilliary scripts and folders available in this repository as AnalyzeSrttpf.zip (https://github.com/BKutschke/srttpf/blob/main/AnalyzeSrttpf.zip) (Creative Commons Lizenzvertrag  Creative Commons Tobias Bachmann, MA (Paris Lodron Universität Salzburg) 4.0 International Lizenz (http://creativecommons.org/licenses/by/4.0/))

# 3. How to use one of the tools to carry out an analysis:
- Create images of the scores (PNGs): In order to create images (PNGs) of the scores to be displayed together with the analytic results (Repeated-notes indicator on infinite HTML), open IDLE (Python) (in Windows 10: search for IDLE via Cortana). In IDLE, click on“File“ (in the menu), then on „Open“. Navigate to the folder „AnalyzeSrttpf“ and double click on „MakeNotes.py“. Python displays the script in its console. In line 23, you can change the path to the folder with the MusXMLs to be transformed into pictures. The text of this line is: „folder = ‚xml'“. „xml“ is the current default folder and contains two MusicXMLs. Feel free to make a test run with these files or replace them by the MusicXMLs you want to analyze. Run MakeNotes.py by pressing „F5“. MakeNotes.py stores the created notes in the folder „notes“.
- Run AnalyzeSrttpf.py: Open IDLE (Python) (see step 1, if not already open). In IDLE, click on“File“ (in the menu), then on „Open“. Navigate to the folder „AnalyzeSrttpf“ and double click on „AnalyzeSrttpf.py“. Python displays the script in its console.
- Go by means of the find function (Strg + f) to „# choose the config section“ in line 148 and activate „FIRST“ by deleting the hashtag („#“) at the beginning of the line „configNumber = ‚FIRST'“. (Idle changes the colour of the line from red to black and green.)
- Run Analyze Srttpf.py by clicking on Menu –> Run –> F5 or by directly pressing „F5“.
- Repeat steps 3 and 4 by activating SECOND and FOURTH one after the other.
- You will find the results of the analysis in the folder „AnalyzeSrttpf“:
-- You will see three different HTML-files showing three different views of the pieces: 1. repeated note sequences that share pitches and durations with each other; 2. repeated note sequences that share only the durations with each other; 3. repeated note sequences that share only the pitches with each other.
-- In Excel.xlsx, the columns C to BF show the analytical results. (Please note that you need Microsoft EXCEL 2007 (or higher) or LibreOffice to open, modify and save the files in xlsx-format. (OpenOffice opens XLSX-files, but does not allow to save the files as xlsx to be needed if you want py to write further analytical results into the excel.xlsx.)
- If you want to analyse your own MusicXMLs, copy the MusicXMLs you want to analyse to the subfolder „xml“. If you want AnalyzeSrttpf.py write the results in your own EXCEL table, open config.ini with notepad++ (or another editor) and determine the name of the target and source XLSX for all four analytical steps (lines 103, 106, 272, 275, 325, 328, 380, and 383). (They can be identical if you are not afraid of loosing data because of overwriting.) Make sure that the config.ini indicates the proper column where the identifier of the file is indicated – „xlsxIdentifierCol=xy“, line 342 – and the proper columns where the results are to be written.

# 4. Details for the use of analyse.py
File names in JSON format (such as the CriteriaPoolSrttpf.json) must not have blanks. Use hyphens instead, for instance.
Make sure that the data in XLSX-files are in table 1 of the file. Otherwise AnalyzeSrttpf.py won’t find them.
