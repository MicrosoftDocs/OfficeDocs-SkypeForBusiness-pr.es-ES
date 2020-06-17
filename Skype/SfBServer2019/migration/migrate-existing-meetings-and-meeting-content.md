---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cuando una cuenta de usuario se mueve desde a un servidor de Skype empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752692"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="383d3-103">Migración de reuniones existentes y contenido de reuniones</span><span class="sxs-lookup"><span data-stu-id="383d3-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="383d3-104">Cuando una cuenta de usuario se mueve a un servidor de Skype empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="383d3-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="383d3-105">**Reuniones ya programadas por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="383d3-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="383d3-106">Incluye el movimiento de los directorios y los datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="383d3-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="383d3-107">**Número de identificación personal (PIN) del usuario**.</span><span class="sxs-lookup"><span data-stu-id="383d3-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="383d3-108">El PIN actual del usuario sigue funcionando hasta que expira o cuando el usuario solicita un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="383d3-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="383d3-109">La siguiente información de la cuenta del usuario no se pasa al nuevo servidor:</span><span class="sxs-lookup"><span data-stu-id="383d3-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="383d3-110">**Contenido de reuniones**.</span><span class="sxs-lookup"><span data-stu-id="383d3-110">**Meeting content**.</span></span> <span data-ttu-id="383d3-111">Para mover el contenido compartido durante una reunión, como PowerPoint, la pizarra, los datos adjuntos o los datos de sondeo, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="383d3-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

