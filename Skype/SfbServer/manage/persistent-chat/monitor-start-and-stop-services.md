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
description: 'Resumen: Conozca cómo iniciar, detener y supervisar los servicios de Chat persistentes en Skype para Business Server 2015.'
ms.openlocfilehash: 47cd6daeca664f7775455818a5690232e92d4c36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="cc80f-103">Supervisar, iniciar y detener los servicios del chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc80f-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cc80f-104">**Resumen:** Aprenda a iniciar, detener y supervisar los servicios de Chat persistentes en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cc80f-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cc80f-105">Los servicios de Chat persistentes y servicios de cumplimiento de Chat persistentes forman parte de la Skype para la topología de servidores de negocios y pueden, por tanto, se supervisan, detenidos e iniciados mediante los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="cc80f-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cc80f-106">Get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="cc80f-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="cc80f-107">Devuelve información detallada acerca de Skype para Business Server 2015 componentes que se ejecutan como servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="cc80f-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="cc80f-108">inicio CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="cc80f-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="cc80f-109">Inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="cc80f-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="cc80f-110">parada CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="cc80f-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="cc80f-111">Detiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="cc80f-111">Stops the service.</span></span>  <br/> |
   
<span data-ttu-id="cc80f-112">Para obtener información detallada acerca de cómo usar los cmdlets, vea [Skype para el Shell de administración de negocio servidor 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="cc80f-112">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

