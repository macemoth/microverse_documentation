Installation (Entwickler)
=========================
Die folgende Installation richtet sich an Entwickler, die an der Weiterentwicklung von *Microverse* interessiert sind. Eine Benutzeranleitung ist unter :doc:`userdoc` gegeben.

Voraussetzungen
---------------
Für die Entwicklung an *Microverse* ist *Microsoft Windows 10* (wegen besserer Unterstützung von *Visual Studio*) empfohlen.

===========================    ======================  ============================================
Software                       Version                 Benutzt für
---------------------------    ----------------------  --------------------------------------------
Blender_                       2.82.0 <                Modellierung von Spielelementen (Viren etc.)
`Unity Hub`_                   2.1.0  =                Kernumgebung für Entwicklung von Microverse
`Visual Studio Community`_     16.4 <                  Bearbeiten von C#-Skripts
===========================    ======================  ============================================


.. _Blender: https://www.blender.org/download/
.. _`Unity Hub`: https://public-cdn.cloud.unity3d.com/hub/prod/UnityHubSetup.exe
.. _`Visual Studio Community`: https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=16


Code
----
*Microverse* ist auf einem eigenen GitLab_-Server gehostet. Der Code kann mit folgendem Befehl geklont werden:

``git clone https://microverse.sns.network/microverse/microverse``

Branches
~~~~~~~~
Grundsätzlich dürfen keine *Commits* direkt auf den *master*-Branch erfolgen.

- Bei kleinen Änderungen, die **keinen** Einfluss auf andere Bestandteile hat, kann direkt der *develop*-Branch verwendet werden
- Bei grösseren Änderungen sollte ein eigener Branch erstellt werden. Nach Fertigstellung der Änderungen kann ein *Pull-Request* in den *develop*-Branch getätigt werden.

.. _GitLab: https://microverse.sns.network
