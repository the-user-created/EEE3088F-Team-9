# PCB notes
To allow your collaborators to have the same setup as you when cloning a git hosted PCB design you need to ensure they have access to the same fottprints and symbols and project configuration as you.  In this template the footprints and symbols are stored in the libraries sub-folder, and 2 approaches that can be taken:

## Option 1:
In this repository a second repo has been added as a submodule and is available in the libraries folder [here](./PCB/Library/kicad6-libraries/).  This is an example of storing all the symbols and footprints you collect and make over time in a single location.  Go and look at the source of this submodule [here](https://gitlab.com/r4space/kicad6-libraries.git).  

The advantage of this approach is that as you develop more PCBs you will collect and create an increasing number of custom symbols and footprints that are not provided in the std KiCAD libraries.  By adding this submodule to all of your projects you will always have access to this extended library.  The cost of this, however, is clearly that your project repos will get increasingly large as your personal library grows.  In the context of collaborative work in a company, this would not be a problem and the company likely has exactly such a custom in-house set of libraries and the repos are not released to a client with the entire submodule but rather a specific release repo is made for this.

For the project, this is an effective way of starting your own libraries repo and collaborating.

At any point, you are able to enter the folder containing this submodule and updating it via a normal git pull.

## Option 2

The second possible approach, is to simply add the libraries of symbols and footprints you use in this project directly to the project repo in the Library folder only.  This is simpler, but means that in a future project you would need to re-download or copy over any components from this project you wish to use again in a new project.  In the long term this is not a sustainable approach for anyone developing many boards or working in a company with many in-house part designs, but will be entirely sufficient for the purposes of this course.

## Usage Instructions

Regardless of the option selected above, in order for KiCAD to be able to see any custom libraries you add you need to tell it where they are.  However, when first configuring your project you will need to do the following in KiCAD:
1. From the main KiCAD page.  Go to Preferences > Manage Symbol Libraries > Project Specific Libraries. And click the folder symbol to add the location of this Library Symbols folder
2. From the main KiCAD page.  Go to Preferences > Manage Footprint Libraries > Project Specific Libraries. And click the folder symbol to add the location of this Library Footprints folder


## Notes on KiCAD file types:
**Schematic library files**
- \*.lib — Container symbol descriptions, pins and graphical information i.e. shape, size or filled color.
- \*.dcm — library documentations for each symbol

**PCB Layout files**
- \*.pretty — Footprint library folders. The folder itself is the library.
- \*.kicad_mod — Footprint files, containing one footprint description each.
