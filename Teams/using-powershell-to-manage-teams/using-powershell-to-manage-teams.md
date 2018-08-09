---
title: Uso de PowerShell para administrar los equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
description: Aprenda a usar Windows PowerShell para administrar todas las características que se encuentran en Microsoft Teams de.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a83d6281352ca4ef6a5a8d57d3a27692c7288d6
ms.sourcegitcommit: 41e325c5440e26cc39a3c8945020f597f8dfac96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "22213375"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="c5587-103">Uso de PowerShell para administrar los equipos</span><span class="sxs-lookup"><span data-stu-id="c5587-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="c5587-104">Las características de los equipos se pueden administrar mediante PowerShell o el Microsoft Teams y Skype para centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="c5587-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="c5587-105">! [Nota] No todas las características en los equipos se pueden administrar con el módulo del conector de los equipos.</span><span class="sxs-lookup"><span data-stu-id="c5587-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="c5587-106">Debe usar la Skype para Business connector.</span><span class="sxs-lookup"><span data-stu-id="c5587-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="c5587-107">Vea [descargar e instalar el Skype para conector de negocio en línea](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="c5587-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="c5587-108">Paso 1: requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c5587-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="c5587-109">Administración remota de Microsoft Teams mediante PowerShell sólo se admite en los equipos de 64 bits que ejecutan uno de los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="c5587-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="c5587-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c5587-110">Windows 10</span></span>
- <span data-ttu-id="c5587-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c5587-111">Windows 8.1</span></span>
- <span data-ttu-id="c5587-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="c5587-112">Windows 8</span></span> 
- <span data-ttu-id="c5587-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c5587-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="c5587-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c5587-114">Windows Server 2012</span></span>
- <span data-ttu-id="c5587-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="c5587-115">Windows Server 2008</span></span>
- <span data-ttu-id="c5587-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="c5587-116">Windows 7</span></span>
    
<span data-ttu-id="c5587-117">Además de un sistema operativo compatible, el equipo también debe ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5587-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="c5587-118">PowerShell 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="c5587-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="c5587-119">Módulo de conector de PowerShell de los equipos</span><span class="sxs-lookup"><span data-stu-id="c5587-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="c5587-120">Paso 2: Instalar PowerShell 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="c5587-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="c5587-121">Use este tema para obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="c5587-121">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="c5587-122">Paso 3: Descargar e instalar el módulo del conector de los equipos</span><span class="sxs-lookup"><span data-stu-id="c5587-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="c5587-123">Use este tema para obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="c5587-123">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="c5587-124">Este es el vínculo de descarga de Isabella:https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="c5587-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="c5587-125">Paso 4: Conectar con el módulo del conector de los equipos</span><span class="sxs-lookup"><span data-stu-id="c5587-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="c5587-126">Use este tema para obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="c5587-126">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="c5587-127">See also</span><span class="sxs-lookup"><span data-stu-id="c5587-127">Related topics</span></span>
- [<span data-ttu-id="c5587-128">Administrar las características de los equipos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5587-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)