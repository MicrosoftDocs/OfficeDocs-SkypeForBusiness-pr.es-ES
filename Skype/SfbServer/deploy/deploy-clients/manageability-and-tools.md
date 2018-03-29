---
title: Administración y herramientas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="38424-103">Administración y herramientas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="38424-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="38424-104">Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="38424-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="38424-105">Portal administrativo</span><span class="sxs-lookup"><span data-stu-id="38424-105">Administrative Portal</span></span>

<span data-ttu-id="38424-106">Para Skype para las implementaciones locales de Business Server, puede utilizar el portal de Skype sala sistema administrativo para administrar y supervisar la implementación del sistema de sala de Skype dentro de su organización activamente.</span><span class="sxs-lookup"><span data-stu-id="38424-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="38424-107">Vea los artículos siguientes para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="38424-107">See the following articles for more details:</span></span>
  
- [<span data-ttu-id="38424-108">Implementar el Portal de Web administrativa sistema de sala de Lync Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38424-108">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [<span data-ttu-id="38424-109">Configurar el entorno de Lync Server 2013 para Lync sala sistema administrativo Portal Web</span><span class="sxs-lookup"><span data-stu-id="38424-109">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [<span data-ttu-id="38424-110">Instalación del Portal de administración Web de sistema de sala de Lync 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38424-110">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [<span data-ttu-id="38424-111">Mediante el Portal de administración Web de sistema de sala de Lync 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38424-111">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="38424-112">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="38424-112">System Center Operations Manager</span></span>

<span data-ttu-id="38424-113">Sistema de sala de Skype puede controlarse a través de System Center Operations Manager (SCOM) descargando el [Paquete de administración de sistema de sala de Skype](https://www.microsoft.com/en-us/download/details.aspx?id=42320) e instalarlo en el servidor SCOM.</span><span class="sxs-lookup"><span data-stu-id="38424-113">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/en-us/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="38424-114">Puede utilizar SCOM para establecer alertas, supervisar el estado del sistema del sitio de Skype, generar informes de actividad y mucho más.</span><span class="sxs-lookup"><span data-stu-id="38424-114">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="38424-115">Sistema de sala de Skype viene con un agente de supervisión preinstalado que puede configurarse para que apunte al servidor SCOM.</span><span class="sxs-lookup"><span data-stu-id="38424-115">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="38424-116">Consulte la Guía de instalación proporcionada por el fabricante del sistema del sitio de Skype para saber cómo configurar al agente de supervisión en el sistema del sitio de Skype.</span><span class="sxs-lookup"><span data-stu-id="38424-116">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="38424-117">Lista de comprobación de Exchange</span><span class="sxs-lookup"><span data-stu-id="38424-117">Exchange Checklist</span></span>

- <span data-ttu-id="38424-118">Confirme que la Detección automática está configurada y que hay un REGISTRO DE A/CNAME DE DNS disponible para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="38424-118">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="38424-119">Realice un ping de detección automática (p. ej. Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="38424-119">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="38424-120">Pruebe su servicio de Detección automática con la Herramienta Analizador de conectividad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38424-120">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="38424-121">Elija la primera prueba, "Yo no puedo iniciar sesión con Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="38424-121">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="38424-122">Si la sala de reuniones ya tiene un buzón de recursos, ampliar esta cuenta para el sistema de sala de Skype (secuencia de comandos de ejemplo en la parte inferior de la página).</span><span class="sxs-lookup"><span data-stu-id="38424-122">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="38424-123">Skype para lista de comprobación de negocio</span><span class="sxs-lookup"><span data-stu-id="38424-123">Skype for Business Checklist</span></span>

- <span data-ttu-id="38424-124">Ejecute las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="38424-124">Run the following tools:</span></span>
    
  - <span data-ttu-id="38424-125">Skype para negocios Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="38424-125">Skype for Business Best Practices Analyzer</span></span> 
    
  - <span data-ttu-id="38424-126">Skype para la herramienta de análisis de negocio salud (Excel)</span><span class="sxs-lookup"><span data-stu-id="38424-126">Skype for Business Health Analysis Tool (Excel)</span></span> 
    
  - <span data-ttu-id="38424-127">Skype para el analizador de conectividad empresarial 32 bits o 64 bits</span><span class="sxs-lookup"><span data-stu-id="38424-127">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="38424-128">Revise [la solución de problemas de nuevo de forma útil y herramientas de análisis para Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="38424-128">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="38424-129">Confirme que tiene un Skype para el grupo de negocio y un servidor de Office Web Apps y puede compartir un deck de PowerPoint utilizando el Skype para el cliente de Business.</span><span class="sxs-lookup"><span data-stu-id="38424-129">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="38424-130">Si la sala de reuniones ya tiene un buzón de recursos, habilitarla para Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="38424-130">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="38424-131">Si es necesario, solicite un DID (número de teléfono) para el sistema de salas de reuniones y actualice el campo Teléfono general en la herramienta de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38424-131">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="38424-132">Red</span><span class="sxs-lookup"><span data-stu-id="38424-132">Network</span></span>

- <span data-ttu-id="38424-133">Asegúrese de que dispone de una conexión de red con cable para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="38424-133">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="38424-134">Lea la Guía de planeamiento para Skype para el negocio de red.</span><span class="sxs-lookup"><span data-stu-id="38424-134">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="38424-135">Solicitar un Skype para la evaluación de la red empresarial desde un Skype para el socio comercial.</span><span class="sxs-lookup"><span data-stu-id="38424-135">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="38424-136">Lea los datos de rendimiento capturados en el Skype para la herramienta de análisis de negocio salud (Excel).</span><span class="sxs-lookup"><span data-stu-id="38424-136">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="38424-137">Ejecute la Herramienta de análisis de red.</span><span class="sxs-lookup"><span data-stu-id="38424-137">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="38424-138">Ejecute la Herramienta de diagnóstico previa a llamadas.</span><span class="sxs-lookup"><span data-stu-id="38424-138">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="38424-139">Seguridad del sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="38424-139">Skype Room System Security</span></span>

<span data-ttu-id="38424-140">Sistema de sala de Skype es un sistema incrustado que puede integrarse completamente en una implementación de Windows, usando el Skype para el modelo de seguridad de negocios, administración de derechos y herramientas de administración como SCOM.</span><span class="sxs-lookup"><span data-stu-id="38424-140">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="38424-141">Estas características incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38424-141">Features include:</span></span>
  
- <span data-ttu-id="38424-142">Un filtro de escritura para evitar escrituras en el disco en modo de usuario</span><span class="sxs-lookup"><span data-stu-id="38424-142">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="38424-p105">Un bloqueador de aplicaciones para evitar que se ejecuten aplicaciones no autorizadas. Todos los puertos USB están deshabilitados en el modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="38424-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="38424-145">No hay aplicaciones estándares o visores residen en el hardware del sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="38424-145">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="38424-146">Todo el contenido se representa mediante los protocolos HTTP o RDP.</span><span class="sxs-lookup"><span data-stu-id="38424-146">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="38424-p107">El equipo ejecuta el sistema operativo Windows Embedded Standard 7. Los socios OEM proporcionan todo el hardware, incluidos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="38424-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="38424-149">Unión de dominio opcional a Active Directory Domain Services (AD DS), que permite la administración y el control de cuentas de seguridad locales.</span><span class="sxs-lookup"><span data-stu-id="38424-149">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="38424-150">También puede administrar la cuenta de administrador local mediante el Skype para el centro de administración de negocios.</span><span class="sxs-lookup"><span data-stu-id="38424-150">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="38424-151">Sistema de sala de Skype se actualiza mediante los procesos estándar de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="38424-151">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="38424-152">Sistema de sala de Skype se conecta con Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="38424-152">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="38424-153">Skype para empresas utiliza cifrado de extremo a extremo y la autorización para todos los modos de comunicación</span><span class="sxs-lookup"><span data-stu-id="38424-153">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="38424-154">Sistema de sala de Skype es compatible con Skype para los estándares de seguridad y cumplimiento de normas empresariales.</span><span class="sxs-lookup"><span data-stu-id="38424-154">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="38424-155">Consulte Planear la seguridad en Lync Server 2013 para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="38424-155">See Planning for security in Lync Server 2013 for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="38424-156">Licencia</span><span class="sxs-lookup"><span data-stu-id="38424-156">License</span></span>

<span data-ttu-id="38424-157">Compruebe que usa un KMS para activar software.</span><span class="sxs-lookup"><span data-stu-id="38424-157">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="38424-158">Si es así, puede que necesite comprobar o agregar el Skype para la clave KMS cliente empresarial a él.</span><span class="sxs-lookup"><span data-stu-id="38424-158">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="38424-159">Si no utiliza KMS, solicitar la clave de licencias por para el Skype para Business client MAK de volumen.</span><span class="sxs-lookup"><span data-stu-id="38424-159">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="38424-160">Claves de licencia</span><span class="sxs-lookup"><span data-stu-id="38424-160">License keys</span></span>

<span data-ttu-id="38424-161">Sistema de sala de Skype se ejecuta el Skype para el cliente de escritorio de negocios en el plano.</span><span class="sxs-lookup"><span data-stu-id="38424-161">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="38424-162">Si el sistema del sitio de Skype es miembro de un dominio, descubrirá el KMS.</span><span class="sxs-lookup"><span data-stu-id="38424-162">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="38424-163">(y si tiene la clave de Lync KMS de licencias por volumen se activará automáticamente).</span><span class="sxs-lookup"><span data-stu-id="38424-163">(and if it has the Volume Licensing KMS Lync Key it will activate automatically).</span></span> <span data-ttu-id="38424-164">Licencias por volumen también proporciona una MAK, que se escribe como muestra xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="38424-164">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="38424-165">(Necesita acceso a Internet para activarse utilizando MAK pero no KMS).</span><span class="sxs-lookup"><span data-stu-id="38424-165">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="38424-166">Para obtener más información, vea activación por volumen de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="38424-166">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="38424-167">Para introducir la clave MAK, vaya a configuración del OEM \> SRS Licensing Tool.</span><span class="sxs-lookup"><span data-stu-id="38424-167">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="38424-168">Haga clic en Comprobar estado.</span><span class="sxs-lookup"><span data-stu-id="38424-168">Click Check Status.</span></span> <span data-ttu-id="38424-169">Cuando el estado dice "no se activa el producto", introduzca la clave.</span><span class="sxs-lookup"><span data-stu-id="38424-169">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="38424-170">Si durante la activación se produce un error que dice: "' el servicio de licencias de Software informó que la clave del producto es válida," a continuación, compruebe que:</span><span class="sxs-lookup"><span data-stu-id="38424-170">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="38424-171">La clave se ha escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="38424-171">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="38424-172">Insertó el Skype de clave MAK de negocio y no en otro.</span><span class="sxs-lookup"><span data-stu-id="38424-172">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="38424-173">El sistema tiene acceso a Internet.</span><span class="sxs-lookup"><span data-stu-id="38424-173">The system has Internet access.</span></span>
    
- <span data-ttu-id="38424-174">Puede realizar la activación mediante teléfono, pero debe haber intentado la activación con la Herramienta de licencias de SRS antes.</span><span class="sxs-lookup"><span data-stu-id="38424-174">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="38424-175">Para realizar la activación por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado breve).</span><span class="sxs-lookup"><span data-stu-id="38424-175">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="38424-176">En el Asistente para la activación de Office, seleccione la activación por teléfono, llame a Microsoft, escriba el número de tipo long y escribir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="38424-176">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="38424-177">Entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="38424-177">Certificate Authority</span></span>

<span data-ttu-id="38424-178">Confirme que la Entidad de certificación usada para emitir el certificado de Office Web Apps Server 2013 tiene una ruta HTTP incluida en la propiedad Lista de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="38424-178">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="38424-179">Importar el archivo de certificado (.crt) al sistema de sala de Skype si utiliza Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="38424-179">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="38424-180">Puede obtenerlo fácilmente del recurso compartido CertEnroll del servidor de la Entidad de certificación, o en la carpeta raíz de confianza de cualquier equipo unido al dominio.</span><span class="sxs-lookup"><span data-stu-id="38424-180">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="38424-181">Certificados</span><span class="sxs-lookup"><span data-stu-id="38424-181">Certificates</span></span>

<span data-ttu-id="38424-p114">Compruebe que la Entidad de certificación tiene una ruta HTTP en la Lista de revocación de certificados. Si no es así, actualice su Entidad de certificación para que tenga una.</span><span class="sxs-lookup"><span data-stu-id="38424-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="38424-184">Instalar los certificados en la configuración del administrador del sistema de sala de Skype en la configuración del sistema \> Administrador de certificados.</span><span class="sxs-lookup"><span data-stu-id="38424-184">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="38424-185">Necesita la Entidad de certificación raíz de la empresa para su certificado interno.</span><span class="sxs-lookup"><span data-stu-id="38424-185">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="38424-186">Una forma de obtener los certificados que necesita es detectar la Entidad de certificación que emitió los certificados.</span><span class="sxs-lookup"><span data-stu-id="38424-186">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="38424-187">Skype para Business Server, en un PC de Skype para el negocio, haga clic en configuración \> herramientas \> configuración conferencia de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="38424-187">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="38424-188">Esto abrirá una página web asegurada por la Entidad de certificación que emitió los certificados de Lync internos.</span><span class="sxs-lookup"><span data-stu-id="38424-188">This opens a web page secured by the CA that issued the internal Lync certificates.</span></span> <span data-ttu-id="38424-189">Haga clic en el icono de candado en la barra de dirección del navegador para mostrar un informe de seguridad.</span><span class="sxs-lookup"><span data-stu-id="38424-189">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="38424-190">Haga clic en Ver certificados y examine la propiedad Puntos de distribución CRL.</span><span class="sxs-lookup"><span data-stu-id="38424-190">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="38424-191">El segundo parámetro de CN debería ser el nombre del servidor de la Entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="38424-191">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="38424-192">Ahora abra el Explorador de Windows para esa dirección \\ \< nombre del servidor de entidad emisora de certificados \>\CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="38424-192">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="38424-193">Copie los dos archivos .crl y el archivo .crt en una unidad extraíble y póngalos en la parte izquierda del panel SMART.</span><span class="sxs-lookup"><span data-stu-id="38424-193">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="38424-194">Importar el archivo .crt al sistema de sala de Skype bajo carpeta de sala de confianza entidad emisora de certificados.</span><span class="sxs-lookup"><span data-stu-id="38424-194">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="38424-195">Importar los archivos .crl en el sistema de sala de Skype en la carpeta entidades emisoras de certificados intermedias.</span><span class="sxs-lookup"><span data-stu-id="38424-195">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="38424-196">(Necesita cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).</span><span class="sxs-lookup"><span data-stu-id="38424-196">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="38424-p118">Nota: El servidor de Office Web Apps 2013 puede compartir la misma Entidad de certificación que Lync. Si no lo hace, no podrá compartir archivos de PowerPoint durante una reunión. Póngase en contacto con el departamento de TI y obtenga los archivos CRT y CRL del CertEnroll del recurso compartido de red de la Entidad de certificación tal y como se ha explicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="38424-p118">Note: The Office Web Apps 2013 server may share the same CA as Lync. If it doesn't you won't be able to share PowerPoint in a meeting. Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="38424-200">Pertenencia a un dominio puede simplificar algunas cosas porque el sistema de sala de Skype puede tratar como un sistema de Windows y puede depender de Active Directory para algunos de los aspectos del certificado.</span><span class="sxs-lookup"><span data-stu-id="38424-200">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="38424-201">De todas formas, es mejor administrar esto manualmente.</span><span class="sxs-lookup"><span data-stu-id="38424-201">However, it's best to manually manage this.</span></span>
  

