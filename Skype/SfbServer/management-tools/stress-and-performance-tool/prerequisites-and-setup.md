---
title: Requisitos previos y configuración de la Herramienta de esfuerzo y rendimiento de Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Requisitos o requisitos previos para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015. Cómo instalar o configurar la Herramienta de esfuerzo y rendimiento.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814960"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="03314-104">Requisitos previos y configuración de la Herramienta de esfuerzo y rendimiento de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="03314-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="03314-105">Requisitos o requisitos previos para la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="03314-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="03314-106">Cómo instalar o configurar la Herramienta de esfuerzo y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="03314-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="03314-107">Tenemos las siguientes secciones de requisitos de configuración de hardware, software y sistema que deberá conocer antes de ejecutar la Herramienta de esfuerzo y rendimiento:</span><span class="sxs-lookup"><span data-stu-id="03314-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="03314-108">Requisitos de hardware de cliente</span><span class="sxs-lookup"><span data-stu-id="03314-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="03314-109">Requisitos de software de cliente</span><span class="sxs-lookup"><span data-stu-id="03314-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="03314-110">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="03314-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="03314-111">Además, también tenemos una sección a continuación para instalar la Herramienta de esfuerzo y rendimiento de [Skype Empresarial Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="03314-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="03314-112">Requisitos de hardware de cliente</span><span class="sxs-lookup"><span data-stu-id="03314-112">Client hardware requirements</span></span>
<span data-ttu-id="03314-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="03314-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="03314-114">Al ejecutar la Herramienta de esfuerzo y rendimiento en su implementación de Skype Empresarial Server 2015, necesitará, como mínimo, que se cumplen estos requisitos de hardware por cada 4500 usuarios en su prueba:</span><span class="sxs-lookup"><span data-stu-id="03314-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="03314-115">Adaptador de red de 1 gigabit</span><span class="sxs-lookup"><span data-stu-id="03314-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="03314-116">8 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="03314-116">8 GB RAM</span></span>
    
- <span data-ttu-id="03314-117">2 CPU de doble núcleo</span><span class="sxs-lookup"><span data-stu-id="03314-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="03314-118">Requisitos de software de cliente</span><span class="sxs-lookup"><span data-stu-id="03314-118">Client software requirements</span></span>
<span data-ttu-id="03314-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="03314-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="03314-120">Los sistemas operativos compatibles con la herramienta Stress and Performance son:</span><span class="sxs-lookup"><span data-stu-id="03314-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="03314-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="03314-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="03314-122">Windows Server 2008 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="03314-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="03314-123">Además, los equipos deben cumplir los siguientes requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="03314-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="03314-124">Necesitará microsoft .NET 4.5 Framework instalado.</span><span class="sxs-lookup"><span data-stu-id="03314-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="03314-125">Descargue .Net 4.5 Framework aquí.</span><span class="sxs-lookup"><span data-stu-id="03314-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="03314-126">Necesitarás la característica Experiencia de escritorio habilitada en Windows.</span><span class="sxs-lookup"><span data-stu-id="03314-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="03314-127">Necesitarás que Microsoft Visual C++ 2013 (x64) esté instalado.</span><span class="sxs-lookup"><span data-stu-id="03314-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="03314-128">Descarga Visual C++ 2013 aquí</span><span class="sxs-lookup"><span data-stu-id="03314-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="03314-129">Necesitará que Skype Empresarial Server 2015 se implemente correctamente.</span><span class="sxs-lookup"><span data-stu-id="03314-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="03314-130">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="03314-130">Configuration requirements</span></span>
<span data-ttu-id="03314-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="03314-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="03314-132">Necesitará realizar estas configuraciones adicionales para ejecutar correctamente la herramienta Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="03314-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="03314-133">Debe iniciar sesión en el servidor como miembro del grupo De dominio o Administrador local.</span><span class="sxs-lookup"><span data-stu-id="03314-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="03314-134">No puede instalar la herramienta de creación de usuarios de Skype Empresarial Server 2015 (UserProvisioningTool.exe) en ningún servidor front-end o servidor Standard Edition donde residirán las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="03314-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="03314-135">Cuando la herramienta de creación de usuarios se ejecuta varias veces, cada usuario habilitado para las comunicaciones unificadas de Microsoft debe tener un número de teléfono único.</span><span class="sxs-lookup"><span data-stu-id="03314-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="03314-136">El tamaño del archivo de página debe ser administrado por sistemas o, de lo contrario, debe ser al menos 1,5 veces la cantidad de RAM en el sistema del equipo.</span><span class="sxs-lookup"><span data-stu-id="03314-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="03314-137">Instalación de la Herramienta de esfuerzo y rendimiento de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="03314-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="03314-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="03314-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="03314-139">La instalación no pudo ser más sencilla.</span><span class="sxs-lookup"><span data-stu-id="03314-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="03314-140">Debe ejecutar el archivo de Windows Installer, **CapacityPlanningTool.msi**, en cada equipo cliente que vaya a usar para simular el tráfico de usuarios y en un servidor front-end en cada grupo de servidores donde creará usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="03314-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="03314-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="03314-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

