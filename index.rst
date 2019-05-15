.. B2NOTEdocs documentation master file, created by
   sphinx-quickstart on Wed May 15 11:32:16 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to B2NOTEdocs's documentation!
======================================

A note in the margins of a book or a scientific paper, 
a comment on a manuscript or a reference to other related content: 
we are all using annotations to add information to existing physical documents. 
To offer a similar experience with digital content, we developed B2NOTE, 
a service that allows to associate additional information to a file in a computer-readable format based on the W3C Web Annotation standard. 
These digital annotations can then be searched to retrieve the related files and datasets using the user-defined content without changing the data records itself. 
This service has been developed within the EUDAT Common Data Infrastructure and is now part of the EOSC-Hub service portfolio.

User's Guide section contains information how to use B2NOTE service and it's UI, mainly from public deployment of the service. 

Administration Guide section contains information about installation and deployment of the B2NOTE service.

Integration Guide section contains information about how to integrate web UI widget and API with your application.


.. toctree::
   :maxdepth: 2
   :caption: User's Guide:
   
   usage/overview
   usage/searchinannotation
   usage/createannotation
   
.. toctree::
   :maxdepth: 2
   :caption: Administration Guide:
   
   admin/installation
   admin/configuration
   
.. toctree::
   :maxdepth: 2
   :caption: Integration Guide:
   
   integration/widget
   integration/api

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
