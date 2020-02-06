---
title: Quitar los servidores de archivado y supervisión heredados
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
description: Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype empresarial Server 2019, esos servidores se pueden quitar del entorno heredado siempre que todos los usuarios hayan sido eliminados de cualquier grupo heredado. Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia. El requisito clave es que se han quitado todos los usuarios de cualquier grupo heredado.
ms.openlocfilehash: 034d2ad284c0247b19e56e4cd8d751a0cf32ee69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812998"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="f4783-105">Quitar los servidores de archivado y supervisión heredados</span><span class="sxs-lookup"><span data-stu-id="f4783-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="f4783-106">Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Skype empresarial Server 2019, esos servidores se pueden quitar del entorno heredado, siempre y cuando todos los usuarios hayan sido eliminados de cualquier grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="f4783-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="f4783-107">Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia.</span><span class="sxs-lookup"><span data-stu-id="f4783-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="f4783-108">El requisito clave es que se han quitado todos los usuarios de cualquier grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="f4783-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="f4783-109">Puede mover usuarios a Skype empresarial Server 2019 siguiendo los procedimientos descritos en la [fase 4: mover usuarios de prueba a la agrupación piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f4783-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="f4783-110">Una vez que haya confirmado que todos los usuarios se han quitado del grupo restante, decommision el servidor y quite roles.</span><span class="sxs-lookup"><span data-stu-id="f4783-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="f4783-111">Un ejemplo de fecha, pero relevante es "desinstalar Microsoft Lync Server y quitar roles de servidor", que se puede descargar en [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="f4783-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

