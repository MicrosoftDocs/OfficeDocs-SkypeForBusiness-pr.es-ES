---
title: Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumen: Obtenga información sobre cómo iniciar, detener y supervisar los servicios de Chat persistente de Skype para Business Server 2015.'
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991592"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="aa12f-103">Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa12f-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aa12f-104">**Resumen:** Obtenga información sobre cómo iniciar, detener y supervisar los servicios de Chat persistente de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aa12f-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="aa12f-105">Los servicios de Chat persistente y cumplimiento de Chat persistente forman parte de la Skype para la topología de servidor empresarial y puede, por tanto, se supervisan, detenido e iniciarse mediante los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa12f-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aa12f-106">Get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="aa12f-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="aa12f-107">Devuelve información detallada acerca de Skype para Business Server 2015 componentes que se ejecutan como servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="aa12f-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="aa12f-108">Start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="aa12f-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="aa12f-109">Inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="aa12f-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="aa12f-110">Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="aa12f-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="aa12f-111">Detiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="aa12f-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="aa12f-112">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aa12f-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aa12f-113">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="aa12f-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="aa12f-114">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="aa12f-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="aa12f-115">Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aa12f-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="aa12f-116">Para obtener información detallada sobre cómo usar los cmdlets, vea [Skype para Shell de administración de Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="aa12f-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

