# sky_ros_package_template

This repo is a complete Catkin package. Create a new repo based on this template, then clone it to the `src/` directory of an existing your sky_ws.

**IMPORTANT: CHANGE THE NAME OF SKY_ROS_PACKAGE_TEMPLATE (INSIDE SRC) TO MATCH THE NAME OF THE PROJECT**

## Structuring a Catkin Package for ROS and Python
The structure of a Catkin package varies depending on its intended use, but this one is designed for *simplicity* and *flexibility*, requiring minimal configuration and providing examples and templates to quickly get new ROS nodes up and running.

```
sky_ros_package_template/     # Root folder defines the name of a Catkin package
|   launch/                 # Launch folder holds .launch files, each of which starts one or more ROS node.
|   |   teste.launch    # Launches a simple square test
|   |
|   scripts/                # Scripts folder holds all python mission code.
|   |
|   |   teste.py       # The square code for testing the drone
|   |
|   src/                    # Src folder holds all python submoules
|   |
|   |   sky_ros_package_template/         # This Python package should have the same name as the Catkin package (sky_ros_package_template in this case, but should be the name of the competition)
|   |   |   
|   |   |   sky_utils/                   # A python sub-package
|   |   |   |   
|   |   |   |   __init__.py             # Designates this folder as a package. Just imports everything from this folder.
|   |   |   |   config_utils.py         # Common utilities for configuring rospy nodes
|   |   |   |   
|   |   |   __init__.py         # Designates this folder as a package. Just imports everything from this folder.
|   |   |   
|   |
|   CMakeLists.txt          # Catkin-required file which defines the build process  
|   install.sh              # Installs dependencies for this package (edit as required)
|   package.xml             # Catkin-required file which defines the package (name, dependencies on other packages, etc)  
|   requirements.txt        # List of python packages required to be installed by Pip
|   setup.py                # Installs nodes, scripts, launch files, and Python packages (src) such that other packages (and ROS) can find them
|
```

## Initial Setup

1. Create new Github repo using this as template, and clone in to `sky_ws/src`.
2. Rename `your_pkg/src/ros_python_pkg/`  to  `your_pkg/src/your_pkg/`.
3. Change the path for sky_utils in git submodules.
4. Configuration: Need to edit the following files:
    - `package.xml`      : Edit package name, description, author, etc. Add `<depend>` tags as necessary to link to other Catkin packages.
    - `CMakeLists.txt`   : Edit package name. Need to add package dependencies here as well; same ones as in `package.xml`.
    - `requirements.txt` : Edit if this package requires any Pip packages which are not available as standard ROS dependencies; delete if not.
 
At this point the package should build successfully if all dependencies are met.