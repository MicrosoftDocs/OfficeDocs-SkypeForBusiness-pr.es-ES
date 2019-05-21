---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Cuando una cuenta de usuario pasa de un servidor de Skype empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:'
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288603"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="e3556-103">Migración de reuniones existentes y contenido de reuniones</span><span class="sxs-lookup"><span data-stu-id="e3556-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="e3556-104">Cuando se mueve una cuenta de usuario a un servidor de Skype empresarial Server 2019, se mueve la siguiente información con esa cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="e3556-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="e3556-105">**Reuniones ya programadas por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="e3556-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="e3556-106">Esto incluye mover los directorios de conferencias y los datos de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="e3556-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="e3556-107">**Número de identificación personal (PIN) del usuario**.</span><span class="sxs-lookup"><span data-stu-id="e3556-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="e3556-108">El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="e3556-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="e3556-109">La siguiente información de la cuenta de usuario no se mueve al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="e3556-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="e3556-110">**Contenido**de la reunión.</span><span class="sxs-lookup"><span data-stu-id="e3556-110">**Meeting content**.</span></span> <span data-ttu-id="e3556-111">Para mover el contenido compartido durante una reunión como, por ejemplo, PowerPoint, pizarra, datos adjuntos o sondeo de datos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="e3556-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

