---
title: Solucionar problemas de conectividad con el cliente de Teams
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
ms.openlocfilehash: 59041734887a667eca325a3d2650425d6d336b78
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918546"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="e7978-103">Solucionar problemas de conectividad con el cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7978-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="e7978-p101">La mayoría de los problemas detectados con el cliente de Microsoft Teams se pueden rastrear hasta la conectividad de proxy o firewall. Comprobar que las direcciones URL, las direcciones IP y los puertos necesarios están abiertos en el firewall o proxy minimizará la solución de problemas innecesaria. Para obtener información específica sobre las URL e IP necesarias para Microsoft Teams, consulte el artículo de soporte técnico de direcciones IP y URL de [Microsoft 365 y Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) Los siguientes escenarios requieren que se abran puertos y DIRECCIONES URL específicas en el firewall.</span><span class="sxs-lookup"><span data-stu-id="e7978-p101">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity. Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting. For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article. The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="e7978-108">Autenticación</span><span class="sxs-lookup"><span data-stu-id="e7978-108">Authentication</span></span>

- <span data-ttu-id="e7978-109">Conectividad de cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7978-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="e7978-110">Colaboración</span><span class="sxs-lookup"><span data-stu-id="e7978-110">Collaboration</span></span>

- <span data-ttu-id="e7978-111">Elementos multimedia</span><span class="sxs-lookup"><span data-stu-id="e7978-111">Media</span></span>

- <span data-ttu-id="e7978-112">Servicios compartidos</span><span class="sxs-lookup"><span data-stu-id="e7978-112">Shared Services</span></span>

- <span data-ttu-id="e7978-113">Integración de terceros</span><span class="sxs-lookup"><span data-stu-id="e7978-113">Third Party Integration</span></span>

- <span data-ttu-id="e7978-114">Interoperabilidad de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e7978-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="e7978-115">Interoperabilidad del cliente de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e7978-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="e7978-116">Cuando Teams está sin conexión o con condiciones de ancho de banda bajo</span><span class="sxs-lookup"><span data-stu-id="e7978-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="e7978-117">La buena noticia es que Teams sigue ejecutándose incluso cuando trabaja sin conexión o con poco ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="e7978-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="e7978-118">Teams guarda todos los mensajes no enviados de los chats existentes (hasta 24 horas) y los envía en cuanto vuelve a estar en línea.</span><span class="sxs-lookup"><span data-stu-id="e7978-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="e7978-119">Si está sin conexión durante más de 24 horas, Teams le permite elegir entre reenviar o eliminar los mensajes no enviados.</span><span class="sxs-lookup"><span data-stu-id="e7978-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="e7978-120">Estamos trabajando para agregar esta funcionalidad a nuevos chats y actualizaremos esta documentación cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="e7978-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7978-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e7978-121">Related topics</span></span>

[<span data-ttu-id="e7978-122">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="e7978-122">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
