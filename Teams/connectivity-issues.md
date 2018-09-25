---
title: Solucionar problemas de conectividad con el cliente de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Aprenda a resolver problemas de conectividad con el cliente de Microsoft Teams, ocasionadas principalmente por el firewall o la conexión del proxy.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b95ed6f223b9ec2f5c72a0d387fc1bfd9e693881
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012140"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="fc7c3-103">Solucionar problemas de conectividad con el cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc7c3-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="fc7c3-104">Mayoría de los problemas detectada con el cliente de Microsoft Teams puede deberse a la conectividad de servidor de seguridad o proxy.</span><span class="sxs-lookup"><span data-stu-id="fc7c3-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="fc7c3-105">Comprobar que las direcciones URL necesarias, direcciones IP y puertos están abiertos en el servidor de seguridad o proxy va a minimizar la solución de problemas innecesarios.</span><span class="sxs-lookup"><span data-stu-id="fc7c3-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="fc7c3-106">Para obtener información específica sobre IP necesarios para Microsoft Teams y direcciones URL, vea [direcciones URL de Office 365 y la dirección IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) artículo de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fc7c3-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="fc7c3-107">Los siguientes escenarios requieren específico las direcciones URL y puertos estén abiertos en el firewall.</span><span class="sxs-lookup"><span data-stu-id="fc7c3-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="fc7c3-108">Autenticación</span><span class="sxs-lookup"><span data-stu-id="fc7c3-108">Authentication</span></span>

-   <span data-ttu-id="fc7c3-109">Conectividad de cliente de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc7c3-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="fc7c3-110">Colaboración</span><span class="sxs-lookup"><span data-stu-id="fc7c3-110">Collaboration</span></span>

-   <span data-ttu-id="fc7c3-111">Medios</span><span class="sxs-lookup"><span data-stu-id="fc7c3-111">Media</span></span>

-   <span data-ttu-id="fc7c3-112">Servicios compartidos</span><span class="sxs-lookup"><span data-stu-id="fc7c3-112">Shared Services</span></span>

-   <span data-ttu-id="fc7c3-113">Integración de terceros</span><span class="sxs-lookup"><span data-stu-id="fc7c3-113">Third Party Integration</span></span>

-   <span data-ttu-id="fc7c3-114">Interoperabilidad de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fc7c3-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="fc7c3-115">Interoperabilidad del cliente de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fc7c3-115">Skype for Business Client Interoperability</span></span>
