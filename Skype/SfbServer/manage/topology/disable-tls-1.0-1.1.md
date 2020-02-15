---
title: Deshabilitar TLS 1.0/1.1 en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumen: Prepare e implemente la deshabilitación de TLS 1,0 y 1,1 en sus entornos.'
ms.openlocfilehash: 0a25060463ed3b67db8ca523171c2bc48660293d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012753"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="40883-103">Deshabilitar TLS 1.0/1.1 en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="40883-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="40883-104">El propósito de este artículo es proporcionar las instrucciones necesarias para preparar e implementar la deshabilitación de TLS 1,0 y 1,1 en los entornos.</span><span class="sxs-lookup"><span data-stu-id="40883-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="40883-105">Este proceso requiere una amplia planeación y preparación.</span><span class="sxs-lookup"><span data-stu-id="40883-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="40883-106">Revise atentamente toda la información de este artículo a medida que realiza el plan para deshabilitar TLS 1,0 y 1,1 para su organización.</span><span class="sxs-lookup"><span data-stu-id="40883-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="40883-107">Tenga en cuenta que hay muchas dependencias externas y condiciones de conectividad que podrían verse afectadas por la deshabilitación de TLS 1.0/1.1, por lo que la planeación y las pruebas exhaustivas están garantizadas.</span><span class="sxs-lookup"><span data-stu-id="40883-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="40883-108">En este artículo</span><span class="sxs-lookup"><span data-stu-id="40883-108">In this article</span></span>

- [<span data-ttu-id="40883-109">Fondo y ámbito</span><span class="sxs-lookup"><span data-stu-id="40883-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="40883-110">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="40883-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="40883-111">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="40883-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="40883-112">Fondo</span><span class="sxs-lookup"><span data-stu-id="40883-112">Background</span></span>

<span data-ttu-id="40883-113">Los controladores principales para proporcionar TLS 1,0 y 1,1 deshabilitar la compatibilidad con Skype empresarial Server local son el Consejo de estándares de seguridad de la industria de la tarjeta de pago (PCI) y los estándares federales de procesamiento de información.</span><span class="sxs-lookup"><span data-stu-id="40883-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="40883-114">Puede encontrar más información sobre los requisitos de PCI [aquí](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="40883-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="40883-115">Microsoft no puede proporcionar instrucciones sobre si su organización debe o no cumplir con estos u otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="40883-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="40883-116">Debe determinar si es necesario para deshabilitar TLS 1,0 o 1,1 en sus entornos.</span><span class="sxs-lookup"><span data-stu-id="40883-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="40883-117">Microsoft ha creado una nota del producto sobre TLS disponible [aquí](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)y también se recomienda la lectura en segundo plano disponible en este [blog de Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="40883-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="40883-118">Ámbito de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="40883-118">Supportability Scope</span></span>

<span data-ttu-id="40883-119">El *ámbito* se refiere a los límites de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="40883-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="40883-120">*Totalmente probadas y admitidas* significa que hemos admitido completamente y probado la deshabilitación de TLS 1,0 y 1,1 para las versiones de producto indicadas.</span><span class="sxs-lookup"><span data-stu-id="40883-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="40883-121">*Actualmente investigado* significa eso; Estamos investigando activamente la introducción de estos productos en el ámbito de la compatibilidad con la deshabilitación de TLS.</span><span class="sxs-lookup"><span data-stu-id="40883-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="40883-122">*Fuera del ámbito* significa que estas versiones de producto no admiten la deshabilitación de TLS 1,0 o 1,1 y no funcionarán, con las excepciones indicadas.</span><span class="sxs-lookup"><span data-stu-id="40883-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="40883-123">Servidores completamente probados y admitidos</span><span class="sxs-lookup"><span data-stu-id="40883-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="40883-124">Skype empresarial Server 2019 CU1 17.0.2046.123 (2019 de junio) o superior</span><span class="sxs-lookup"><span data-stu-id="40883-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="40883-125">Skype empresarial Server 2015 CU9 6.0.9319.548 (May 2019) o posterior en Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o reemplazando la actualización), 2012 R2 o 2016.</span><span class="sxs-lookup"><span data-stu-id="40883-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="40883-126">Actualización local de Skype empresarial Server 2015 con CU9 6.0.9319.548 (May 2019) o posterior en Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o reemplazando la actualización) o 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="40883-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="40883-127">Conectividad de Exchange y Outlook Web App con Exchange Server 2010 SP3 RU19 o superior, guía [aquí](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="40883-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="40883-128">Aplicación de sucursal con funciones de supervivencia (SBA) con Skype empresarial Server 2015 CU6 HF2 o superior (confirme con su proveedor que empaqueta las actualizaciones de espacios y que están disponibles para su dispositivo)</span><span class="sxs-lookup"><span data-stu-id="40883-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="40883-129">Servidor de sucursal con funciones de supervivencia (SBS) con Skype empresarial Server 2015 CU6 HF2 o superior</span><span class="sxs-lookup"><span data-stu-id="40883-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="40883-130">Lync Server 2013 **solo rol perimetral**, esto se debe a que el rol perimetral no tiene una dependencia en Windows fabric 1,0.</span><span class="sxs-lookup"><span data-stu-id="40883-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="40883-131">Clientes completamente probados y admitidos</span><span class="sxs-lookup"><span data-stu-id="40883-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="40883-132">Cliente de escritorio de Lync 2013 (Skype empresarial), MSI y C2R, incluido el [15.0.5023.1000 básico o superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="40883-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="40883-133">Cliente de escritorio de Skype empresarial 2016, MSI [16.0.4678.1000 o superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluido Basic</span><span class="sxs-lookup"><span data-stu-id="40883-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="40883-134">Skype empresarial 2016 hacer clic para ejecutar requiere las actualizaciones de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="40883-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="40883-135">De destino mensual y semestral, 16\.0\.9126\.2152 o superior</span><span class="sxs-lookup"><span data-stu-id="40883-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="40883-136">Canal semestral y diferido, 16\.0\.8431\.2242 o superior</span><span class="sxs-lookup"><span data-stu-id="40883-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="40883-137">Skype empresarial en Mac 16,15 o superior</span><span class="sxs-lookup"><span data-stu-id="40883-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="40883-138">Skype empresarial para iOS y Android 6,19 o superior</span><span class="sxs-lookup"><span data-stu-id="40883-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="40883-139">Salones de Microsoft Teams (anteriormente conocido como sistema de salas de Skype v2 SRS V2) 4.0.64.0 (2018 de diciembre) o superior</span><span class="sxs-lookup"><span data-stu-id="40883-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="40883-140">Actualización de Surface hub para Team Edition basada en KB4499162 (mayo 2019, OS compilación 15063,1835) o superior</span><span class="sxs-lookup"><span data-stu-id="40883-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="40883-141">Skype Web App 2015 CU6 HF2 o superior (incluye el servidor)</span><span class="sxs-lookup"><span data-stu-id="40883-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="40883-142">Actualmente investigando</span><span class="sxs-lookup"><span data-stu-id="40883-142">Currently being investigated</span></span>

- <span data-ttu-id="40883-143">Panel de calidad de llamadas (nueva instalación después de que se hayan deshabilitado los 1,1 TLS 1,0, vea a continuación) \*</span><span class="sxs-lookup"><span data-stu-id="40883-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="40883-144">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="40883-144">Out of scope</span></span>

<span data-ttu-id="40883-145">Excepto donde se indique, los siguientes productos no se encuentran en el ámbito de la compatibilidad con TLS 1.0/1.1 deshabilitar y no funcionarán en un entorno en el que se hayan deshabilitado TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="40883-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="40883-146">Esto significa que: Si todavía utiliza servidores o clientes fuera del ámbito, debe actualizarlos o quitarlos si necesita deshabilitar TLS 1.0/1.1 en cualquier lugar de su implementación local de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="40883-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="40883-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40883-147">Lync Server 2013</span></span>
- <span data-ttu-id="40883-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="40883-148">Lync Server 2010</span></span>
- <span data-ttu-id="40883-149">Windows Server 2008 o inferior</span><span class="sxs-lookup"><span data-stu-id="40883-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="40883-150">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="40883-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="40883-151">Lync 2013 para Mobile-iOS, iPad, Android o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="40883-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="40883-152">Cliente de la tienda Windows "MX" de Lync</span><span class="sxs-lookup"><span data-stu-id="40883-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="40883-153">Sistema Lync Room (también conocido como</span><span class="sxs-lookup"><span data-stu-id="40883-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="40883-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="40883-154">SRSv1).</span></span> <span data-ttu-id="40883-155">LRS ha alcanzado el final del soporte técnico el 9 de octubre de 2018 y no se actualizará para admitir TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="40883-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="40883-156">Todos los clientes de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="40883-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="40883-157">Lync Phone Edition: Guía actualizada [aquí](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="40883-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="40883-158">Aplicación de sucursal con funciones de supervivencia basada en 2013 (SBA) o servidor de sucursal con funciones de supervivencia (SBS)</span><span class="sxs-lookup"><span data-stu-id="40883-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="40883-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="40883-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="40883-160">Skype empresarial para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="40883-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="40883-161">Excepciones</span><span class="sxs-lookup"><span data-stu-id="40883-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="40883-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40883-162">Lync Server 2013</span></span>

<span data-ttu-id="40883-163">Lync Server 2013 toma una dependencia en Windows fabric versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="40883-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="40883-164">En la fase de diseño de Lync Server 2013, se escogió Windows fabric 1,0 por su nueva arquitectura distribuida y convincente para proporcionar replicación, alta disponibilidad y tolerancia a errores.</span><span class="sxs-lookup"><span data-stu-id="40883-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="40883-165">Con el tiempo, tanto Skype empresarial Server como Windows fabric han mejorado enormemente esta arquitectura conjunta con rediseño significativo en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="40883-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="40883-166">El servidor actual de Skype empresarial 2015 usa Windows fabric 3,0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="40883-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="40883-167">Por desgracia, Windows fabric 1,0 **no admite TLS 1,2.  Sin embargo, se actualizará Lync Server 2013 para trabajar con TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="40883-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="40883-168">Esto estará disponible en la próxima actualización acumulativa de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40883-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="40883-169">Proporcionamos compatibilidad con TLS 1,2 para habilitar los escenarios de coexistencia, migración, Federación y híbrido.</span><span class="sxs-lookup"><span data-stu-id="40883-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="40883-170">Si su organización debe deshabilitar TLS 1,0 y 1,1 y actualmente usa Lync Server 2013, le recomendamos que comience el proceso de planeación, con la posibilidad de que tenga que realizar una actualización local o una migración en paralelo (nuevos grupos, mover usuarios) a Skype Business Server 2015 o superior.</span><span class="sxs-lookup"><span data-stu-id="40883-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="40883-171">O bien, puede que quiera acelerar la migración a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="40883-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="40883-172">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="40883-172">Call Quality Dashboard</span></span>

<span data-ttu-id="40883-173">El panel de calidad de llamadas local actualmente tiene una dependencia de TLS 1,0 durante la nueva instalación (la primera vez que se instala en los entornos locales).</span><span class="sxs-lookup"><span data-stu-id="40883-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="40883-174">Actualmente estamos investigando este problema y planea liberar una corrección en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="40883-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="40883-175">Si tiene previsto instalar el CQD y deshabilitar también TLS 1,0, se recomienda completar primero la instalación del CQD y, a continuación, continuar con la deshabilitación de TLS 1,0.</span><span class="sxs-lookup"><span data-stu-id="40883-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="40883-176">Dispositivos de otros fabricantes</span><span class="sxs-lookup"><span data-stu-id="40883-176">Third-party devices</span></span>

<span data-ttu-id="40883-177">En dispositivos de terceros, como teléfonos 3PIP, conferencias de vídeo, proxies inversos y equilibradores de carga, asegúrese de validar la compatibilidad con TLS 1,2, realice pruebas minuciosamente y póngase en contacto con el proveedor si es necesario.</span><span class="sxs-lookup"><span data-stu-id="40883-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="40883-178">Consideraciones sobre la Federación al deshabilitar TLS 1.0/1.1 en servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="40883-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="40883-179">Debe planear cuidadosamente y considerar el impacto de la deshabilitación de TLS 1.0/1.1 en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="40883-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="40883-180">Una vez que se han deshabilitado los TLS 1,0 y 1,1, es posible que otras organizaciones ya no puedan federarse a su organización.</span><span class="sxs-lookup"><span data-stu-id="40883-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="40883-181">Puede optar por mantener TLS 1.0/1.1 habilitado en los servidores perimetrales para mantener la compatibilidad con versiones anteriores con sistemas externos no revisados (SfB 2015, Lync 2013) o anteriores (2010).</span><span class="sxs-lookup"><span data-stu-id="40883-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="40883-182">Microsoft no puede proporcionar consejos o recomendaciones sobre si la red perimetral (o cualquier red) cae en el estándar PCI; que debe determinar la empresa individual.</span><span class="sxs-lookup"><span data-stu-id="40883-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="40883-183">Skype empresarial online es compatible con TLS 1,2 en la actualidad, por lo que no se espera ningún impacto en Hybrid/Federation con online.</span><span class="sxs-lookup"><span data-stu-id="40883-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="40883-184">PIC (conectividad de mensajería instantánea pública) para el servicio de consumidor de Skype: no esperamos que la deshabilitación de TLS 1.0/1.1 afecte a la [conectividad de Skype](../../deploy/deploy-skype-connectivity.md); Las puertas de enlace de Microsoft PIC ya admiten TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="40883-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="40883-185">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="40883-185">Prerequisites and process</span></span>

<span data-ttu-id="40883-186">Excepto cuando se haya indicado anteriormente, una 1,1 1,0 vez que se hayan deshabilitado los servidores fuera de ámbito, los clientes y dispositivos podrán funcionar correctamente, o en todo caso.</span><span class="sxs-lookup"><span data-stu-id="40883-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="40883-187">Esto puede significar que debe pausar y esperar una guía actualizada de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40883-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="40883-188">Una vez que esté seguro de que cumple todos los requisitos y tiene un plan para abordar las brechas, continúe.</span><span class="sxs-lookup"><span data-stu-id="40883-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="40883-189">En un nivel alto, mientras Skype empresarial Server 2019 está preparado para el procedimiento en la instalación, Skype empresarial Server 2015 requerirá la instalación de CU9, la aplicación de actualizaciones de requisitos previos a .NET y SQL, la implementación de claves de registro de requisitos previos y, por último, una ronda de actualizaciones de configuración del sistema operativo (por ejemplo, deshabilitar TLS 1,0 y 1,1 a través de la importación de archivos de registro).</span><span class="sxs-lookup"><span data-stu-id="40883-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="40883-190">Es muy importante que complete la instalación de todos los requisitos previos, incluido Skype for Business Server 2015 CU6 HF2, antes de deshabilitar TLS 1,0 y 1,1 en cualquier servidor del entorno.</span><span class="sxs-lookup"><span data-stu-id="40883-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="40883-191">Todos los servidores de Skype empresarial, incluidos el rol perimetral y los extremos de SQL, requieren las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="40883-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="40883-192">Asegúrese también de que todos los clientes compatibles (en el ámbito) se han actualizado a las versiones mínimas necesarias.</span><span class="sxs-lookup"><span data-stu-id="40883-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="40883-193">No olvide actualizar también las estaciones de trabajo de administración.</span><span class="sxs-lookup"><span data-stu-id="40883-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="40883-194">Queremos seguir el orden habitual de las operaciones de "Inside Out" para actualizar servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="40883-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="40883-195">Trate los grupos de directores, el chat persistente y los grupos emparejados de la misma manera que lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="40883-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="40883-196">El orden y los métodos para la actualización se tratan [aquí](topology.md) y [aquí](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="40883-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="40883-197">Proceso de alto nivel</span><span class="sxs-lookup"><span data-stu-id="40883-197">High-level process</span></span>

1. <span data-ttu-id="40883-198">Pruebe todos los pasos del laboratorio antes de configurar los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="40883-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="40883-199">Realice una copia de seguridad y conserve una copia del registro exportado en todos y cada uno de los servidores individuales que se van a actualizar.</span><span class="sxs-lookup"><span data-stu-id="40883-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="40883-200">No puede compartir registros entre servidores; contienen claves únicas basadas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="40883-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="40883-201">Actualice todos los servidores de Skype empresarial 2015 a CU9 o superior.</span><span class="sxs-lookup"><span data-stu-id="40883-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="40883-202">Para Skype empresarial Server 2019, actualice a CU1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="40883-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="40883-203">Instale todos los requisitos previos en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="40883-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="40883-204">Implementar claves de registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="40883-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="40883-205">Asegúrese de que se actualizan todos los clientes del ámbito.</span><span class="sxs-lookup"><span data-stu-id="40883-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="40883-206">Deshabilite TLS 1,0 y 1,1 a través de importación de registro.</span><span class="sxs-lookup"><span data-stu-id="40883-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="40883-207">Validar que las cargas de trabajo funcionan como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="40883-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="40883-208">Si se detectan problemas, la solución de problemas y la resolución o</span><span class="sxs-lookup"><span data-stu-id="40883-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="40883-209">Restaure el registro desde el paso 2 para volver a habilitar TLS 1,0 y 1,1</span><span class="sxs-lookup"><span data-stu-id="40883-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="40883-210">Valide que solo se use TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="40883-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="40883-211">Instalar los requisitos previos para todos los servidores</span><span class="sxs-lookup"><span data-stu-id="40883-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="40883-212">La actualización de dependencias exhaustivas es necesaria antes de empezar a deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo en las implementaciones de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="40883-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="40883-213">Las siguientes son las versiones mínimas que pueden admitir TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="40883-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="40883-214">Implemente todas las actualizaciones de requisitos previos en todos los servidores de Skype empresarial Server del entorno antes de empezar a deshabilitar TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="40883-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="40883-215">Skype empresarial Server 2015 CU9 6.0.9319.548 (mayo 2019) o posterior</span><span class="sxs-lookup"><span data-stu-id="40883-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="40883-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) o superior con valor schusestrongcrypto habilitado en el registro (proporcionado a continuación)</span><span class="sxs-lookup"><span data-stu-id="40883-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="40883-217">SQL debe actualizarse en todos los servidores y servidores de la 2015 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="40883-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="40883-218">Actualice primero el SQL del grupo de servidores Enterprise Edition, y luego sus respectivos FEs.</span><span class="sxs-lookup"><span data-stu-id="40883-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="40883-219">[SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)o superior/sql server 2012 SP2 + CU16 o superior/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)o superior/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="40883-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="40883-220">SQL Server Native Client para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="40883-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="40883-221">[Controlador ODBC 11 de Microsoft para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)o superior</span><span class="sxs-lookup"><span data-stu-id="40883-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="40883-222">Objetos de administración compartidos para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="40883-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="40883-223">SQLSysClrTypes para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="40883-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="40883-224">Pasos básicos para instalar los requisitos previos, en el orden recomendado de operaciones</span><span class="sxs-lookup"><span data-stu-id="40883-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="40883-225">Instale la actualización de CU9 de Skype empresarial Server en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="40883-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="40883-226">Instale la actualización de los componentes que usan el actualizador.</span><span class="sxs-lookup"><span data-stu-id="40883-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="40883-227">Actualice las bases de datos de acuerdo con procedimientos documentados.</span><span class="sxs-lookup"><span data-stu-id="40883-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="40883-228">Para Skype empresarial Server 2015, consulte KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="40883-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="40883-229">Validar la funcionalidad del producto en la implementación antes de seguir adelante con otros cambios.</span><span class="sxs-lookup"><span data-stu-id="40883-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="40883-230">Descargue el instalador sin conexión de .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="40883-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="40883-231">Referencias[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="40883-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="40883-232">Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="40883-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="40883-233">Referencias[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="40883-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="40883-234">Ex (edición estándar):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="40883-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="40883-235">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="40883-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="40883-236">Ejecute el paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="40883-236">Run the installer package.</span></span>
    7. <span data-ttu-id="40883-237">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="40883-237">Reboot the server.</span></span>
3. <span data-ttu-id="40883-238">Actualice SQL Express 2014 en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="40883-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="40883-239">Referencias[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="40883-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="40883-240">Descargar SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="40883-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="40883-241">Referencias[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="40883-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="40883-242">Copie los medios de instalación en una carpeta del servidor (ej: C:\ 01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="40883-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="40883-243">Asegurarse de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end</span><span class="sxs-lookup"><span data-stu-id="40883-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="40883-244">Ex (edición estándar):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="40883-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="40883-245">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="40883-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="40883-246">Abrir un símbolo del sistema de administración y actualizar todos los componentes e instancias instalados</span><span class="sxs-lookup"><span data-stu-id="40883-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="40883-247">Ejemplo: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/Action = patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="40883-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="40883-248">Actualice SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="40883-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="40883-249">Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="40883-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="40883-250">Descargar desde[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="40883-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="40883-251">Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="40883-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="40883-252">Ex (edición estándar):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="40883-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="40883-253">Ex (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="40883-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="40883-254">Detener la ejecución de las instancias de SQL instaladas</span><span class="sxs-lookup"><span data-stu-id="40883-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="40883-255">Precio```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="40883-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="40883-256">Precio```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="40883-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="40883-257">Ex (sólo en Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="40883-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="40883-258">Instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="40883-258">Install the update.</span></span>
5. <span data-ttu-id="40883-259">Actualice ODBC driver 11 for SQL Server para que incluya compatibilidad con TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="40883-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="40883-260">Descargue [ODBC driver 11 for SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="40883-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="40883-261">Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="40883-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="40883-262">Ejemplo (Standard Edition):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="40883-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="40883-263">Ejemplo (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="40883-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="40883-264">Instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="40883-264">Install the update.</span></span>
6. <span data-ttu-id="40883-265">Implementar claves de registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="40883-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="40883-266">Claves del registro de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="40883-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="40883-267">Copie y pegue la siguiente prueba en el Bloc de notas y cambie el nombre a TLSPreReq. reg o un nombre de su elección y, a continuación, importe:</span><span class="sxs-lookup"><span data-stu-id="40883-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="40883-268">Para los back-end de SQL para los grupos de servidores Enterprise Edition, los requisitos previos y la deshabilitación de TLS deben tratarse como actualizaciones de SQL o del sistema operativo; Consulte:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="40883-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="40883-269">Aunque se pueden combinar los pasos de la aplicación de requisitos previos y TLS, recomendamos que se apliquen todos los requisitos previos antes de deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="40883-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="40883-270">El enfoque de los procedimientos recomendados sería preparar el entorno mediante la implementación de todos los requisitos previos, validando que las cargas de trabajo funcionan correctamente y según lo esperado y, a continuación, deshabilitar la deshabilitación de TLS 1.0/1.1 en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="40883-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="40883-271">Deshabilitar TLS 1,0 y 1,1 a través de importación de registro</span><span class="sxs-lookup"><span data-stu-id="40883-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="40883-272">Antes de continuar con los pasos siguientes, asegúrese de *haber completado todos los requisitos previos y los servidores actualizados de Skype empresarial*.</span><span class="sxs-lookup"><span data-stu-id="40883-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="40883-273">Copie el siguiente texto en un archivo del Bloc de notas y cambie el nombre a **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="40883-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="40883-274">Importe el archivo. reg en cada servidor en el que desee deshabilitar TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="40883-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="40883-275">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="40883-275">Reboot the server.</span></span> <span data-ttu-id="40883-276">Una vez que los servicios vuelvan a estar en línea, pase al siguiente servidor.</span><span class="sxs-lookup"><span data-stu-id="40883-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="40883-277">El enfoque para los grupos de servidores Enterprise Edition es el mismo que se realizaría para cualquier actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="40883-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="40883-278">Es posible que haya observado que estamos haciendo algo más que simplemente deshabilitar la TLS 1,0 y la 1,1 aquí.</span><span class="sxs-lookup"><span data-stu-id="40883-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="40883-279">Estamos admitiendo el reordenamiento del conjunto de cifrado (como se mostró anteriormente) y la deshabilitación de algunos de los cifrados débiles más antiguos.</span><span class="sxs-lookup"><span data-stu-id="40883-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="40883-280">Esta es la primera vez que hemos admitido oficialmente estos cambios en SCHANNEL y Crypto API en Skype empresarial Server, y es importante tener en cuenta que estos cambios son los únicos admitidos y que se han probado en este momento.</span><span class="sxs-lookup"><span data-stu-id="40883-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="40883-281">Es posible que considere configuraciones adicionales en el futuro, pero por ahora, no modifique el archivo de importación de registro en la implementación.</span><span class="sxs-lookup"><span data-stu-id="40883-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="40883-282">Validar que las cargas de trabajo funcionan según lo esperado</span><span class="sxs-lookup"><span data-stu-id="40883-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="40883-283">Una vez que se hayan deshabilitado los TLS 1,0 y 1,1 en el entorno, asegúrese de que todas las cargas de trabajo principales funcionan como se esperaba, como la mensajería instantánea & presencia, las llamadas P2P, la telefonía IP empresarial, etc.</span><span class="sxs-lookup"><span data-stu-id="40883-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="40883-284">**Validar que solo se use TLS 1,2**</span><span class="sxs-lookup"><span data-stu-id="40883-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="40883-285">Haga que el equipo de seguridad realice una nueva auditoría del tráfico de Skype empresarial para asegurarse de que los protocolos antiguos TLS 1,0 y 1,1 ya no se usan.</span><span class="sxs-lookup"><span data-stu-id="40883-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="40883-286">Como alternativa, puede usar Internet Explorer para probar las conexiones TLS a los servicios web desde Skype empresarial Server 2015 después de que se hayan deshabilitado TLS 1,0 y TLS 1,1.</span><span class="sxs-lookup"><span data-stu-id="40883-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="40883-287">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="40883-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="40883-288">Seleccione **herramientas** > **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="40883-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="40883-289">Seleccione la pestaña **avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="40883-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="40883-290">En **configuración**, desplácese hasta la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="40883-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="40883-291">Compruebe que están habilitados TLS 1,0, TLS 1,1 y TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="40883-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="40883-292">Examine la dirección URL del servicio Web interno del grupo de SfB 2015 (debe conectarse correctamente).</span><span class="sxs-lookup"><span data-stu-id="40883-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="40883-293">Vuelva a Internet Explorer y deshabilite la opción para **usar TLS 1,2** solamente.</span><span class="sxs-lookup"><span data-stu-id="40883-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="40883-294">Explore la dirección URL del servicio Web interno del grupo de SfB 2015 de nuevo (debe producirse un error de conexión).</span><span class="sxs-lookup"><span data-stu-id="40883-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opciones de Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="40883-296">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="40883-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="40883-297">Debido a que se necesitan algunos requisitos previos de dependencia para admitir TLS 1,2 en 2015 Skype empresarial, se producirá un error en la instalación desde medios de RTM en cualquier sistema en el que se hayan deshabilitado TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="40883-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="40883-298">**Implementar nuevos servidores Standard Edition o grupos de servidores Enterprise Edition una vez que se hayan deshabilitado TLS 1,0 y 1,1 en su entorno.**</span><span class="sxs-lookup"><span data-stu-id="40883-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="40883-299">**Opción 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="40883-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="40883-300">Tenga en cuenta que estamos actualizando SmartSetup para dar cabida a los archivos binarios de SQL actualizados en un CU posterior y se actualizará este artículo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="40883-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="40883-301">**Opción 2:** Preinstalar instancias locales de SQL (RTCLOCAL y LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="40883-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="40883-302">Descargue y copie SQL Express 2014 SP2 (SQLEXPR_x64. exe) en la carpeta local en FE.</span><span class="sxs-lookup"><span data-stu-id="40883-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="40883-303">Supongamos que la ruta de acceso a la carpeta <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="40883-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="40883-304">Inicie PowerShell o el símbolo del sistema y vaya a <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="40883-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="40883-305">Para crear la instancia de SQL de RTCLOCAL, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="40883-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="40883-306">Espere hasta que finalice SQLEXPR_x64. exe antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="40883-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="40883-307">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati</span><span class="sxs-lookup"><span data-stu-id="40883-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="40883-308">Para crear la instancia de SQL de LYNCLOCAL, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="40883-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="40883-309">Espere hasta que finalice SQLEXPR_x64. exe antes de continuar con el paso siguiente:</span><span class="sxs-lookup"><span data-stu-id="40883-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="40883-310">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="40883-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="40883-311">Ejecute el programa de instalación de Skype empresarial Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="40883-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="40883-312">Siga los pasos restantes de la sección requisitos previos anterior.</span><span class="sxs-lookup"><span data-stu-id="40883-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="40883-313">**Opción 3:** También puede reemplazar manualmente los archivos binarios en un directorio de medios de instalación local de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="40883-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="40883-314">Instalación de requisitos previos de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="40883-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="40883-315">Instale .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="40883-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="40883-316">**Nota:** Primero presentamos compatibilidad para .NET 4,7 en Skype empresarial Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="40883-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="40883-317">Por lo tanto, en los pasos posteriores que se indican a continuación, actualizaremos los componentes principales antes de la instalación principal.</span><span class="sxs-lookup"><span data-stu-id="40883-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="40883-318">Descargar: https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="40883-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="40883-319">Referencia: [software que debe instalarse antes de una implementación de Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="40883-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="40883-320">Copiar archivos o carpetas ISO:</span><span class="sxs-lookup"><span data-stu-id="40883-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="40883-321">Con la ISO adjunta de Skype empresarial Server 2015, abra el directorio raíz de la unidad en la que se ha adjuntado como\) (ej: D: en el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="40883-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="40883-322">Copie todas las carpetas y los archivos en una carpeta de un disco local (por ejemplo: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="40883-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="40883-323">**Nota:** Antes de instalar componentes, será necesario actualizar algunos archivos para admitir TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="40883-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="40883-324">Reemplazar paquetes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="40883-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="40883-325">Reemplace los paquetes MSI y EXE existentes en la carpeta/SETUP/AMD64/de los medios de instalación en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="40883-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="40883-326">SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="40883-326">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="40883-327">Cambie el nombre a SQLEXPR_x64 en el equipo local y reemplace el archivo existente en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="40883-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="40883-328">SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="40883-328">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="40883-329">**Nota:** Cambie el nombre si es necesario a SQLNCLI. msi y, a continuación, reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="40883-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="40883-330">Objetos de administración de SQL:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="40883-330">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="40883-331">**Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="40883-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="40883-332">Seleccione solo para descargar SharedManagementObjects. msi.</span><span class="sxs-lookup"><span data-stu-id="40883-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="40883-333">**Nota:** Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="40883-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="40883-334">Tipos de SQL CLR:https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="40883-334">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="40883-335">**Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="40883-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="40883-336">Seleccione esta selección para descargar sólo CQLSysClrTypes. msi</span><span class="sxs-lookup"><span data-stu-id="40883-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="40883-337">**Nota**: Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="40883-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="40883-338">Instale los componentes principales:</span><span class="sxs-lookup"><span data-stu-id="40883-338">Install Core Components:</span></span> 
    - <span data-ttu-id="40883-339">Ejecute setup. exe desde la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="40883-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="40883-340">Siga las instrucciones para instalar los componentes principales</span><span class="sxs-lookup"><span data-stu-id="40883-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="40883-341">Cierre los componentes principales.</span><span class="sxs-lookup"><span data-stu-id="40883-341">Close Core Components.</span></span>
6. <span data-ttu-id="40883-342">Actualizar componentes principales:</span><span class="sxs-lookup"><span data-stu-id="40883-342">Update Core Components:</span></span> 
    - <span data-ttu-id="40883-343">Descargue el instalador de la actualización de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="40883-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="40883-344">Ejecute el instalador para actualizar los componentes principales e instalar los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="40883-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="40883-345">**Nota:** A partir de la versión de CU6HF2, la característica de actualización automática solo se instala actualmente hasta CU6.</span><span class="sxs-lookup"><span data-stu-id="40883-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="40883-346">Por lo tanto, el actualizador debe ejecutarse por separado para actualizar los componentes principales a 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="40883-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="40883-347">Referenciashttps://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="40883-347">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="40883-348">Instalar herramientas administrativas (opcional):</span><span class="sxs-lookup"><span data-stu-id="40883-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="40883-349">Se instalarán Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) y Microsoft System CLR Types for SQL Server 2014 (x64) con los archivos actualizados.</span><span class="sxs-lookup"><span data-stu-id="40883-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="40883-350">Además, el generador de topologías y el panel de control de Skype empresarial Server 2015 estarán disponibles en la máquina local.</span><span class="sxs-lookup"><span data-stu-id="40883-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="40883-351">Instale el almacén de configuración local (paso 1):</span><span class="sxs-lookup"><span data-stu-id="40883-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="40883-352">Abra el Asistente para la implementación, haga clic en instalar o actualizar el sistema de Skype empresarial Server y, a continuación, haga clic en **Ejecutar** en el paso 1: instalar el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="40883-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="40883-353">Haga clic en **siguiente** en el cuadro de diálogo **instalar almacén de configuración local** .</span><span class="sxs-lookup"><span data-stu-id="40883-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="40883-354">![Cuadro de diálogo instalar el almacén de configuración local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="40883-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="40883-355">Revise los resultados y asegúrese de que el estado de la tarea es completada.</span><span class="sxs-lookup"><span data-stu-id="40883-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="40883-356">Revise el archivo de registro resultante; para ello, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="40883-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="40883-357">![El estado de la tarea muestra como completado](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="40883-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="40883-358">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="40883-358">Click **Finish**.</span></span>
9. <span data-ttu-id="40883-359">Configurar o quitar componentes de Skype empresarial Server (paso 2):</span><span class="sxs-lookup"><span data-stu-id="40883-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="40883-360">Abra el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**y, a continuación, haga clic en **Ejecutar** en el paso 2: configurar o quitar componentes de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="40883-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="40883-361">Haga clic en **siguiente** en el cuadro de diálogo Configurar componentes de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="40883-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="40883-362">![la ventana Configurar componentes de Skype empresarial Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="40883-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="40883-363">Revise el registro mediante Ver registro y compruebe que la instalación se ha completado sin problemas.</span><span class="sxs-lookup"><span data-stu-id="40883-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="40883-364">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="40883-364">Click **Finish**.</span></span>
10. <span data-ttu-id="40883-365">Continúe con la instalación y la configuración adicionales según sea necesario (puede reanudar los procedimientos de instalación normales en este momento).</span><span class="sxs-lookup"><span data-stu-id="40883-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
