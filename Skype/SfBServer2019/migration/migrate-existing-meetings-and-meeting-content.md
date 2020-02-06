---
title: Migración de reuniones existentes y contenido de reuniones
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Cuando una cuenta de usuario pasa de un servidor de Skype empresarial Server 2019, la siguiente información se mueve con esa cuenta de usuario:'
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813478"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="67c8c-103">Migración de reuniones existentes y contenido de reuniones</span><span class="sxs-lookup"><span data-stu-id="67c8c-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="67c8c-104">Cuando se mueve una cuenta de usuario a un servidor de Skype empresarial Server 2019, se mueve la siguiente información con esa cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="67c8c-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="67c8c-105">**Reuniones ya programadas por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="67c8c-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="67c8c-106">Esto incluye mover los directorios de conferencias y los datos de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="67c8c-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="67c8c-107">**Número de identificación personal (PIN) del usuario**.</span><span class="sxs-lookup"><span data-stu-id="67c8c-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="67c8c-108">El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="67c8c-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="67c8c-109">La siguiente información de la cuenta de usuario no se mueve al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="67c8c-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="67c8c-110">**Contenido**de la reunión.</span><span class="sxs-lookup"><span data-stu-id="67c8c-110">**Meeting content**.</span></span> <span data-ttu-id="67c8c-111">Para mover el contenido compartido durante una reunión como, por ejemplo, PowerPoint, pizarra, datos adjuntos o sondeo de datos, use el parámetro **-MoveConferenceData** como parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="67c8c-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

