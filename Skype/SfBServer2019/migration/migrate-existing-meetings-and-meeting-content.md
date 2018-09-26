---
title: Migrar reuniones existentes y contenido de la reunión
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cuando una cuenta de usuario se mueve de a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:'
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030374"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="2d447-103">Migrar reuniones existentes y contenido de la reunión</span><span class="sxs-lookup"><span data-stu-id="2d447-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="2d447-104">Cuando una cuenta de usuario se mueve a un Skype para Business Server 2019 server, se mueve la información siguiente con esa cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="2d447-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="2d447-105">**Las reuniones ya programadas por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="2d447-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="2d447-106">Esto incluye mover los directorios de conferencia y los datos de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="2d447-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="2d447-107">**Número de identificación personal (PIN) de un usuario**.</span><span class="sxs-lookup"><span data-stu-id="2d447-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="2d447-108">El PIN del usuario actual sigue funcionando hasta que caduque o el usuario solicita un nuevo NIP.</span><span class="sxs-lookup"><span data-stu-id="2d447-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="2d447-109">La siguiente información de cuenta de usuario no se mueve al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="2d447-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="2d447-110">**Contenido de la reunión**.</span><span class="sxs-lookup"><span data-stu-id="2d447-110">**Meeting content**.</span></span> <span data-ttu-id="2d447-111">Para mover el contenido compartido durante una reunión, por ejemplo, PowerPoint, Pizarra, datos adjuntos o datos de sondeo, use el parámetro **- MoveConferenceData** como parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="2d447-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

