---
title: Expansor de configuración perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Dispone de las siguientes secciones para editar la configuración de un servidor perimetral o un grupo de servidores perimetrales existente:'
ms.openlocfilehash: 769633001beba3f4f982507155c788b8dd4896b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910759"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="282cc-103">Expansor de configuración perimetral</span><span class="sxs-lookup"><span data-stu-id="282cc-103">Edge Settings Expander</span></span>

<span data-ttu-id="282cc-104">Dispone de las siguientes secciones para editar la configuración de un servidor perimetral o un grupo de servidores perimetrales existente:</span><span class="sxs-lookup"><span data-stu-id="282cc-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="282cc-105">Configuración general</span><span class="sxs-lookup"><span data-stu-id="282cc-105">General settings</span></span>

- <span data-ttu-id="282cc-106">Configuración de la selección de próximo salto</span><span class="sxs-lookup"><span data-stu-id="282cc-106">Next hop selection settings</span></span>

- <span data-ttu-id="282cc-107">Configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="282cc-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="282cc-108">Configuración general</span><span class="sxs-lookup"><span data-stu-id="282cc-108">General settings</span></span>

<span data-ttu-id="282cc-p101">Nombre de dominio completo (FQDN) de grupo interno del grupo de servidores perimetrales. Edite el FQDN del grupo de servidores para cambiar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="282cc-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="282cc-111">Seleccione la casilla de verificación **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** si va a configurar la federación con un Skype para server Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="282cc-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="282cc-112">Indique el número de puerto del **Puerto interno de replicación de configuración (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="282cc-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="282cc-113">Configuración de la selección de próximo salto</span><span class="sxs-lookup"><span data-stu-id="282cc-113">Next hop selection settings</span></span>

<span data-ttu-id="282cc-114">Para definir o modificar el **Grupo de servidores del próximo salto** que van a usar los servidores perimetrales para comunicarse con la infraestructura interna, seleccione un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="282cc-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="282cc-115">Sólo los directores o servidores front-end que se han configurado en el generador de topología aparecerán para la selección.</span><span class="sxs-lookup"><span data-stu-id="282cc-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="282cc-116">Configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="282cc-116">Edge Server configuration</span></span>

<span data-ttu-id="282cc-117">Para modificar o especificar los parámetros de **Configuración externa** de los servidores perimetrales, antes necesitará determinar si va a usar direcciones IP diferentes para el acceso SIP, la conferencia web y el servicio de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="282cc-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="282cc-p103">Si tiene previsto usar direcciones IP distintas para cada uno de ellos, active la casilla **Habilitar combinaciones distintas de FQDN y dirección IP para conferencia web y A/V**. Cada servicio necesita tener el registro del host DNS (A) pertinente creado para ello.</span><span class="sxs-lookup"><span data-stu-id="282cc-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="282cc-p104">En cada uno de los servicios externos, especifique un nombre de dominio completo y un puerto asociado. Por ejemplo, en **Acceso SIP** puede usar sip.contoso.com con el puerto asociado 5061.</span><span class="sxs-lookup"><span data-stu-id="282cc-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="282cc-p105">Si selecciona FQDN diferentes para cada uno de los servicios externos, cada servicio necesita tener asociado un valor de puerto exclusivo. SIP se encuentra de forma predeterminada en el puerto 5061/TLS, el servicio perimetral de conferencia web se encuentra en el puerto 444/TLS y el servidor de conferencia de audio y vídeo, en el puerto 443/TLS. Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQFN y direcciones IP o puertos diferentes, necesitará actualizar todos los demás servicios que dependan de los valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="282cc-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="282cc-p106">Si decide que la organización va a usar una sola dirección IP y un solo nombre de dominio completo para los servicios externos, desactive la casilla **Habilitar combinaciones distintas de FQDN y dirección IP para conferencia web y A/V**. Luego, puede editar los valores del puerto y el nombre de dominio completo de **Acceso SIP** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="282cc-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="282cc-127">Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQDN y direcciones IP o puertos diferentes, necesita actualizar todos los demás servicios que dependan de los valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="282cc-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="282cc-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="282cc-128">See also</span></span>

<span data-ttu-id="282cc-129">Para más detalles sobre cómo definir y configurar las opciones de los servicios perimetrales, mire [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="282cc-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


