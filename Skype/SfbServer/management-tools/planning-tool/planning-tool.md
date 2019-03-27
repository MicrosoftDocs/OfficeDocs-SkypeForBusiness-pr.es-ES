---
title: Herramienta de planeación de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Instrucciones sobre el uso de la Skype para la herramienta de planeación de Business Server 2015.
ms.openlocfilehash: 7a2230344cc31a14fbd8898706973af5ed0e6d9c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873530"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="220c1-103">Herramienta de planeación de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="220c1-104">Instrucciones sobre el uso de la Skype para la herramienta de planeación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="220c1-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="220c1-105">El Skype para la herramienta de planeación de Business Server 2015 es un asistente controlada por, herramienta de entrevista similar que realiza preguntas sobre el Skype para topología empresarial Server 2015 que está diseñando.</span><span class="sxs-lookup"><span data-stu-id="220c1-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="220c1-106">Los usos de la herramienta de planeación la información suministrada, junto con las prácticas recomendadas para el diseño de la topología y la capacidad, para presentar una topología recomendada en función de las respuestas proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="220c1-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="220c1-107">Puede descargar la herramienta de planeación de la [Skype para la herramienta de planeación de Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="220c1-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="220c1-108">En última instancia, el objetivo de la herramienta de planeación es facilitar la complejidad del diseño de una completa Skype para Business Server 2015 topología posible.</span><span class="sxs-lookup"><span data-stu-id="220c1-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="220c1-109">La herramienta también proporciona referencias contextuales a la documentación de planeación e implementación dentro de la herramienta, siempre que una conexión a Internet está disponible para conectarse al sitio Web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="220c1-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="220c1-110">Después de personalizar la topología con las direcciones de la infraestructura TCP/IP y nombres de dominio completo (FQDN), la herramienta de planeación pone a disposición una serie de informes que incluyen nombres de sistema de nombres de dominio (DNS), las reglas de firewall, certificados y más.</span><span class="sxs-lookup"><span data-stu-id="220c1-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="220c1-111">El uso de esta herramienta es el primer paso a la hora de planear la implementación.</span><span class="sxs-lookup"><span data-stu-id="220c1-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="220c1-112">El paso siguiente sería ser para las características del sitio información de entrada de datos en el [Skype para Calculadora de capacidad de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196), ajustar según sea necesario y luego use el [Skype para Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) para simular y compruebe el implementación servirá a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="220c1-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="220c1-113">La herramienta de planeación también proporciona la capacidad de exportar información en dos formatos:</span><span class="sxs-lookup"><span data-stu-id="220c1-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="220c1-114">Microsoft Excel (hoja de cálculo en .xml)</span><span class="sxs-lookup"><span data-stu-id="220c1-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="220c1-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="220c1-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="220c1-116">Los siguientes temas se presentan y la herramienta de planeación de detalles.</span><span class="sxs-lookup"><span data-stu-id="220c1-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="220c1-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="220c1-117">In this section</span></span>

- [<span data-ttu-id="220c1-118">Install the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="220c1-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="220c1-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="220c1-120">Navigate the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="220c1-121">Create the initial topology design for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="220c1-122">Edit the topology in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="220c1-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="220c1-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="220c1-124">Review the Administrator Reports in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="220c1-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="220c1-125">See also</span></span>

[<span data-ttu-id="220c1-126">Instalar Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="220c1-127">Plan for instant messaging and presence in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="220c1-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
