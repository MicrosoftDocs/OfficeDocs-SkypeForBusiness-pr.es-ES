---
title: Expansor de configuración del servidor de mediación
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Para el servidor de mediación, puede especificar lo siguiente:'
ms.openlocfilehash: e322b2ffd383c2bd0170852a6fec6c3122251700
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="ba56b-103">Expansor de configuración del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ba56b-103">Mediation Service Settings Expander</span></span>
 
<span data-ttu-id="ba56b-104">Puede especificar lo siguiente en relación con un **servidor de mediación**:</span><span class="sxs-lookup"><span data-stu-id="ba56b-104">For **Mediation Server**, you can specify the following:</span></span>
  
<span data-ttu-id="ba56b-105">Si son colocación del servidor de mediación en el grupo de servidores frontales o el servidor Standard Edition, active la casilla de verificación **habilitado servidor de mediación ubicados**.</span><span class="sxs-lookup"><span data-stu-id="ba56b-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="ba56b-106">Si no decide colocar el servidor de mediación, no hay ninguna configuración definible en esta sección.</span><span class="sxs-lookup"><span data-stu-id="ba56b-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span> 
  
<span data-ttu-id="ba56b-107">Si ha habilitado la colocación del servidor de mediación, debe definir el intervalo de puertos de escucha en el servidor de seguridad de capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="ba56b-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="ba56b-108">Este puerto es 5067 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ba56b-108">By default, this port is 5067.</span></span> <span data-ttu-id="ba56b-109">Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado.</span><span class="sxs-lookup"><span data-stu-id="ba56b-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="ba56b-110">Se trata de una configuración opcional; recomendamos consultar los requisitos de la puerta de enlace o los de la RTC para saber si esto es realmente necesario.</span><span class="sxs-lookup"><span data-stu-id="ba56b-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="ba56b-111">El valor de este puerto es 5068 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ba56b-111">By default, the TCP port value is 5068.</span></span>
  
<span data-ttu-id="ba56b-112">Definir puertas de enlace PSTN que están asociados con el servidor de mediación colocadas.</span><span class="sxs-lookup"><span data-stu-id="ba56b-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="ba56b-113">Si ya ha definido las puertas de enlace, estarán disponibles para asociar con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ba56b-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> 
  
<span data-ttu-id="ba56b-114">Si tiene más de una puerta de enlace asociada con un servidor de mediación, la primera puerta de enlace asociada será la puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ba56b-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="ba56b-115">Si necesita establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ba56b-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="ba56b-116">Para anular la selección de la puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ba56b-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>
  
<span data-ttu-id="ba56b-117">Para obtener más información sobre cómo definir y configurar las opciones para el grupo de servidores Enterprise Edition Front-End o un servidor Standard Edition, consulte [definición y configuración de la topología](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [implementar servidores de mediación y definir pares](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="ba56b-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  

