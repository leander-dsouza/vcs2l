Installation
============

vcs2l can be installed through multiple package managers.
Choose the method that best fits your environment.

pip
---
The recommended way to install vcs2l is through `pip <https://pypi.org/project/vcs2l/>`_.
You can install it using the following command:

.. code-block:: bash

    pip3 install vcs2l

conda
-----
If you prefer using conda, you can install vcs2l from the `conda-forge <https://anaconda.org/conda-forge/vcs2l>`_ channel:

.. code-block:: bash

   conda install -c conda-forge vcs2l

debian
------
If you are using a Debian-based system, you can install vcs2l using ``apt``.
First, add the ROS repository to your sources list and then install the package.

`ROS 2 <https://docs.ros.org/en/kilted/Installation/Ubuntu-Install-Debs.html>`_ (**recommended**):

.. code-block:: bash

   sudo apt update && sudo apt install curl -y
   export ROS_APT_SOURCE_VERSION=$(curl -s https://api.github.com/repos/ros-infrastructure/ros-apt-source/releases/latest | grep -F "tag_name" | awk -F\" '{print $4}')
   curl -L -o /tmp/ros2-apt-source.deb "https://github.com/ros-infrastructure/ros-apt-source/releases/download/${ROS_APT_SOURCE_VERSION}/ros2-apt-source_${ROS_APT_SOURCE_VERSION}.$(. /etc/os-release && echo $VERSION_CODENAME)_all.deb" # If using Ubuntu derivates use $UBUNTU_CODENAME
   sudo dpkg -i /tmp/ros2-apt-source.deb
   sudo apt-get update

`ROS 1 <https://wiki.ros.org/noetic/Installation/Ubuntu>`_ (**EOL**):

.. code-block:: bash

   sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
   sudo apt-get install curl
   curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
   sudo apt-get update

Then, install vcs2l:

.. code-block:: bash

   sudo apt-get install python3-vcs2l

Verifying the Installation
---------------------------
After installation, you can verify that vcs2l is installed correctly by running:

.. code-block:: bash

   $ vcs
    usage: vcs <command>

    Most commands take directory arguments, recursively searching for repositories
    in these directories.  If no arguments are supplied to a command, it recurses
    on the current directory (inclusive) by default.

    The available commands are:
    branch     Show the branches
    custom     Run a custom command
    delete     Remove the directories indicated by the list of given repositories.
    diff       Show changes in the working tree
    export     Export the list of repositories
    import     Import the list of repositories
    log        Show commit logs
    pull       Bring changes from the repository into the working copy
    push       Push changes from the working copy to the repository
    remotes    Show the URL of the repository
    status     Show the working tree status
    validate   Validate the repository list file

    See 'vcs <command> --help' for more information on a specific command.
