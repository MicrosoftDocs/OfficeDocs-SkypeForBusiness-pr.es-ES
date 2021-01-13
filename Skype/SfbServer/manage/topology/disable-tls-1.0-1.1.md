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
description: 'Resumen: prepare e implemente la deshabilitación de TLS 1.0 y 1.1 en sus entornos.'
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826400"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="b966a-103">Deshabilitar TLS 1.0/1.1 en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b966a-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="b966a-104">El propósito de este artículo es proporcionar las instrucciones necesarias para preparar e implementar la deshabilitación de TLS 1.0 y 1.1 en sus entornos.</span><span class="sxs-lookup"><span data-stu-id="b966a-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="b966a-105">Este proceso requiere una planeación y preparación exhaustivas.</span><span class="sxs-lookup"><span data-stu-id="b966a-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="b966a-106">Revise cuidadosamente toda la información de este artículo mientras planea deshabilitar TLS 1.0 y 1.1 para su organización.</span><span class="sxs-lookup"><span data-stu-id="b966a-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="b966a-107">Tenga en cuenta que hay muchas dependencias externas y condiciones de conectividad que se podrían ver afectadas al deshabilitar TLS 1.0/1.1, por lo que se requiere una planeación y pruebas exhaustivas.</span><span class="sxs-lookup"><span data-stu-id="b966a-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="b966a-108">En este artículo</span><span class="sxs-lookup"><span data-stu-id="b966a-108">In this article</span></span>

- [<span data-ttu-id="b966a-109">Fondo y ámbito</span><span class="sxs-lookup"><span data-stu-id="b966a-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="b966a-110">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="b966a-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="b966a-111">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="b966a-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="b966a-112">Información previa</span><span class="sxs-lookup"><span data-stu-id="b966a-112">Background</span></span>

<span data-ttu-id="b966a-113">Los principales impulsores para proporcionar TLS 1.0 y 1.1 deshabilitan la compatibilidad con Skype Empresarial Server local son los requisitos del Consejo de Estándares de Seguridad de la Industria de tarjetas de pago (PCI) y los requisitos de estándares federales de procesamiento de información.</span><span class="sxs-lookup"><span data-stu-id="b966a-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="b966a-114">Puede encontrar más información sobre los requisitos PCI [aquí.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)</span><span class="sxs-lookup"><span data-stu-id="b966a-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="b966a-115">Microsoft no puede proporcionar instrucciones sobre si su organización debe cumplir estos u otros requisitos.</span><span class="sxs-lookup"><span data-stu-id="b966a-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="b966a-116">Debe determinar si es necesario deshabilitar TLS 1.0 o 1.1 en sus entornos.</span><span class="sxs-lookup"><span data-stu-id="b966a-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="b966a-117">Microsoft ha producido unas white paper sobre TLS disponibles [aquí](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)y también recomendamos la lectura en segundo plano disponible en este [blog de Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="b966a-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="b966a-118">Ámbito de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="b966a-118">Supportability Scope</span></span>

<span data-ttu-id="b966a-119">*El ámbito* hace referencia a límites de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b966a-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="b966a-120">*Totalmente probado y admitido significa* que se admite completamente y se ha probado la deshabilitación de TLS 1.0 y 1.1 para las versiones de producto enumeradas.</span><span class="sxs-lookup"><span data-stu-id="b966a-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="b966a-121">*Actualmente, la investigación* significa simplemente eso; estamos investigando activamente la posibilidad de incorporar estos productos al ámbito de la deshabilitación de TLS.</span><span class="sxs-lookup"><span data-stu-id="b966a-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="b966a-122">*Fuera del ámbito* significa que estas versiones de producto no admiten la deshabilitación de TLS 1.0 o 1.1 y no funcionarán, con excepciones anotadas.</span><span class="sxs-lookup"><span data-stu-id="b966a-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="b966a-123">Servidores totalmente probados y compatibles</span><span class="sxs-lookup"><span data-stu-id="b966a-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="b966a-124">Skype Empresarial Server 2019 CU1 17.0.2046.123 (junio de 2019) o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="b966a-125">Skype Empresarial Server 2015 CU9 6.0.9319.548 (mayo de 2019) o superior en Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización superseding), 2012 R2 o 2016.</span><span class="sxs-lookup"><span data-stu-id="b966a-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="b966a-126">Skype Empresarial Server 2015 actualizado localmente, con CU9 6.0.9319.548 (mayo de 2019) o superior en Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o actualización superseding) o 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="b966a-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="b966a-127">Conectividad de Exchange y Outlook Web App con Exchange Server 2010 SP3 RU19 o posterior, [aquí](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="b966a-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="b966a-128">Aplicación de sucursal con funciones de supervivencia (SBA) con Skype Empresarial Server 2015 CU6 DHCP2 o superior (confirme con su proveedor que empaquetaron las actualizaciones adecuadas y que se han puesto a disposición de su dispositivo)</span><span class="sxs-lookup"><span data-stu-id="b966a-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="b966a-129">Servidor de sucursal con funciones de supervivencia (SBS) con Skype Empresarial Server 2015 CU6 HP2 o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="b966a-130">Lync Server 2013 **Solo** rol perimetral , esto se debe a que el rol perimetral no tiene una dependencia en Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="b966a-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="b966a-131">Clientes totalmente probados y compatibles</span><span class="sxs-lookup"><span data-stu-id="b966a-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="b966a-132">Cliente de escritorio de Lync 2013 (Skype Empresarial), MSI y C2R, incluidos basic [15.0.5023.1000 o superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="b966a-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="b966a-133">Cliente de escritorio de Skype Empresarial 2016, MSI [16.0.4678.1000 o](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)superior, incluido Basic</span><span class="sxs-lookup"><span data-stu-id="b966a-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="b966a-134">Skype Empresarial 2016 Hacer clic y ejecutar requiere las actualizaciones [de abril de 2018:](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)</span><span class="sxs-lookup"><span data-stu-id="b966a-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="b966a-135">Mensual y Semi-Annual dirigido, 16 \. 0 \. 9126 \. 2152 o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="b966a-136">Semi-Annual y Canal diferido, 16 \. 0 \. 8431 \. 2242 o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="b966a-137">Skype Empresarial en Mac 16.15 o posterior</span><span class="sxs-lookup"><span data-stu-id="b966a-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="b966a-138">Skype Empresarial para iOS y Android 6.19 o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="b966a-139">Salas de Microsoft Teams (anteriormente conocido como Sistema de salas de Skype V2 SRS V2) 4.0.64.0 (diciembre de 2018) o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="b966a-140">Actualización de Surface Hub para la edición Team basada en KB4499162 (mayo de 2019, compilación del sistema operativo 15063.1835) o posterior</span><span class="sxs-lookup"><span data-stu-id="b966a-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="b966a-141">Skype Web App 2015 CU6 FTP2 o superior (se suministra con el servidor)</span><span class="sxs-lookup"><span data-stu-id="b966a-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="b966a-142">Actualmente se está investigando</span><span class="sxs-lookup"><span data-stu-id="b966a-142">Currently being investigated</span></span>

- <span data-ttu-id="b966a-143">Panel de calidad de llamadas (nueva instalación después de deshabilitar TLS 1.0, 1.1, vea a continuación)\*</span><span class="sxs-lookup"><span data-stu-id="b966a-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="b966a-144">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="b966a-144">Out of scope</span></span>

<span data-ttu-id="b966a-145">Excepto cuando se indica, los siguientes productos no están en el ámbito de TLS 1.0/1.1 y no funcionarán en un entorno en el que se hayan deshabilitado TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="b966a-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="b966a-146">Esto significa: si sigue utilizando clientes o servidores fuera del ámbito, debe actualizarlos o quitarlos si necesita deshabilitar TLS 1.0/1.1 en cualquier lugar de su implementación local de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b966a-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="b966a-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b966a-147">Lync Server 2013</span></span>
- <span data-ttu-id="b966a-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b966a-148">Lync Server 2010</span></span>
- <span data-ttu-id="b966a-149">Windows Server 2008 o inferior</span><span class="sxs-lookup"><span data-stu-id="b966a-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="b966a-150">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="b966a-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="b966a-151">Lync 2013 para dispositivos móviles: iOS, iPad, Android o Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b966a-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="b966a-152">Cliente de la Tienda Windows "MX" de Lync</span><span class="sxs-lookup"><span data-stu-id="b966a-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="b966a-153">Sistema Lync Room (también k.a.</span><span class="sxs-lookup"><span data-stu-id="b966a-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="b966a-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="b966a-154">SRSv1).</span></span> <span data-ttu-id="b966a-155">LRS alcanzó el final del soporte el 9 de octubre de 2018 y no se actualizará para admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b966a-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="b966a-156">Todos los clientes de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b966a-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="b966a-157">Lync Phone Edition: guía actualizada [aquí.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="b966a-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="b966a-158">Aplicación de sucursal con funciones de supervivencia (SBA) o servidor de sucursal con funciones de supervivencia (SBS) basado en 2013</span><span class="sxs-lookup"><span data-stu-id="b966a-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="b966a-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="b966a-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="b966a-160">Skype Empresarial para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b966a-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="b966a-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="b966a-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="b966a-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b966a-162">Lync Server 2013</span></span>

<span data-ttu-id="b966a-163">Lync Server 2013 toma una dependencia en Windows Fabric versión 1.0.</span><span class="sxs-lookup"><span data-stu-id="b966a-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="b966a-164">En la fase de diseño de Lync Server 2013, se eligió Windows Fabric 1.0 por su atractiva y nueva arquitectura distribuida para proporcionar replicación, alta disponibilidad y tolerancia a errores.</span><span class="sxs-lookup"><span data-stu-id="b966a-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="b966a-165">Con el tiempo, Tanto Skype Empresarial Server como Windows Fabric han mejorado considerablemente esta arquitectura conjunta con un nuevo diseño significativo en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b966a-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="b966a-166">Actualmente, Skype Empresarial 2015 Server usa Windows Fabric 3.0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b966a-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="b966a-167">Desafortunadamente, Windows Fabric 1.0 **no admite TLS 1.2.  Sin embargo, actualizaremos Lync Server 2013 para que funcione con TLS 1.2**.</span><span class="sxs-lookup"><span data-stu-id="b966a-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="b966a-168">Esto se mostrará en la próxima actualización acumulativa de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b966a-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="b966a-169">Proporcionamos compatibilidad con TLS 1.2 para habilitar la coexistencia, la migración, la federación y los escenarios híbridos.</span><span class="sxs-lookup"><span data-stu-id="b966a-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="b966a-170">Si su organización necesita deshabilitar TLS 1.0 y 1.1, y actualmente usa Lync Server 2013, le recomendamos que inicie el proceso de planeación, con la posibilidad de que tenga que realizar una actualización local o migrar en paralelo (nuevos grupos de servidores, mover usuarios) a Skype Empresarial Server 2015 o superior.</span><span class="sxs-lookup"><span data-stu-id="b966a-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="b966a-171">O quizás quiera acelerar la migración a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="b966a-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="b966a-172">Panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="b966a-172">Call Quality Dashboard</span></span>

<span data-ttu-id="b966a-173">El Panel de calidad de llamadas local actualmente tiene una dependencia en TLS 1.0 durante la nueva instalación (la primera vez que se instala en los entornos locales).</span><span class="sxs-lookup"><span data-stu-id="b966a-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="b966a-174">We are currently investigating this issue and plan to release a fix in the near future.</span><span class="sxs-lookup"><span data-stu-id="b966a-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="b966a-175">Si tiene previsto instalar el CQD y también deshabilitar TLS 1.0, le recomendamos que primero complete la instalación de CQD y, a continuación, continúe con la deshabilitación de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="b966a-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="b966a-176">Administrador de SDN de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b966a-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="b966a-177">Skype Empresarial SDN Manager con SQL una base de datos tiene una dependencia en TLS 1.0 durante la nueva instalación.</span><span class="sxs-lookup"><span data-stu-id="b966a-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="b966a-178">Si tiene previsto instalar Skype Empresarial SDN Manager con SQL una base de datos y también deshabilitar TLS 1.0, le recomendamos que primero complete el Administrador de SDN de Skype Empresarial y, a continuación, continúe con la deshabilitación de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="b966a-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="b966a-179">En caso de que TLS 1.0 se deshabilite antes de la instalación, debe habilitar temporalmente TLS 1. SQL Server 0 de nuevo en un servidor back-end que se usará para hospedar la base de datos de SQL del Administrador sdn de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b966a-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="b966a-180">Dispositivos de terceros</span><span class="sxs-lookup"><span data-stu-id="b966a-180">Third-party devices</span></span>

<span data-ttu-id="b966a-181">En dispositivos de terceros como teléfonos 3PIP, videoconferencias, servidores proxy inversos y equilibradores de carga, asegúrese de validar la compatibilidad con TLS 1.2, realizar pruebas cuidadosamente y ponerse en contacto con el proveedor si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b966a-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="b966a-182">Consideraciones de federación al deshabilitar TLS 1.0/1.1 en servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="b966a-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="b966a-183">Debe planear cuidadosamente y tener en cuenta el impacto de deshabilitar TLS 1.0/1.1 en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="b966a-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="b966a-184">Una vez que TLS 1.0 y 1.1 están deshabilitados, es posible que otras organizaciones ya no puedan federar con su organización.</span><span class="sxs-lookup"><span data-stu-id="b966a-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="b966a-185">Puede optar por mantener TLS 1.0/1.1 habilitado en los servidores perimetrales para mantener la compatibilidad con versiones anteriores con sistemas externos sin revisión (SfB 2015, Lync 2013) o versiones anteriores (2010).</span><span class="sxs-lookup"><span data-stu-id="b966a-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="b966a-186">Microsoft no puede proporcionar consejos o recomendaciones sobre si la red perimetral (o cualquier red) está o no dentro del estándar PCI; que debe ser determinada por la empresa individual.</span><span class="sxs-lookup"><span data-stu-id="b966a-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="b966a-187">Skype Empresarial Online es capaz de TLS 1.2 hoy en día, por lo que no se espera ningún impacto en la implementación híbrida/federación con online.</span><span class="sxs-lookup"><span data-stu-id="b966a-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="b966a-188">PIC (Conectividad de mensajería instantánea pública) con el servicio de consumidor de Skype: no esperamos que deshabilitar TLS 1.0/1.1 repercuta en la [conectividad de Skype;](../../deploy/deploy-skype-connectivity.md) Las puertas de enlace PIC de Microsoft ya son compatibles con TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b966a-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="b966a-189">Requisitos previos y proceso</span><span class="sxs-lookup"><span data-stu-id="b966a-189">Prerequisites and process</span></span>

<span data-ttu-id="b966a-190">Excepto cuando se indica anteriormente, una vez que TLS 1.0 y 1.1 se deshabilitan servidores fuera del ámbito, los clientes y dispositivos ya no funcionarán correctamente o en absoluto.</span><span class="sxs-lookup"><span data-stu-id="b966a-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="b966a-191">Esto puede significar que necesita pausar y esperar a que Microsoft le haya actualizado las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b966a-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="b966a-192">Una vez que esté satisfecho de que cumple todos los requisitos y tiene un plan para solucionar las diferencias, continúe.</span><span class="sxs-lookup"><span data-stu-id="b966a-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="b966a-193">En un nivel alto, mientras Skype Empresarial Server 2019 está listo para el procedimiento en la instalación, Skype Empresarial Server 2015 requerirá que instale CU9, aplique actualizaciones de requisitos previos a .NET y SQL, implemente claves del Registro de requisitos previos y, por último, una ronda independiente de actualizaciones de configuración del sistema operativo (es decir, deshabilitar TLS 1.0 y 1.1 a través de la importación de archivos del Registro).</span><span class="sxs-lookup"><span data-stu-id="b966a-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="b966a-194">Es muy importante que complete la instalación de todos los requisitos previos, incluido Skype Empresarial Server 2015 CU6 DHCP2, antes de deshabilitar TLS 1.0 y 1.1 en cualquier servidor de su entorno.</span><span class="sxs-lookup"><span data-stu-id="b966a-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="b966a-195">Todos los servidores de Skype Empresarial, incluidos los roles perimetrales SQL back-end, requieren las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b966a-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="b966a-196">Asegúrese también de que todos los clientes compatibles (en el ámbito) se hayan actualizado a las versiones mínimas necesarias.</span><span class="sxs-lookup"><span data-stu-id="b966a-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="b966a-197">No olvide actualizar también las estaciones de trabajo de administración.</span><span class="sxs-lookup"><span data-stu-id="b966a-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="b966a-198">Queremos seguir el orden habitual de las operaciones de "inside out" para actualizar los servidores de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b966a-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="b966a-199">Trate los grupos de directores, el chat persistente y los grupos emparejados de la misma manera que lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="b966a-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="b966a-200">El orden y los métodos de actualización se [tratan aquí](topology.md) [y aquí.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="b966a-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="b966a-201">Proceso de alto nivel</span><span class="sxs-lookup"><span data-stu-id="b966a-201">High-level process</span></span>

1. <span data-ttu-id="b966a-202">Pruebe todos los pasos del laboratorio antes de configurar los servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="b966a-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="b966a-203">Haga una copia de seguridad y conserve una copia del Registro exportado en todos y cada uno de los servidores que se actualizarán.</span><span class="sxs-lookup"><span data-stu-id="b966a-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="b966a-204">No puede compartir registros entre servidores; contienen claves únicas basadas en máquina.</span><span class="sxs-lookup"><span data-stu-id="b966a-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="b966a-205">Actualice todos los servidores de Skype Empresarial 2015 a CU9 o superior.</span><span class="sxs-lookup"><span data-stu-id="b966a-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="b966a-206">Para Skype Empresarial Server 2019, actualice a CU1 o superior.</span><span class="sxs-lookup"><span data-stu-id="b966a-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="b966a-207">Instale todos los requisitos previos en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="b966a-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="b966a-208">Implementar claves del Registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="b966a-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="b966a-209">Asegúrese de que se actualicen todos los clientes en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="b966a-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="b966a-210">Deshabilite TLS 1.0 y 1.1 mediante la importación del Registro.</span><span class="sxs-lookup"><span data-stu-id="b966a-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="b966a-211">Valide que las cargas de trabajo funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="b966a-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="b966a-212">Si se encuentran problemas, solucionar y solucionar problemas, o</span><span class="sxs-lookup"><span data-stu-id="b966a-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="b966a-213">Restaurar el Registro del paso 2 para volver a habilitar TLS 1.0 y 1.1</span><span class="sxs-lookup"><span data-stu-id="b966a-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="b966a-214">Valide que solo se esté utilizando TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b966a-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="b966a-215">Instalación de requisitos previos en todos los servidores</span><span class="sxs-lookup"><span data-stu-id="b966a-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="b966a-216">Es necesaria una actualización extensiva de dependencias antes de empezar a deshabilitar TLS 1.0 y 1.1 en el nivel del sistema operativo en las implementaciones de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b966a-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="b966a-217">Las siguientes son las versiones mínimas que pueden admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b966a-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="b966a-218">Implemente todas las actualizaciones de requisitos previos en todos los servidores de Skype Empresarial de su entorno antes de empezar a deshabilitar TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="b966a-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="b966a-219">Skype Empresarial Server 2015 CU9 6.0.9319.548 (mayo de 2019) o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="b966a-220">[.NET Framework 4.7 o](https://www.microsoft.com/download/details.aspx?id=55167) superior con SchUseStrongCrypto habilitado en el Registro (proporcionado a continuación)</span><span class="sxs-lookup"><span data-stu-id="b966a-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="b966a-221">SQL deben actualizarse en todos los servidores y back-end de Skype Empresarial 2015.</span><span class="sxs-lookup"><span data-stu-id="b966a-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="b966a-222">Actualice primero los back-end de SQL Enterprise Edition y, a continuación, sus correspondientes FEs.</span><span class="sxs-lookup"><span data-stu-id="b966a-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="b966a-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)o superior / SQL Server 2012 SP2 + CU16 o superior / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), o superior / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b966a-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="b966a-224">SQL Server Native Client para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="b966a-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="b966a-225">[Controlador ODBC de Microsoft 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)o superior</span><span class="sxs-lookup"><span data-stu-id="b966a-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="b966a-226">Objetos de administración compartidos para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b966a-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="b966a-227">SQLSysClrTypes para SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b966a-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="b966a-228">Pasos básicos para instalar requisitos previos, en el orden recomendado de las operaciones</span><span class="sxs-lookup"><span data-stu-id="b966a-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="b966a-229">Instale la actualización CU9 de Skype Empresarial Server en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="b966a-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="b966a-230">Instale la actualización de los componentes mediante el actualizador.</span><span class="sxs-lookup"><span data-stu-id="b966a-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="b966a-231">Actualice las bases de datos de acuerdo con los procedimientos documentados.</span><span class="sxs-lookup"><span data-stu-id="b966a-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="b966a-232">Para Skype Empresarial Server 2015, consulte KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="b966a-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="b966a-233">Validar la funcionalidad del producto en la implementación antes de avanzar con cualquier otro cambio.</span><span class="sxs-lookup"><span data-stu-id="b966a-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="b966a-234">Descarga el Instalador sin conexión de .NET 4.7.</span><span class="sxs-lookup"><span data-stu-id="b966a-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="b966a-235">Referencia: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="b966a-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="b966a-236">Asegúrese de que los servicios de Skype Empresarial Server 2015 estén detenidos en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b966a-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="b966a-237">Referencia: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="b966a-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="b966a-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b966a-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="b966a-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b966a-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="b966a-240">Ejecuta el paquete del instalador.</span><span class="sxs-lookup"><span data-stu-id="b966a-240">Run the installer package.</span></span>
    7. <span data-ttu-id="b966a-241">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="b966a-241">Reboot the server.</span></span>
3. <span data-ttu-id="b966a-242">Actualice SQL Express 2014 en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="b966a-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="b966a-243">Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="b966a-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="b966a-244">Descargar SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="b966a-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="b966a-245">Referencia: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="b966a-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="b966a-246">Copiar los medios de instalación en una carpeta del servidor (por ejemplo, C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="b966a-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="b966a-247">Asegurarse de que los servicios de Skype Empresarial Server 2015 están detenidos en el servidor front-end</span><span class="sxs-lookup"><span data-stu-id="b966a-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="b966a-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b966a-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="b966a-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b966a-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="b966a-250">Abrir un símbolo del sistema de administración y actualizar todos los componentes e instancias instalados</span><span class="sxs-lookup"><span data-stu-id="b966a-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="b966a-251">Ejemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="b966a-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="b966a-252">Actualizar SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="b966a-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="b966a-253">Referencia: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="b966a-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="b966a-254">Descargar desde [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="b966a-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="b966a-255">Asegúrese de que los servicios de Skype Empresarial Server 2015 están detenidos en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b966a-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="b966a-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="b966a-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="b966a-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b966a-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="b966a-258">Detener la ejecución SQL las instancias de SQL instaladas</span><span class="sxs-lookup"><span data-stu-id="b966a-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="b966a-259">Por ejemplo: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b966a-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="b966a-260">Por ejemplo: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b966a-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="b966a-261">Ex (solo Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="b966a-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="b966a-262">Instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="b966a-262">Install the update.</span></span>
5. <span data-ttu-id="b966a-263">Actualice el controlador ODBC 11 SQL Server para incluir compatibilidad con TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="b966a-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="b966a-264">Descargar [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="b966a-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="b966a-265">Asegúrese de que los servicios de Skype Empresarial Server 2015 estén detenidos en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b966a-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="b966a-266">Ejemplo (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="b966a-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="b966a-267">Ejemplo (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="b966a-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="b966a-268">Instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="b966a-268">Install the update.</span></span>
6. <span data-ttu-id="b966a-269">Implementar claves del Registro de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="b966a-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="b966a-270">Claves del Registro de requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b966a-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="b966a-271">Copie y pegue la siguiente prueba en el Bloc de notas y cambie el nombre de TLSPreReq.reg o un nombre de su elección y, a continuación, importe:</span><span class="sxs-lookup"><span data-stu-id="b966a-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="b966a-272">Para SQL back-end para grupos de servidores Enterprise Edition, los requisitos previos y la deshabilitación de TLS deben tratarse como cualquier SQL actualizaciones del sistema operativo; consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="b966a-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="b966a-273">Aunque se pueden combinar los pasos de deshabilitación de TLS y la aplicación de requisitos previos, recomendamos encarecidamente que se apliquen todos los requisitos previos antes de continuar con la deshabilitación de TLS 1.0 y 1.1 en el nivel del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b966a-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="b966a-274">El método recomendado sería preparar el entorno implementando todos los requisitos previos, validando que todas las cargas de trabajo funcionen correctamente y según lo esperado y, a continuación, continuar con TLS 1.0/1.1 deshabilitada más adelante.</span><span class="sxs-lookup"><span data-stu-id="b966a-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="b966a-275">Deshabilitar TLS 1.0 y 1.1 mediante la importación del Registro</span><span class="sxs-lookup"><span data-stu-id="b966a-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="b966a-276">Antes de continuar con los pasos siguientes, asegúrese de que ha completado todos los *requisitos previos y* actualizado Los servidores de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b966a-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="b966a-277">Copie el siguiente texto en un archivo del Bloc de notas y cámbiele el nombre **TLSDisable.reg:**</span><span class="sxs-lookup"><span data-stu-id="b966a-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="b966a-278">Importe el archivo .reg en cada servidor en el que desee deshabilitar TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="b966a-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="b966a-279">Reinicie el servidor.</span><span class="sxs-lookup"><span data-stu-id="b966a-279">Reboot the server.</span></span> <span data-ttu-id="b966a-280">Una vez que los servicios vuelvan a estar en línea, pase al siguiente servidor.</span><span class="sxs-lookup"><span data-stu-id="b966a-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="b966a-281">El enfoque para los grupos de servidores de Enterprise Edition es el mismo que se tomaría para cualquier actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b966a-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="b966a-282">Puede que haya observado que estamos haciendo algo más que deshabilitar TLS 1.0 y 1.1 aquí.</span><span class="sxs-lookup"><span data-stu-id="b966a-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="b966a-283">Estamos siendo compatibles con el nuevo orden del conjunto de cifrado (como se muestra anteriormente) y la deshabilitación de algunos cifrados débiles más antiguos.</span><span class="sxs-lookup"><span data-stu-id="b966a-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="b966a-284">Esta es la primera vez que hemos admitido oficialmente estos cambios en SCHANNEL y API de criptografía en Skype Empresarial Server, y es importante tener en cuenta que estos cambios son los únicos que admitemos y que hemos probado en este momento.</span><span class="sxs-lookup"><span data-stu-id="b966a-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="b966a-285">Podemos considerar configuraciones adicionales en el futuro, pero por ahora, no modifique el archivo de importación del Registro en su implementación.</span><span class="sxs-lookup"><span data-stu-id="b966a-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="b966a-286">Validar que las cargas de trabajo funcionan según lo esperado</span><span class="sxs-lookup"><span data-stu-id="b966a-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="b966a-287">Una vez que TLS 1.0 y 1.1 se hayan deshabilitado en su entorno, asegúrese de que todas las cargas de trabajo principales funcionan según lo esperado, como presencia de mensajería instantánea &, llamadas P2P, Telefonía IP empresarial, etc.</span><span class="sxs-lookup"><span data-stu-id="b966a-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="b966a-288">**Validar que solo se usa TLS 1.2**</span><span class="sxs-lookup"><span data-stu-id="b966a-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="b966a-289">Haga que el equipo de seguridad realice una nueva auditoría del tráfico de Skype Empresarial para asegurarse de que los protocolos antiguos TLS 1.0 y 1.1 ya no están en uso.</span><span class="sxs-lookup"><span data-stu-id="b966a-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="b966a-290">Como alternativa, puede usar Internet Explorer para probar las conexiones TLS a los servicios web desde Skype Empresarial Server 2015 después de deshabilitar TLS 1.0 y TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="b966a-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="b966a-291">Inicia Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b966a-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="b966a-292">Seleccione **Herramientas opciones** de  >  **Internet.**</span><span class="sxs-lookup"><span data-stu-id="b966a-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="b966a-293">Seleccione la **pestaña** Avanzadas.</span><span class="sxs-lookup"><span data-stu-id="b966a-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="b966a-294">En **Configuración,** desplácese hasta la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="b966a-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="b966a-295">Compruebe que TLS 1.0, TLS 1.1 y TLS 1.2 están habilitados.</span><span class="sxs-lookup"><span data-stu-id="b966a-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="b966a-296">Examine la dirección URL del servicio web interno del grupo de servidores de SfB 2015 (debe conectarse correctamente).</span><span class="sxs-lookup"><span data-stu-id="b966a-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="b966a-297">Vuelva a Internet Explorer y deshabilite la opción **de usar solo TLS 1.2.**</span><span class="sxs-lookup"><span data-stu-id="b966a-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="b966a-298">Vuelva a examinar la dirección URL del servicio web interno de su grupo de servidores de SfB 2015 (no se puede conectar).</span><span class="sxs-lookup"><span data-stu-id="b966a-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opciones de Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="b966a-300">Escenarios de implementación avanzada</span><span class="sxs-lookup"><span data-stu-id="b966a-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="b966a-301">Dado que algunos requisitos previos de dependencia son necesarios para admitir TLS 1.2 en Skype Empresarial Server 2015, la instalación desde medios RTM producirá un error en cualquier sistema en el que se hayan deshabilitado TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="b966a-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="b966a-302">**Implementar nuevos servidores Standard Edition o grupos de servidores Enterprise Edition una vez que TLS 1.0 y 1.1 se hayan deshabilitado en el entorno.**</span><span class="sxs-lookup"><span data-stu-id="b966a-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="b966a-303">**Opción 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="b966a-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="b966a-304">Tenga en cuenta que estamos actualizando SmartSetup para incluir los archivos binarios de SQL actualizados en una actualización acumulativa futura y actualizaremos este artículo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="b966a-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="b966a-305">**Opción 2:** Preinstalación de las SQL locales (RTCLOCAL y LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="b966a-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="b966a-306">Descargue y copie SQL Express 2014 SP2 (SQLEXPR_x64.exe) a la carpeta local en FE.</span><span class="sxs-lookup"><span data-stu-id="b966a-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="b966a-307">Supongamos que la ruta de acceso de <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="b966a-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="b966a-308">Inicie PowerShell o el símbolo del sistema y vaya a <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="b966a-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="b966a-309">Cree la instancia de SQL RTCLOCAL ejecutando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="b966a-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="b966a-310">Espere hasta SQLEXPR_x64.exe termine antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="b966a-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="b966a-311">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="b966a-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="b966a-312">Cree la instancia de SQL LYNCLOCAL ejecutando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="b966a-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="b966a-313">Espere hasta SQLEXPR_x64.exe termine antes de continuar con el paso siguiente:</span><span class="sxs-lookup"><span data-stu-id="b966a-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="b966a-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="b966a-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="b966a-315">Ejecute el programa de instalación de Skype Empresarial Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="b966a-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="b966a-316">Siga los pasos restantes de la sección de requisitos previos anterior.</span><span class="sxs-lookup"><span data-stu-id="b966a-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="b966a-317">**Opción 3:** También puede reemplazar manualmente los archivos binarios en un directorio de medios de instalación local de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b966a-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="b966a-318">Instalar requisitos previos para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b966a-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="b966a-319">Instale .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="b966a-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="b966a-320">**Nota:** Introdujimos por primera vez compatibilidad con .NET 4.7 en Skype Empresarial Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="b966a-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="b966a-321">Por lo tanto, en pasos posteriores, actualizaremos componentes principales antes de la instalación principal.</span><span class="sxs-lookup"><span data-stu-id="b966a-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="b966a-322">Descargar: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="b966a-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="b966a-323">Referencia: software que debe instalarse antes de una implementación de [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="b966a-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="b966a-324">Copiar archivos o carpetas ISO:</span><span class="sxs-lookup"><span data-stu-id="b966a-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="b966a-325">Con la ISO de Skype Empresarial Server 2015 adjunta, abra el directorio raíz de la unidad que está adjunta como (por ejemplo, D: en el Explorador \) de archivos.</span><span class="sxs-lookup"><span data-stu-id="b966a-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="b966a-326">Copie todas las carpetas y archivos en una carpeta en un disco local (por ejemplo, C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="b966a-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="b966a-327">**Nota:** Antes de instalar componentes, algunos archivos tendrán que actualizarse para admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b966a-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="b966a-328">Reemplace los paquetes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="b966a-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="b966a-329">Reemplace los paquetes MSI y EXE existentes en la carpeta /Setup/amd64/ del medio de instalación en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b966a-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="b966a-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="b966a-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="b966a-331">Cambia el nombre SQLEXPR_x64 en el equipo local y reemplaza el archivo existente en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b966a-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b966a-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="b966a-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="b966a-333">**Nota:** Cambie el nombre si es necesario para sqlncli.msi y, a continuación, reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b966a-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b966a-334">SQL de administración: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="b966a-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="b966a-335">**Nota:** El Paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="b966a-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="b966a-336">Seleccione esta opción para SharedManagementObjects.msi solo.</span><span class="sxs-lookup"><span data-stu-id="b966a-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="b966a-337">**Nota:** Reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b966a-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="b966a-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="b966a-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="b966a-339">**Nota:** El Paquete de características tendrá una gran cantidad de elementos que se pueden descargar.</span><span class="sxs-lookup"><span data-stu-id="b966a-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="b966a-340">Seleccionar para descargar CQLSysClrTypes.msi solo</span><span class="sxs-lookup"><span data-stu-id="b966a-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="b966a-341">**Nota:** Reemplace el archivo existente que existe en la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b966a-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="b966a-342">Instalar componentes principales:</span><span class="sxs-lookup"><span data-stu-id="b966a-342">Install Core Components:</span></span> 
    - <span data-ttu-id="b966a-343">Ejecute Setup.exe desde la carpeta Setup/amd64/ del medio de instalación.</span><span class="sxs-lookup"><span data-stu-id="b966a-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="b966a-344">Siga las instrucciones para instalar componentes principales</span><span class="sxs-lookup"><span data-stu-id="b966a-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="b966a-345">Cerrar componentes principales.</span><span class="sxs-lookup"><span data-stu-id="b966a-345">Close Core Components.</span></span>
6. <span data-ttu-id="b966a-346">Actualizar componentes principales:</span><span class="sxs-lookup"><span data-stu-id="b966a-346">Update Core Components:</span></span> 
    - <span data-ttu-id="b966a-347">Descargue el Instalador de actualización de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b966a-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="b966a-348">Ejecute el instalador para actualizar componentes principales e instalar los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b966a-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="b966a-349">**Nota:** A fecha de lanzamiento de CU6HF2, la característica de actualización automática solo se instalará actualmente hasta CU6.</span><span class="sxs-lookup"><span data-stu-id="b966a-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="b966a-350">Por lo tanto, el actualizador debe ejecutarse por separado para actualizar componentes principales a la versión 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="b966a-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="b966a-351">Referencia: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="b966a-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="b966a-352">Instalar herramientas administrativas (opcional):</span><span class="sxs-lookup"><span data-stu-id="b966a-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="b966a-353">Esto instalará los tipos Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) y Microsoft System CLR Types for SQL Server 2014 (x64) mediante los archivos actualizados.</span><span class="sxs-lookup"><span data-stu-id="b966a-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="b966a-354">Además, el Generador de topologías y el Panel de control de Skype Empresarial Server 2015 estarán disponibles en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b966a-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="b966a-355">Instalar almacén de configuración local (paso 1):</span><span class="sxs-lookup"><span data-stu-id="b966a-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="b966a-356">Abra el Asistente para la implementación, haga clic en Instalar o actualizar el sistema de Skype Empresarial Server y haga clic en Ejecutar **en** el paso 1: Instalar almacén de configuración local.</span><span class="sxs-lookup"><span data-stu-id="b966a-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="b966a-357">Haga **clic en Siguiente** en el cuadro de diálogo Instalar almacén de **configuración** local.</span><span class="sxs-lookup"><span data-stu-id="b966a-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="b966a-358">![Cuadro de diálogo Instalar almacén de configuración local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="b966a-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="b966a-359">Revise los resultados y asegúrese de que el estado de la tarea se ha completado.</span><span class="sxs-lookup"><span data-stu-id="b966a-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="b966a-360">Revise el archivo de registro resultante haciendo clic **en Ver registro.**</span><span class="sxs-lookup"><span data-stu-id="b966a-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="b966a-361">![El estado de la tarea se muestra como completado](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="b966a-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="b966a-362">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b966a-362">Click **Finish**.</span></span>
9. <span data-ttu-id="b966a-363">Configurar o quitar componentes de Skype Empresarial Server (paso 2):</span><span class="sxs-lookup"><span data-stu-id="b966a-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="b966a-364">Abra el Asistente para la implementación, haga clic  en Instalar o actualizar el sistema **de Skype** Empresarial Server y, a continuación, haga clic en Ejecutar en el paso 2: Configurar o quitar componentes de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b966a-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="b966a-365">Haga **clic en Siguiente** en el cuadro de diálogo Configurar componentes de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b966a-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="b966a-366">![La ventana Configurar componentes de Skype Empresarial Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="b966a-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="b966a-367">Revise el registro con View Log y valide que la instalación se haya completado sin problemas.</span><span class="sxs-lookup"><span data-stu-id="b966a-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="b966a-368">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b966a-368">Click **Finish**.</span></span>
10. <span data-ttu-id="b966a-369">Continúe con la instalación y configuración adicionales según sea necesario (puede reanudar los procedimientos de instalación normales en este punto).</span><span class="sxs-lookup"><span data-stu-id="b966a-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
