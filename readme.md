# nbpaths

This package addresses the `ModuleNotFoundError` issue described [here](https://stackoverflow.com/questions/15514593/importerror-no-module-named-when-trying-to-run-python-script/15622021#15622021) where local modules in parent directories are not found when using iPython notebooks.

It will add parent (and grandparent, etc) directories to `sys.path`. By default it will do this up the directory tree up to and inclusive of any directory which contains a `.gitignore` file (typically the project root).

To use, simply add `import nbpaths` to the top of your notebook.

This will silently add the parents to your path thus making any modules there usable in subsequent code.

It is by design that this is not configurable using arguments, as this would diminish its benefit (which is as a more succinct alternative to `sys.path.insert(0, "path/to/your/module")` for each module); those seeking alternative behaviour are welcome to clone and modify the `stopfile` settings, etc.



