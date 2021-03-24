---
title: Deshabilitar TLS 1.0/1.1 en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Preparar e implementar la deshabilitación de TLS 1.0 y 1.1 en los entornos.
ms.openlocfilehash: b07b9b5319b858a20a8073de8c6a37dd4d3299ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103216"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="b04ed-103">Deshabilitar TLS 1.0/1.1 en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b04ed-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="b04ed-104">Este artículo le ayuda a preparar e implementar la deshabilitación de TLS 1.0 y 1.1 en sus entornos.</span><span class="sxs-lookup"><span data-stu-id="b04ed-104">This article helps you prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="b04ed-105">Este proceso requiere una amplia planeación y preparación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="b04ed-106">Revise detenidamente toda la información de este artículo mientras planea deshabilitar TLS 1.0 y 1.1 para su organización.</span><span class="sxs-lookup"><span data-stu-id="b04ed-106">Carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="b04ed-107">Existen muchas dependencias externas y condiciones de conectividad que podrían afectarse al deshabilitar TLS 1.0/1.1, por lo que se requiere una planeación y pruebas exhaustivas.</span><span class="sxs-lookup"><span data-stu-id="b04ed-107">There are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

- [<span data-ttu-id="b04ed-108">Fondo y ámbito</span><span class="sxs-lookup"><span data-stu-id="b04ed-108">Background and scope</span></span>](#background-and-scope)
- [<span data-ttu-id="b04ed-109">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="b04ed-109">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="b04ed-110">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="b04ed-110">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a><span data-ttu-id="b04ed-111">Fondo y ámbito</span><span class="sxs-lookup"><span data-stu-id="b04ed-111">Background and scope</span></span>

<span data-ttu-id="b04ed-112">Los controladores principales para proporcionar TLS 1.0 y 1.1 deshabilitan la compatibilidad con Skype Empresarial Server local son los requisitos del Consejo de estándares de seguridad de la industria de tarjetas de pago (PCI) y los estándares federales de procesamiento de información.</span><span class="sxs-lookup"><span data-stu-id="b04ed-112">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="b04ed-113">Encontrará más información sobre los requisitos pci [aquí](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="b04ed-113">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="b04ed-114">Microsoft no puede proporcionar instrucciones sobre si su organización está obligada a cumplir estos u otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="b04ed-114">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="b04ed-115">Debe determinar si es necesario deshabilitar TLS 1.0 o 1.1 en sus entornos.</span><span class="sxs-lookup"><span data-stu-id="b04ed-115">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="b04ed-116">Microsoft ha producido una white paper sobre TLS disponible [aquí](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)y también se recomienda la lectura en segundo plano disponible en este [blog de Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="b04ed-116">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="b04ed-117">Ámbito de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="b04ed-117">Supportability Scope</span></span>

<span data-ttu-id="b04ed-118">*El ámbito* hace referencia a los límites de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b04ed-118">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="b04ed-119">*Totalmente probado y compatible significa* que se admite totalmente y se ha probado la deshabilitación de TLS 1.0 y 1.1 para las versiones de producto enumeradas.</span><span class="sxs-lookup"><span data-stu-id="b04ed-119">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="b04ed-120">*Actualmente se está investigando* significa justo eso; estamos investigando activamente la posibilidad de que estos productos entren en el ámbito de la compatibilidad con la deshabilitación tls.</span><span class="sxs-lookup"><span data-stu-id="b04ed-120">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="b04ed-121">*Fuera del ámbito* significa que estas versiones de producto no admiten la deshabilitación de TLS 1.0 o 1.1 y no funcionarán, con excepciones observadas.</span><span class="sxs-lookup"><span data-stu-id="b04ed-121">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="b04ed-122">Servidores totalmente probados y compatibles</span><span class="sxs-lookup"><span data-stu-id="b04ed-122">Fully tested and supported servers</span></span>

- <span data-ttu-id="b04ed-123">Skype Empresarial Server 2019 CU1 17.0.2046.123 (junio de 2019) o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-123">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="b04ed-124">Skype Empresarial Server 2015 CU9 6.0.9319.548 (mayo de 2019) o posterior en Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización de superseding), 2012 R2 o 2016.</span><span class="sxs-lookup"><span data-stu-id="b04ed-124">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="b04ed-125">Skype empresarial actualizado local 2015, con CU9 6.0.9319.548 (mayo de 2019) o posterior en Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización de superseding), o 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b04ed-125">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="b04ed-126">Conectividad de Exchange y Outlook Web App con Exchange Server 2010 SP3 RU19 o posterior, instrucciones [aquí](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="b04ed-126">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="b04ed-127">Aplicación de sucursal con funciones de supervivencia (SBA) con Skype Empresarial Server 2015 CU6 HF2 o posterior (confirme con su proveedor que empaquetaron las actualizaciones adecuadas y que se han puesto a disposición de su dispositivo)</span><span class="sxs-lookup"><span data-stu-id="b04ed-127">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="b04ed-128">Servidor de sucursal con funciones de supervivencia (SBS) con Skype Empresarial Server 2015 CU6 HF2 o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-128">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="b04ed-129">Solo rol perimetral de Lync Server 2013 , esto se debe a que el rol perimetral no tiene una dependencia de Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="b04ed-129">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="b04ed-130">Clientes totalmente probados y compatibles</span><span class="sxs-lookup"><span data-stu-id="b04ed-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="b04ed-131">Cliente de escritorio de Lync 2013 (Skype Empresarial), MSI y C2R, incluidos basic [15.0.5023.1000 o posterior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="b04ed-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="b04ed-132">Cliente de escritorio de Skype Empresarial 2016, MSI [16.0.4678.1000 o](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)posterior, incluido Basic</span><span class="sxs-lookup"><span data-stu-id="b04ed-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="b04ed-133">Skype Empresarial 2016 Haga clic para ejecutar Requerir las actualizaciones de abril [de 2018:](/officeupdates/release-notes-office365-proplus)</span><span class="sxs-lookup"><span data-stu-id="b04ed-133">Skype for Business 2016 Click to Run Require the [April 2018](/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="b04ed-134">Mensual y Semi-Annual dirigida, 16 \. 0 \. 9126 \. 2152 o superior</span><span class="sxs-lookup"><span data-stu-id="b04ed-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="b04ed-135">Semi-Annual y canal diferido, 16 \. 0 \. 8431 \. 2242 o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="b04ed-136">Skype Empresarial en Mac 16.15 o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-136">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="b04ed-137">Skype Empresarial para iOS y Android 6.19 o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-137">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="b04ed-138">Salas de Microsoft Teams (anteriormente conocidas como Sistema de salas de Skype V2 SRS V2) 4.0.64.0 (diciembre de 2018) o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-138">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="b04ed-139">Actualización de Surface Hub para team edition basada en KB4499162 (mayo de 2019, compilación del sistema operativo 15063.1835) o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-139">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="b04ed-140">Skype Web App 2015 CU6 HF2 o superior (se incluye con servidor)</span><span class="sxs-lookup"><span data-stu-id="b04ed-140">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="b04ed-141">Actualmente se está investigando</span><span class="sxs-lookup"><span data-stu-id="b04ed-141">Currently being investigated</span></span>

- <span data-ttu-id="b04ed-142">Panel de calidad de llamadas (nueva instalación después de deshabilitar TLS 1.0, 1.1, vea a continuación)\*</span><span class="sxs-lookup"><span data-stu-id="b04ed-142">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="b04ed-143">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="b04ed-143">Out of scope</span></span>

<span data-ttu-id="b04ed-144">Excepto donde se indica, los siguientes productos no están en el ámbito de la deshabilitación de TLS 1.0/1.1 y no funcionarán en un entorno donde SEL 1.0 y 1.1 se hayan deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="b04ed-144">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="b04ed-145">Esto significa: si sigue utilizando clientes o servidores fuera del ámbito, debe actualizarlos o quitarlos si necesita deshabilitar TLS 1.0/1.1 en cualquier lugar de la implementación local de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b04ed-145">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="b04ed-146">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b04ed-146">Lync Server 2013</span></span>
- <span data-ttu-id="b04ed-147">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b04ed-147">Lync Server 2010</span></span>
- <span data-ttu-id="b04ed-148">Windows Server 2008 o inferior</span><span class="sxs-lookup"><span data-stu-id="b04ed-148">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="b04ed-149">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="b04ed-149">Lync for Mac 2011</span></span>
- <span data-ttu-id="b04ed-150">Lync 2013 para dispositivos móviles: iOS, iPad, Android o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b04ed-150">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="b04ed-151">Cliente de la Tienda Windows Lync "MX"</span><span class="sxs-lookup"><span data-stu-id="b04ed-151">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="b04ed-152">Sistema de sala de Lync (a.k.a.</span><span class="sxs-lookup"><span data-stu-id="b04ed-152">Lync Room System (a.k.a.</span></span> <span data-ttu-id="b04ed-153">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="b04ed-153">SRSv1).</span></span> <span data-ttu-id="b04ed-154">LRS llegó al final de la compatibilidad el 9 de octubre de 2018 y no se actualizará para admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b04ed-154">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="b04ed-155">Todos los clientes de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b04ed-155">All Lync 2010 clients</span></span>
- <span data-ttu-id="b04ed-156">Lync Phone Edition: guía actualizada [aquí.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="b04ed-156">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="b04ed-157">Aplicación de sucursal con funciones de supervivencia (SBA) basada en 2013 o servidor de sucursal con funciones de supervivencia (SBS)</span><span class="sxs-lookup"><span data-stu-id="b04ed-157">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="b04ed-158">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="b04ed-158">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="b04ed-159">Skype Empresarial para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b04ed-159">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="b04ed-160">Exceptions</span><span class="sxs-lookup"><span data-stu-id="b04ed-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="b04ed-161">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b04ed-161">Lync Server 2013</span></span>

<span data-ttu-id="b04ed-162">Lync Server 2013 depende de Windows Fabric versión 1.0.</span><span class="sxs-lookup"><span data-stu-id="b04ed-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="b04ed-163">En la fase de diseño de Lync Server 2013, Se eligió Windows Fabric 1.0 por su atractiva y nueva arquitectura distribuida para proporcionar replicación, alta disponibilidad y tolerancia a errores.</span><span class="sxs-lookup"><span data-stu-id="b04ed-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="b04ed-164">Con el tiempo, Tanto Skype Empresarial Server como Windows Fabric han mejorado enormemente esta arquitectura conjunta con un diseño significativo en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b04ed-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="b04ed-165">El Skype Empresarial 2015 Server actual usa Windows Fabric 3.0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b04ed-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="b04ed-166">Desafortunadamente, Windows Fabric 1.0 **no es compatible con TLS 1.2.  Sin embargo, actualizaremos Lync Server 2013 para que funcione con TLS 1.2**.</span><span class="sxs-lookup"><span data-stu-id="b04ed-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="b04ed-167">Esto aparecerá en la próxima actualización acumulativa para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b04ed-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="b04ed-168">Proporcionamos compatibilidad con TLS 1.2 para habilitar escenarios híbridos, de migración, de migración y de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="b04ed-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="b04ed-169">Si su organización tiene que deshabilitar TLS 1.0 y 1.1 y actualmente usa Lync Server 2013, le recomendamos que inicie el proceso de planeación, con la posibilidad de que tenga que actualizar localmente o migrar en paralelo (nuevos grupos de servidores, mover usuarios) a Skype Empresarial Server 2015 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b04ed-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="b04ed-170">O quizás quiera acelerar la migración a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="b04ed-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="b04ed-171">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="b04ed-171">Call Quality Dashboard</span></span>

<span data-ttu-id="b04ed-172">El Panel de calidad de llamadas local actualmente tiene una dependencia de TLS 1.0 durante la nueva instalación (primera vez que se instala en los entornos locales).</span><span class="sxs-lookup"><span data-stu-id="b04ed-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="b04ed-173">Actualmente estamos investigando este problema y planeamos publicar una corrección en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="b04ed-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="b04ed-174">Si planea instalar CQD y deshabilitar TLS 1.0, le recomendamos que complete primero la instalación de CQD y, a continuación, continúe con la deshabilitación de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="b04ed-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="b04ed-175">Administrador de SDN de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b04ed-175">Skype for Business SDN Manager</span></span>

<span data-ttu-id="b04ed-176">El Administrador de SDN de Skype Empresarial SQL una base de datos depende de TLS 1.0 durante la nueva instalación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-176">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="b04ed-177">Si planea instalar el Administrador de SDN de Skype Empresarial con SQL una base de datos y también deshabilitar TLS 1.0, se recomienda completar primero el Administrador de SDN de Skype Empresarial y, a continuación, continuar con la deshabilitación de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="b04ed-177">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="b04ed-178">En caso de que TLS 1.0 se deshabilite antes de la instalación, debe habilitar temporalmente TLS 1. SQL Server 0 de nuevo en un servidor back-end que se usará para hospedar la base de datos del Administrador de SDN de Skype Empresarial SQL.</span><span class="sxs-lookup"><span data-stu-id="b04ed-178">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="b04ed-179">Dispositivos de terceros</span><span class="sxs-lookup"><span data-stu-id="b04ed-179">Third-party devices</span></span>

<span data-ttu-id="b04ed-180">En dispositivos de terceros, como teléfonos 3PIP, videoconferencias, servidores proxy inversos y equilibradores de carga, asegúrese de validar la compatibilidad con TLS 1.2, probar detenidamente y ponerse en contacto con el proveedor si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b04ed-180">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="b04ed-181">Consideraciones de federación al deshabilitar TLS 1.0/1.1 en servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="b04ed-181">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="b04ed-182">Debe planear cuidadosamente y considerar el impacto de deshabilitar TLS 1.0/1.1 en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="b04ed-182">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="b04ed-183">Una vez que TLS 1.0 y 1.1 están deshabilitados, es posible que encuentre que otras organizaciones ya no pueden federar con su organización.</span><span class="sxs-lookup"><span data-stu-id="b04ed-183">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="b04ed-184">Puede optar por mantener TLS 1.0/1.1 habilitado en los servidores perimetrales para mantener la compatibilidad con versiones anteriores con sistemas externos no parcheados (SfB 2015, Lync 2013) o anteriores (2010).</span><span class="sxs-lookup"><span data-stu-id="b04ed-184">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="b04ed-185">Microsoft no puede proporcionar consejos ni recomendaciones sobre si la red perimetral (o cualquier red) está bajo el estándar PCI; que debe ser determinada por la empresa individual.</span><span class="sxs-lookup"><span data-stu-id="b04ed-185">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="b04ed-186">Skype Empresarial Online es capaz de TLS 1.2 hoy en día, por lo que no se espera ningún impacto en la federación híbrida con Online.</span><span class="sxs-lookup"><span data-stu-id="b04ed-186">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="b04ed-187">PIC (conectividad de mensajería instantánea pública) con el servicio de consumidor de Skype: no esperamos que deshabilitar TLS 1.0/1.1 repercuta en la conectividad [de Skype;](../../deploy/deploy-skype-connectivity.md) Las puertas de enlace de Microsoft PIC ya son compatibles con TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b04ed-187">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="b04ed-188">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="b04ed-188">Prerequisites and process</span></span>

<span data-ttu-id="b04ed-189">Excepto donde se indica anteriormente, una vez que TLS 1.0 y 1.1 están deshabilitados servidores fuera del ámbito, los clientes y dispositivos funcionarán más tiempo correctamente o en absoluto.</span><span class="sxs-lookup"><span data-stu-id="b04ed-189">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="b04ed-190">Esto puede significar que debes pausar y esperar a que Microsoft te actualice las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b04ed-190">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="b04ed-191">Una vez que esté satisfecho de que cumple todos los requisitos y tiene un plan para solucionar las diferencias, continúe.</span><span class="sxs-lookup"><span data-stu-id="b04ed-191">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="b04ed-192">En un nivel alto, mientras Skype Empresarial Server 2019 está listo para el procedimiento en la instalación, Skype Empresarial Server 2015 requerirá instalar CU9, aplicar actualizaciones previas a .NET y SQL, implementar claves de registro de requisitos previos y, por último, una ronda independiente de actualizaciones de configuración del sistema operativo (es decir, deshabilitar TLS 1.0 y 1.1 mediante la importación de archivos del Registro).</span><span class="sxs-lookup"><span data-stu-id="b04ed-192">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="b04ed-193">Es fundamental que complete la instalación de todos los requisitos previos, incluido Skype Empresarial Server 2015 CU6 HF2, antes de deshabilitar TLS 1.0 y 1.1 en cualquier servidor de su entorno.</span><span class="sxs-lookup"><span data-stu-id="b04ed-193">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="b04ed-194">Todos los servidores de Skype Empresarial, incluidos los roles perimetrales y SQL back-end, requieren las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b04ed-194">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="b04ed-195">Asegúrese también de que todos los clientes compatibles (en el ámbito) se hayan actualizado a las versiones mínimas necesarias.</span><span class="sxs-lookup"><span data-stu-id="b04ed-195">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="b04ed-196">No olvide actualizar las estaciones de trabajo de administración también.</span><span class="sxs-lookup"><span data-stu-id="b04ed-196">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="b04ed-197">Queremos seguir el orden habitual de las operaciones de "inside out" para actualizar los servidores de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b04ed-197">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="b04ed-198">Trate grupos de directores, chat persistente y grupos emparejados de la misma manera que lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="b04ed-198">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="b04ed-199">El orden y los métodos de actualización se tratan [aquí](topology.md) [y aquí](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="b04ed-199">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="b04ed-200">Proceso de alto nivel</span><span class="sxs-lookup"><span data-stu-id="b04ed-200">High-level process</span></span>

1. <span data-ttu-id="b04ed-201">Pruebe todos los pasos del laboratorio antes de configurar los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="b04ed-201">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="b04ed-202">Haga una copia de seguridad y conserve una copia del Registro exportado en todos y cada uno de los servidores que se actualizarán.</span><span class="sxs-lookup"><span data-stu-id="b04ed-202">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="b04ed-203">No puede compartir registros entre servidores; contienen claves únicas basadas en máquinas.</span><span class="sxs-lookup"><span data-stu-id="b04ed-203">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="b04ed-204">Actualice todos los servidores de Skype Empresarial 2015 a CU9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b04ed-204">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="b04ed-205">Para Skype Empresarial Server 2019, actualice a CU1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b04ed-205">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="b04ed-206">Instale todos los requisitos previos en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="b04ed-206">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="b04ed-207">Implementar claves del Registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="b04ed-207">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="b04ed-208">Asegúrese de que todos los clientes del ámbito estén actualizados.</span><span class="sxs-lookup"><span data-stu-id="b04ed-208">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="b04ed-209">Deshabilite TLS 1.0 y 1.1 mediante la importación del Registro.</span><span class="sxs-lookup"><span data-stu-id="b04ed-209">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="b04ed-210">Valide que las cargas de trabajo funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="b04ed-210">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="b04ed-211">Si se encuentran problemas, solucionar y solucionar problemas, o</span><span class="sxs-lookup"><span data-stu-id="b04ed-211">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="b04ed-212">Restaurar el Registro desde el paso 2 para volver a habilitar TLS 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="b04ed-212">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="b04ed-213">Valide que solo se esté utilizando TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b04ed-213">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="b04ed-214">Instalar requisitos previos en todos los servidores</span><span class="sxs-lookup"><span data-stu-id="b04ed-214">Install prerequisites to all servers</span></span>

<span data-ttu-id="b04ed-215">Es necesaria una actualización extensiva de dependencias antes de empezar a deshabilitar TLS 1.0 y 1.1 en el nivel del sistema operativo en las implementaciones de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b04ed-215">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="b04ed-216">Las siguientes son las versiones mínimas que pueden admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b04ed-216">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="b04ed-217">Implemente todas las actualizaciones de requisitos previos en todos los servidores de Skype Empresarial del entorno antes de empezar a deshabilitar TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="b04ed-217">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="b04ed-218">Skype Empresarial Server 2015 CU9 6.0.9319.548 (mayo de 2019) o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-218">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="b04ed-219">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) o posterior con SchUseStrongCrypto habilitado en el Registro (proporcionado a continuación)</span><span class="sxs-lookup"><span data-stu-id="b04ed-219">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="b04ed-220">SQL debe actualizarse en todos los servidores y back-end de Skype Empresarial 2015.</span><span class="sxs-lookup"><span data-stu-id="b04ed-220">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="b04ed-221">Actualice el grupo de servidores de Enterprise Edition SQL back-end primero y, a continuación, sus respectivas FEs.</span><span class="sxs-lookup"><span data-stu-id="b04ed-221">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="b04ed-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), o superior / SQL Server 2012 SP2 + CU16 o superior / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), o superior / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b04ed-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="b04ed-223">SQL Server native client for SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="b04ed-223">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="b04ed-224">[Controlador ODBC de Microsoft 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), o posterior</span><span class="sxs-lookup"><span data-stu-id="b04ed-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="b04ed-225">Objetos de administración compartidos para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b04ed-225">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="b04ed-226">SQLSysClrTypes para SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b04ed-226">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="b04ed-227">Pasos básicos para instalar requisitos previos, en el orden recomendado de las operaciones</span><span class="sxs-lookup"><span data-stu-id="b04ed-227">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="b04ed-228">Instale la actualización cu9 de Skype Empresarial Server en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="b04ed-228">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="b04ed-229">Instale la actualización en los componentes mediante el actualizador.</span><span class="sxs-lookup"><span data-stu-id="b04ed-229">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="b04ed-230">Actualice las bases de datos de acuerdo con los procedimientos documentados.</span><span class="sxs-lookup"><span data-stu-id="b04ed-230">Update databases according to documented procedures.</span></span> <span data-ttu-id="b04ed-231">Para Skype Empresarial Server 2015, vea KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="b04ed-231">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="b04ed-232">Valide la funcionalidad del producto en la implementación antes de avanzar con cualquier otro cambio.</span><span class="sxs-lookup"><span data-stu-id="b04ed-232">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="b04ed-233">Descargue .NET 4.7 Offline Installer.</span><span class="sxs-lookup"><span data-stu-id="b04ed-233">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="b04ed-234">Referencia: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="b04ed-234">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="b04ed-235">Asegúrese de que los servicios de Skype Empresarial Server 2015 están detenidos en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b04ed-235">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="b04ed-236">Referencia: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="b04ed-236">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="b04ed-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b04ed-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="b04ed-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b04ed-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="b04ed-239">Ejecute el paquete del instalador.</span><span class="sxs-lookup"><span data-stu-id="b04ed-239">Run the installer package.</span></span>
    7. <span data-ttu-id="b04ed-240">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="b04ed-240">Reboot the server.</span></span>
3. <span data-ttu-id="b04ed-241">Actualice SQL Express 2014 en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="b04ed-241">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="b04ed-242">Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="b04ed-242">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="b04ed-243">Descargar SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b04ed-243">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="b04ed-244">Referencia: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="b04ed-244">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="b04ed-245">Copie el medio de instalación en una carpeta del servidor (por ejemplo, C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="b04ed-245">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="b04ed-246">Asegúrese de que los servicios de Skype Empresarial Server 2015 se detengan en el servidor front-end</span><span class="sxs-lookup"><span data-stu-id="b04ed-246">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="b04ed-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b04ed-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="b04ed-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b04ed-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="b04ed-249">Abra un símbolo del sistema de administración y actualice todos los componentes e instancias instalados</span><span class="sxs-lookup"><span data-stu-id="b04ed-249">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="b04ed-250">Ejemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="b04ed-250">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="b04ed-251">Actualice SQL native client.</span><span class="sxs-lookup"><span data-stu-id="b04ed-251">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="b04ed-252">Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="b04ed-252">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="b04ed-253">Descargar desde [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="b04ed-253">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="b04ed-254">Asegúrese de que los servicios de Skype Empresarial Server 2015 se detengan en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b04ed-254">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="b04ed-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="b04ed-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="b04ed-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b04ed-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="b04ed-257">Detener la ejecución SQL instancias instaladas</span><span class="sxs-lookup"><span data-stu-id="b04ed-257">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="b04ed-258">Por ejemplo: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b04ed-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="b04ed-259">Por ejemplo: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b04ed-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="b04ed-260">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b04ed-260">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="b04ed-261">Instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="b04ed-261">Install the update.</span></span>
5. <span data-ttu-id="b04ed-262">Actualice el controlador ODBC 11 para SQL Server para incluir compatibilidad con TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="b04ed-262">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="b04ed-263">Descargar [odbc driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="b04ed-263">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="b04ed-264">Asegúrese de que los servicios de Skype Empresarial Server 2015 están detenidos en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b04ed-264">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="b04ed-265">Ejemplo (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b04ed-265">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="b04ed-266">Ejemplo (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b04ed-266">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="b04ed-267">Instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="b04ed-267">Install the update.</span></span>
6. <span data-ttu-id="b04ed-268">Implementar claves del Registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="b04ed-268">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="b04ed-269">Claves del Registro de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b04ed-269">Pre-requisite registry keys</span></span>

<span data-ttu-id="b04ed-270">Copie o pegue la siguiente prueba en el Bloc de notas y cambie el nombre tlsPreReq.reg o un nombre de su elección y luego importe:</span><span class="sxs-lookup"><span data-stu-id="b04ed-270">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="b04ed-271">Para SQL back-end para grupos de servidores Enterprise Edition, los requisitos previos y la deshabilitación de TLS deben tratarse como cualquier SQL actualizaciones del sistema operativo; consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)</span><span class="sxs-lookup"><span data-stu-id="b04ed-271">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)</span></span>

<span data-ttu-id="b04ed-272">Aunque se pueden combinar los pasos de deshabilitación de TLS y la aplicación de requisitos previos, recomendamos encarecidamente que se apliquen todos los requisitos previos antes de continuar con la deshabilitación de TLS 1.0 y 1.1 en el nivel del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b04ed-272">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="b04ed-273">El método recomendado sería preparar el entorno implementando todos los requisitos previos, validando que todas las cargas de trabajo funcionen correctamente y según lo esperado y, a continuación, continuar con la deshabilitación de TLS 1.0/1.1 más adelante.</span><span class="sxs-lookup"><span data-stu-id="b04ed-273">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="b04ed-274">Deshabilitar TLS 1.0 y 1.1 mediante la importación del Registro</span><span class="sxs-lookup"><span data-stu-id="b04ed-274">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="b04ed-275">Antes de continuar con los pasos siguientes, asegúrese de que ha completado todos los *requisitos previos y* actualizado Skype Empresarial Servers .</span><span class="sxs-lookup"><span data-stu-id="b04ed-275">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="b04ed-276">Copie el siguiente texto en un archivo del Bloc de notas y cambie el nombre **tlsDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="b04ed-276">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="b04ed-277">Importe el archivo .reg en cada servidor que desee deshabilitar TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="b04ed-277">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="b04ed-278">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="b04ed-278">Reboot the server.</span></span> <span data-ttu-id="b04ed-279">Una vez que los servicios vuelvan a estar en línea, muévete al siguiente servidor.</span><span class="sxs-lookup"><span data-stu-id="b04ed-279">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="b04ed-280">El enfoque de los grupos de servidores de Enterprise Edition es el mismo que se tomaría para cualquier actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b04ed-280">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="b04ed-281">Puede que haya notado que estamos haciendo algo más que deshabilitar TLS 1.0 y 1.1 aquí.</span><span class="sxs-lookup"><span data-stu-id="b04ed-281">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="b04ed-282">Estamos soportando el reojo de conjunto de cifrado (como se muestra anteriormente) y la deshabilitación de algunos cifrados débiles más antiguos.</span><span class="sxs-lookup"><span data-stu-id="b04ed-282">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="b04ed-283">Es la primera vez que se admiten oficialmente estos cambios en SCHANNEL y API de criptografía en Skype Empresarial Server, y es importante tener en cuenta que estos cambios son los únicos que admitemos y hemos probado en este momento.</span><span class="sxs-lookup"><span data-stu-id="b04ed-283">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="b04ed-284">Podemos considerar configuraciones adicionales en el futuro, pero por ahora, no modifique el archivo de importación del Registro en su implementación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-284">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="b04ed-285">Validar que las cargas de trabajo funcionan según lo esperado</span><span class="sxs-lookup"><span data-stu-id="b04ed-285">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="b04ed-286">Una vez que TLS 1.0 y 1.1 se hayan deshabilitado en su entorno, asegúrese de que todas las cargas de trabajo principales funcionan según lo esperado, como im & Presence, llamadas P2P, Telefonía IP empresarial, etc.</span><span class="sxs-lookup"><span data-stu-id="b04ed-286">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="b04ed-287">**Validar que solo se usa TLS 1.2**</span><span class="sxs-lookup"><span data-stu-id="b04ed-287">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="b04ed-288">Haga que el equipo de seguridad realice una nueva auditoría del tráfico de Skype Empresarial para asegurarse de que los protocolos anteriores TLS 1.0 y 1.1 ya no están en uso.</span><span class="sxs-lookup"><span data-stu-id="b04ed-288">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="b04ed-289">Como alternativa, puede usar Internet Explorer para probar conexiones TLS a servicios web desde Skype Empresarial Server 2015 después de deshabilitar TLS 1.0 y TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="b04ed-289">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="b04ed-290">Inicie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b04ed-290">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="b04ed-291">Seleccione **Herramientas Opciones** de  >  **Internet**.</span><span class="sxs-lookup"><span data-stu-id="b04ed-291">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="b04ed-292">Seleccione la pestaña **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="b04ed-292">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="b04ed-293">En **Configuración**, desplácese hasta la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="b04ed-293">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="b04ed-294">Compruebe que TLS 1.0, TLS 1.1 y TLS 1.2 están habilitados.</span><span class="sxs-lookup"><span data-stu-id="b04ed-294">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="b04ed-295">Examine la dirección URL del servicio web interno del grupo de servidores de SfB 2015 (debe conectarse correctamente).</span><span class="sxs-lookup"><span data-stu-id="b04ed-295">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="b04ed-296">Vuelva a Internet Explorer y deshabilite la opción **usar solo TLS 1.2.**</span><span class="sxs-lookup"><span data-stu-id="b04ed-296">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="b04ed-297">Examine de nuevo la dirección URL del servicio web interno del grupo de servidores de SfB 2015 (no debería conectarse).</span><span class="sxs-lookup"><span data-stu-id="b04ed-297">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opciones de Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="b04ed-299">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="b04ed-299">Advanced deployment scenarios</span></span>

<span data-ttu-id="b04ed-300">Dado que algunos requisitos previos de dependencia son necesarios para admitir TLS 1.2 en Skype Empresarial Server 2015, la instalación desde medios RTM producirá un error en cualquier sistema en el que se hayan deshabilitado TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="b04ed-300">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="b04ed-301">**Implementación de nuevos servidores Standard Edition o grupos de servidores Enterprise Edition una vez que TLS 1.0 y 1.1 se han deshabilitado en su entorno.**</span><span class="sxs-lookup"><span data-stu-id="b04ed-301">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="b04ed-302">**Opción 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="b04ed-302">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="b04ed-303">Tenga en cuenta que estamos actualizando SmartSetup para dar cabida a los archivos binarios de SQL actualizados en una CU futura y actualizaremos este artículo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="b04ed-303">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="b04ed-304">**Opción 2:** Preinstalar instancias SQL locales (RTCLOCAL y LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="b04ed-304">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="b04ed-305">Descargue y copie SQL Express 2014 SP2 (SQLEXPR_x64.exe) en la carpeta local de FE.</span><span class="sxs-lookup"><span data-stu-id="b04ed-305">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="b04ed-306">Supongamos que la ruta de acceso de carpeta <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="b04ed-306">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="b04ed-307">Inicie PowerShell o símbolo del sistema y vaya a <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="b04ed-307">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="b04ed-308">Cree la instancia de SQL RTCLOCAL ejecutando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="b04ed-308">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="b04ed-309">Espere hasta SQLEXPR_x64.exe finaliza antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="b04ed-309">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="b04ed-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="b04ed-310">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="b04ed-311">Cree la instancia de SQL LYNCLOCAL ejecutando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="b04ed-311">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="b04ed-312">Espere hasta SQLEXPR_x64.exe finaliza antes de continuar con el paso siguiente:</span><span class="sxs-lookup"><span data-stu-id="b04ed-312">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="b04ed-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="b04ed-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="b04ed-314">Ejecute el programa de instalación de Skype Empresarial Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="b04ed-314">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="b04ed-315">Siga los pasos restantes de la sección de requisitos previos anterior.</span><span class="sxs-lookup"><span data-stu-id="b04ed-315">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="b04ed-316">**Opción 3:** También puede reemplazar manualmente los archivos binarios en un directorio multimedia de instalación local de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b04ed-316">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="b04ed-317">Instalar requisitos previos para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b04ed-317">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="b04ed-318">Instalar .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="b04ed-318">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="b04ed-319">**Nota:** Introdujimos por primera vez compatibilidad con .NET 4.7 en Skype Empresarial Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="b04ed-319">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="b04ed-320">Por lo tanto, en los pasos posteriores que se indican a continuación, actualizaremos componentes principales antes de la instalación principal.</span><span class="sxs-lookup"><span data-stu-id="b04ed-320">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="b04ed-321">Descargar: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="b04ed-321">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="b04ed-322">Referencia: Software que debe instalarse antes de una implementación de [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="b04ed-322">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="b04ed-323">Copiar archivos o carpetas ISO:</span><span class="sxs-lookup"><span data-stu-id="b04ed-323">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="b04ed-324">Con la ISO de Skype Empresarial Server 2015 adjunta, abra el directorio raíz de la unidad que está adjunta como (Por ejemplo: D: \) en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="b04ed-324">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="b04ed-325">Copie todas las carpetas y archivos en una carpeta de un disco local (por ejemplo: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="b04ed-325">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="b04ed-326">**Nota:** Antes de instalar componentes, algunos archivos tendrán que actualizarse para admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b04ed-326">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="b04ed-327">Reemplazar paquetes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="b04ed-327">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="b04ed-328">Reemplace los paquetes MSI y EXE existentes en la carpeta /Setup/amd64/ del medio de instalación en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b04ed-328">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="b04ed-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="b04ed-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="b04ed-330">Cambie el SQLEXPR_x64 a la máquina local y reemplace el archivo existente en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-330">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b04ed-331">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="b04ed-331">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="b04ed-332">**Nota:** Cambie el nombre si es necesario sqlncli.msi y, a continuación, reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-332">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b04ed-333">SQL objetos de administración: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="b04ed-333">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="b04ed-334">**Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="b04ed-334">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="b04ed-335">Seleccione para descargar SharedManagementObjects.msi solo.</span><span class="sxs-lookup"><span data-stu-id="b04ed-335">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="b04ed-336">**Nota:** Reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-336">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b04ed-337">SQL CLR: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="b04ed-337">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="b04ed-338">**Nota:** El paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="b04ed-338">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="b04ed-339">Seleccione para descargar CQLSysClrTypes.msi solo</span><span class="sxs-lookup"><span data-stu-id="b04ed-339">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="b04ed-340">**Nota:** Reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-340">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="b04ed-341">Instalar componentes principales:</span><span class="sxs-lookup"><span data-stu-id="b04ed-341">Install Core Components:</span></span> 
    - <span data-ttu-id="b04ed-342">Ejecute Setup.exe desde la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b04ed-342">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="b04ed-343">Siga las instrucciones para instalar componentes principales</span><span class="sxs-lookup"><span data-stu-id="b04ed-343">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="b04ed-344">Cerrar componentes principales.</span><span class="sxs-lookup"><span data-stu-id="b04ed-344">Close Core Components.</span></span>
6. <span data-ttu-id="b04ed-345">Actualizar componentes principales:</span><span class="sxs-lookup"><span data-stu-id="b04ed-345">Update Core Components:</span></span> 
    - <span data-ttu-id="b04ed-346">Descargue el Instalador de actualización de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b04ed-346">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="b04ed-347">Ejecute el instalador para actualizar componentes principales e instalar los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b04ed-347">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="b04ed-348">**Nota:** Desde la versión de CU6HF2, la característica de actualización automática actualmente solo se instalará hasta CU6.</span><span class="sxs-lookup"><span data-stu-id="b04ed-348">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="b04ed-349">Por lo tanto, el actualizador debe ejecutarse por separado para actualizar componentes principales a 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="b04ed-349">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="b04ed-350">Referencia: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="b04ed-350">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="b04ed-351">Instalar herramientas administrativas (opcional):</span><span class="sxs-lookup"><span data-stu-id="b04ed-351">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="b04ed-352">Esto instalará los tipos Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) y Microsoft System CLR Types for SQL Server 2014 (x64) mediante los archivos actualizados.</span><span class="sxs-lookup"><span data-stu-id="b04ed-352">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="b04ed-353">Además, el Generador de topologías y el Panel de control de Skype Empresarial Server 2015 estarán disponibles en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b04ed-353">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="b04ed-354">Instalar el almacén de configuración local (paso 1):</span><span class="sxs-lookup"><span data-stu-id="b04ed-354">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="b04ed-355">Abra el Asistente para implementación, haga clic en Instalar o actualizar el sistema de Skype Empresarial Server y haga clic en **Ejecutar** en paso 1: Instalar almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="b04ed-355">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="b04ed-356">Haga **clic en Siguiente** en el cuadro de diálogo Instalar almacén **de** configuración local.</span><span class="sxs-lookup"><span data-stu-id="b04ed-356">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="b04ed-357">![Cuadro de diálogo Instalar almacén de configuración local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="b04ed-357">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="b04ed-358">Revise los resultados y asegúrese de que el estado de la tarea está completado.</span><span class="sxs-lookup"><span data-stu-id="b04ed-358">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="b04ed-359">Revise el archivo de registro resultante haciendo clic **en Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="b04ed-359">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="b04ed-360">![El estado de la tarea se muestra como Completado](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="b04ed-360">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="b04ed-361">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b04ed-361">Click **Finish**.</span></span>
9. <span data-ttu-id="b04ed-362">Configurar o quitar componentes de Skype Empresarial Server (paso 2):</span><span class="sxs-lookup"><span data-stu-id="b04ed-362">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="b04ed-363">Abra el Asistente para implementación, haga clic en  Instalar o actualizar Skype Empresarial **Server System** y haga clic en Ejecutar en paso 2: Configurar o quitar componentes de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b04ed-363">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="b04ed-364">Haga **clic en** Siguiente en el cuadro de diálogo Configurar componentes de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b04ed-364">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="b04ed-365">![la ventana Configurar componentes de Skype Empresarial Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="b04ed-365">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="b04ed-366">Revise el registro con View Log y valide que la instalación se completó sin problemas.</span><span class="sxs-lookup"><span data-stu-id="b04ed-366">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="b04ed-367">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b04ed-367">Click **Finish**.</span></span>
10. <span data-ttu-id="b04ed-368">Continúe con la instalación y configuración adicionales según sea necesario (puede reanudar los procedimientos de instalación normales en este momento).</span><span class="sxs-lookup"><span data-stu-id="b04ed-368">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>