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
ms.openlocfilehash: 9d811a9e66f368752107020de48e5e09dd641115
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="796bd-102">Migración de reuniones existentes y contenido de reuniones</span><span class="sxs-lookup"><span data-stu-id="796bd-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="796bd-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="796bd-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="796bd-104">Cuando se mueve una cuenta de usuario de Lync Server 2010 a un servidor de Lync Server 2013, la siguiente información se mueve con esa cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="796bd-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="796bd-p101">**Reuniones ya programadas por el usuario**. Incluye el movimiento de los directorios y los datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="796bd-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="796bd-p102">**Número de identificación personal (PIN) del usuario**. El PIN actual del usuario seguirá funcionando hasta que caduque o hasta que el usuario solicite un PIN nuevo.</span><span class="sxs-lookup"><span data-stu-id="796bd-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="796bd-109">La siguiente información de la cuenta del usuario no se pasa al nuevo servidor:</span><span class="sxs-lookup"><span data-stu-id="796bd-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="796bd-p103">**Contenido de reuniones**. Para mover el contenido compartido durante una reunión como, por ejemplo, una presentación de PowerPoint, la pizarra, los datos adjuntos o de sondeos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="796bd-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

