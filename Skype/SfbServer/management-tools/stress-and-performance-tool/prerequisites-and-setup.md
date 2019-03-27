---
title: Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Requisitos o requisitos previos de la herramienta Stress and Performance de Skype Empresarial Server 2015. Cómo se instala o se configura la herramienta Stress and Performance.
ms.openlocfilehash: 840891a7a356866755e89a7ef63e23fb62bfa12f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895093"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="048b4-104">Requisitos previos y configuración de la herramienta Stress and Performance de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="048b4-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="048b4-p102">Requisitos o requisitos previos de la herramienta Stress and Performance de Skype Empresarial Server 2015. Cómo se instala o se configura la herramienta Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="048b4-p102">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool. How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="048b4-107">Antes de ejecutar la herramienta Stress and Performance, debe tener en cuenta las siguientes secciones de requisitos de hardware, software y configuración del sistema:</span><span class="sxs-lookup"><span data-stu-id="048b4-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="048b4-108">Requisitos de hardware del cliente</span><span class="sxs-lookup"><span data-stu-id="048b4-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="048b4-109">Requisitos de software del cliente</span><span class="sxs-lookup"><span data-stu-id="048b4-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="048b4-110">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="048b4-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="048b4-111">Además, a continuación se incluye una sección sobre la [Instalación de la herramienta Stress and Performance de Skype Empresarial Server 2015](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="048b4-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="048b4-112">Requisitos de hardware del cliente</span><span class="sxs-lookup"><span data-stu-id="048b4-112">Client hardware requirements</span></span>
<span data-ttu-id="048b4-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="048b4-113"></span></span>

<span data-ttu-id="048b4-114">Cuando se disponga a ejecutar la herramienta Stress and Performance en su implementación de Skype Empresarial Server 2015, tendrá que cumplir, al menos, estos requisitos de hardware por cada 4.500 usuarios que haya en la prueba:</span><span class="sxs-lookup"><span data-stu-id="048b4-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="048b4-115">Adaptador de red de 1 gigabit</span><span class="sxs-lookup"><span data-stu-id="048b4-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="048b4-116">8 GB de memoria RAM</span><span class="sxs-lookup"><span data-stu-id="048b4-116">8 GB RAM</span></span>
    
- <span data-ttu-id="048b4-117">2 CPU de doble núcleo</span><span class="sxs-lookup"><span data-stu-id="048b4-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="048b4-118">Requisitos de software del cliente</span><span class="sxs-lookup"><span data-stu-id="048b4-118">Client software requirements</span></span>
<span data-ttu-id="048b4-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="048b4-119"></span></span>

<span data-ttu-id="048b4-120">Los sistemas operativos compatibles con la herramienta Stress and Performance son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="048b4-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="048b4-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="048b4-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="048b4-122">Windows Server 2008 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="048b4-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="048b4-123">Además, los equipos deben cumplir los siguientes requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="048b4-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="048b4-124">Tendrá que tener instalado Microsoft .NET 4.5 Framework.</span><span class="sxs-lookup"><span data-stu-id="048b4-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="048b4-125">Descargar la 4.5 de .net Framework aquí.</span><span class="sxs-lookup"><span data-stu-id="048b4-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- <span data-ttu-id="048b4-126">Deberá tener habilitada la característica Experiencia de escritorio en Windows.</span><span class="sxs-lookup"><span data-stu-id="048b4-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="048b4-127">Tendrá que tener instalado Microsoft Visual C++ 2013 (x64).</span><span class="sxs-lookup"><span data-stu-id="048b4-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="048b4-128">Descargar aquí 2013 de Visual C++</span><span class="sxs-lookup"><span data-stu-id="048b4-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- <span data-ttu-id="048b4-129">Va a necesitar que Skype Empresarial Server 2015 esté correctamente implementado.</span><span class="sxs-lookup"><span data-stu-id="048b4-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="048b4-130">Requisitos de configuración</span><span class="sxs-lookup"><span data-stu-id="048b4-130">Configuration requirements</span></span>
<span data-ttu-id="048b4-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="048b4-131"></span></span>

<span data-ttu-id="048b4-132">Para que la herramienta Stress and Performance se ejecute correctamente, necesitará aplicar estas configuraciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="048b4-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="048b4-133">Tiene que iniciar sesión en el servidor como miembro del grupo del administrador local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="048b4-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="048b4-134">No se puede instalar la herramienta de creación de usuarios de Skype Empresarial Server 2015 (UserProvisioningTool.exe) en un servidor front-end o un servidor Standard Edition en el que residirán las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="048b4-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="048b4-135">Cuando la herramienta de creación de usuarios se ejecuta varias veces, cada uno de los usuarios que está habilitado para Microsoft Unified Communications deberá tener un número de teléfono exclusivo.</span><span class="sxs-lookup"><span data-stu-id="048b4-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="048b4-136">El tamaño del archivo de paginación lo debe administrar el sistema; de lo contrario, tendría que tener al menos 1,5 veces la cantidad de RAM del sistema del equipo.</span><span class="sxs-lookup"><span data-stu-id="048b4-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="048b4-137">Instalación de la herramienta Stress and Performance de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="048b4-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="048b4-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="048b4-138"></span></span>

<span data-ttu-id="048b4-p105">La instalación no podía ser más sencilla. Tiene que ejecutar el archivo de Windows Installer, **CapacityPlanningTool.msi**, en cada equipo cliente que vaya a usar para simular el tráfico de usuarios y en el servidor front-end de cada grupo donde vaya a crear usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="048b4-p105">Installing couldn't be simpler. You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="048b4-141">Para descargar el archivo .msi, junto con las secuencias de comandos de ejemplo que se mencionan en nuestros otros artículos, vaya al vínculo Centro de descarga: [Skype para Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span><span class="sxs-lookup"><span data-stu-id="048b4-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

