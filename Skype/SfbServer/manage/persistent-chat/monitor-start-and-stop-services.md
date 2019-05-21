---
title: Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumen: Aprenda a iniciar, detener y supervisar los servicios de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279294"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="b25e2-103">Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b25e2-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b25e2-104">**Resumen:** Obtenga información sobre cómo iniciar, detener y supervisar los servicios de chat persistentes en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b25e2-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b25e2-105">Los servicios de chat persistente y el cumplimiento de chat persistente forman parte de la topología de servidor de Skype empresarial y, por lo tanto, se pueden supervisar, detener e iniciar con los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b25e2-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b25e2-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b25e2-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b25e2-107">Devuelve información detallada sobre los componentes de Skype empresarial Server 2015 que se ejecutan como servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="b25e2-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="b25e2-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b25e2-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b25e2-109">Inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="b25e2-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="b25e2-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="b25e2-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="b25e2-111">Detiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="b25e2-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b25e2-112">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b25e2-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b25e2-113">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="b25e2-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="b25e2-114">Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="b25e2-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="b25e2-115">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b25e2-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="b25e2-116">Para más información sobre cómo usar los cmdlets, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="b25e2-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

