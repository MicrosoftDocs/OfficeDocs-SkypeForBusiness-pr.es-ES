---
title: Configurar servidores de aplicaciones de confianza
TOCTitle: Configurar servidores de aplicaciones de confianza
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48274633
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar servidores de aplicaciones de confianza

 

_**Última modificación del tema:** 2014-11-05_

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el siguiente grupo de salto para que sea un grupo de servidores de Lync Server 2013. En un entorno mixto, tanto el grupo de Lync Server 2010 heredado como el grupo de Lync Server 2013 aparecen en la lista desplegable. No se admite la selección del grupo heredado.

**Seleccionar Lync Server 2013 como el siguiente salto al crear un servidor de aplicaciones de confianza**

1.  Abrir Generador de topologías.

2.  En el panel izquierdo, haga clic con el botón derecho en **Servidores de aplicaciones de confianza** y haga clic en **Nuevo grupo de aplicaciones de confianza**.

3.  Escriba el **FQDN del grupo de servidores** correspondiente al grupo de aplicaciones de confianza y seleccione si se tratará de un servidor único o de varios servidores.

4.  Después, haga clic en **Siguiente**.

5.  En la página **Seleccionar el siguiente salto**, en la lista, seleccione el grupo front-end de Lync Server 2013.

6.  Haga clic en **Finalizar**.

7.  Seleccione el nodo superior **Lync Server** y, a continuación, en el menú **Acción**, seleccione **Publicar**.
    
    Compruebe que se ha creado el **Grupo de aplicaciones de confianza** y que está asociado correctamente con el grupo de servidores front-end correcto.

