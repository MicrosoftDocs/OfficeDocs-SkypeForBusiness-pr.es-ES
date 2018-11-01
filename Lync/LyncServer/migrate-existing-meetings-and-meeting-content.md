---
title: Migrar las reuniones y el contenido de reuniones existentes
TOCTitle: Migrar las reuniones y el contenido de reuniones existentes
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49889026
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar las reuniones y el contenido de reuniones existentes

 

_**Última modificación del tema:** 2013-02-22_

Cuando se mueve una cuenta de usuario de Lync Server 2010 a un servidor Lync Server 2013, se mueve la información siguiente con la cuenta de usuario:

  - **Reuniones ya programadas por el usuario**. Incluye el movimiento de los directorios y los datos de conferencia.

  - **Número de identificación personal (PIN) del usuario**. El PIN actual del usuario seguirá funcionando hasta que caduque o hasta que el usuario solicite un PIN nuevo.

La siguiente información de la cuenta del usuario no se pasa al nuevo servidor:

  - **Contenido de reuniones**. Para mover el contenido compartido durante una reunión como, por ejemplo, una presentación de PowerPoint, la pizarra, los datos adjuntos o de sondeos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser**.

