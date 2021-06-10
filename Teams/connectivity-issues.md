---
title: Solucionar problemas de conectividad con Teams cliente
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a resolver problemas de conectividad con el cliente de Microsoft Teams, ocasionadas principalmente por el firewall o la conexión del proxy.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9ef787a5e103649c1526fab321cc8a9a088254c
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856169"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="12ade-103">Solucionar problemas de conectividad con el cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12ade-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>

<span data-ttu-id="12ade-104">La mayoría de los problemas detectados con Microsoft Teams cliente se pueden rastrear a la conectividad de firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="12ade-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="12ade-105">Comprobar que las direcciones URL, direcciones IP y puertos necesarios se abren en el firewall o proxy minimizará la solución de problemas innecesaria.</span><span class="sxs-lookup"><span data-stu-id="12ade-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="12ade-106">Para obtener información específica sobre las direcciones URL e IP necesarias para Microsoft Teams, consulte el artículo de soporte técnico Microsoft 365 direcciones IP y url de Office 365 y direcciones [IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="12ade-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="12ade-107">Los escenarios siguientes requieren que se abran direcciones URL y puertos específicos en el firewall.</span><span class="sxs-lookup"><span data-stu-id="12ade-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="12ade-108">Autenticación</span><span class="sxs-lookup"><span data-stu-id="12ade-108">Authentication</span></span>

- <span data-ttu-id="12ade-109">Conectividad de cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12ade-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="12ade-110">Colaboración</span><span class="sxs-lookup"><span data-stu-id="12ade-110">Collaboration</span></span>

- <span data-ttu-id="12ade-111">Elementos multimedia</span><span class="sxs-lookup"><span data-stu-id="12ade-111">Media</span></span>

- <span data-ttu-id="12ade-112">Servicios compartidos</span><span class="sxs-lookup"><span data-stu-id="12ade-112">Shared Services</span></span>

- <span data-ttu-id="12ade-113">Integración de terceros</span><span class="sxs-lookup"><span data-stu-id="12ade-113">Third Party Integration</span></span>

- <span data-ttu-id="12ade-114">Interoperabilidad de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="12ade-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="12ade-115">Interoperabilidad del cliente de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="12ade-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="12ade-116">Cuando Teams sin conexión o en condiciones de ancho de banda bajos</span><span class="sxs-lookup"><span data-stu-id="12ade-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="12ade-117">La buena noticia es que Teams se sigue ejecutando incluso cuando está sin conexión o se está ejecutando en condiciones de ancho de banda bajos.</span><span class="sxs-lookup"><span data-stu-id="12ade-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="12ade-118">Teams guarda todos los mensajes no enviados para chats existentes (hasta 24 horas) y los envía tan pronto como vuelva a estar en línea.</span><span class="sxs-lookup"><span data-stu-id="12ade-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="12ade-119">Si está sin conexión durante más de 24 horas, Teams permite volver a enviar o eliminar mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="12ade-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="12ade-120">Estamos trabajando para agregar esta funcionalidad a nuevos chats y actualizaremos esta documentación cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="12ade-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="12ade-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="12ade-121">Related topics</span></span>

[<span data-ttu-id="12ade-122">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="12ade-122">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)