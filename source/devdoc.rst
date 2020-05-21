Informationen für Entwickler
============================
Diese Informationen richten sich an Entwickler, die an der Weiterentwicklung von *Microverse* interessiert sind. Eine Benutzeranleitung ist unter :doc:`userdoc` gegeben.

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

Testen
------
Für alle Tests wird das NUnit_ Framework verwendet und müssen über den TestRunner von Unity ausgeführt werden. Es wird zwischen zwei Arten von Tests unterschieden:

- *EditorMode*-Tests: Hier werden Tests ausgeführt, als wäre das Spiel im normalen Betrieb. Diese Tests werden für UI-Elemente verwendet
- *PlayMode*-Tests: Hier werden Tests einzelner Komponenten in einer "leeren" Spielwelt ausgeführt. Diese Tests eigenen sich für Domänenlogik, z.B. Controller.

Für die Unterscheidung zwischen UI und Domäne, siehe :ref:`Architektur`.

Die CodeCoverage wird mit einem AddOn ermittelt, welches in der Beta-Version ist, deshalb muss bei der Installation explizit nach AddOns in der Beta-Version gesucht werden.

Typische Probleme Testen
~~~~~~~~~~~~~~~~~~~~~~~~
Im *EditorMode* sind einige Probleme bekannt, die hier aufgelistet sind:

| **Problem**: ``start()`` und ``update()``-Methoden von *MonoBehaviour*-Klassen werden nicht aufgerufen.
| **Lösung**: Benötigte Methoden *public* setzen und selbst aufgerufen

| **Problem**: Auf nächstes Frame warten
| **Lösung**: ``yield return null`` aufgerufen

| **Problem**: ``destroy`` funktioniert in Tests nicht
| **Lösung**: Momentan keine Lösung von Unity bereit gestellt

.. _NUnit: https://nunit.org/

Architektur
-----------
