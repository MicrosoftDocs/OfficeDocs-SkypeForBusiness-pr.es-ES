---
title: Solucionar problemas de conectividad con el cliente de Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Aprenda a resolver problemas de conectividad con el cliente de Microsoft Teams, ocasionadas principalmente por el firewall o la conexión del proxy.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79718ebc58205cd63ab291f0985e4dd7e452be3e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236554"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="fd6a1-103">Solucionar problemas de conectividad con el cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd6a1-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="fd6a1-104">Es posible que la mayoría de los problemas detectados con el cliente de Microsoft Teams vuelvan a la conectividad de proxy o firewall.</span><span class="sxs-lookup"><span data-stu-id="fd6a1-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="fd6a1-105">Comprobando que las direcciones URL, direcciones IP y puertos necesarios se abren en el firewall o proxy minimizará la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="fd6a1-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="fd6a1-106">Para obtener información específica sobre las direcciones URL e IPs necesarias para Microsoft Teams, consulte el artículo [Office 365 URLs e](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) información sobre la compatibilidad con direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="fd6a1-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="fd6a1-107">Los siguientes escenarios requieren que se abran direcciones URL y puertos específicos en el firewall.</span><span class="sxs-lookup"><span data-stu-id="fd6a1-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="fd6a1-108">Autenticación</span><span class="sxs-lookup"><span data-stu-id="fd6a1-108">Authentication</span></span>

-   <span data-ttu-id="fd6a1-109">Conectividad de cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd6a1-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="fd6a1-110">Colaboración</span><span class="sxs-lookup"><span data-stu-id="fd6a1-110">Collaboration</span></span>

-   <span data-ttu-id="fd6a1-111">Medios</span><span class="sxs-lookup"><span data-stu-id="fd6a1-111">Media</span></span>

-   <span data-ttu-id="fd6a1-112">Servicios compartidos</span><span class="sxs-lookup"><span data-stu-id="fd6a1-112">Shared Services</span></span>

-   <span data-ttu-id="fd6a1-113">Integración de terceros</span><span class="sxs-lookup"><span data-stu-id="fd6a1-113">Third Party Integration</span></span>

-   <span data-ttu-id="fd6a1-114">Interoperabilidad de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fd6a1-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="fd6a1-115">Interoperabilidad del cliente de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fd6a1-115">Skype for Business Client Interoperability</span></span>
