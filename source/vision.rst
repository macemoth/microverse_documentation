Vision
======

Context
--------
*Microverse* is a desktop 3D game, situated in microscopic game world. Game elements are inspired from Microbiology and Chemistry (e.g. molecules, microorganisms, proteins). The player navigates a Nanobot_. through a human body in order to protect it from computer-minded hostile viruses and bacteria.

The game is intended to be educational, tackling a current problem: STEM students etc. are often drawn to technology or finance industry after their graduation since these jobs are financially more benefitial. However, these people are missing in research areas, where there are pressing (and potentially lucrative) problems to be solved, as stated for examble by MfA_.

.. _Nanobot: https://en.wikipedia.org/wiki/Nanorobotics
.. _MfA: https://www.mathforamerica.org/about

Objectives and functional overview
----------------------------------
A selection of the most important functions of *Microverse*' are:

- Navigating a Nanobot through a human body representing map
- Competing missions in order to protect the human host (by fighting viruses and bacteria, for instance)
- Improve the Nanobot's abilities by crafting new items
- Collect items and carry out research to create items
- Learn fundamental topics about Microbiology and Chemistry throughout the game

For an exhaustive functions list, please refer to the `Product Backlog`_.

.. _`Product Backlog`: https://teams.microsoft.com/l/team/19%3a1f5dee47520740e7916b948ebdc7d2d8%40thread.tacv2/conversations?groupId=88f8a2ab-9835-4f98-b163-92186ae0632d&tenantId=5d1a9f9d-201f-4a10-b983-451cf65cbc1e

Quality Attributes and non-functional requirements
---------------------------------------------------

    *If the implementation is hard to explain, it's a bad idea.*
    - Zen of Python

For non-functional requirements, *Microverse* is oriented around IBM's FURPS_+. That is, *design*, *implementation*, *interface* and *physical* requirements are also regarded in addition to the common FURPS requirements. It should however be noted that during the development stage, *Microverse* emphasizes the introduction of new features. The non-functional requirements may therefore (and by considering Pareto's Principle) not be on a production-ready level.

Usability
~~~~~~~~~
Usability shall be achieved by creating a intuitive and clean interface. A player shall be able to understand the ~90% of the UIs functions within 30 minutes of playing. If necessary, the tutorial level introduces him to the UI's functions.

*Micoverse* is also only available in English language, as an international audience is targeted. For physical quantities, `SI base units`_ are used. For date, time and other information dependent upon region, `Swiss High German`_ locale (de_CH) is used.

*Microverse* is primarily availabe for the *Microsoft Windows* platform. Versions for *GNU / Linux* and *Apple MacOS* may be published at a later point in time.

Reliability
~~~~~~~~~~~
On computers meeting the `Unity system requirements`_ *Microverse* should be played for 30 minutes without application crash. 

Performance
~~~~~~~~~~~
Computers meeting the `Unity system requirements` should be able to display *Microverse* without significant lag. This requirements may however be violated if the necessary improvement would take more than 20% of the underlying tasks' time.

Supportability
~~~~~~~~~~~~~~
Supportability is concerned in respect to maintainability and adaptability: *Microverse* features a documentation_ that supports understanding the software's architecture and principles. Also, adequate architecture and common patterns are chosen to increase recognition. Furthermore, the code is held as easy as possible and commented well. This way, changes can be embraced and implemented efficiently.

Design requirements
~~~~~~~~~~~~~~~~~~~
Design requirements are given by two constraints: 1. To rapidly integrate 3D- and game capabilities, the Unity Framework is used and 2. any persistency is implemented by the use of configuration files or similar. There should no database be necessary.

Implementation requirements
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Implementation requirements are given by Unity's constraint of using C# as programming language.

Interface requirements
~~~~~~~~~~~~~~~~~~~~~~
Interface requirements are described under `External Interfaces`_

Physical requirements
~~~~~~~~~~~~~~~~~~~~~~
Physical requirements may be given by meeting the requirements listed in *Reliability*.

.. _FURPS: https://www.ibm.com/developerworks/rational/library/4706.html
.. _`Unity system requirements`: https://docs.unity3d.com/Manual/system-requirements.html
.. _documentation: https://docs.microverse.sns.network
.. _PDB: https://www.rcsb.org/
.. _VIPER: http://dante.scripps.edu/
.. _`SI base units`: https://www.nist.gov/pml/weights-and-measures/metric-si/si-units
.. _`Swiss High German`: http://www.localeplanet.com/icu/de-CH/index.html

Constraints
-----------
Following a list of *Microverse*'s known constraints:

1. No network- or multiplayer mode
2. Closeness to reality: The concepts and elements displayed in *Microverse* cannot perfectly represent reality (e.g. size relationships, Nanobot, procedures to fight viruses and bacteria)
3. There is no score mechanism intended for the first release
4. Any constraints given by `Quality Attributes and non-functional requirements`_

Principles
----------

Continuous Integration
~~~~~~~~~~~~~~~~~~~~~~
*Unit*, *integration* and partially *acceptance* testing of *Microverse* is integrated into the CI infrastructure using a GitLab server. Code contributions across various Git branches are built on the GitLab server and tests are executed. This procedure ensures better overall code quality and allows only proven code to be integrated into *Microverses* code base.

If *Microverse* should comprise more security-related code, use of a *SonarQube_ * instance is considered. *SonarQube* carries out static code analysis in order to detect security issues or code smells.

.. _SonarQube: https://www.sonarqube.org/

Persistency
~~~~~~~~~~~~
The game state, (i.e. player's progress or crafted items) is stored locally as one or multiple text files. The exact methods to access these files is yet to be determined, suiting the platform's needs and following it's best practices.

External Interfaces
-------------------
External interfaces are given by the Microbiology and Chemistry theme surrounding the game. Interfaces are e.g. molecule or virus data which is acquired by databases such as PDB_ or VIPER_. Since there is no need for a real-time pipeline, the conversion of this data is not a part of *Microverse* itself, but of development. It is primarily handled by the Blender_ Software and secondarily by various Molecular Graphics tools.

.. _Blender: https://www.blender.org/

Decision Log
-------------
=========     ======================  ======================================================
Sprint        Decision                Motivation
---------     ----------------------  ------------------------------------------------------
Prep.         Use of Unity Framework  Need for a comprehensive 3D and game framework
Sprint 0      Use of GitLab for CI    Missing capabilities for Unity with existing solutions
=========     ======================  ======================================================