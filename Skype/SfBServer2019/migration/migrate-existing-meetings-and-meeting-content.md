---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cuando una cuenta de usuario se mueve de a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874664"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="e8eb9-103">Migración de reuniones existentes y contenido de reuniones</span><span class="sxs-lookup"><span data-stu-id="e8eb9-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="e8eb9-104">Cuando una cuenta de usuario se mueve a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="e8eb9-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="e8eb9-105">**Las reuniones ya programadas por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="e8eb9-106">Esto incluye mover los directorios de conferencia y los datos de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="e8eb9-107">**Número de identificación personal (PIN) de un usuario**.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="e8eb9-108">El PIN del usuario actual sigue funcionando hasta que caduque o el usuario solicita un nuevo NIP.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="e8eb9-109">La siguiente información de cuenta de usuario no se mueve al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="e8eb9-110">**Contenido de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-110">**Meeting content**.</span></span> <span data-ttu-id="e8eb9-111">Para mover el contenido compartido durante una reunión, por ejemplo, PowerPoint, Pizarra, datos adjuntos o datos de sondeo, use el parámetro **- MoveConferenceData** como parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="e8eb9-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

