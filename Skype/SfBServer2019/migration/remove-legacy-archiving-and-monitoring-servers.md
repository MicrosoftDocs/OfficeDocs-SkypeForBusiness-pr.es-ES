---
title: Quitar archivado heredado y supervisión de servidores
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si su implementación heredada contenía un servidor de archivado o en un servidor de supervisión, después de migrar a Skype para Business Server 2019, esos servidores se pueden quitar del entorno heredado siempre que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante.
ms.openlocfilehash: 4de6d9db5538864646f978e9fc33a79b39d4c2a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028617"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="6d0bf-105">Quitar archivado heredado y supervisión de servidores</span><span class="sxs-lookup"><span data-stu-id="6d0bf-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="6d0bf-106">Si su implementación heredada contenía un servidor de archivado o en un servidor de supervisión, después de migrar a Skype para Business Server 2019, esos servidores se puede quitarse del entorno heredado, proporcionado que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante.</span><span class="sxs-lookup"><span data-stu-id="6d0bf-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="6d0bf-107">Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia.</span><span class="sxs-lookup"><span data-stu-id="6d0bf-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="6d0bf-108">El requisito clave es que se han quitado todos los usuarios de cualquier grupo de servidores heredado restante.</span><span class="sxs-lookup"><span data-stu-id="6d0bf-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="6d0bf-109">Puede mover los usuarios a Skype para Business Server 2019 siguiendo los procedimientos descritos en [fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="6d0bf-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="6d0bf-110">Una vez que se ha confirmado que se han quitado todos los usuarios de cualquier de los grupos restantes, decommision el servidor y quitar roles.</span><span class="sxs-lookup"><span data-stu-id="6d0bf-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="6d0bf-111">Una fecha, pero relevantes, el ejemplo es "Desinstalar Microsoft Lync Server y quitar Roles de servidor," que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="6d0bf-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

