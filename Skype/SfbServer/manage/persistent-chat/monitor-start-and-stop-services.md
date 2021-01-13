---
title: Supervisar, iniciar y detener los servicios de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumen: obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814140"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="a4fbc-103">Supervisar, iniciar y detener los servicios de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a4fbc-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a4fbc-104">**Resumen:** Obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a4fbc-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a4fbc-105">Los servicios de chat persistente y los servicios de cumplimiento de chat persistente forman parte de la topología de Skype Empresarial Server y, por lo tanto, se pueden supervisar, detener e iniciar con los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4fbc-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a4fbc-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a4fbc-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a4fbc-107">Devuelve información detallada sobre los componentes de Skype Empresarial Server 2015 que se ejecutan como servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="a4fbc-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="a4fbc-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a4fbc-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a4fbc-109">Inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4fbc-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="a4fbc-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a4fbc-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a4fbc-111">Detiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="a4fbc-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="a4fbc-112">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a4fbc-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a4fbc-113">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="a4fbc-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="a4fbc-114">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="a4fbc-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="a4fbc-115">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a4fbc-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="a4fbc-116">Para obtener información detallada sobre cómo usar los cmdlets, consulte Shell de administración de [Skype Empresarial Server 2015.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="a4fbc-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

