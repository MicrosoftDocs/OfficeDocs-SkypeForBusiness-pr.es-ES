---
title: Expansor de configuración perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Para editar la configuración de un grupo de servidores perimetrales de uno o varios servidores existentes, le presentamos las secciones siguientes:'
ms.openlocfilehash: 7f202dc03d0c83c324f4dc2a75928e022a68250c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828580"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="e38a4-103">Expansor de configuración perimetral</span><span class="sxs-lookup"><span data-stu-id="e38a4-103">Edge Settings Expander</span></span>

<span data-ttu-id="e38a4-104">Para editar la configuración de un grupo de servidores perimetrales de uno o varios servidores existentes, le presentamos las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e38a4-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="e38a4-105">Configuración general</span><span class="sxs-lookup"><span data-stu-id="e38a4-105">General settings</span></span>

- <span data-ttu-id="e38a4-106">Configuración de la selección de próximo salto</span><span class="sxs-lookup"><span data-stu-id="e38a4-106">Next hop selection settings</span></span>

- <span data-ttu-id="e38a4-107">Configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e38a4-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="e38a4-108">Configuración general</span><span class="sxs-lookup"><span data-stu-id="e38a4-108">General settings</span></span>

<span data-ttu-id="e38a4-p101">Nombre de dominio completo (FQDN) del grupo de servidores internos del grupo de servidores perimetrales. Edite el FQDN del grupo de servidores para cambiar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="e38a4-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="e38a4-111">Active la casilla Habilitar federación para este grupo de servidores perimetrales **(puerto 5061)** si va a configurar la federación con un socio de confianza de Lync Server 2013, Microsoft Lync Server 2010 o Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e38a4-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="e38a4-112">Seleccione **Habilitar federación XMPP para este grupo de servidores perimetrales** para habilitar la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="e38a4-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="e38a4-113">Especifique el número de puerto para el **Puerto de replicación de configuración interna (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="e38a4-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="e38a4-114">Configuración de la selección de próximo salto</span><span class="sxs-lookup"><span data-stu-id="e38a4-114">Next hop selection settings</span></span>

<span data-ttu-id="e38a4-115">Para establecer o  modificar el grupo de servidores del próximo salto que usarán los servidores perimetrales para comunicarse con la infraestructura interna, seleccione un director, un grupo de directores, un servidor front-end o un grupo de servidores front-end en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e38a4-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="e38a4-116">Solo se seleccionarán los directores o front-ends que se hayan configurado en el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="e38a4-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="e38a4-117">Configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="e38a4-117">Edge Server configuration</span></span>

<span data-ttu-id="e38a4-118">Para editar o especificar los parámetros de la **Configuración externa** de los servidores perimetrales, primero debe determinar si utilizará direcciones IP diferentes para el acceso SIP, la conferencia web y el servicio de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e38a4-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="e38a4-p103">Si tiene previsto utilizar direcciones IP distintas para cada uno, marque la casilla de verificación **Habilitar FQDN y direcciones IP distintos para conferencia web y A/V**. Cada servicio debe tener el registro (A) DNS creado para ello.</span><span class="sxs-lookup"><span data-stu-id="e38a4-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="e38a4-p104">En cada uno de los servicios de tipo externo, especifique un nombre de dominio completo y un puerto asociado. Por ejemplo, para **Acceso SIP** puede usar sip.contoso.com con un puerto asociado de 5061.</span><span class="sxs-lookup"><span data-stu-id="e38a4-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e38a4-123">Si selecciona FQDN diferentes para cada uno de los servicios externos, cada servicio debe tener asociado un valor de puerto exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e38a4-123">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="e38a4-124">De forma predeterminada, el SIP está en el puerto 5061/TLS, el servicio perimetral de conferencia web está en el puerto 444/TLS y el servidor de conferencia A/V está en el puerto 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="e38a4-124">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="e38a4-125">Si efectúa cambios en cualquiera de estas opciones, incluido el uso de nombres de dominio completo y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="e38a4-125">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="e38a4-p106">Si decide que la organización va a usar una sola dirección IP y un solo nombre de dominio completo para los servicios externos, desmarque la casilla de verificación **Habilitar FQDN y direcciones IP diferentes para conferencia web y A/V**. A continuación, si es necesario, puede editar los valores de puerto y FQDN del grupo de servidores de **Acceso SIP**.</span><span class="sxs-lookup"><span data-stu-id="e38a4-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e38a4-128">Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQDN y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="e38a4-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="e38a4-129">Ver también</span><span class="sxs-lookup"><span data-stu-id="e38a4-129">See also</span></span>

<span data-ttu-id="e38a4-130">Para obtener más información sobre cómo definir y configurar las opciones de los servicios de servidores perimetrales, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="e38a4-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


