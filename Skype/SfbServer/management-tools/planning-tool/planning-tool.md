---
title: Herramienta de planeación de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Guía para utilizar el Skype para la herramienta de planeación de Business Server 2015.
ms.openlocfilehash: 9995b17274377025f2531ca53966859d1ca716b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="8888f-103">Herramienta de planeación de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="8888f-104">Guía para utilizar el Skype para la herramienta de planeación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8888f-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="8888f-105">El Skype para la herramienta de planeación de 2015 Business Server es un asistente de gobernado, entrevista-como la herramienta que hace preguntas sobre el Skype para Business Server 2015 la topología que está diseñando.</span><span class="sxs-lookup"><span data-stu-id="8888f-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="8888f-106">Los usos de la herramienta de planeación la información suministrada, junto con las prácticas recomendadas para el diseño de la topología y capacidad para presentar una topología recomendada basada en las respuestas proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="8888f-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="8888f-107">Puede descargar la herramienta de planeación desde el [Centro de descargas de Microsoft](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="8888f-107">You can download the Planning Tool from the [Microsoft Downloads Center](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="8888f-108">En última instancia, el objetivo de la herramienta de planeación es facilitar la complejidad de diseñar un Skype para Business Server 2015 topología completa.</span><span class="sxs-lookup"><span data-stu-id="8888f-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="8888f-109">De igual modo, esta herramienta proporciona referencias contextuales a la documentación de planeación e implementación de la propia herramienta, siempre y cuando haya una conexión a Internet disponible que permita conectarse al sitio web de Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="8888f-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>
  
<span data-ttu-id="8888f-110">Después de personalizar la topología con direcciones de TCP/IP de la infraestructura y los nombres de dominio completo (FQDN), la herramienta de planeación pone a disposición una serie de informes que incluyen los nombres de sistema de nombres de dominio (DNS), reglas de cortafuegos, certificados y más.</span><span class="sxs-lookup"><span data-stu-id="8888f-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="8888f-111">El uso de esta herramienta es el primer paso a la hora de planear la implementación.</span><span class="sxs-lookup"><span data-stu-id="8888f-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="8888f-112">El siguiente paso podría ser a las características del sitio información de entrada en el [Skype para Business Server 2015 capacidad calculadora](https://www.microsoft.com/en-us/download/details.aspx?id=51196), ajustar según sea necesario y luego utilice el [Skype para Business Server 2015 Stress y la herramienta de rendimiento](https://www.microsoft.com/en-us/download/details.aspx?id=50367) para simular y comprobar el implementación servirá a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="8888f-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="8888f-113">La herramienta de planeación también proporciona la capacidad de exportar información en dos formatos:</span><span class="sxs-lookup"><span data-stu-id="8888f-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="8888f-114">Microsoft Excel (hoja de cálculo en .xml)</span><span class="sxs-lookup"><span data-stu-id="8888f-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="8888f-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="8888f-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="8888f-116">Los temas siguientes presentan y detallan de la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="8888f-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8888f-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8888f-117">In this section</span></span>

- [<span data-ttu-id="8888f-118">Instalar la herramienta de planeación de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="8888f-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="8888f-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="8888f-120">Navegar por la herramienta de planeación de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="8888f-121">Crear el diseño de topología inicial para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="8888f-122">Modificar la topología de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="8888f-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="8888f-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="8888f-124">Revisar los informes de administrador de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="8888f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8888f-125">See also</span></span>

#### 

[<span data-ttu-id="8888f-126">Instalar Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="8888f-127">Plan para la mensajería instantánea y presencia en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8888f-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)

