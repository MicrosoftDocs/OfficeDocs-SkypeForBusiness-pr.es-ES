---
title: Administración y herramientas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.
ms.openlocfilehash: c9289d3fffa78dd7ffd94fa17784c1b06c2278b1
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547263"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="e610d-103">Administración y herramientas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="e610d-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="e610d-104">Lea este tema para obtener información acerca de las herramientas de administración para el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="e610d-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="e610d-105">Portal administrativo</span><span class="sxs-lookup"><span data-stu-id="e610d-105">Administrative Portal</span></span>

<span data-ttu-id="e610d-106">Para las implementaciones locales de Skype empresarial Server, puede usar el portal administrativo del sistema de salas de Skype para administrar y supervisar activamente las implementaciones de sistemas de salas de Skype dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="e610d-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="e610d-107">Para obtener más información, consulte el artículo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e610d-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="e610d-108">Implementar el portal web administrativo SRS V1 en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e610d-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="e610d-109">Lista de comprobación de Exchange</span><span class="sxs-lookup"><span data-stu-id="e610d-109">Exchange Checklist</span></span>

- <span data-ttu-id="e610d-110">Confirme que la Detección automática está configurada y que hay un REGISTRO DE A/CNAME DE DNS disponible para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="e610d-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="e610d-111">Realice un ping de detección automática (p. ej. Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e610d-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="e610d-112">Pruebe su servicio de Detección automática con la Herramienta Analizador de conectividad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e610d-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="e610d-113">Elija la primera prueba, "no puedo iniciar sesión con Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="e610d-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="e610d-114">Si la sala de reuniones ya tiene un buzón de recursos, extienda esta cuenta para el sistema de salas de Skype (secuencia de comandos de ejemplo en la parte inferior de la página).</span><span class="sxs-lookup"><span data-stu-id="e610d-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="e610d-115">Lista de comprobación de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="e610d-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="e610d-116">Ejecute las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="e610d-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="e610d-117">Analizador de procedimientos recomendados de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="e610d-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="e610d-118">Herramienta de análisis de mantenimiento de Skype empresarial (Excel)</span><span class="sxs-lookup"><span data-stu-id="e610d-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="e610d-119">Analizador de conectividad de Skype para empresas 32-bit o 64 bits</span><span class="sxs-lookup"><span data-stu-id="e610d-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="e610d-120">Revise [nuevas herramientas de análisis y solución de problemas para Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="e610d-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="e610d-121">Confirme que tiene un grupo de Skype empresarial y un servidor de Office Web Apps y que puede compartir un lote de PowerPoint con el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="e610d-122">Si la sala de reuniones ya tiene un buzón de recursos, habilítelo para Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="e610d-123">Si es necesario, solicite un DID (número de teléfono) para el sistema de salas de reuniones y actualice el campo Teléfono general en la herramienta de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e610d-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="e610d-124">Red</span><span class="sxs-lookup"><span data-stu-id="e610d-124">Network</span></span>

- <span data-ttu-id="e610d-125">Asegúrate de tener una conexión de red cableada para el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="e610d-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="e610d-126">Lea la guía de planificación de redes para Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="e610d-127">Solicite una evaluación de la red de Skype empresarial desde un socio de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="e610d-128">Lea los datos de rendimiento que se capturan en la herramienta de análisis de estado de Skype empresarial (Excel).</span><span class="sxs-lookup"><span data-stu-id="e610d-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="e610d-129">Ejecute la Herramienta de análisis de red.</span><span class="sxs-lookup"><span data-stu-id="e610d-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="e610d-130">Ejecute la Herramienta de diagnóstico previa a llamadas.</span><span class="sxs-lookup"><span data-stu-id="e610d-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="e610d-131">Seguridad del sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="e610d-131">Skype Room System Security</span></span>

<span data-ttu-id="e610d-132">El sistema de salas de Skype es un sistema integrado que se puede integrar completamente en una implementación de Windows mediante el modelo de seguridad de Skype para empresas, la administración de derechos y las herramientas de administración, como SCOM.</span><span class="sxs-lookup"><span data-stu-id="e610d-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="e610d-133">Estas características incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e610d-133">Features include:</span></span>
  
- <span data-ttu-id="e610d-134">Un filtro de escritura para evitar escrituras en el disco en modo de usuario</span><span class="sxs-lookup"><span data-stu-id="e610d-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="e610d-p104">Un bloqueador de aplicaciones para evitar que se ejecuten aplicaciones no autorizadas. Todos los puertos USB están deshabilitados en el modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="e610d-p104">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="e610d-137">No hay aplicaciones ni visores estándar en el hardware del sistema de Skype Room.</span><span class="sxs-lookup"><span data-stu-id="e610d-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="e610d-138">Todo el contenido se representa a través de protocolos HTTP o RDP.</span><span class="sxs-lookup"><span data-stu-id="e610d-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="e610d-p106">El equipo ejecuta el sistema operativo Windows Embedded Standard 7. Los socios OEM proporcionan todo el hardware, incluidos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e610d-p106">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="e610d-141">Unión de dominio opcional a Active Directory Domain Services (AD DS), que permite la administración y el control de cuentas de seguridad locales.</span><span class="sxs-lookup"><span data-stu-id="e610d-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="e610d-142">También puede administrar la cuenta de administrador local con el centro de administración de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="e610d-143">El sistema de salas de Skype se actualiza a través de los procesos estándar de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="e610d-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="e610d-144">El sistema de salas de Skype se conecta con Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="e610d-145">Skype empresarial usa el cifrado y la autorización end-to-end para todos los modos de comunicación</span><span class="sxs-lookup"><span data-stu-id="e610d-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="e610d-146">El sistema de salas de Skype es compatible con las normas de seguridad y cumplimiento de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="e610d-147">Para obtener más información, consulte [planear la seguridad en Skype empresarial Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="e610d-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="e610d-148">Licencia</span><span class="sxs-lookup"><span data-stu-id="e610d-148">License</span></span>

<span data-ttu-id="e610d-149">Compruebe que usa un KMS para activar software.</span><span class="sxs-lookup"><span data-stu-id="e610d-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="e610d-150">Si es así, es posible que tenga que comprobar o agregar la clave KMS del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="e610d-151">Si no usa KMS, solicite la clave de licencias por volumen para la MAK de cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="e610d-152">Claves de licencia</span><span class="sxs-lookup"><span data-stu-id="e610d-152">License keys</span></span>

<span data-ttu-id="e610d-153">El sistema de salas de Skype ejecuta el cliente de escritorio de Skype empresarial en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e610d-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="e610d-154">Si el sistema de la sala de Skype es un miembro de dominio, detectará su KMS.</span><span class="sxs-lookup"><span data-stu-id="e610d-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="e610d-155">(y si tiene la clave KMS de licencias por volumen, se activará automáticamente).</span><span class="sxs-lookup"><span data-stu-id="e610d-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="e610d-156">Las licencias por volumen también proporcionan una MAK, que se especifica al mostrar xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="e610d-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="e610d-157">(Necesita acceso a Internet para activarse mediante MAK, pero no KMS).</span><span class="sxs-lookup"><span data-stu-id="e610d-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="e610d-158">Para obtener más información, consulte activación por volumen de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="e610d-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="e610d-159">Para introducir la clave MAK, vaya a configuración \> OEM herramienta de licencias de SRS.</span><span class="sxs-lookup"><span data-stu-id="e610d-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="e610d-160">Haga clic en Comprobar estado.</span><span class="sxs-lookup"><span data-stu-id="e610d-160">Click Check Status.</span></span> <span data-ttu-id="e610d-161">Cuando el estado indica "el producto no está activado", escribe la tecla.</span><span class="sxs-lookup"><span data-stu-id="e610d-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="e610d-162">Si durante la activación recibe un error que dice "' el servicio de licencias de software notificó que la clave de producto no es válida", compruebe que:</span><span class="sxs-lookup"><span data-stu-id="e610d-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="e610d-163">La clave se ha escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="e610d-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="e610d-164">Introdujo la clave MAK de Skype empresarial y no otra tecla.</span><span class="sxs-lookup"><span data-stu-id="e610d-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="e610d-165">El sistema tiene acceso a Internet.</span><span class="sxs-lookup"><span data-stu-id="e610d-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="e610d-166">Puede realizar la activación mediante teléfono, pero debe haber intentado la activación con la Herramienta de licencias de SRS antes.</span><span class="sxs-lookup"><span data-stu-id="e610d-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="e610d-167">Para realizar la activación por teléfono, inicie una reunión de prueba (no una llamada de prueba, ya que es demasiado breve).</span><span class="sxs-lookup"><span data-stu-id="e610d-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="e610d-168">En el Asistente para la activación de Office, seleccione activación por teléfono, llamar a Microsoft, escriba el número largo y escriba una respuesta.</span><span class="sxs-lookup"><span data-stu-id="e610d-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="e610d-169">Entidad de certificación</span><span class="sxs-lookup"><span data-stu-id="e610d-169">Certificate Authority</span></span>

<span data-ttu-id="e610d-170">Confirme que la Entidad de certificación usada para emitir el certificado de Office Web Apps Server 2013 tiene una ruta HTTP incluida en la propiedad Lista de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="e610d-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="e610d-171">Si usas Skype empresarial Server, importa el archivo de certificados (. CRT) al sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="e610d-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="e610d-172">Puede obtenerlo fácilmente del recurso compartido CertEnroll del servidor de la Entidad de certificación, o en la carpeta raíz de confianza de cualquier equipo unido al dominio.</span><span class="sxs-lookup"><span data-stu-id="e610d-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="e610d-173">Certificados</span><span class="sxs-lookup"><span data-stu-id="e610d-173">Certificates</span></span>

<span data-ttu-id="e610d-p113">Compruebe que la Entidad de certificación tiene una ruta HTTP en la Lista de revocación de certificados. Si no es así, actualice su Entidad de certificación para que tenga una.</span><span class="sxs-lookup"><span data-stu-id="e610d-p113">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="e610d-176">Instale certificados en la configuración del administrador del sistema de salas de Skype en \> el administrador de certificados de configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="e610d-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="e610d-177">Necesita la Entidad de certificación raíz de la empresa para su certificado interno.</span><span class="sxs-lookup"><span data-stu-id="e610d-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="e610d-178">Una forma de obtener los certificados que necesita es detectar la Entidad de certificación que emitió los certificados.</span><span class="sxs-lookup"><span data-stu-id="e610d-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="e610d-179">Para Skype empresarial Server, en un equipo PC en Skype empresarial, haga clic en \> configuración \> herramientas de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="e610d-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="e610d-180">Se abrirá una página web asegurada por la entidad emisora que emitió los certificados internos.</span><span class="sxs-lookup"><span data-stu-id="e610d-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="e610d-181">Haga clic en el icono de candado en la barra de dirección del navegador para mostrar un informe de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e610d-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="e610d-182">Haga clic en Ver certificados y examine la propiedad Puntos de distribución CRL.</span><span class="sxs-lookup"><span data-stu-id="e610d-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="e610d-183">El segundo parámetro de CN debería ser el nombre del servidor de la Entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="e610d-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="e610d-184">Ahora abra el explorador de Windows para \\ \< esa dirección nombre \>de servidor CA \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="e610d-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="e610d-185">Copie los dos archivos .crl y el archivo .crt en una unidad extraíble y póngalos en la parte izquierda del panel SMART.</span><span class="sxs-lookup"><span data-stu-id="e610d-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="e610d-186">Importe el archivo. CRT a la carpeta de la entidad emisora de certificados de confianza en el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="e610d-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="e610d-187">Importe los archivos. CRL en el sistema de salas de Skype en la carpeta entidades emisoras de certificados intermedias.</span><span class="sxs-lookup"><span data-stu-id="e610d-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="e610d-188">(Necesita cambiar el filtro de extensión de archivo en el Administrador de certificados a .crl para ver los archivos).</span><span class="sxs-lookup"><span data-stu-id="e610d-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="e610d-189">Nota: el servidor de Office Web Apps 2013 puede compartir la misma CA como Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e610d-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="e610d-190">Si no lo hace, no podrá compartir archivos de PowerPoint durante una reunión.</span><span class="sxs-lookup"><span data-stu-id="e610d-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="e610d-191">Póngase en contacto con el departamento de TI y obtenga los archivos CRT y CRL del CertEnroll del recurso compartido de red de la Entidad de certificación tal y como se ha explicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e610d-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="e610d-192">La pertenencia a dominios puede simplificar algunas cosas porque puede tratar el sistema de salas de Skype como sistema Windows y puede confiar en Active Directory para algunos de los aspectos de los certificados.</span><span class="sxs-lookup"><span data-stu-id="e610d-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="e610d-193">De todas formas, es mejor administrar esto manualmente.</span><span class="sxs-lookup"><span data-stu-id="e610d-193">However, it's best to manually manage this.</span></span>
  

