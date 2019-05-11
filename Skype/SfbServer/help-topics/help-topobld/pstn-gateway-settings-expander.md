---
title: Expansor de configuración de puerta de enlace RTC
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Modifique los siguientes campos para editar o modificar la configuración de una puerta de enlace de la red telefónica conmutada (RTC):'
ms.openlocfilehash: ae9afbdd69bd719ea42064d23923d3737683d85c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910542"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="360fb-103">Expansor de configuración de puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="360fb-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="360fb-104">Modifique los siguientes campos para editar o modificar la configuración de una puerta de enlace de la red telefónica conmutada (RTC):</span><span class="sxs-lookup"><span data-stu-id="360fb-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="360fb-105">El nombre de dominio completo o la dirección IP de la puerta de enlace es una entrada necesaria, que define el **Nombre de dominio completo (FQDN)** de la puerta de enlace de RTC según un registro de host (A) del sistema de nombres de dominio (DNS), una entrada de archivo de hosts estático, o bien la dirección IP de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="360fb-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="360fb-p101">El protocolo de transporte de SIP puede ser el Protocolo de control de transmisión (TCP) o la Seguridad de la capa de transporte (TLS). TLS es el valor predeterminado. Consulte la documentación del proveedor de la puerta de enlace para obtener información sobre la compatibilidad de la puerta de enlace. El valor predeterminado es TLS; si la puerta de enlace admite TLS, en principio es la opción más segura.</span><span class="sxs-lookup"><span data-stu-id="360fb-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="360fb-110">Seleccione si desea habilitar IPv4 e IPv6 para la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="360fb-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="360fb-111">La **dirección IP de medios alternativa** es una definición para el servidor de mediación para los que la puerta de enlace RTC implementada tiene una dirección IP diferente para el tráfico de medios que la dirección IP predeterminado configurado, que normalmente está dedicado para el tráfico SIP.</span><span class="sxs-lookup"><span data-stu-id="360fb-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="360fb-112">Si este parámetro se define, la puerta de enlace RTC admite una ruta de acceso o una interfaz de red distintas para el medio.</span><span class="sxs-lookup"><span data-stu-id="360fb-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="360fb-113">Si esta dirección se deja en blanco, la puerta de enlace RTC no admitirá la ruta de acceso alternativa para el medio.</span><span class="sxs-lookup"><span data-stu-id="360fb-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

