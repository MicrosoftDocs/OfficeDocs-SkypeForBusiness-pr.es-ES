---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849976"
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

