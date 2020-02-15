---
title: Herramienta de planeación de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Instrucciones sobre el uso de la herramienta de planeación de Skype empresarial Server 2015.
ms.openlocfilehash: 8eec7865b74640cf6dfe4f5a5122f4c7091cc5ae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050102"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="b37c1-103">Herramienta de planeación de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="b37c1-104">Instrucciones sobre el uso de la herramienta de planeación de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b37c1-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="b37c1-105">La herramienta de planeación de Skype empresarial Server 2015 es una herramienta basada en una entrevista guiada por un asistente que formula preguntas sobre la topología de Skype empresarial Server 2015 que está diseñando.</span><span class="sxs-lookup"><span data-stu-id="b37c1-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="b37c1-106">La herramienta de planeación usa la información suministrada, junto con las prácticas recomendadas para el diseño y la capacidad de la topología, para presentar una topología recomendada en función de las respuestas proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="b37c1-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="b37c1-107">Puede descargar la herramienta de planeación de la [herramienta de planeación de Skype empresarial Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="b37c1-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="b37c1-108">En última instancia, el objetivo de la herramienta de planeación es facilitar la complejidad del diseño de una topología completa de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b37c1-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="b37c1-109">La herramienta también proporciona referencias contextuales a la documentación de planeación e implementación dentro de la herramienta, siempre que haya una conexión a Internet disponible para conectarse al sitio web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b37c1-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="b37c1-110">Después de personalizar la topología con las direcciones TCP/IP de la infraestructura y los nombres de dominio completos (FQDN), la herramienta de planeación pone a disposición una serie de informes que cubren el nombre del sistema de nombres de dominio (DNS), las reglas de firewall, los certificados y mucho más.</span><span class="sxs-lookup"><span data-stu-id="b37c1-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="b37c1-111">El uso de esta herramienta es el primer paso para planear la implementación de.</span><span class="sxs-lookup"><span data-stu-id="b37c1-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="b37c1-112">El paso siguiente sería especificar los detalles de la información del sitio en la [calculadora de capacidad de Skype empresarial server 2015](https://www.microsoft.com/download/details.aspx?id=51196), ajustarla según sea necesario y, a continuación, usar la [herramienta stress and performance de skype empresarial Server 2015](https://www.microsoft.com/download/details.aspx?id=50367) para simular y verificar que la implementación se adapte a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="b37c1-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="b37c1-113">La herramienta de planeación también ofrece la posibilidad de exportar información en dos formatos:</span><span class="sxs-lookup"><span data-stu-id="b37c1-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="b37c1-114">Microsoft Excel (hoja de cálculo. xml)</span><span class="sxs-lookup"><span data-stu-id="b37c1-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="b37c1-115">Microsoft Visio (. VDX)</span><span class="sxs-lookup"><span data-stu-id="b37c1-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="b37c1-116">Los temas siguientes presentan y detallan la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="b37c1-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b37c1-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b37c1-117">In this section</span></span>

- [<span data-ttu-id="b37c1-118">Instalar la herramienta de planeación en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="b37c1-119">Software opcional</span><span class="sxs-lookup"><span data-stu-id="b37c1-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="b37c1-120">Navegar por la herramienta de planeación en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="b37c1-121">Crear el diseño de topología inicial para Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="b37c1-122">Editar la topología en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="b37c1-123">Edición del diagrama de configuración de red</span><span class="sxs-lookup"><span data-stu-id="b37c1-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="b37c1-124">Revisar los informes del administrador en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="b37c1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b37c1-125">See also</span></span>

[<span data-ttu-id="b37c1-126">Instalar Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="b37c1-127">Planeación de la mensajería instantánea y la presencia en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b37c1-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
