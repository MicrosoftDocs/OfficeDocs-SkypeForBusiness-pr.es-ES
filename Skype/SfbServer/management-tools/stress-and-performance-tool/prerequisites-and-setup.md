---
title: Requisitos previos y configuración de la herramienta stress and performance de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisitos o requisitos previos para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015. Cómo instalar o configurar la herramienta stress and performance.
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005985"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="e8e5a-104">Requisitos previos y configuración de la herramienta stress and performance de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="e8e5a-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="e8e5a-105">Requisitos o requisitos previos para la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="e8e5a-106">Cómo instalar o configurar la herramienta stress and performance.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="e8e5a-107">Tenemos las siguientes secciones de requisitos de configuración de hardware, software y sistema que debe conocer antes de ejecutar la herramienta stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="e8e5a-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="e8e5a-108">Requisitos de hardware del cliente</span><span class="sxs-lookup"><span data-stu-id="e8e5a-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="e8e5a-109">Requisitos de software del cliente</span><span class="sxs-lookup"><span data-stu-id="e8e5a-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="e8e5a-110">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="e8e5a-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="e8e5a-111">Además, también tenemos una sección a continuación para [instalar la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="e8e5a-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="e8e5a-112">Requisitos de hardware del cliente</span><span class="sxs-lookup"><span data-stu-id="e8e5a-112">Client hardware requirements</span></span>
<span data-ttu-id="e8e5a-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="e8e5a-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="e8e5a-114">Al ejecutar la herramienta stress and performance en su implementación de Skype empresarial Server 2015, tendrá que cumplir, como mínimo, estos requisitos de hardware para cada 4500 usuarios de la prueba:</span><span class="sxs-lookup"><span data-stu-id="e8e5a-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="e8e5a-115">adaptador de red de 1 Gigabit</span><span class="sxs-lookup"><span data-stu-id="e8e5a-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="e8e5a-116">8 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="e8e5a-116">8 GB RAM</span></span>
    
- <span data-ttu-id="e8e5a-117">2 CPUs de doble núcleo</span><span class="sxs-lookup"><span data-stu-id="e8e5a-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="e8e5a-118">Requisitos de software del cliente</span><span class="sxs-lookup"><span data-stu-id="e8e5a-118">Client software requirements</span></span>
<span data-ttu-id="e8e5a-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="e8e5a-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="e8e5a-120">Los sistemas operativos compatibles con la herramienta stress and Performance son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8e5a-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="e8e5a-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e8e5a-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="e8e5a-122">Windows Server 2008 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="e8e5a-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="e8e5a-123">Además, los equipos deben cumplir con los siguientes requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="e8e5a-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="e8e5a-124">Necesitará Microsoft .NET 4,5 Framework instalado.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="e8e5a-125">Descargue .net 4,5 Framework aquí.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="e8e5a-126">Necesitará la característica experiencia de escritorio habilitada en Windows.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="e8e5a-127">Necesitará Microsoft Visual C++ 2013 (x64) instalado.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="e8e5a-128">Descargue Visual C++ 2013 aquí</span><span class="sxs-lookup"><span data-stu-id="e8e5a-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="e8e5a-129">Necesitará que Skype empresarial Server 2015 se haya implementado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="e8e5a-130">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="e8e5a-130">Configuration requirements</span></span>
<span data-ttu-id="e8e5a-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="e8e5a-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="e8e5a-132">Necesitará estas configuraciones adicionales para ejecutar la herramienta stress and Performance correctamente:</span><span class="sxs-lookup"><span data-stu-id="e8e5a-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="e8e5a-133">Debe iniciar sesión en el servidor como miembro del grupo del administrador local o del dominio.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="e8e5a-134">No puede instalar la herramienta de creación de usuarios de Skype empresarial Server 2015 (UserProvisioningTool. exe) en cualquier servidor front-end o servidor Standard Edition en el que residirán las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="e8e5a-135">Cuando la herramienta de creación de usuarios se ejecuta varias veces, cada usuario que esté habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="e8e5a-136">El tamaño del archivo de paginación se debe administrar con los sistemas o, de lo contrario, debe ser al menos 1,5 veces la cantidad de RAM del sistema del equipo.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e8e5a-137">Instalación de la herramienta de esfuerzo y rendimiento de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8e5a-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="e8e5a-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="e8e5a-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="e8e5a-139">La instalación no puede ser más sencilla.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="e8e5a-140">Tiene que ejecutar el archivo de Windows Installer, **CapacityPlanningTool. msi**, en cada equipo cliente que vaya a usar para simular el tráfico de usuarios y en un servidor front-end en cada grupo de servidores en el que creará usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="e8e5a-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="e8e5a-141">Para descargar el. msi, junto con los scripts de ejemplo mencionados en nuestros otros artículos, vaya al vínculo centro de descarga: [Skype for Business Server 2015, herramienta stress and Performance](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="e8e5a-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

