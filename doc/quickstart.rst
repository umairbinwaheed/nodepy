==============================
Quick Start Guide
==============================

.. .. contents::

Obtaining NodePy
================

The current development version of NodePy can be obtained via Mercurial::
    
    hg clone http://bitbucket.org/ketch/nodepy

If you don't have mercurial, you can download it from 
http://mercurial.selenic.com/downloads/.

Alternatively, the last release version of NodePy can be downloaded 
from http://web.kaust.edu.sa/faculty/davidketcheson/Software.html.

Installing NodePy
====================

After downloading, simply add the directory
containing the nodepy directory to your Python path.  For instance, if
your nodepy directory is */user/home/python/nodepy*, the appropriate
C shell command is::

    $ setenv PYTHONPATH 'user/home/python'

You will probably want to add this command to your :file:`.cshrc` file to
avoid retyping it.

NodePy Documentation
====================

NodePy documentation can be found at 
http://web.kaust.edu.sa/faculty/davidketcheson/nodepy

The documentation is also included in the nodepy/doc directory, and can
be built from your local install.  However, you will need to have Sphinx
and JsMath installed on your system for this.

Examples
====================

NodePy comes with some canned examples that can be run to confirm
your installation and to demonstrate capabilities of NodePy.
These can be found in the directory nodepy/examples.  
Additional examples can be found in the `User Guide <userguide.html>`_ .
