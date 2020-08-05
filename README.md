# FSL_Windows
<h3>
<img src="https://twiki.cern.ch/twiki/pub/IPv6/ResourceRepository/work_in_progress.png" width=10% height=10%>
this project is highly Work-In-Pogress
<img src="https://twiki.cern.ch/twiki/pub/IPv6/ResourceRepository/work_in_progress.png" width=10% height=10%>
</h3>

#
#
steps to compile **FSL** (https://fsl.fmrib.ox.ac.uk) under Windows using **MSYS2** (https://www.msys2.org/)
#

### Install MSYS2/MinGW64
- download and run the installer from https://www.msys2.org/#installation-prerequisites <br>
in the following we will only use the MinGW64 shell, <br>
so you may remove the Desktop Shortcuts for MinGW32 and MSYS2
- run the **Setup_MinGW64.sh** shellscript from this repository <br>
this will automatically download and install the required packages from the <br>
<a href="https://packages.msys2.org/base">MSYS2 repository</a>

### Download and Patch FSL sourcecode
- run the **Setup_FSLsources.sh** shellscript from this repository <br>
this will automatically download and install FSL 6.0.3 sources from the <br>
<a href="https://fsl.fmrib.ox.ac.uk">FMRIB website</a>
(if the download fails (due to a newer FSL version available) edit the script)

### Compile FSL
- run the **Compile_FSLsources.sh** shellscript from this repository <br>
(this will take a while and should finish with "Build completed successfully."

### Post-Install
```diff
-   NOT IMPLE<ENTED YET
```

### Test FSL with official FEEDS testsuite
- run the **Test_FSLfeedsy.sh** shellscript from this repository <br>
```diff
-   steps that are NOT WORKING YET are commented out in the script
```

### Test FSL Graphical User Interface
- run the **runFSL.sh** shellscript from this repository <br>
feel free to play arround
```diff
-   you probably will find many things that are NOT WORKING YET
```

### Known Problems
- Post-Install not implemented yet
- some TCL commands do not work yet <br>
(if you happen to know TCL you are very much wellcome to contribute;)
- does not read/write compressed NIFTI (.nii.gz) only uncompressed (.nii) <br> 
(don't know how to solve this, anybody help?)
- may have problems when trying to process .xml files in atlas operations (memory leaks ?) <br>
(to see my dirty patches search for "///xmlFree" in "fsl_patch")
- may have problems parsing arguments passed to executables <br>
(to see my dirty patches search for "fsl/src/utils" in "fsl_patch" and lookout for "///") <br>
- there are probably many more bugs, if you find any please don't hesitate to open an issue
