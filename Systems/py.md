# Python Ecosystem
## Python Packaging Options
- Module
    - a `.py` file.
    - Standalone: only imports from standart library.
    - e.g. `bottle.py` in Flask.
- Package
    - a directory of `.py` files with a `__init__.py` in it.
    - can be installed with `pip`
    - e.g. `Django`, `requests`, `hyperlink`
- Distribution 
    - an archive of zero or more packages.
    - built by `setuptools` through `setup.py`.
    - e.g. `sdist`
- Full Python package
    - e.g. numpy, SciPy, Pandas
    - need to use `wheel` to distrubute
        - a binary distribution, `bdist`
        - static linking vs. dynamic linking
        - `pip` can't store `deb` or `RPM` but `wheel` can
        - does not require `gcc` or `clang`
- Latest  way to build and upload a Python package:
    - `python setup.py sdist bdist_wheel upload`
- Python's native package management will get:
    - libraries
    - basic dev tools
- PyPI is not general purpose app store
    - some packages require other build tools like `gcc` and `clang`
- `PEX` 
    - no setup or install
    - same constraints as `wheel`
- `Anaconda`
    - provides lib, include, etc as in standard UNIX filesystem
- Freezing
    - involves an installer like `.exe` executable or `.app` double-click
    - `virtualenv` cannot be shipped in user apps
    - `dh-virtualenv` by Spotify 
        - includes libraries not Python (like PEX)
        - artifacts managed by `dpkg`
- Userspace images
    - `AppImage` does not require Python to be installed
    - `Docker` needs container runtime and 'pull' step
- Virtual machines
    - bring the whole kernel
    - production-grade emulation

## Packaging Strategy
### Packaging Python Libraries
1. `.py` for standalone modules
2. `sdist` for pure Python packages
3. `wheel` for Python packages that contain non-python code
### Packaging Python Applications
1. PEX - includes libraries
2. anaconda - includes Python ecosystem
3. freezers - includes Python
4. images - includes system libraries, runtime, Python libraries
5. containers - sandboxed images
5. virtual machines - includes kernel

## Questions
- what is `requirements.txt` and `self.py`
- what is `RPM` and `deb`

## References
- [Official Python packaging user guide](https://packaging.python.org/#)
- [Nylas on packaging and deploying Python code](https://www.nylas.com/blog/packaging-deploying-python/) - using `PEX` and `dh-virtualenv`
- [Python packaging in 'Architecture of Open Source Applications'](http://aosabook.org/en/packaging.html)
- [Many layers of Python packaging](http://sedimental.org/the_packaging_gradient.html)
- [Python packaging ecosystem](http://www.curiousefficiency.org/posts/2016/09/python-packaging-ecosystem.html)
- [A new package index for Python](https://lwn.net/Articles/751458/)