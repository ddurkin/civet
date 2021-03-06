# Civet
A Lightweight Pipeline Framework

## Overview
Civet is a framework for developing command line analysis pipelines 
that execute through a batch system common on High Performance 
Computing (HPC) systems.  Currently only the TORQUE resource manager is 
supported, but others may be supported in the future.

A Civet pipeline is defined by an XML file that describes the files 
operated on by the pipeline (the files can be input from the user, 
produced by a step in the pipeline, or may be hard coded reference 
files) and the steps that act on the files. Each tool that may be 
invoked by the pipeline is defined by its own XML file. These tool 
definitions may be shared between pipelines, allowing multiple 
pipelines to make use of a common set of tools.

Civet operates entirely in the user space, and can be installed 
without administrator permissions. It leverages the batch system's job 
dependency features to control pipeline execution. Pipeline flow is 
fixed at submission time; conditional branching is not supported.

See the documentation in the docs subdirectory for more information 
about the framework.

## License and Copyright

Copyright 2016 The Jackson Laboratory  
  
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at  
  
http://www.apache.org/licenses/LICENSE-2.0  
  
Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or 
implied. See the License for the specific language governing 
permissions and limitations under the License.

A copy of the Apache 2.0 License is included with this software. See
the included file named `LICENSE`.

## Installation

### Requirements
Civet has been tested with several versions of Python 2.7.  It has not
been tested with Python 3, but there are potentially some 
incompatibilities. We have slowly been making the code more Python 3 
friendly and plan to officially support Python 3 in the future.

Civet uses one Python module that is not part of a standard Python 2.7
installation: `pbs_python`. This module can be obtained from 
https://oss.trac.surfsara.nl/pbs_python and must be installed before 
you can use Civet.

### Installing Civet
To install civet, you simply need a copy of the Civet source code. We 
typically clone the git repository into a directory named after the 
version we are installing: `/prefix/civet/version` and do a 
`git checkout version` in that directory.  You would then add 
`/prefix/civet/version/bin` to your PATH and 
`/prefix/civet/version/lib` to your PYTHONPATH. We use Environment
Modules (http://modules.sourceforge.net/) to setup the user's 
environment for Civet.



## Authors
Glen Beane, The Jackson Laboratory
glen.beane@jax.org

Al Simons, The Jackson Laboratory
al.simons@jax.org