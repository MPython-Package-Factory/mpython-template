# MPython Template
This repo is a simple to wrap Matlab projects in Python using Matlab Compiler and [MPython](https://github.com/MPython-Package-Factory/mpython)

## To wrap your project from Github 
### 0. Prerequisites.

This requires [Matlab Compiler](https://uk.mathworks.com/products/compiler.html?requestedDomain=), as well as a version of [Matlab Runtime](https://uk.mathworks.com/products/compiler/matlab-runtime.html) compatible with your version of Matlab. 


### 1. Clone [mpython-template](https://github.com/MPython-Package-Factory/mpython-template).
```bash
git clone git@github.com:MPython-Package-Factory/mpython-template.git YOUR_PROJECT_NAME
cd YOUR_PROJECT_NAME
```
  
### 2. Edit [mpython/wrap_project.py](https://github.com/MPython-Package-Factory/mpython-template/blob/main/.mpython/wrap_project.m#L5)... 
...to target the right project URL and configure the name of the Python package
```matlab
python_package_name = 'example_project'; 
matlab_project_url  = 'https://github.com/MPython-Package-Factory/example-project-matlab.git'; 
```

### 3. Wrap your project
```bash
cd .mpython                     # Move to .mpython
matlab -batch "wrap_project"    # Create the Python wrapper
cd ..                           # Move back to the main folder
```

### 4. Finally, install your package with Pip and try it out
```bash
python3 -m pip install -e .    # Install the package in developper mode
python3 -c "import example_project"
```

## Configuring the code generation 

MPython will generate Python code using certain templates for common code structures (e.g., function signature or class definition).

A full list of the existing templates can be found in [mpython/templates](https://github.com/MPython-Package-Factory/mpython/tree/main/templates). 

You can customize these defaults templates by copying them to your [.mpython/templates](https://github.com/MPython-Package-Factory/mpython-template/blob/main/.mpython/templates) and editing them (as for [this custom docstring template](https://github.com/MPython-Package-Factory/mpython-template/blob/main/.mpython/templates/docstring)).  
