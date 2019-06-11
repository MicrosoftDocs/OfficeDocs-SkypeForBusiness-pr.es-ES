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

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="c0aaf-102">Migración de reuniones existentes y contenido de reuniones</span><span class="sxs-lookup"><span data-stu-id="c0aaf-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0aaf-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c0aaf-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c0aaf-104">Cuando una cuenta de usuario se mueve de Lync Server 2010 a un servidor de Lync Server 2013, la siguiente información se mueve con esa cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="c0aaf-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="c0aaf-105">**Reuniones ya programadas por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="c0aaf-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="c0aaf-106">Esto incluye mover los directorios de conferencias y los datos de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c0aaf-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="c0aaf-107">**Número de identificación personal (PIN) del usuario**.</span><span class="sxs-lookup"><span data-stu-id="c0aaf-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="c0aaf-108">El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="c0aaf-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="c0aaf-109">La siguiente información de la cuenta de usuario no se mueve al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="c0aaf-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="c0aaf-110">**Contenido**de la reunión.</span><span class="sxs-lookup"><span data-stu-id="c0aaf-110">**Meeting content**.</span></span> <span data-ttu-id="c0aaf-111">Para mover el contenido compartido durante una reunión, por ejemplo, PowerPoint, whiteboard, datos adjuntos o sondeo de datos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="c0aaf-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

