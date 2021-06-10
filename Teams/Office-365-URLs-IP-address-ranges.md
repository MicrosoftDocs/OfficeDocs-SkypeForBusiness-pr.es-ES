---
title: Microsoft 365 y Office 365 direcciones URL e intervalos de direcciones IP
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Obtenga información sobre cómo configurar correctamente Microsoft 365 o Office 365 direcciones URL e intervalos de direcciones IP y omitir el proxy de reenvío cuando sea posible para las conexiones con Microsoft Teams servicio.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094522"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="af6a2-103">Microsoft 365 y Office 365 direcciones URL e intervalos de direcciones IP</span><span class="sxs-lookup"><span data-stu-id="af6a2-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="af6a2-104">Vaya a Microsoft 365 y Office 365 direcciones URL e [intervalos](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) de direcciones IP para obtener una lista detallada y actualizada de las direcciones URL, direcciones IP, puertos y protocolos que deben configurarse correctamente para Teams.</span><span class="sxs-lookup"><span data-stu-id="af6a2-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="af6a2-105">Microsoft trata de mejorar constantemente el servicio de Microsoft 365 y Office 365, así como de agregar nuevas funcionalidades, lo que implica que las direcciones IP, las direcciones URL y los puertos pueden cambiar a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="af6a2-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="af6a2-106">Le recomendamos que [se suscriba a través de RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para recibir notificaciones cuando esta información se actualice o cambie.</span><span class="sxs-lookup"><span data-stu-id="af6a2-106">We recommend that you [subscribe via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="af6a2-107">La Teams de llamadas y reuniones se basa en la infraestructura basada en la nube de nueva generación que también usan Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="af6a2-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="af6a2-108">Estas inversiones tecnológicas incluyen servicios en la nube basados en Azure para procesamiento y señalización multimedia, códec de vídeo H.264, códec de audio SILK y Opus, resistencia de red, telemetría y diagnósticos de calidad.</span><span class="sxs-lookup"><span data-stu-id="af6a2-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="af6a2-109">Por lo tanto, hay direcciones URL e IP necesarias que pueden estar asociadas con Skype y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="af6a2-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="af6a2-110">Para todas las Microsoft 365 y Office 365 de trabajo, el método de conexión recomendado para Teams servicios es omitir el proxy de reenvío siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="af6a2-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="af6a2-111">Cuando un servidor proxy se encuentra entre un cliente y los centros de datos Office 365, es posible que los medios se forzaran a través de TCP en lugar de UDP, lo que afectaría a la calidad de los medios.</span><span class="sxs-lookup"><span data-stu-id="af6a2-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="af6a2-112">Descargue archivos PAC de proxy de ejemplo que se pueden usar para configurar la omisión del tráfico desde Administrar Microsoft 365 y [Office 365 extremos](/office365/enterprise/managing-office-365-endpoints).</span><span class="sxs-lookup"><span data-stu-id="af6a2-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="af6a2-113">Si las directivas de red y seguridad requieren que Microsoft 365 o Office 365 tráfico fluya a través de un servidor proxy, asegúrese de que los requisitos anteriores ya se cumplen antes de implementar Teams en producción.</span><span class="sxs-lookup"><span data-stu-id="af6a2-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="af6a2-114">Para obtener más información, lea [Servidores proxy para Teams o Skype Empresarial en línea.](proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="af6a2-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>