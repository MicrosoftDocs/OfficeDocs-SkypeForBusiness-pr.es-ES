---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa0b83e2e206421300d16faf220b3fa0bb81503
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Cuando una cuenta de usuario se mueve de Lync Server 2010 a un servidor de Lync Server 2013, la siguiente información se mueve con esa cuenta de usuario:

  - **Reuniones ya programadas por el usuario**. Esto incluye mover los directorios de conferencias y los datos de la Conferencia.

  - **Número de identificación personal (PIN) del usuario**. El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.

La siguiente información de la cuenta de usuario no se mueve al nuevo servidor.

  - **Contenido**de la reunión. Para mover el contenido compartido durante una reunión, por ejemplo, PowerPoint, whiteboard, datos adjuntos o sondeo de datos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser** .

</div>

<span> </span>

</div>

</div>

</div>

