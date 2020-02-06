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
ms.openlocfilehash: 691dcc170830b3efa6129d23401930fcf1c149cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817151"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="18559-103">Deshabilitar TLS 1.0/1.1 en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="18559-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="18559-104">El propósito de este artículo es proporcionar la orientación necesaria para preparar e implementar la deshabilitación de TLS 1,0 y 1,1 en sus entornos.</span><span class="sxs-lookup"><span data-stu-id="18559-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="18559-105">Este proceso requiere una extensa planificación y preparación.</span><span class="sxs-lookup"><span data-stu-id="18559-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="18559-106">Revise atentamente toda la información de este artículo a medida que realiza su plan para deshabilitar TLS 1,0 y 1,1 para su organización.</span><span class="sxs-lookup"><span data-stu-id="18559-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="18559-107">Tenga en cuenta que existen muchas dependencias externas y condiciones de conectividad que pueden verse afectadas por la deshabilitación de TLS 1.0/1.1 para garantizar una planificación y pruebas amplias.</span><span class="sxs-lookup"><span data-stu-id="18559-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="18559-108">En este artículo</span><span class="sxs-lookup"><span data-stu-id="18559-108">In this article</span></span>

- [<span data-ttu-id="18559-109">Fondo y ámbito</span><span class="sxs-lookup"><span data-stu-id="18559-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="18559-110">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="18559-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="18559-111">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="18559-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="18559-112">Información general</span><span class="sxs-lookup"><span data-stu-id="18559-112">Background</span></span>

<span data-ttu-id="18559-113">Los drivers principales para proporcionar TLS 1,0 y 1,1 deshabilitar el soporte para Skype empresarial Server local son los requisitos del Consejo de estándares de seguridad de la industria de las tarjetas de pago (PCI) y los estándares federales de procesamiento de información.</span><span class="sxs-lookup"><span data-stu-id="18559-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="18559-114">Puede encontrar más información sobre los requisitos de PCI [aquí](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="18559-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="18559-115">Microsoft no puede proporcionar instrucciones sobre si su organización debe cumplir con estos u otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="18559-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="18559-116">Debe determinar si es necesario para deshabilitar TLS 1,0 o 1,1 en sus entornos.</span><span class="sxs-lookup"><span data-stu-id="18559-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="18559-117">Microsoft ha creado un documento sobre TLS disponible [aquí](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), y también recomendamos la lectura en segundo plano disponible en este [blog de Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="18559-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="18559-118">Ámbito de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="18559-118">Supportability Scope</span></span>

<span data-ttu-id="18559-119">El *ámbito* se refiere a los límites de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="18559-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="18559-120">*Completamente probado y admitido* significa que hemos admitido completamente la deshabilitación de las versiones de los productos de TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="18559-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="18559-121">*Actualmente investigado* significa eso; Estamos investigando de forma activa el alcance de estos productos para la compatibilidad con la desactivación de TLS.</span><span class="sxs-lookup"><span data-stu-id="18559-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="18559-122">*Fuera del ámbito* significa que estas versiones de producto no admiten la deshabilitación de TLS 1,0 o 1,1 y no funcionarán, con las excepciones indicadas.</span><span class="sxs-lookup"><span data-stu-id="18559-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="18559-123">Servidores totalmente probados y admitidos</span><span class="sxs-lookup"><span data-stu-id="18559-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="18559-124">Skype empresarial Server 2019 CU1 17.0.2046.123 (2019 de junio) o superior</span><span class="sxs-lookup"><span data-stu-id="18559-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="18559-125">Skype empresarial Server 2015 CU9 6.0.9319.548 (mayo 2019) o versiones posteriores en Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización que reemplaza), 2012 R2 o 2016.</span><span class="sxs-lookup"><span data-stu-id="18559-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="18559-126">Actualización local de Skype para empresas Server 2015, con CU9 6.0.9319.548 (mayo 2019) o superior en Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o reemplazando la actualización) o 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="18559-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="18559-127">Conectividad de Exchange y Outlook Web App con Exchange Server 2010 SP3 RU19 o versiones posteriores, guía [aquí](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="18559-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="18559-128">Dispositivo de rama superviviente (SBA) con Skype empresarial Server 2015 CU6 HF2 o superior (confirme con su proveedor que han embalado las actualizaciones de Appropiate y que están disponibles para su dispositivo)</span><span class="sxs-lookup"><span data-stu-id="18559-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="18559-129">Servidor de sucursal (SBS) superviviente con Skype empresarial Server 2015 CU6 HF2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="18559-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="18559-130">**Solo rol de Edge**de Lync Server 2013, esto se debe a que el rol de Edge no tiene una dependencia en Windows fabric 1,0.</span><span class="sxs-lookup"><span data-stu-id="18559-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="18559-131">Clientes totalmente probados y admitidos</span><span class="sxs-lookup"><span data-stu-id="18559-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="18559-132">Cliente de escritorio de Lync 2013 (Skype empresarial), MSI y C2R, que incluye Basic [15.0.5023.1000 o superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="18559-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="18559-133">Cliente de escritorio de Skype empresarial 2016, MSI [16.0.4678.1000 o superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluido básico</span><span class="sxs-lookup"><span data-stu-id="18559-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="18559-134">Skype empresarial 2016 hacer clic para ejecutarse requiere las actualizaciones de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="18559-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="18559-135">Con objetivo mensual y semianual, 16\.0\.9126\.2152 o superior</span><span class="sxs-lookup"><span data-stu-id="18559-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="18559-136">Canal semianual y diferido, 16\.0\.8431\.2242 o superior</span><span class="sxs-lookup"><span data-stu-id="18559-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="18559-137">Skype empresarial en Mac 16,15 o superior</span><span class="sxs-lookup"><span data-stu-id="18559-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="18559-138">Skype empresarial para iOS y Android 6,19 o superior</span><span class="sxs-lookup"><span data-stu-id="18559-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="18559-139">Salas de Microsoft Teams (anteriormente conocido como Skype Room System V2, SRS V2) 4.0.64.0 (2018 de diciembre) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="18559-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="18559-140">Actualización de Surface hub para Team Edition basada en KB4499162 (2019, OS compilación 15063,1835) o superior</span><span class="sxs-lookup"><span data-stu-id="18559-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="18559-141">Skype Web App 2015 CU6 HF2 o superior (se incluye en el servidor)</span><span class="sxs-lookup"><span data-stu-id="18559-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="18559-142">Investigando en este momento</span><span class="sxs-lookup"><span data-stu-id="18559-142">Currently being investigated</span></span>

- <span data-ttu-id="18559-143">Panel de calidad de llamadas (nueva instalación después de que se haya deshabilitado TLS 1,0, 1,1, consulte a continuación) \*</span><span class="sxs-lookup"><span data-stu-id="18559-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="18559-144">Fuera del ámbito</span><span class="sxs-lookup"><span data-stu-id="18559-144">Out of scope</span></span>

<span data-ttu-id="18559-145">Excepto donde se indique lo contrario, los siguientes productos no están en el ámbito de TLS 1.0/1.1 deshabilitar el soporte técnico y no funcionarán en un entorno en el que se hayan deshabilitado TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="18559-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="18559-146">Qué significa: Si aún usa clientes o servidores fuera del ámbito, debe actualizarlos o eliminarlos si necesita deshabilitar TLS 1.0/1.1 en cualquier lugar de su implementación local de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="18559-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="18559-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18559-147">Lync Server 2013</span></span>
- <span data-ttu-id="18559-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="18559-148">Lync Server 2010</span></span>
- <span data-ttu-id="18559-149">Windows Server 2008 o inferior</span><span class="sxs-lookup"><span data-stu-id="18559-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="18559-150">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="18559-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="18559-151">Lync 2013 para móvil: iOS, iPad, Android o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="18559-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="18559-152">Cliente de la tienda Windows "MX" de Lync</span><span class="sxs-lookup"><span data-stu-id="18559-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="18559-153">Sistema de sala de Lync (también conocido como</span><span class="sxs-lookup"><span data-stu-id="18559-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="18559-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="18559-154">SRSv1).</span></span> <span data-ttu-id="18559-155">LRS alcanzó el final del 9 de octubre de 2018 y no se actualizará para admitir TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="18559-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="18559-156">Todos los clientes de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="18559-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="18559-157">Lync Phone Edition: Guía actualizada [aquí](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="18559-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="18559-158">Equipo de sucursal basado en 2013 (SBA) o servidor de sucursal superviviente (SBS)</span><span class="sxs-lookup"><span data-stu-id="18559-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="18559-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="18559-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="18559-160">Skype Empresarial para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="18559-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="18559-161">Excepciones</span><span class="sxs-lookup"><span data-stu-id="18559-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="18559-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18559-162">Lync Server 2013</span></span>

<span data-ttu-id="18559-163">Lync Server 2013 toma una dependencia en Windows fabric versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="18559-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="18559-164">En la fase de diseño de Lync Server 2013, se escogió Windows fabric 1,0 para su nueva arquitectura distribuida y atractiva para proporcionar replicación, alta disponibilidad y tolerancia a errores.</span><span class="sxs-lookup"><span data-stu-id="18559-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="18559-165">Con el tiempo, tanto Skype empresarial Server como Windows fabric han mejorado enormemente esta arquitectura conjunta con un rediseño significativo en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="18559-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="18559-166">El servidor actual de Skype empresarial 2015 usa Windows fabric 3,0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="18559-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="18559-167">Lamentablemente, Windows fabric 1,0 **no es compatible con TLS 1,2.  Sin embargo, actualizaremos Lync Server 2013 para que funcione con TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="18559-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="18559-168">Esto estará disponible en la siguiente actualización acumulativa para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18559-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="18559-169">Proporcionamos compatibilidad con TLS 1,2 para habilitar escenarios de coexistencia, migración, Federación y híbrida.</span><span class="sxs-lookup"><span data-stu-id="18559-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="18559-170">Si su organización tiene que deshabilitar TLS 1,0 y 1,1 y actualmente usa Lync Server 2013, le recomendamos que comience su proceso de planeación, con la posibilidad de que tenga que realizar una actualización local o una migración en paralelo (nuevos grupos, mover usuarios) a Skype para Business Server 2015 o superior.</span><span class="sxs-lookup"><span data-stu-id="18559-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="18559-171">O bien, es posible que desee acelerar la migración a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="18559-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="18559-172">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="18559-172">Call Quality Dashboard</span></span>

<span data-ttu-id="18559-173">El panel de calidad de llamadas local actualmente tiene una dependencia de TLS 1,0 durante la nueva instalación (la primera vez que se instala en entornos locales).</span><span class="sxs-lookup"><span data-stu-id="18559-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="18559-174">Actualmente estamos investigando este problema y tenemos previsto publicar una corrección en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="18559-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="18559-175">Si tiene previsto instalar el CQD y también deshabilitar TLS 1,0, le recomendamos que complete primero la instalación del CQD y, a continuación, continúe con la desactivación de TLS 1,0.</span><span class="sxs-lookup"><span data-stu-id="18559-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="18559-176">Dispositivos de terceros</span><span class="sxs-lookup"><span data-stu-id="18559-176">Third-party devices</span></span>

<span data-ttu-id="18559-177">En dispositivos de terceros, como teléfonos 3PIP, videoconferencias, proxies inversos y equilibradores de carga, asegúrese de validar la compatibilidad con TLS 1,2, realizar pruebas con cuidado y póngase en contacto con el proveedor si es necesario.</span><span class="sxs-lookup"><span data-stu-id="18559-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="18559-178">Consideraciones sobre la Federación al deshabilitar TLS 1.0/1.1 en servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="18559-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="18559-179">Debe planificar cuidadosamente y considerar el impacto de la deshabilitación de TLS 1.0/1.1 en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="18559-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="18559-180">Una vez que TLS 1,0 y 1,1 estén deshabilitados, es posible que vea que otras organizaciones ya no pueden federarse con su organización.</span><span class="sxs-lookup"><span data-stu-id="18559-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="18559-181">Puede optar por mantener TLS 1.0/1.1 habilitado en los servidores perimetrales para mantener la compatibilidad con los sistemas externos no revisados (SfB 2015, Lync 2013) o versiones anteriores (2010).</span><span class="sxs-lookup"><span data-stu-id="18559-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="18559-182">Microsoft no puede proporcionar asesoramiento ni recomendaciones sobre si su red perimetral (o cualquier red) está bajo el estándar PCI; que debe determinar la empresa individual.</span><span class="sxs-lookup"><span data-stu-id="18559-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="18559-183">Skype empresarial online es capaz de TLS 1,2 hoy, así que no se espera ninguna repercusión en la híbrida o la Federación con conexión.</span><span class="sxs-lookup"><span data-stu-id="18559-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="18559-184">PIC (conectividad de mensajería instantánea pública) para el servicio de consumidores de Skype: no esperamos que la deshabilitación de TLS 1.0/1.1 afecte a la [conectividad de Skype](../../deploy/deploy-skype-connectivity.md); Las puertas de enlace de Microsoft PIC ya son compatibles con TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="18559-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="18559-185">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="18559-185">Prerequisites and process</span></span>

<span data-ttu-id="18559-186">Excepto cuando se indique lo mencionado anteriormente, una vez que los servidores TLS 1,0 y 1,1 estén deshabilitados fuera de ámbito, los clientes y dispositivos dejarán de funcionar correctamente o en todo momento.</span><span class="sxs-lookup"><span data-stu-id="18559-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="18559-187">Esto puede significar que debes pausar y esperar la orientación actualizada de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18559-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="18559-188">Una vez que esté satisfecho con todos los requisitos y tenga un plan para abordar las brechas, continúe.</span><span class="sxs-lookup"><span data-stu-id="18559-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="18559-189">En un nivel alto, mientras Skype empresarial Server 2019 está listo para su procedimiento en la instalación, Skype empresarial Server 2015 requerirá que instale CU9, aplique las actualizaciones de requisitos previos a .NET y SQL, implementando las claves de registro de requisitos previos y, por último, una el redondeo de las actualizaciones de configuración del sistema operativo (es decir, deshabilitar TLS 1,0 y 1,1 a través de la importación de archivos de registro).</span><span class="sxs-lookup"><span data-stu-id="18559-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="18559-190">Es muy importante que complete la instalación de todos los requisitos previos, incluyendo Skype empresarial Server 2015 CU6 HF2, antes de deshabilitar TLS 1,0 y 1,1 en cualquier servidor de su entorno.</span><span class="sxs-lookup"><span data-stu-id="18559-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="18559-191">Todos los servidores de Skype empresarial, incluidos el rol perimetral y los extremos SQL, requieren las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="18559-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="18559-192">Asegúrese también de que todos los clientes compatibles (dentro del ámbito) se hayan actualizado a las versiones mínimas necesarias.</span><span class="sxs-lookup"><span data-stu-id="18559-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="18559-193">No se olvide de actualizar también las estaciones de trabajo de administración.</span><span class="sxs-lookup"><span data-stu-id="18559-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="18559-194">Queremos seguir el orden habitual de las operaciones de "Inside Out" para actualizar los servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="18559-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="18559-195">Tratar los pools de directores, los chats persistentes y los grupos emparejados de la misma manera que lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="18559-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="18559-196">El orden y los métodos de actualización se tratan [aquí](topology.md) y [aquí](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="18559-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="18559-197">Proceso de alto nivel</span><span class="sxs-lookup"><span data-stu-id="18559-197">High-level process</span></span>

1. <span data-ttu-id="18559-198">Pruebe todos los pasos de su laboratorio antes de configurar los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="18559-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="18559-199">Realice una copia de seguridad y conserve una copia del registro exportado en cada servidor individual que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="18559-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="18559-200">No puede compartir registros entre servidores; contienen claves únicas basadas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="18559-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="18559-201">Actualiza todos los servidores de Skype empresarial 2015 a CU9 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="18559-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="18559-202">Para Skype empresarial Server 2019, Actualícese a CU1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="18559-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="18559-203">Instale todos los requisitos previos para todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="18559-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="18559-204">Implementar claves de registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="18559-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="18559-205">Asegúrese de que se actualizan todos los clientes dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="18559-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="18559-206">Deshabilite TLS 1,0 y 1,1 a través de importación de registro.</span><span class="sxs-lookup"><span data-stu-id="18559-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="18559-207">Valide que las cargas de trabajo funcionen según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="18559-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="18559-208">Si se producen problemas, solucionar problemas y resolverlos, o bien</span><span class="sxs-lookup"><span data-stu-id="18559-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="18559-209">Restaurar el registro del paso 2 para volver a habilitar TLS 1,0 y 1,1</span><span class="sxs-lookup"><span data-stu-id="18559-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="18559-210">Valide que solo se use TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="18559-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="18559-211">Instalar los requisitos previos para todos los servidores</span><span class="sxs-lookup"><span data-stu-id="18559-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="18559-212">Es necesario actualizar las dependencias extensas antes de empezar a deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo en las implementaciones de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="18559-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="18559-213">A continuación se muestran las versiones mínimas que pueden admitir TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="18559-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="18559-214">Implemente todas las actualizaciones de requisitos previos en todos los servidores de Skype empresarial en su entorno antes de deshabilitar TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="18559-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="18559-215">Skype empresarial Server 2015 CU9 6.0.9319.548 (mayo 2019) o superior</span><span class="sxs-lookup"><span data-stu-id="18559-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="18559-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) o superior con SchUseStrongCrypto habilitado en el registro (proporcionado a continuación)</span><span class="sxs-lookup"><span data-stu-id="18559-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="18559-217">SQL debe actualizarse en todos los servidores y servidores de la versión 2015 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="18559-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="18559-218">Actualice en primer lugar SQL del grupo de servidores Enterprise Edition y luego sus respectivos FEs.</span><span class="sxs-lookup"><span data-stu-id="18559-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="18559-219">[SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)o superior/sql server 2012 SP2 + CU16 o superior/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)o superior/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="18559-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="18559-220">SQL Server Native Client para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="18559-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="18559-221">[Microsoft ODBC driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)o superior</span><span class="sxs-lookup"><span data-stu-id="18559-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="18559-222">Objetos de administración compartida para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="18559-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="18559-223">SQLSysClrTypes para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="18559-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="18559-224">Pasos básicos para instalar requisitos previos, en el orden recomendado de operaciones</span><span class="sxs-lookup"><span data-stu-id="18559-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="18559-225">Instale la actualización de CU9 de Skype empresarial Server en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="18559-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="18559-226">Instale la actualización de los componentes con el actualizador.</span><span class="sxs-lookup"><span data-stu-id="18559-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="18559-227">Actualice las bases de datos de acuerdo con procedimientos documentados.</span><span class="sxs-lookup"><span data-stu-id="18559-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="18559-228">Para Skype empresarial Server 2015, consulte KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="18559-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="18559-229">Validar la funcionalidad del producto en la implementación antes de continuar con cualquier otro cambio.</span><span class="sxs-lookup"><span data-stu-id="18559-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="18559-230">Descargue el instalador sin conexión de .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="18559-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="18559-231">Reference[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="18559-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="18559-232">Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="18559-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="18559-233">Reference[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="18559-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="18559-234">Ex (edición estándar):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="18559-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="18559-235">Ex (edición empresarial):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="18559-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="18559-236">Ejecute el paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="18559-236">Run the installer package.</span></span>
    7. <span data-ttu-id="18559-237">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="18559-237">Reboot the server.</span></span>
3. <span data-ttu-id="18559-238">Actualice SQL Express 2014 en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="18559-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="18559-239">Reference[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="18559-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="18559-240">Descargar SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="18559-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="18559-241">Reference[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="18559-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="18559-242">Copie los medios de instalación a una carpeta en el servidor (ejemplo: C:\ 01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="18559-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="18559-243">Asegurarse de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end</span><span class="sxs-lookup"><span data-stu-id="18559-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="18559-244">Ex (edición estándar):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="18559-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="18559-245">Ex (edición empresarial):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="18559-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="18559-246">Abrir un símbolo del sistema de administrador y actualizar todos los componentes e instancias instalados</span><span class="sxs-lookup"><span data-stu-id="18559-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="18559-247">Ejemplo: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/Action = patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="18559-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="18559-248">Actualice SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="18559-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="18559-249">Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="18559-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="18559-250">Descargar de[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="18559-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="18559-251">Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="18559-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="18559-252">Ex (edición estándar):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="18559-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="18559-253">Ex (edición empresarial):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="18559-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="18559-254">Detener la ejecución de las instancias de SQL instaladas</span><span class="sxs-lookup"><span data-stu-id="18559-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="18559-255">Posterior```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="18559-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="18559-256">Posterior```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="18559-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="18559-257">Ex (solo en Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="18559-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="18559-258">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="18559-258">Install the update.</span></span>
5. <span data-ttu-id="18559-259">Actualice ODBC driver 11 for SQL Server para que incluya compatibilidad con TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="18559-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="18559-260">Descargue [ODBC driver 11 for SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="18559-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="18559-261">Asegúrese de que los servicios de Skype empresarial Server 2015 se detienen en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="18559-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="18559-262">Ejemplo (edición estándar):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="18559-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="18559-263">Ejemplo (edición Enterprise):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="18559-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="18559-264">Instale la actualización.</span><span class="sxs-lookup"><span data-stu-id="18559-264">Install the update.</span></span>
6. <span data-ttu-id="18559-265">Implementar claves de registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="18559-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="18559-266">Claves de registro de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="18559-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="18559-267">Copie/pegue la prueba siguiente en el Bloc de notas y cambie el nombre a TLSPreReq. reg o un nombre de su elección, a continuación, importe:</span><span class="sxs-lookup"><span data-stu-id="18559-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="18559-268">Para los back-end de SQL para los grupos de Enterprise Edition, los requisitos previos y la desactivación de TLS deberían tratarse como cualquier otra actualización de SQL o OS; Consulte:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="18559-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="18559-269">Aunque se pueden combinar los pasos de la aplicación previa y la deshabilitación de TLS, recomendamos encarecidamente que se apliquen todos los requisitos previos antes de deshabilitar TLS 1,0 y 1,1 en el nivel del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="18559-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="18559-270">El enfoque más práctico sería preparar el entorno mediante la implementación de todos los requisitos previos, la validación de que todas las cargas de trabajo funcionan correctamente y de la manera esperada, y, a continuación, deshabilitar la desactivación de TLS 1.0/1.1 más adelante.</span><span class="sxs-lookup"><span data-stu-id="18559-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="18559-271">Deshabilitar TLS 1,0 y 1,1 a través de importación de registro</span><span class="sxs-lookup"><span data-stu-id="18559-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="18559-272">Antes de continuar con los pasos siguientes, asegúrese de *que ha completado todos los requisitos previos y los servidores actualizados de Skype empresarial*.</span><span class="sxs-lookup"><span data-stu-id="18559-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="18559-273">Copie el texto siguiente en un archivo del Bloc de notas y cambie el nombre a **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="18559-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="18559-274">Importe el archivo. reg en cada servidor en el que desee deshabilitar TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="18559-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="18559-275">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="18559-275">Reboot the server.</span></span> <span data-ttu-id="18559-276">Una vez que los servicios se vuelvan a conectar, pasa al siguiente servidor.</span><span class="sxs-lookup"><span data-stu-id="18559-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="18559-277">El enfoque para los grupos de Enterprise Edition es el mismo que haría para cualquier actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="18559-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="18559-278">Es posible que haya observado que estamos haciendo algo más que simplemente deshabilitar TLS 1,0 y 1,1 aquí.</span><span class="sxs-lookup"><span data-stu-id="18559-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="18559-279">Hemos admitido el reorden de conjuntos de cifrado (como se muestra arriba) y la desactivación de algunos cifrados débiles más antiguos.</span><span class="sxs-lookup"><span data-stu-id="18559-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="18559-280">Esta es la primera vez que hemos admitido oficialmente estos cambios en SCHANNEL y Crypto API en Skype empresarial Server, y es importante tener en cuenta que estos cambios son los únicos que admitimos y que hemos probado en este momento.</span><span class="sxs-lookup"><span data-stu-id="18559-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="18559-281">Es posible que consideres configuraciones adicionales en el futuro, pero por ahora, no modifiques el archivo de importación de registro en la implementación.</span><span class="sxs-lookup"><span data-stu-id="18559-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="18559-282">Validar que las cargas de trabajo funcionen según lo esperado</span><span class="sxs-lookup"><span data-stu-id="18559-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="18559-283">Una vez que TLS 1,0 y 1,1 se hayan deshabilitado en su entorno, asegúrese de que todas las cargas de trabajo principales funcionen de la manera esperada, como la mensajería instantánea & presencia, las llamadas P2P, la telefonía IP empresarial, etc.</span><span class="sxs-lookup"><span data-stu-id="18559-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="18559-284">**Validar que solo se use TLS 1,2**</span><span class="sxs-lookup"><span data-stu-id="18559-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="18559-285">Haga que su equipo de seguridad realice una nueva auditoría del tráfico de Skype empresarial para asegurarse de que los protocolos antiguos TLS 1,0 y 1,1 ya no se usan.</span><span class="sxs-lookup"><span data-stu-id="18559-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="18559-286">Como alternativa, puede usar Internet Explorer para probar las conexiones TLS con los servicios Web de Skype empresarial Server 2015 después de que se haya deshabilitado TLS 1,0 y TLS 1,1.</span><span class="sxs-lookup"><span data-stu-id="18559-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="18559-287">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="18559-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="18559-288">Seleccione **herramientas** > **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="18559-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="18559-289">Seleccione la pestaña **avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="18559-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="18559-290">En **configuración**, desplácese hasta la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="18559-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="18559-291">Compruebe que las TLS 1,0, TLS 1,1 y TLS 1,2 estén habilitadas.</span><span class="sxs-lookup"><span data-stu-id="18559-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="18559-292">Examine la dirección URL del servicio Web interno del grupo de SfB 2015 (debe conectarse correctamente).</span><span class="sxs-lookup"><span data-stu-id="18559-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="18559-293">Vuelva a Internet Explorer y deshabilite la opción para **usar TLS 1,2** solo.</span><span class="sxs-lookup"><span data-stu-id="18559-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="18559-294">Vuelva a examinar la dirección URL del servicio Web interno de su grupo de SfB 2015 (no se puede conectar).</span><span class="sxs-lookup"><span data-stu-id="18559-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opciones de Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="18559-296">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="18559-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="18559-297">Debido a que se necesitan algunos requisitos previos de dependencia para admitir TLS 1,2 en Skype empresarial para 2015, la instalación desde medios de RTM fallará en cualquier sistema donde se hayan deshabilitado TLS 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="18559-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="18559-298">**Implementar nuevos servidores Standard Edition o grupos de servidores Enterprise Edition una vez que se hayan deshabilitado TLS 1,0 y 1,1 en su entorno.**</span><span class="sxs-lookup"><span data-stu-id="18559-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="18559-299">**Opción 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="18559-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="18559-300">Tenga en cuenta que estamos actualizando SmartSetup para dar cabida a los binarios de SQL actualizados en una CU futura, y Actualizaremos este artículo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="18559-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="18559-301">**Opción 2:** Anteriores a la instalación de instancias locales de SQL (RTCLOCAL y LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="18559-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="18559-302">Descargue y copie SQL Express 2014 SP2 (SQLEXPR_x64. exe) en la carpeta local de FE.</span><span class="sxs-lookup"><span data-stu-id="18559-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="18559-303">Supongamos que la ruta de acceso a la carpeta <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="18559-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="18559-304">Inicie PowerShell o símbolo del sistema y vaya a <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="18559-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="18559-305">Para crear la instancia de SQL RTCLOCAL, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="18559-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="18559-306">Espere hasta que finalice SQLEXPR_x64. exe antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="18559-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="18559-307">SQLEXPR_x64. exe/q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/Action = install/Features = SQLEngine, Tools/InstanceName = RTCLOCAL/TCPENABLED =,/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "BUILTIN\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = auto</span><span class="sxs-lookup"><span data-stu-id="18559-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="18559-308">Para crear la instancia de SQL LYNCLOCAL, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="18559-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="18559-309">Espere hasta que finalice SQLEXPR_x64. exe antes de continuar con el siguiente paso:</span><span class="sxs-lookup"><span data-stu-id="18559-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="18559-310">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED =,/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="18559-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="18559-311">Ejecute el programa de instalación de Skype empresarial Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="18559-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="18559-312">Siga los pasos restantes de la sección requisitos previos anterior.</span><span class="sxs-lookup"><span data-stu-id="18559-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="18559-313">**Opción 3:** También puede reemplazar manualmente los binarios en un directorio de medios de instalación local de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="18559-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="18559-314">Instalar los requisitos previos de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="18559-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="18559-315">Instale .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="18559-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="18559-316">**Nota:** En primer lugar, presentamos la compatibilidad con .NET 4,7 en Skype empresarial Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="18559-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="18559-317">Por lo tanto, en los pasos posteriores siguientes actualizaremos los componentes principales antes de la instalación principal.</span><span class="sxs-lookup"><span data-stu-id="18559-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="18559-318">Descargar: https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="18559-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="18559-319">Referencia: [software que debe instalarse antes de una implementación de Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="18559-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="18559-320">Copiar archivos o carpetas ISO:</span><span class="sxs-lookup"><span data-stu-id="18559-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="18559-321">Con la conexión ISO de Skype empresarial Server 2015, abra el directorio raíz de la unidad a la que se ha adjuntado (\) por ejemplo: D: en el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="18559-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="18559-322">Copie todas las carpetas y archivos en una carpeta de un disco local (p. ej.: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="18559-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="18559-323">**Nota:** Antes de instalar componentes, será necesario actualizar algunos archivos para admitir TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="18559-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="18559-324">Reemplazar paquetes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="18559-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="18559-325">Sustituya los paquetes MSI y EXE existentes en la carpeta/SETUP/AMD64/de los medios de instalación de la máquina local.</span><span class="sxs-lookup"><span data-stu-id="18559-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="18559-326">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="18559-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="18559-327">Cambie el nombre a SQLEXPR_x64 en la máquina local y reemplace el archivo existente en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="18559-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="18559-328">Cliente SQL Native:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="18559-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="18559-329">**Nota:** Cambie el nombre si es necesario a SQLNCLI. msi y, a continuación, reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="18559-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="18559-330">Objetos de administración de SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="18559-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="18559-331">**Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="18559-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="18559-332">Seleccione esta para descargar solo SharedManagementObjects. msi.</span><span class="sxs-lookup"><span data-stu-id="18559-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="18559-333">**Nota:** Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="18559-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="18559-334">Tipos de SQL CLR:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="18559-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="18559-335">**Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="18559-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="18559-336">Seleccione para descargar solo CQLSysClrTypes. msi.</span><span class="sxs-lookup"><span data-stu-id="18559-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="18559-337">**Nota**: Reemplace el archivo existente que existe en la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="18559-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="18559-338">Instalar componentes básicos:</span><span class="sxs-lookup"><span data-stu-id="18559-338">Install Core Components:</span></span> 
    - <span data-ttu-id="18559-339">Ejecute setup. exe desde la carpeta SETUP/AMD64/de los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="18559-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="18559-340">Siga las instrucciones para instalar los componentes principales</span><span class="sxs-lookup"><span data-stu-id="18559-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="18559-341">Cierre los componentes principales.</span><span class="sxs-lookup"><span data-stu-id="18559-341">Close Core Components.</span></span>
6. <span data-ttu-id="18559-342">Actualizar componentes básicos:</span><span class="sxs-lookup"><span data-stu-id="18559-342">Update Core Components:</span></span> 
    - <span data-ttu-id="18559-343">Descargar el instalador de actualización de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="18559-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="18559-344">Ejecute el instalador para actualizar los componentes principales e instale los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="18559-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="18559-345">**Nota:** A partir de la versión de CU6HF2, la característica de actualización automática solo se instalará actualmente hasta CU6.</span><span class="sxs-lookup"><span data-stu-id="18559-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="18559-346">Por lo tanto, el actualizador debe ejecutarse por separado para actualizar los componentes principales a 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="18559-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="18559-347">Referencehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="18559-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="18559-348">Instalar herramientas administrativas (opcional):</span><span class="sxs-lookup"><span data-stu-id="18559-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="18559-349">Esto instalará el cliente nativo de Microsoft SQL Server 2012, los objetos de administración de SQL Server 2014 (x64) y los tipos CLR del sistema de Microsoft para SQL Server 2014 (x64) con los archivos actualizados.</span><span class="sxs-lookup"><span data-stu-id="18559-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="18559-350">Además, el generador de topología y el panel de control de Skype empresarial Server 2015 estarán disponibles en la máquina local.</span><span class="sxs-lookup"><span data-stu-id="18559-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="18559-351">Instalar el almacén de configuración local (paso 1):</span><span class="sxs-lookup"><span data-stu-id="18559-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="18559-352">Abra el Asistente para la implementación, haga clic en instalar o actualizar el sistema de Skype empresarial Server y haga clic en **Ejecutar** en el paso 1: instalar el almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="18559-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="18559-353">Haga clic en **siguiente** en el cuadro de diálogo **instalar el almacén de configuración local** .</span><span class="sxs-lookup"><span data-stu-id="18559-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="18559-354">![Cuadro de diálogo instalar el almacén de configuración local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="18559-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="18559-355">Revise los resultados y asegúrese de que el estado de la tarea es completada.</span><span class="sxs-lookup"><span data-stu-id="18559-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="18559-356">Revise el archivo de registro resultante haciendo clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="18559-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="18559-357">![El estado de la tarea muestra completado](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="18559-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="18559-358">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="18559-358">Click **Finish**.</span></span>
9. <span data-ttu-id="18559-359">Instalar o quitar componentes de Skype empresarial Server (paso 2):</span><span class="sxs-lookup"><span data-stu-id="18559-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="18559-360">Abra el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**y haga clic en **Ejecutar** en el paso 2: configurar o quitar los componentes de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="18559-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="18559-361">Haga clic en **siguiente** en el cuadro de diálogo Configurar componentes de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="18559-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="18559-362">![la ventana Configurar componentes de Skype empresarial Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="18559-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="18559-363">Revise el registro con Ver registro y valide que la configuración se haya completado sin problemas.</span><span class="sxs-lookup"><span data-stu-id="18559-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="18559-364">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="18559-364">Click **Finish**.</span></span>
10. <span data-ttu-id="18559-365">Continúe con la instalación y la configuración adicionales según sea necesario (puede reanudar los procedimientos de instalación normales en este momento).</span><span class="sxs-lookup"><span data-stu-id="18559-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
