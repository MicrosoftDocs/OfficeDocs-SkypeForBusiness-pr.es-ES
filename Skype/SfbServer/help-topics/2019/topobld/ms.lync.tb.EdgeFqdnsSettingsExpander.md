---
title: Expansor de configuración de FQDN del servidor perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar o especificar la configuración externa para los servidores perimetrales, primero debe determinar si usará direcciones IP independientes para el acceso al Protocolo de inicio de sesión (SIP), el servicio perimetral de conferencia web y el servicio perimetral de audio y vídeo.
ms.openlocfilehash: 11b8ea534a332e756e8effc89fcefcf4a3197832
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822580"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="0ce56-103">Expansor de configuración de FQDN del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="0ce56-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="0ce56-104">Para editar  o especificar la configuración externa para los servidores perimetrales, primero debe determinar si usará direcciones IP independientes para el acceso al Protocolo de inicio de sesión (SIP), el servicio perimetral de conferencia web y el servicio perimetral de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="0ce56-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="0ce56-p101">Si tiene previsto usar direcciones IP diferentes para cada uno, seleccione la casilla **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V**. Cada servicio debe tener su propio registro host (A) de DNS creado para ello.</span><span class="sxs-lookup"><span data-stu-id="0ce56-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="0ce56-p102">En cada uno de los servicios de tipo externo, especifique un nombre de dominio completo y un puerto asociado. Por ejemplo, para **Acceso SIP**, puede usar sip.contoso.com con un puerto asociado de 5061.</span><span class="sxs-lookup"><span data-stu-id="0ce56-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ce56-p103">Si selecciona nombres de dominio completos diferentes para cada uno de los servicios externos, cada servicio debe tener asociado un valor de puerto exclusivo. De forma predeterminada, SIP se encuentra en el puerto 5601/TLS, el servicio perimetral de conferencia web se encuentra en el puerto 444/TLS y el servidor perimetral de conferencia de audio y vídeo se encuentra en el puerto 443/TLS. Si efectúa cambios en cualquiera de estas opciones, incluido el uso de nombres de dominio completo y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="0ce56-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="0ce56-p104">Si decide que la organización va a usar una sola dirección IP y un solo nombre de dominio completo para los servicios externos, desactive la casilla **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V**. A continuación, puede editar los valores del puerto y el nombre de dominio completo de **Acceso SIP** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0ce56-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ce56-114">Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQDN y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente.</span><span class="sxs-lookup"><span data-stu-id="0ce56-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="0ce56-115">Para obtener más información sobre cómo definir y configurar las opciones de los servicios perimetrales, consulte [Definir la topología perimetral.](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ce56-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


