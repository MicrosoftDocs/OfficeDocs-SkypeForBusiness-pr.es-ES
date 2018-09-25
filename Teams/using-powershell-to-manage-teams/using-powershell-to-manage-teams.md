---
title: Uso de PowerShell para administrar los equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Aprenda a usar Windows PowerShell para administrar todas las características que se encuentran en Microsoft Teams de.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0daff64e5a0f6f876de4adb7b60d913fbcce78cb
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016080"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="adada-103">Uso de PowerShell para administrar los equipos</span><span class="sxs-lookup"><span data-stu-id="adada-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="adada-104">Las características de los equipos se pueden administrar mediante PowerShell o el Microsoft Teams y Skype para centro de administración de negocio.</span><span class="sxs-lookup"><span data-stu-id="adada-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="adada-105">! [Nota] No todas las características en los equipos se pueden administrar con el módulo del conector de los equipos.</span><span class="sxs-lookup"><span data-stu-id="adada-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="adada-106">Debe usar la Skype para Business connector.</span><span class="sxs-lookup"><span data-stu-id="adada-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="adada-107">Vea [descargar e instalar el Skype para conector de negocio en línea](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="adada-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="adada-108">Paso 1: requisitos previos</span><span class="sxs-lookup"><span data-stu-id="adada-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="adada-109">Administración remota de Microsoft Teams mediante PowerShell sólo se admite en los equipos de 64 bits que ejecutan uno de los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="adada-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="adada-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="adada-110">Windows 10</span></span>
- <span data-ttu-id="adada-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="adada-111">Windows 8.1</span></span>
- <span data-ttu-id="adada-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="adada-112">Windows 8</span></span> 
- <span data-ttu-id="adada-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="adada-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="adada-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="adada-114">Windows Server 2012</span></span>
- <span data-ttu-id="adada-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="adada-115">Windows Server 2008</span></span>
- <span data-ttu-id="adada-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="adada-116">Windows 7</span></span>
    
<span data-ttu-id="adada-117">Además de un sistema operativo compatible, el equipo también debe ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="adada-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="adada-118">PowerShell 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="adada-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="adada-119">Módulo de conector de PowerShell de los equipos</span><span class="sxs-lookup"><span data-stu-id="adada-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="adada-120">Paso 2: Instalar PowerShell 3.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="adada-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="adada-121">Use este tema para obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="adada-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="adada-122">Paso 3: Descargar e instalar el módulo del conector de los equipos</span><span class="sxs-lookup"><span data-stu-id="adada-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="adada-123">Use este tema para obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="adada-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="adada-124">Este es el vínculo de descarga de Isabella:https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="adada-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="adada-125">Paso 4: Conectar con el módulo del conector de los equipos</span><span class="sxs-lookup"><span data-stu-id="adada-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="adada-126">Use este tema para obtener ayuda</span><span class="sxs-lookup"><span data-stu-id="adada-126">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="adada-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="adada-127">Related topics</span></span>
- [<span data-ttu-id="adada-128">Administrar las características de los equipos con PowerShell</span><span class="sxs-lookup"><span data-stu-id="adada-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)