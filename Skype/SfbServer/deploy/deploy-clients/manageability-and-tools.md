---
title: Herramientas y capacidad de administración del sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lea este tema para obtener información sobre las herramientas de administración de Skype Room System.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093554"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="0799d-103">Herramientas y capacidad de administración del sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="0799d-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="0799d-104">Lea este tema para obtener información sobre las herramientas de administración de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="0799d-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="0799d-105">Portal administrativo</span><span class="sxs-lookup"><span data-stu-id="0799d-105">Administrative Portal</span></span>

<span data-ttu-id="0799d-106">Para las implementaciones locales de Skype Empresarial Server, puede usar el portal administrativo sistema de salón de Skype para administrar y supervisar activamente las implementaciones del sistema de sala de Skype dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="0799d-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="0799d-107">Vea el siguiente artículo para obtener más detalles:</span><span class="sxs-lookup"><span data-stu-id="0799d-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="0799d-108">Implementar SRS v1 Administrative Web Portal en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0799d-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="0799d-109">Lista de comprobación de Exchange</span><span class="sxs-lookup"><span data-stu-id="0799d-109">Exchange Checklist</span></span>

- <span data-ttu-id="0799d-110">Confirme que la detección automática está configurada y que hay disponible un REGISTRO A/CNAME de DNS interno para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="0799d-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="0799d-111">Ping autodiscover (por ejemplo, Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0799d-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="0799d-112">Pruebe el servicio de detección automática con la herramienta Analizador de conectividad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0799d-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="0799d-113">Elija la primera prueba: "No puedo iniciar sesión con Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="0799d-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="0799d-114">Si la sala de reuniones ya tiene un buzón de recursos, extienda esta cuenta para el sistema de salas de Skype (script de ejemplo en la parte inferior de la página).</span><span class="sxs-lookup"><span data-stu-id="0799d-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="0799d-115">Lista de comprobación de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0799d-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="0799d-116">Ejecute las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="0799d-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="0799d-117">Analizador de procedimientos recomendados de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0799d-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="0799d-118">Herramienta de análisis de estado de Skype Empresarial (Excel)</span><span class="sxs-lookup"><span data-stu-id="0799d-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="0799d-119">Analizador de conectividad de Skype Empresarial de 32 o 64 bits</span><span class="sxs-lookup"><span data-stu-id="0799d-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="0799d-120">Revisar [Útiles nuevas herramientas de solución de problemas y análisis para Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="0799d-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span></span> <span data-ttu-id="0799d-121">Confirme que tiene un grupo de Skype Empresarial y un servidor de Office Web Apps y que puede compartir una plataforma de PowerPoint con el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="0799d-122">Si la sala de reuniones ya tiene un buzón de recursos, habilitelo para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="0799d-123">Si es necesario, solicite un DID (número de teléfono) para el sistema de salas de reuniones y actualice el campo Teléfono general en la herramienta Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0799d-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="0799d-124">Red</span><span class="sxs-lookup"><span data-stu-id="0799d-124">Network</span></span>

- <span data-ttu-id="0799d-125">Asegúrese de que tiene una conexión de red por cable para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="0799d-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="0799d-126">Lea la Guía de planeación de red para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="0799d-127">Solicitar una evaluación de red de Skype Empresarial a un partner de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="0799d-128">Lea los datos de rendimiento capturados en la Herramienta de análisis de estado de Skype Empresarial (Excel).</span><span class="sxs-lookup"><span data-stu-id="0799d-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="0799d-129">Ejecute la Herramienta de análisis de red.</span><span class="sxs-lookup"><span data-stu-id="0799d-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="0799d-130">Ejecute la Herramienta de diagnóstico de llamadas previas.</span><span class="sxs-lookup"><span data-stu-id="0799d-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="0799d-131">Seguridad del sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="0799d-131">Skype Room System Security</span></span>

<span data-ttu-id="0799d-132">Sistema de salón de Skype es un sistema incrustado que se puede integrar completamente en una implementación de Windows, con el modelo de seguridad de Skype Empresarial, la administración de derechos y las herramientas de administración como SCOM.</span><span class="sxs-lookup"><span data-stu-id="0799d-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="0799d-133">Entre las características se incluyen:</span><span class="sxs-lookup"><span data-stu-id="0799d-133">Features include:</span></span>
  
- <span data-ttu-id="0799d-134">Un filtro de escritura para evitar escrituras en disco en modo de usuario</span><span class="sxs-lookup"><span data-stu-id="0799d-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="0799d-135">App Locker para evitar que se ejecuten aplicaciones no autorizadas.</span><span class="sxs-lookup"><span data-stu-id="0799d-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="0799d-136">Todos los puertos USB están deshabilitados en modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="0799d-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="0799d-137">No hay aplicaciones ni visores estándar en el hardware del sistema de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="0799d-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="0799d-138">Todo el contenido se representa a través de protocolos HTTP o RDP.</span><span class="sxs-lookup"><span data-stu-id="0799d-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="0799d-139">El equipo del dispositivo ejecuta el sistema operativo Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="0799d-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="0799d-140">Todo el hardware, incluidos los dispositivos, lo proporcionan los partners OEM.</span><span class="sxs-lookup"><span data-stu-id="0799d-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="0799d-141">Combinación de dominio opcional a servicios de dominio de Active Directory (AD DS), lo que habilita la administración y el control de cuentas de seguridad local.</span><span class="sxs-lookup"><span data-stu-id="0799d-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="0799d-142">También puede administrar la cuenta de administrador local mediante el Centro de administración de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="0799d-143">El sistema de sala de Skype se actualiza a través de procesos estándar de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="0799d-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="0799d-144">El sistema de sala de Skype se conecta con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="0799d-145">Skype Empresarial usa el cifrado y la autorización de extremo a extremo para todos los modos de comunicación</span><span class="sxs-lookup"><span data-stu-id="0799d-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="0799d-146">Skype Room System admite estándares de seguridad y cumplimiento de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="0799d-147">Vea [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0799d-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="0799d-148">Licencia</span><span class="sxs-lookup"><span data-stu-id="0799d-148">License</span></span>

<span data-ttu-id="0799d-149">Compruebe que usa un KMS para activar software.</span><span class="sxs-lookup"><span data-stu-id="0799d-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="0799d-150">Si es así, es posible que deba comprobar o agregarle la clave KMS del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="0799d-151">Si no usa KMS, solicite la clave de licencia por volumen para mak del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="0799d-152">Claves de licencia</span><span class="sxs-lookup"><span data-stu-id="0799d-152">License keys</span></span>

<span data-ttu-id="0799d-153">Sistema de sala de Skype ejecuta el cliente de escritorio de Skype Empresarial en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0799d-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="0799d-154">Si El sistema de salón de Skype es un miembro del dominio, descubrirá el KMS.</span><span class="sxs-lookup"><span data-stu-id="0799d-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="0799d-155">(y si tiene la clave KMS de licencias por volumen, se activará automáticamente).</span><span class="sxs-lookup"><span data-stu-id="0799d-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="0799d-156">Las licencias por volumen también proporcionan una MAK, que se especifica ya que muestra xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="0799d-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="0799d-157">(Necesita acceso a Internet para activarse con MAK, pero no kms).</span><span class="sxs-lookup"><span data-stu-id="0799d-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="0799d-158">Para obtener más información, vea Activación por volumen de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="0799d-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="0799d-159">Para escribir la clave MAK, vaya a Configuración de OEM \> SRS Licensing Tool.</span><span class="sxs-lookup"><span data-stu-id="0799d-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="0799d-160">Haga clic en Comprobar estado.</span><span class="sxs-lookup"><span data-stu-id="0799d-160">Click Check Status.</span></span> <span data-ttu-id="0799d-161">Cuando el estado diga "el producto no está activado", escriba la clave.</span><span class="sxs-lookup"><span data-stu-id="0799d-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="0799d-162">Si durante la activación se produce un error que indica: "'El servicio de licencias de software informó de que la clave del producto no es válida", compruebe que:</span><span class="sxs-lookup"><span data-stu-id="0799d-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="0799d-163">La clave se introdujo correctamente.</span><span class="sxs-lookup"><span data-stu-id="0799d-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="0799d-164">Ha escrito la clave MAK de Skype Empresarial y no otra clave.</span><span class="sxs-lookup"><span data-stu-id="0799d-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="0799d-165">El sistema tiene acceso a Internet.</span><span class="sxs-lookup"><span data-stu-id="0799d-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="0799d-166">Puede activarse por teléfono, pero debe haber intentado activarla primero con la herramienta de licencias SRS.</span><span class="sxs-lookup"><span data-stu-id="0799d-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="0799d-167">Para activarla por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado corta).</span><span class="sxs-lookup"><span data-stu-id="0799d-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="0799d-168">En el Asistente para activación de Office, seleccione Activación telefónica, llame a Microsoft, escriba el número largo y escriba una respuesta.</span><span class="sxs-lookup"><span data-stu-id="0799d-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="0799d-169">Entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="0799d-169">Certificate Authority</span></span>

<span data-ttu-id="0799d-170">Confirme que la entidad de certificación usada para emitir el certificado de Office Web Apps Server 2013 tiene una ruta de acceso HTTP incluida en la propiedad Lista de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="0799d-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="0799d-171">Importe el archivo de certificado (.crt) al sistema de sala de Skype si usa Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0799d-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="0799d-172">Se obtiene fácilmente desde el recurso compartido CertEnroll del servidor de ca o en la carpeta Raíz de confianza de cualquier equipo unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="0799d-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="0799d-173">Certificados</span><span class="sxs-lookup"><span data-stu-id="0799d-173">Certificates</span></span>

<span data-ttu-id="0799d-174">Compruebe que la entidad de certificación tiene una ruta de acceso http para la lista de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="0799d-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="0799d-175">Si no es así, actualice la CA para que incluya una.</span><span class="sxs-lookup"><span data-stu-id="0799d-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="0799d-176">Instale certificados en la configuración de administración del sistema de salón de Skype en System Settings \> Certificate Manager.</span><span class="sxs-lookup"><span data-stu-id="0799d-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="0799d-177">Necesita la CA raíz de empresa para el certificado interno.</span><span class="sxs-lookup"><span data-stu-id="0799d-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="0799d-178">Una forma de obtener los certificados que necesita es detectar la CA que emitió los certificados.</span><span class="sxs-lookup"><span data-stu-id="0799d-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="0799d-179">Para Skype Empresarial Server, en un equipo de Skype Empresarial, haga clic en Configuración \> Herramientas configuración Configuración de conferencia de acceso telefónico \> local.</span><span class="sxs-lookup"><span data-stu-id="0799d-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="0799d-180">Se abre una página web protegida por la CA que emitió los certificados internos.</span><span class="sxs-lookup"><span data-stu-id="0799d-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="0799d-181">Haga clic en el icono Bloquear de la barra de direcciones del explorador para mostrar un informe de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0799d-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="0799d-182">Haga clic en Ver certificados y examine la propiedad Punto de distribución CRL.</span><span class="sxs-lookup"><span data-stu-id="0799d-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="0799d-183">El segundo parámetro CN debe ser el nombre del servidor de la CA.</span><span class="sxs-lookup"><span data-stu-id="0799d-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="0799d-184">Ahora abre el Explorador de Windows para esa \\ \< CA Server Name \> dirección \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="0799d-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="0799d-185">Copie los dos archivos .crl y el archivo .crt en una unidad flash y póngalo en el lado izquierdo de la tarjeta SMART.</span><span class="sxs-lookup"><span data-stu-id="0799d-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="0799d-186">Importe el archivo .crt al sistema de salón de Skype en la carpeta Entidad de certificación de sala de confianza.</span><span class="sxs-lookup"><span data-stu-id="0799d-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="0799d-187">Importe los archivos .crl en el sistema de salón de Skype en la carpeta Autoridades de certificado intermedias.</span><span class="sxs-lookup"><span data-stu-id="0799d-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="0799d-188">(Debe cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).</span><span class="sxs-lookup"><span data-stu-id="0799d-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="0799d-189">Nota: El servidor de Office Web Apps 2013 puede compartir la misma CA que Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0799d-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="0799d-190">Si no es así, no podrá compartir PowerPoint en una reunión.</span><span class="sxs-lookup"><span data-stu-id="0799d-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="0799d-191">Compruebe con IT y obtenga los archivos CRT y CRL de certEnroll del recurso compartido de red de ca, tal como se ha explicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0799d-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="0799d-192">La pertenencia a dominios puede simplificar algunas cosas porque puede tratar el sistema de salón de Skype como un sistema windows y puede depender de Active Directory para algunos de los aspectos del certificado.</span><span class="sxs-lookup"><span data-stu-id="0799d-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="0799d-193">Sin embargo, lo mejor es administrarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="0799d-193">However, it's best to manually manage this.</span></span>
