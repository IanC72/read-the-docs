================================
Using NVIDIA Jetpack and PyTorch
================================

This page is targeted towards using NVIDIA JetPack functions and PyTorch with the Jetson boards in the testbed.

NVIDIA JetPack
==============

What functions does it have for Jetsons?
----------------------------------------

- point to existing docs
- Share info on general JetPack tools

Using PyTorch with Jetson
=========================

Start by opening a new shell instance on https://rg-ood.crnch.gatech.edu/ under the clusters dropdown menu.

Once in the shell, log into the cluster and request a new allocation on rudi2 (this example is an allocation of 1 hour):
      
.. code::

    salloc -t 1:00:00 -p rg-neuro -w rudi2

Once the allocation is accepted, create a new python virtual environment and activate it:

.. code::

    $ mkdir myproject
    $ python -m venv myproject
    $ source myproject/bin/activate

Now we need to install PyTorch in the virtual environment:


- Share how to do this with Python venv on rudi1/2
- Talk about the AI Hello World example
