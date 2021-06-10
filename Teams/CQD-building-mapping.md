---
title: Crear un mapa de creación para el panel de calidad de llamadas (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Obtenga información sobre cómo crear un mapa de creación que puede usar para cargar datos de inquilino y creación en el Panel de calidad de llamadas (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584039"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="064a6-103">Crear un mapa de creación para el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="064a6-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="064a6-104">En una Microsoft Teams o Skype Empresarial online, todos los clientes son externos.</span><span class="sxs-lookup"><span data-stu-id="064a6-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="064a6-105">Como resultado, de forma predeterminada, todos los clientes se notifican como externos en el Panel de calidad de llamadas (CQD), independientemente de si el cliente está conectado en una red corporativa interna.</span><span class="sxs-lookup"><span data-stu-id="064a6-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="064a6-106">Cuando trabaja con CQD, necesita conocer la ubicación de un punto de conexión y si estaba conectado a una red que puede administrar o una red que no puede administrar, lo que supone que solo puede mejorar las redes que puede administrar.</span><span class="sxs-lookup"><span data-stu-id="064a6-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="064a6-107">Al cargar la subred y generar información en CQD, habilita CQD para determinar si el punto de conexión estaba conectado a una red interna (administrada) o a una red externa (no administrada).</span><span class="sxs-lookup"><span data-stu-id="064a6-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="064a6-108">Por eso es importante crear un mapa de creación para su organización y [cargarlo en CQD.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="064a6-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="064a6-109">Crear herramientas de asignación</span><span class="sxs-lookup"><span data-stu-id="064a6-109">Building mapping tools</span></span>

<span data-ttu-id="064a6-110">Hay muchas maneras de asignar subredes de su organización.</span><span class="sxs-lookup"><span data-stu-id="064a6-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="064a6-111">Si necesita ayuda, puede usar el módulo de PowerShell CQDTools descrito en esta [entrada de blog.](https://aka.ms/cqdtools)</span><span class="sxs-lookup"><span data-stu-id="064a6-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="064a6-112">Estas herramientas se basan en PowerShell y usan sitios y servicios de Active Directory (AD) y servicios DE MICROSOFT DHCP para ayudar a rellenar previamente el archivo de creación.</span><span class="sxs-lookup"><span data-stu-id="064a6-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="064a6-113">Estas herramientas le ayudarán con las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="064a6-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="064a6-114">Consulte sitios y servicios de AD y cree un archivo de creación basado en la información que contiene.</span><span class="sxs-lookup"><span data-stu-id="064a6-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="064a6-115">Consulte un servidor o servidores DHCP de Microsoft para extraer información de subred y crear automáticamente un archivo de creación.</span><span class="sxs-lookup"><span data-stu-id="064a6-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="064a6-116">Valide un archivo de creación existente, buscando duplicados y superpuestos.</span><span class="sxs-lookup"><span data-stu-id="064a6-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="064a6-117">Busque subredes no recortadas en CQD.</span><span class="sxs-lookup"><span data-stu-id="064a6-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="064a6-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="064a6-118">Related topics</span></span>

[<span data-ttu-id="064a6-119">Upload inquilino y generar datos en CQD</span><span class="sxs-lookup"><span data-stu-id="064a6-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)