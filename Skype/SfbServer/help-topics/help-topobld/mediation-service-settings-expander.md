---
title: Expansor de configuración del servidor de mediación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Puede especificar lo siguiente en relación con un servidor de mediación:'
ms.openlocfilehash: a6e0321ddde79a088610e9e2b1c79739c68b2b90
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684513"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="dc045-103">Expansor de configuración del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="dc045-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="dc045-104">Puede especificar lo siguiente en relación con un **servidor de mediación**:</span><span class="sxs-lookup"><span data-stu-id="dc045-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="dc045-105">Si collocating el servidor de mediación en el grupo de servidores front-end o el servidor Standard Edition, seleccione la casilla **servidor de mediación**con el que se ha habilitado.</span><span class="sxs-lookup"><span data-stu-id="dc045-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="dc045-106">Si decide no collocater el servidor de mediación, no hay ninguna configuración que se pueda definir en esta sección.</span><span class="sxs-lookup"><span data-stu-id="dc045-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="dc045-107">Si ha habilitado la collocation del servidor de mediación, debe definir el intervalo de puertos de escucha en el servidor para seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="dc045-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="dc045-108">Este puerto es 5067 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc045-108">By default, this port is 5067.</span></span> <span data-ttu-id="dc045-109">Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado.</span><span class="sxs-lookup"><span data-stu-id="dc045-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="dc045-110">Se trata de una configuración opcional; recomendamos consultar los requisitos de la puerta de enlace o los de la RTC para saber si esto es realmente necesario.</span><span class="sxs-lookup"><span data-stu-id="dc045-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="dc045-111">El valor de este puerto es 5068 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc045-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="dc045-112">Las puertas de enlace RTC se definen con el servidor de mediación de anuncios.</span><span class="sxs-lookup"><span data-stu-id="dc045-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="dc045-113">Si ya ha definido las puertas de enlace, estarán disponibles para asociarlas con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="dc045-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="dc045-114">Si tiene más de una puerta de enlace asociada con un servidor de mediación, la primera puerta de enlace asociada será la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc045-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="dc045-115">Si necesita establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="dc045-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="dc045-116">Para anular la selección de la puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="dc045-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="dc045-117">Para obtener detalles sobre la definición y configuración de la configuración del grupo de servidores front-end Enterprise Edition o del servidor Standard Edition, consulte [definir y configurar la topología](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [implementar servidores de mediación y definir pares](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="dc045-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


