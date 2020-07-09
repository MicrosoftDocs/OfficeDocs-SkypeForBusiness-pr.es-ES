---
title: Crear un mapa de creación para el panel de calidad de llamadas (CQD)
ms.author: lolaj
author: LolaJacobsen
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
description: Aprenda a crear un mapa de edificio que pueda usar para cargar inquilinos y datos de compilación en el panel de calidad de llamadas (CQD).
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086124"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="8e719-103">Crear un mapa de creación para el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="8e719-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="8e719-104">En una implementación de Microsoft Teams o de Skype empresarial online, todos los clientes son externos.</span><span class="sxs-lookup"><span data-stu-id="8e719-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="8e719-105">Como resultado, de forma predeterminada, todos los clientes se notifican como externos en el panel de calidad de llamadas (CQD), independientemente de si el cliente está conectado a una red corporativa interna.</span><span class="sxs-lookup"><span data-stu-id="8e719-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="8e719-106">Cuando trabaja con el CQD, necesita conocer la ubicación de un extremo y si está conectado a una red que puede administrar o a una red que no puede administrar; se supone que solo puede mejorar las redes que puede administrar.</span><span class="sxs-lookup"><span data-stu-id="8e719-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="8e719-107">Al cargar la subred y la información de creación en el CQD, habilitará el CQD para determinar si el punto de conexión se ha conectado a una red interna (administrada) o a una red externa (no administrada).</span><span class="sxs-lookup"><span data-stu-id="8e719-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="8e719-108">Por eso es importante crear un mapa de creación para la organización y [cargarlo en el CQD](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="8e719-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="8e719-109">Creación de herramientas de asignación</span><span class="sxs-lookup"><span data-stu-id="8e719-109">Building mapping tools</span></span>

<span data-ttu-id="8e719-110">Hay muchas maneras de asignar las subredes de su organización.</span><span class="sxs-lookup"><span data-stu-id="8e719-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="8e719-111">Si necesita ayuda, puede usar el módulo de PowerShell CQDTools que se describe en esta [entrada de blog](https://aka.ms/cqdtools).</span><span class="sxs-lookup"><span data-stu-id="8e719-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="8e719-112">Estas herramientas se basan en PowerShell y usan sitios y servicios de Active Directory (AD) y servicios DHCP de Microsoft para ayudarle a rellenar previamente el archivo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8e719-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="8e719-113">Estas herramientas le ayudarán a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="8e719-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="8e719-114">Consultar sitios y servicios de AD y crear un archivo de compilación basado en la información contenida en él.</span><span class="sxs-lookup"><span data-stu-id="8e719-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="8e719-115">Consulte un servidor o servidores DHCP de Microsoft para extraer la información de subred y crear automáticamente un archivo de creación.</span><span class="sxs-lookup"><span data-stu-id="8e719-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="8e719-116">Validar un archivo de compilación existente, comprobando si existen duplicados y superposiciones.</span><span class="sxs-lookup"><span data-stu-id="8e719-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="8e719-117">Busque subredes sin asignar en el CQD.</span><span class="sxs-lookup"><span data-stu-id="8e719-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e719-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8e719-118">Related topics</span></span>

[<span data-ttu-id="8e719-119">Cargar inquilino y datos de compilación en el CQD</span><span class="sxs-lookup"><span data-stu-id="8e719-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)