---
title: Direcciones URL e intervalos de direcciones IP de Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Aprenda a configurar correctamente los intervalos de direcciones IP y URL de Office 365, omita el proxy de reenvío cuando esté disponible para las conexiones con el servicio de Microsoft Teams y los requisitos para las directivas de redes y seguridad.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6acf22a10d52aadb90ff6312edfa4a5de33b1a17
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235144"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="f5b5c-103">Direcciones URL e intervalos de direcciones IP de Office 365</span><span class="sxs-lookup"><span data-stu-id="f5b5c-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="f5b5c-104">Vaya a [Intervalos de direcciones IP y URL de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para ver una lista detallada y actualizada de las direcciones URL, las direcciones IP, los puertos y los protocolos que deben estar bien configurados para Teams.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="f5b5c-105">Microsoft trata de mejorar constantemente el servicio de Office 365 así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="f5b5c-106">Le recomendamos que [se suscriba a través de las redes sociales](https://go.microsoft.com/fwlink/p/?linkid=236301) para recibir notificaciones cuando esta información se cambie o se modifique.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="f5b5c-107">La experiencia de llamadas y reuniones de Teams está integrada en la infraestructura de próxima generación basada en la nube, que también usan Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="f5b5c-108">Estas inversiones en tecnología incluyen servicios en la nube basados en Azure para el procesamiento de medios y la señalización, códec de vídeo H. 264, códec de audio de seda y Opus, resistencia de red, telemetría y diagnósticos de calidad.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="f5b5c-109">Del mismo modo, algunas de las direcciones URL y direcciones IP que se requieren podrían estar asociadas con Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="f5b5c-110">En el caso de todas las cargas de trabajo de Office 365, el método de conexión con los servicios de Teams que se recomienda consiste en omitir el proxy de reenvío siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="f5b5c-111">Cuando un servidor proxy se coloca entre un cliente y los centros de datos de Office 365, es posible que se fuerce el paso de un elemento multimedia por TCP en lugar de por UDP, lo que afectaría a la calidad del medio.</span><span class="sxs-lookup"><span data-stu-id="f5b5c-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="f5b5c-112">Descargue los archivos PAC del proxy de muestra que se pueden usar para configurar la omisión de tráfico en [Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="f5b5c-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="f5b5c-113">Si las directivas de red y de seguridad requieren que el tráfico de Office 365 fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores ya se cumplen antes de implementar Teams en producción (Revise [los servidores proxy para equipos o Skype empresarial online](proxy-servers-for-skype-for-business-online.md) . para obtener instrucciones).</span><span class="sxs-lookup"><span data-stu-id="f5b5c-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
