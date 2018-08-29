---
title: Expansor de configuración del servidor de mediación
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Puede especificar lo siguiente en relación con un servidor de mediación:'
ms.openlocfilehash: 7a42bca81f823fd22d933dd8460cf644605d7908
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261157"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="94718-103">Expansor de configuración del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="94718-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="94718-104">Puede especificar lo siguiente en relación con un **servidor de mediación**:</span><span class="sxs-lookup"><span data-stu-id="94718-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="94718-105">Si está combinando el servidor de mediación en el grupo de servidores Front-End o el servidor Standard Edition, active la casilla de verificación **servidor de mediación combinado habilitado**.</span><span class="sxs-lookup"><span data-stu-id="94718-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="94718-106">Si decide no instalar el servidor de mediación, no hay ninguna configuración arquitectónico en esta sección.</span><span class="sxs-lookup"><span data-stu-id="94718-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="94718-107">Si ha habilitado la colocación del servidor de mediación, debe definir el intervalo de puertos de escucha en el servidor de seguridad de capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="94718-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="94718-108">Este puerto es 5067 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="94718-108">By default, this port is 5067.</span></span> <span data-ttu-id="94718-109">Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado.</span><span class="sxs-lookup"><span data-stu-id="94718-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="94718-110">Se trata de una configuración opcional; recomendamos consultar los requisitos de la puerta de enlace o los de la RTC para saber si esto es realmente necesario.</span><span class="sxs-lookup"><span data-stu-id="94718-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="94718-111">El valor de este puerto es 5068 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="94718-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="94718-112">Definir las puertas de enlace de RTC que están asociados con el servidor de mediación combinado.</span><span class="sxs-lookup"><span data-stu-id="94718-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="94718-113">Si ya se han definido las puertas de enlace, estarán disponibles para asociar con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="94718-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="94718-114">Si tiene más de una puerta de enlace asociada con un servidor de mediación, la primera puerta de enlace asociada será la puerta de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="94718-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="94718-115">Si necesita establecer como predeterminada otra puerta de enlace, seleccione la puerta de enlace correspondiente y haga clic en **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="94718-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="94718-116">Para anular la selección de la puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="94718-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="94718-117">Para obtener información detallada sobre cómo definir y configurar las opciones para el servidor Standard Edition o grupo de servidores Front-End de Enterprise Edition, consulte [definir y configurar la topología](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) y [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="94718-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


