---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9ac7b7851cf5862210c7b343bc80b72b92c08e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527547"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migración de reuniones existentes y contenido de reuniones

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Cuando se mueve una cuenta de usuario de Lync Server 2010 a un servidor de Lync Server 2013, la siguiente información se mueve con esa cuenta de usuario:

  - **Reuniones ya programadas por el usuario**. Incluye el movimiento de los directorios y los datos de conferencia.

  - **Número de identificación personal (PIN) del usuario**. El PIN actual del usuario seguirá funcionando hasta que caduque o hasta que el usuario solicite un PIN nuevo.

La siguiente información de la cuenta del usuario no se pasa al nuevo servidor:

  - **Contenido de reuniones**. Para mover el contenido compartido durante una reunión como, por ejemplo, una presentación de PowerPoint, la pizarra, los datos adjuntos o de sondeos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser**.

</div>

<span> </span>

</div>

</div>

</div>

