---
title: Configurar servidores de aplicaciones de confianza
TOCTitle: Configurar servidores de aplicaciones de confianza
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48275128
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar servidores de aplicaciones de confianza

 

_**Última modificación del tema:** 2012-10-04_

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza después de combinar la topología de Office Communications Server heredada con Lync Server 2013, y define un nuevo servidor de aplicaciones de confianza mediante el Generador de topologías, debe establecer que el siguiente grupo de salto sea un grupo de Lync Server 2013. En un entorno combinado, tanto el grupo de Office Communications Server heredado como el grupo de Lync Server 2013 aparecen en la lista desplegable. *No* se admite la selección del grupo heredado.

## Para seleccionar Lync Server 2013 como el siguiente salto al crear un servidor de aplicaciones de confianza

1.  Abrir una topología existente en el Generador de topologías

2.  En el panel izquierdo, haga clic con el botón derecho en **Servidores de aplicaciones de confianza** y haga clic en **Nuevo grupo de aplicaciones de confianza**.

3.  Introduzca el **FQDN del grupo de servidores** del grupo de aplicaciones de confianza y seleccione si será una implementación de un solo servidor o de varios servidores.

4.  Después, haga clic en **Siguiente**.

5.  En la página **Seleccionar el siguiente salto**, en la lista, seleccione el grupo front-end de Lync Server 2013.
    
    ![Cuadro de diálogo Definir nuevo grupo de servidores de aplicaciones de confianza](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Cuadro de diálogo Definir nuevo grupo de servidores de aplicaciones de confianza")  

6.  Haga clic en **Finalizar**.

7.  Seleccione el nodo superior **Lync Server** y en el panel **Acciones**, seleccione **Publicar**.

8.  El **Grupo de aplicaciones de confianza** se creó correctamente y está asociado con el grupo de front-end correcto.

