---
title: Solución de problemas con la implementación de Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de la implementación de la edición en la nube.
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002080"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="1c60d-103">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1c60d-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="1c60d-104">Solucionar problemas de la implementación de la edición en la nube.</span><span class="sxs-lookup"><span data-stu-id="1c60d-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="1c60d-p101">En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas en los dos sentidos de la red telefónica conmutada (RTC), puede investigar el problema siguiendo las soluciones que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="1c60d-107">El conector de nube proporciona mecanismos integrados para resolver algunos problemas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="1c60d-108">Un proceso de detección automática busca posibles problemas con los dispositivos de conexión en la nube y, si es posible, toma medidas correctivas para resolver esos problemas sin necesidad de que intervenga el administrador.</span><span class="sxs-lookup"><span data-stu-id="1c60d-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="1c60d-109">El proceso de detección funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1c60d-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="1c60d-110">**Secuencia de detección:** El servicio de administración de conector de nube ejecuta un proceso cada 60 segundos para detectar si un dispositivo está desactivado.</span><span class="sxs-lookup"><span data-stu-id="1c60d-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="1c60d-111">En la versión 2,0 y posteriores del conector de la nube, el proceso de detección usa el conmutador de CorpNet de Skype empresarial para establecer conexiones de PowerShell con las máquinas de los conectores de nube; en las versiones anteriores a 2,0, el proceso de detección usa el conmutador de administración del conector de nube.</span><span class="sxs-lookup"><span data-stu-id="1c60d-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c60d-112">Para que la recuperación automática se realice correctamente, debe haber conectividad de red entre el host y las máquinas virtuales a través del conmutador de red de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1c60d-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="1c60d-113">Asegúrese de comprobar la conectividad de red para asegurarse de que la detección y recuperación automáticas pueda realizarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="1c60d-114">**Supervisión:** Los siguientes servicios se supervisan en la versión 2,0 y posteriores del conector de la nube:</span><span class="sxs-lookup"><span data-stu-id="1c60d-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="1c60d-115">Las máquinas virtuales no están conectadas a los conmutadores virtuales de Internet o de la organización del conector de nube</span><span class="sxs-lookup"><span data-stu-id="1c60d-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="1c60d-116">Las máquinas virtuales se encuentran en estado guardado o detenido</span><span class="sxs-lookup"><span data-stu-id="1c60d-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="1c60d-117">Servicios del servidor de administración central: réplica, maestra</span><span class="sxs-lookup"><span data-stu-id="1c60d-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="1c60d-118">Servicios del servidor de mediación: REPLICA, RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="1c60d-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="1c60d-119">Servicios del servidor perimetral: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="1c60d-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="1c60d-120">Las reglas de Firewall entrante están deshabilitadas para CS RTCSRV en el servidor perimetral, CS RTCMEDSRV en el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1c60d-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="1c60d-121">En el conector de nube versión 1.4.2, solo se supervisan los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="1c60d-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="1c60d-122">Servicios del servidor de mediación: RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="1c60d-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="1c60d-123">Servicio de servidor perimetral: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="1c60d-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="1c60d-124">**Proceso de recuperación:** Si algún servicio supervisado está desactivado, un dispositivo se marca y los servicios se detienen y marcan como manual hasta que se puedan resolver todos los problemas.</span><span class="sxs-lookup"><span data-stu-id="1c60d-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="1c60d-125">Esto evitará que las llamadas se enruten a un dispositivo que pueda causar errores en las llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c60d-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="1c60d-126">El servicio de administración de conector de nube volverá a intentar la recuperación automática de la siguiente manera</span><span class="sxs-lookup"><span data-stu-id="1c60d-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="1c60d-127">El intervalo de reintento inicial es cada diez segundos, con un tiempo de intervalo máximo de una hora.</span><span class="sxs-lookup"><span data-stu-id="1c60d-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="1c60d-128">Para los tres primeros intentos de recuperación, el tiempo de intervalo es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="1c60d-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="1c60d-129">A partir del cuarto reintento, el intervalo de tiempo aumenta en dos veces el intervalo de tiempo anterior.</span><span class="sxs-lookup"><span data-stu-id="1c60d-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="1c60d-130">Por ejemplo, el cuarto reintento se realizará en 20 segundos, el quinto de 40 segundos, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="1c60d-131">Cuando se alcanza el tiempo de intervalo máximo de una hora, los reintentos continuarán una vez cada hora.</span><span class="sxs-lookup"><span data-stu-id="1c60d-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="1c60d-132">Cuando la recuperación se realiza correctamente, el intervalo y los reintentos se establecen en sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="1c60d-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="1c60d-133">Si el servicio de administración se reinicia, el intervalo y los recuentos de reintentos se restablecen a sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="1c60d-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="1c60d-134">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1c60d-134">Troubleshooting</span></span>

<span data-ttu-id="1c60d-135">A continuación se muestran algunas soluciones a los problemas más frecuentes:</span><span class="sxs-lookup"><span data-stu-id="1c60d-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="1c60d-136">**Problema: la implementación presenta un error o deja de responder cuando se ejecutan los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o esta es incorrecta para la NIC externa, interna o de administración.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="1c60d-137">**Solución:** Este problema no se puede resolver automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="1c60d-138">No se pueden agregar NICs a las VMs mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="1c60d-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="1c60d-139">Cierre y quite estas máquinas virtuales en Hyper-v Manager y, a continuación, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="1c60d-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="1c60d-140">**Problema: después de instalar el servidor de Active Directory y el bosque, el servidor CMS o el servidor de mediación no se unen al dominio correctamente.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="1c60d-141">**Resolución:** para resolver este problema, lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="1c60d-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="1c60d-142">Inicie sesión en el servidor de Active Directory y compruebe que se haya creado el dominio correctamente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="1c60d-143">Inicie sesión en el servidor CMS o de mediación, y compruebe en el NIC de red corporativa que se haya asignado una dirección IP válida y que estén configurados un DNS y una IP estática válidos como la dirección IP del servidor de AD.</span><span class="sxs-lookup"><span data-stu-id="1c60d-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="1c60d-144">Inicie sesión en el servidor CMS o de mediación y abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1c60d-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="1c60d-145">Asegúrese de poder hacer ping a la dirección IP y el FQDN del servidor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c60d-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="1c60d-146">Si no puede, es posible que haya un conflicto con la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="1c60d-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="1c60d-147">Intente asignar una nueva IP para Active Directory y actualice en consecuencia el DNS en el servidor CMS o de mediación.</span><span class="sxs-lookup"><span data-stu-id="1c60d-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="1c60d-148">**Problema: recibe el siguiente mensaje de error: "Remove-VMSwitch: error al quitar el conmutador Ethernet virtual. El conmutador virtual ' conmutador de administración del conector en la nube ' no se puede eliminar porque está siendo usado por máquinas virtuales en ejecución o asignado a grupos secundarios. "**</span><span class="sxs-lookup"><span data-stu-id="1c60d-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="1c60d-149">**Solución:** El "conmutador de administración del conector de nube" no se eliminó después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="1c60d-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="1c60d-150">Si ha encontrado este error, vaya al administrador de Hyper-v y compruebe que aún no hay una máquina virtual aún conectada a ella.</span><span class="sxs-lookup"><span data-stu-id="1c60d-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="1c60d-151">Si hay máquinas virtuales aún conectadas, desconéctate y elimina el conmutador de administración.</span><span class="sxs-lookup"><span data-stu-id="1c60d-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="1c60d-152">Si el conmutador de administración aún no se puede eliminar, reinicie el servidor host e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="1c60d-153">**Problema: recibe el siguiente mensaje de error "no se pudo iniciar el servicio de RTCMRAUTH. Asegúrese de que el servicio no está deshabilitado.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c60d-154">Este problema solo se aplica a versiones del conector de nube anteriores a la versión 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="1c60d-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="1c60d-p110">La imposibilidad de iniciar también puede deberse a que el servidor front-end se haya conmutado previamente por error (mediante una conmutación por error del equipo), en cuyo caso debería invocar una conmutación por recuperación (mediante una conmutación por recuperación del equipo).</span><span class="sxs-lookup"><span data-stu-id="1c60d-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="1c60d-p111">**Resolución:** este problema se produce en un servidor perimetral cuando dicho servidor no confía en el certificado de CA raíz o de CA intermedia, incluso cuando pueda importarse el certificado externo, pero la cadena de certificados se vea interrumpida. En esta situación, no puede iniciarse el servicio RTCMRAUTH o RTCSRV.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="1c60d-p112">Importe en el servidor perimetral el certificado de CA raíz y todos los certificados de CA intermedia de su certificado externo de forma manual y reinicie el servidor. Después de ver que se hayan iniciado los servicios RTCMRAUTH y RTCSRV en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:</span><span class="sxs-lookup"><span data-stu-id="1c60d-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="1c60d-162">**Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows, y las llamadas a las que presta servicio el servidor están fallando.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="1c60d-p113">**Resolución:** si ha implementado un entorno de alta disponibilidad, Microsoft proporciona un cmdlet que le ayudará a mover una máquina host (instancia de implementación) dentro o fuera de la topología actual cuando compruebe e instale actualizaciones de Windows de forma manual. Use los siguientes pasos para llevar a cabo esto:</span><span class="sxs-lookup"><span data-stu-id="1c60d-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="1c60d-165">En el servidor host, inicie una consola de PowerShell como administrador y después ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c60d-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="1c60d-166">Compruebe si existen actualizaciones e instale las que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="1c60d-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="1c60d-167">En la consola de PowerShell, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1c60d-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="1c60d-168">**Problema: cuando se realiza una llamada desde el cliente de Skype Empresarial con un número de RTC, la llamada no puede escalarse a conferencia invitando a otro número de RTC.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="1c60d-169">**Solución:** Para resolver este problema, vea [configurar la configuración del servidor de mediación híbrida en línea](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="1c60d-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="1c60d-170">**Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar un servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarse de que la característica o el rol recién instalados se actualicen automáticamente, active Windows Update en el Panel de control".**</span><span class="sxs-lookup"><span data-stu-id="1c60d-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="1c60d-171">**Solución:** Inicie una sesión de PowerShell remoto de inquilino con credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ de su sitio:</span><span class="sxs-lookup"><span data-stu-id="1c60d-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="1c60d-172">Si _EnableAutoUpdate_ se establece en **true**, puede pasar por alto este mensaje de advertencia sin riesgos porque el servicio CCEManagement se encargará de descargar e instalar las actualizaciones de Windows tanto para las máquinas virtuales como para el servidor host.</span><span class="sxs-lookup"><span data-stu-id="1c60d-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="1c60d-173">Si _EnableAutoUpdate_ se establece en **false**, ejecute el cmdlet siguiente para establecerla en **true**.</span><span class="sxs-lookup"><span data-stu-id="1c60d-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="1c60d-174">Puede también comprobar si existen actualizaciones e instalarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="1c60d-175">Consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="1c60d-175">See the next section.</span></span>
    
- <span data-ttu-id="1c60d-176">**Problema: recibe un mensaje de error: no se puede registrar el dispositivo porque el nombre \<\> de\> usuario \<y\> la \<configuración de la dirección \<\> IP del siteName o ApplianceName de Media Server o del servidor de mediación de su configuración entran en conflicto con los dispositivos existentes. Quitar el dispositivo de conflicto o actualizar la información de entrada/configuración y vuelva a registrarse. ' cuando se ejecute Register-CcAppliance para registrar el equipo actual en Internet.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="1c60d-177">**Solución:** Los valores para \<la\>dirección \<\> IP del servidor\> de \<mediación de FQDN y mediación de ApplianceName debe ser único y solo se pueden usar para el registro de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="1c60d-178">De forma predeterminada \<,\> ApplianceName viene del nombre de host.</span><span class="sxs-lookup"><span data-stu-id="1c60d-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="1c60d-179">\<FQDN\> del servidor de \<mediación dirección\> IP del servidor de mediación definida en el archivo ini de configuración.</span><span class="sxs-lookup"><span data-stu-id="1c60d-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="1c60d-180">Por ejemplo, se usa (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para el registro en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), experimentará el conflicto.</span><span class="sxs-lookup"><span data-stu-id="1c60d-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="1c60d-181">En primer lugar, verifica el archivo CloudConnector. ini en la sección ApplianceRoot Directory.</span><span class="sxs-lookup"><span data-stu-id="1c60d-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="1c60d-182">\<Obtendrá los valores de\>dirección \<\> IP del servidor\> de \<nombres, FQDN y servidor de mediación en el archivo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="1c60d-183">\<ApplianceName\> es el nombre del servidor host.</span><span class="sxs-lookup"><span data-stu-id="1c60d-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="1c60d-184">En segundo lugar, inicie PowerShell remoto de inquilino con sus credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar los dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="1c60d-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="1c60d-185">Después de identificar cualquier conflicto, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.</span><span class="sxs-lookup"><span data-stu-id="1c60d-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="1c60d-186">**Problema: el cmdlet Get-CcRunningVersion devuelve un valor vacío si hay un dispositivo implementado ejecutándose en el host.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="1c60d-187">**Solución:** Esto puede ocurrir al actualizar de 1.3.4 o 1.3.8 a 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="1c60d-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="1c60d-188">Después de instalar la versión 1.4.1 con el. msi, debe ejecutar `Register-CcAppliance` antes de ejecutar cualquier otro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1c60d-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="1c60d-189">`Register-CcAppliance`migrará el archivo Module. ini de%UserProfile%\CloudConnector a%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="1c60d-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="1c60d-190">Si lo ha perdido, se creará un nuevo Module. ini en la carpeta%ProgramData%\CloudConnector y reemplazará la información de la versión de ejecución o de copia de seguridad para 1.3.4 o 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="1c60d-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="1c60d-191">Compare los archivos module.ini files en la carpeta %perfilusuario%\CloudConnector y %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="1c60d-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="1c60d-192">Si hay diferencias, elimine el archivo Module. ini en%ProgramData%\CloudConnector y vuelva `Register-CcAppliance`a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="1c60d-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="1c60d-193">También puede modificar el archivo de forma manual para la versión correcta de ejecución y copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1c60d-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="1c60d-194">**Problema: después de ejecutar el cmdlet switch-CcVersion para cambiar a una versión anterior que es diferente de la versión actual del script, no hay compatibilidad de alta disponibilidad para esta versión anterior.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="1c60d-195">**Solución:** Por ejemplo, ha actualizado de 1.4.1 a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="1c60d-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="1c60d-196">La versión actual de la secuencia de comandos, que se `Get-CcVersion`puede determinar al ejecutarse, y la versión en ejecución, `Get-CcRunningVersion` que se puede determinar mediante la ejecución, son 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="1c60d-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="1c60d-197">En este momento, si se ejecuta `Switch-CcVersion` para cambiar la versión de ejecución a 1.4.1, no habrá compatibilidad de alta disponibilidad para esta versión antigua.</span><span class="sxs-lookup"><span data-stu-id="1c60d-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="1c60d-p121">Para obtener compatibilidad total con alta disponibilidad, vuelva a 1.4.2 para que la versión en ejecución y la versión del script sean las mismas. Si está experimentando problemas con su implementación de 1.4.2, desinstálela y vuelva a instalarla tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="1c60d-200">**Problema: los certificados de una entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="1c60d-p122">**Resolución:** los certificados de la entidad de certificación de Skype Empresarial son válidos durante cinco años. Los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral son válidos durante dos años.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c60d-203">En el conector de nube versión 2,0 y posteriores, el cmdlet Renew-CcServerCertificate ha cambiado a Update-CcServerCertificate y el cmdlet Renew-CcCACertificate ha cambiado a Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="1c60d-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="1c60d-204">Si los certificados internos emitidos para el almacén central de administración, el servidor de mediación y el servidor perimetral están cerca de la expiración o están comprometidos, ejecute el cmdlet Renew-CcServerCertificate o Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="1c60d-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="1c60d-205">Si los certificados de la entidad de certificación están cercanos, ejecute el cmdlet Renew-CcCACertificate o Update-CcCACertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="1c60d-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="1c60d-206">**Si los certificados de la entidad emisora de certificados se ven comprometidos y solo hay un dispositivo en el sitio,** realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="1c60d-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="1c60d-207">Ejecute el cmdlet Enter-CcUpdate para depurar los servicios y poner el dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="1c60d-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="1c60d-208">Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de la entidad de certificación y todos los certificados internos del servidor:</span><span class="sxs-lookup"><span data-stu-id="1c60d-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="1c60d-209">Para las versiones de conector de nube antes 2,0:</span><span class="sxs-lookup"><span data-stu-id="1c60d-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="1c60d-210">O para el conector de nube versión 2,0 y posteriores:</span><span class="sxs-lookup"><span data-stu-id="1c60d-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="1c60d-211">Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado en las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="1c60d-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="1c60d-212">Es posible que también se le solicite volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1c60d-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="1c60d-213">Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="1c60d-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="1c60d-214">**Si los certificados de la entidad emisora de certificados se ven comprometidos y hay varios dispositivos en el sitio,** realice los siguientes pasos secuenciales en cada dispositivo del sitio.</span><span class="sxs-lookup"><span data-stu-id="1c60d-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="1c60d-215">Microsoft recomienda que realice estos pasos durante los períodos de uso no máximo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="1c60d-216">En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar los archivos de copia de seguridad de \<la\> entidad emisora en el directorio SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="1c60d-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="1c60d-217">Ejecute el cmdlet Enter-CcUpdate para drenar servicios y poner cada dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="1c60d-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="1c60d-218">En el primer dispositivo, ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="1c60d-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="1c60d-219">Para las versiones de conector de nube antes 2,0:</span><span class="sxs-lookup"><span data-stu-id="1c60d-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="1c60d-220">O para el conector de nube versión 2,0 y posteriores:</span><span class="sxs-lookup"><span data-stu-id="1c60d-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="1c60d-221">En el primer dispositivo, ejecute el cmdlet siguiente para realizar la copia de seguridad de los \<archivos\> de CA en la carpeta SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="1c60d-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="1c60d-222">En todos los demás dispositivos del mismo sitio, ejecute los siguientes comandos para consumir los archivos de copia de seguridad de la entidad emisora, de modo que todos los dispositivos usen el mismo certificado raíz y, a continuación, solicite certificados nuevos.</span><span class="sxs-lookup"><span data-stu-id="1c60d-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="1c60d-223">Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo del sitio y, a continuación, instale el certificado exportado en las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="1c60d-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="1c60d-224">Es posible que también se le solicite volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="1c60d-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="1c60d-225">Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="1c60d-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="1c60d-226">**Problema: recibe el siguiente mensaje de error en el registro del servicio de administración del conector de nube, "C:\Archivos de Files\Skype para Business Cloud Connector Edition\ManagementService\CceManagementService.log": error de CceService: excepción inesperada al notificar el estado a en línea: System. Management. \<Automation. CmdletInvocationException\>: error de inicio de sesión para el administrador de inquilinos global de usuario. Cree un nuevo objeto de credencial, asegurándose de que ha usado el nombre de usuario y la contraseña correctos. ---\>**</span><span class="sxs-lookup"><span data-stu-id="1c60d-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="1c60d-227">**Solución:** Las credenciales de administrador de inquilinos globales de Office 365 se han cambiado desde que se registró el equipo del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="1c60d-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="1c60d-228">Para actualizar las credenciales almacenadas de forma local en el dispositivo de conector de nube, ejecute lo siguiente de administrador de PowerShell en el dispositivo de hospedaje:</span><span class="sxs-lookup"><span data-stu-id="1c60d-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="1c60d-229">**Problema: después de cambiar la contraseña de la cuenta de servidor host que usó para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString: clave no válida para usarla en el estado especificado". en%ProgramFiles%\Skype para Business Cloud Connector Edition\ManagementService\CceManagementService.log o al ejecutar el cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="1c60d-230">**Solución:** Todas las credenciales del conector de nube se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="1c60d-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="1c60d-231">Cuando se modifica la contraseña en el servidor host, tendrá que actualizar las credenciales que hay almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="1c60d-232">**Si ejecuta la versión 1.4.2 de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector mediante estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1c60d-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="1c60d-233">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="1c60d-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="1c60d-234">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="1c60d-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="1c60d-235">Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas que siguen a la descripción.</span><span class="sxs-lookup"><span data-stu-id="1c60d-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="1c60d-236">Introduzca las mismas contraseñas que usó antes para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1c60d-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="1c60d-237">**Si está ejecutando Cloud Connector versión 2,0 o posterior,** regenere todas las contraseñas de conector de nube siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1c60d-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="1c60d-238">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="1c60d-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="1c60d-239">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="1c60d-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="1c60d-240">Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas que siguen a la descripción.</span><span class="sxs-lookup"><span data-stu-id="1c60d-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="1c60d-p128">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector, use la contraseña de VMAdmin para la contraseña de CceService cuando se le solicite. Introduzca la misma contraseña que usó antes para la implementación de Cloud Connector de todas las otras cuentas.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="1c60d-243">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector y las contraseñas de DomainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="1c60d-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="1c60d-244">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="1c60d-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="1c60d-245">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="1c60d-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="1c60d-246">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="1c60d-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="1c60d-247">Si el archivo de contraseñas almacenadas en caché se generó con la versión 2,0 o posterior del conector en la nube, de forma predeterminada, VmAdmin y ID.</span><span class="sxs-lookup"><span data-stu-id="1c60d-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="1c60d-248">Si ha cambiado las contraseñas de DomainAdmin y VMAdmin, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="1c60d-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="1c60d-249">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="1c60d-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="1c60d-250">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="1c60d-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="1c60d-251">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="1c60d-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="1c60d-252">Ejecute Set-CcCredential -AccountType VmAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="1c60d-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="1c60d-253">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="1c60d-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="1c60d-254">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin que usó antes. </span><span class="sxs-lookup"><span data-stu-id="1c60d-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="1c60d-255">**Problema: con el conector de nube versión 2,1 y posteriores, cuando se ejecuta Register-CcAppliance u otros cmdlets en el dispositivo, recibe un mensaje de error como: "para cada objeto: no se puede encontrar la propiedad ' Common ' en este objeto. Compruebe que la propiedad existe. En C:\Archivos de Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Car: 14 "**</span><span class="sxs-lookup"><span data-stu-id="1c60d-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="1c60d-256">**Solución:** El conector para la nube 2,1 y versiones posteriores requieren .NET Framework 4.6.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="1c60d-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="1c60d-257">Actualiza .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelve a ejecutar el cmdlet (s).</span><span class="sxs-lookup"><span data-stu-id="1c60d-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="1c60d-258">**Problema: con Cloud Connector Edition 2,1, cuando se ejecuta install-CcAppliance, recibe un mensaje de error como: "error al instalar una nueva instancia con error: no se puede establecer" State "porque solo se pueden usar cadenas como valores para establecer las propiedades de XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="1c60d-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="1c60d-259">**Solución:** En Cloudconnector. ini, en la sección [Common], agregue la configuración "State" como se muestra a continuación: CountryCode = Estados Unidos = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="1c60d-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="1c60d-260">No es obligatorio que la línea "State" tenga valor; sin embargo, la línea "State" no se puede quitar del archivo Cloudconnector. ini.</span><span class="sxs-lookup"><span data-stu-id="1c60d-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="1c60d-261">**Problema: recibe el siguiente mensaje de error "dimount-WindowsImage: dimount-WindowsImage. Código de error = 0xc1550115 "al instalar o actualizar Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="1c60d-262">**Solución:** Inicie una consola de PowerShell como administrador, ejecute "DISM-Cleanup-Wim" ".</span><span class="sxs-lookup"><span data-stu-id="1c60d-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="1c60d-263">De esta forma, se limpiarán todas las imágenes con problemas.</span><span class="sxs-lookup"><span data-stu-id="1c60d-263">This will clean up all troubled images.</span></span> <span data-ttu-id="1c60d-264">Ejecute install-CcAppliance de nuevo o espere a que los bits se actualicen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="1c60d-265">**Problema: no se puede implementar el primer dispositivo del conector de nube en un entorno de alta disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="1c60d-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="1c60d-266">**Solución:** Los pasos que realice dependerán del motivo por el que se produjo el error de implementación:</span><span class="sxs-lookup"><span data-stu-id="1c60d-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="1c60d-267">Si se produce un error en el primer dispositivo del conector de nube y no puede determinar la causa del error, debe instalar el dispositivo de nuevo hasta que la implementación sea correcta y, a continuación, instalar los otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1c60d-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="1c60d-268">Si el primer equipo con el conector de nube falla con un problema leve, como un problema de certificado externo, es posible que pueda solucionar el problema sin volver a instalar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="1c60d-269">Después, puede usar PowerShell remoto de inquilino para marcar la implementación como correcta de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="1c60d-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="1c60d-270">(También puede usar los siguientes pasos si la primera implementación se realizó correctamente, pero, por algún motivo, el conector de nube no puede informar de la implementación como un éxito).</span><span class="sxs-lookup"><span data-stu-id="1c60d-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="1c60d-271">Para obtener la identidad (GUID) del primer dispositivo de conector de nube, ejecute el cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="1c60d-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="1c60d-272">Para marcar el dispositivo como implementado correctamente, ejecute Set-CsCceApplianceDeploymentStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1c60d-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="1c60d-273">**Problema: debe comprobar si existen actualizaciones de Windows e instalarlas manualmente en el servidor host o las máquinas virtuales.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="1c60d-p133">**Resolución:** recomendamos que aproveche las actualizaciones automatizadas del sistema operativo proporcionada por Skype Empresarial Cloud Connector Edition. Después de que se registre un dispositivo para administración en línea y se habilite la actualización automática del sistema operativo, el servidor host y las máquinas virtuales automáticamente comprobarán si existen actualizaciones de Windows y las instalarán de acuerdo con la configuración de la ventana de la hora de actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="1c60d-p134">Si tiene que comprobar si existen actualizaciones de Windows e instalarlas manualmente, siga los pasos provistos en esta sección que se apliquen a su tipo de implementación. Debe planificar y actualizar tanto el servidor host como las máquinas virtuales que estén ejecutándose en él al mismo tiempo a fin de minimizar el tiempo de inactividad necesario para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="1c60d-p135">Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones para los servidores de Cloud Connector. Solo tiene que configurar la actualización de Windows para que **no** se instale automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="1c60d-280">Para obtener información sobre cómo actualizar manualmente su implementación de Cloud Connector, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="1c60d-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="1c60d-281">**Problema: cuando el conector de nube se actualiza a una nueva compilación, los cmdlets de conector de nube no se actualizan.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="1c60d-282">Esto sucede a veces si se deja abierta una ventana de PowerShell cuando se produce la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="1c60d-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="1c60d-283">**Solución:** Para cargar los cmdlets actualizados, puede realizar cualquiera de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c60d-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="1c60d-284">Cierre PowerShell en el dispositivo de conector de nube y, a continuación, vuelva a abrir PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c60d-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="1c60d-285">También puede ejecutar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="1c60d-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="1c60d-286">**Problema: "el término ' Stop-CsWindowsService ' no se reconoce como el nombre de un cmdlet, una función, un archivo de script o un programa ejecutable". error al intentar ejecutar el cmdlet Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="1c60d-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="1c60d-287">**Solución:** Elimine el archivo $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="1c60d-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="1c60d-288">PowerShell crea este archivo como una caché de cmdlets de los módulos que encuentra, de modo que no es necesario volver a analizar todos los módulos cada vez, ya que esto ralentizaría la velocidad.</span><span class="sxs-lookup"><span data-stu-id="1c60d-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="1c60d-289">Lo más probable es que haya daños en los archivos que proporcionaron resultados engañosos a PowerShell cuando se leían de esa caché.</span><span class="sxs-lookup"><span data-stu-id="1c60d-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="1c60d-290">**Problema: "Import-Module CloudConnector" genera el error "Import-Module: el módulo especificado" CloudConnector "no se cargó porque no se encontró ningún archivo de módulo válido en ningún directorio de módulo"**</span><span class="sxs-lookup"><span data-stu-id="1c60d-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="1c60d-291">**Solution**</span><span class="sxs-lookup"><span data-stu-id="1c60d-291">**Resolution:**</span></span>
    - <span data-ttu-id="1c60d-292">Valide que el módulo CloudConnector exista bajo C:\Archivos de Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="1c60d-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="1c60d-293">Después de validar que el módulo CloudConnector existe en esta ubicación, la variable de entorno PSModulePath que almacena la ruta de acceso a las ubicaciones de los módulos se puede cambiar:</span><span class="sxs-lookup"><span data-stu-id="1c60d-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="1c60d-294">a.</span><span class="sxs-lookup"><span data-stu-id="1c60d-294">a.</span></span> <span data-ttu-id="1c60d-295">Cambio temporal: inicie PowerShell como administrador y ejecute el siguiente comando: $env:P SModulePath = $env:P SModulePath + ". C:\Archivos de Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="1c60d-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="1c60d-296">b.</span><span class="sxs-lookup"><span data-stu-id="1c60d-296">b.</span></span> <span data-ttu-id="1c60d-297">Para que el cambio sea persistente, inicie PowerShell como administrador y ejecute los siguientes comandos, uno por uno: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Archivos de Files\WindowsPowerShell\Modules "," equipo ")</span><span class="sxs-lookup"><span data-stu-id="1c60d-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="1c60d-298">Instalar actualizaciones de Windows manualmente</span><span class="sxs-lookup"><span data-stu-id="1c60d-298">Install Windows updates manually</span></span>

<span data-ttu-id="1c60d-299">Si no quiere usar actualizaciones automáticas en su entorno, siga estos pasos para comprobar si existen actualizaciones de Windows y aplicarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="1c60d-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="1c60d-300">Puede ser necesario reiniciar el servidor para la comprobación e instalación de actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="1c60d-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="1c60d-301">Cuando se reinicia un servidor host, los usuarios no podrán usar el conector de nube para realizar o recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="1c60d-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="1c60d-302">Puede comprobar si existen actualizaciones e instalarlas de forma manual a fin de controlar en qué momento deben producirse, y después reiniciar las máquinas según la necesidad durante los tiempos que usted elija para evitar interrupciones de los servicios.</span><span class="sxs-lookup"><span data-stu-id="1c60d-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="1c60d-303">Para comprobar manualmente si existen actualizaciones, conecte cada servidor host y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="1c60d-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="1c60d-304">Seleccione **Windows Update System \>and Security**y, a continuación, administre las actualizaciones y los reinicios del servidor según corresponda para su entorno.</span><span class="sxs-lookup"><span data-stu-id="1c60d-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="1c60d-305">Si existe solo un dispositivo en el sitio, conecte cada máquina virtual y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="1c60d-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="1c60d-306">Seleccione **Windows Update System \>and Security**y, a continuación, configure las actualizaciones y los reinicios del servidor según corresponda.</span><span class="sxs-lookup"><span data-stu-id="1c60d-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="1c60d-p143">Si hay más de un dispositivo en el sitio, los usuarios no pueden acceder a la instancia que se actualiza y reinicia durante las actualizaciones. Estos se conectarán con otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype Empresarial se inicien en las máquinas virtuales después de completadas las actualizaciones. Para evitar cualquier posible interrupción en el servicio, puede quitar la instancia de HA mientras aplica las actualizaciones y restaurarla cuando se completen. Para ello, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c60d-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="1c60d-311">En cada servidor host, abra una consola de PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="1c60d-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="1c60d-312">Quite la instancia de HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1c60d-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="1c60d-313">Siga los pasos para una sola instancia para aplicar manualmente las actualizaciones y reinicie la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="1c60d-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="1c60d-314">Vuelva a configurar la instancia en HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1c60d-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="1c60d-315">Para implementaciones de varios sitios, siga los pasos destinados a un único sitio para cada sitio de la implementación aplicando las actualizaciones de a uno por vez.</span><span class="sxs-lookup"><span data-stu-id="1c60d-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="1c60d-316">Sugerencias al instalar el software antivirus en el equipo host del conector de nube</span><span class="sxs-lookup"><span data-stu-id="1c60d-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="1c60d-317">Si necesita instalar software antivirus en el equipo host del conector de nube, debe agregar las siguientes exclusiones:</span><span class="sxs-lookup"><span data-stu-id="1c60d-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="1c60d-318">Directorio local del equipo en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="1c60d-319">Directorio de sitios remotos en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="1c60d-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="1c60d-320">El directorio de sitios locales del equipo hospeda la carpeta raíz del sitio compartido.</span><span class="sxs-lookup"><span data-stu-id="1c60d-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="1c60d-321">%ProgramFiles%\Skype para Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="1c60d-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="1c60d-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="1c60d-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="1c60d-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="1c60d-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="1c60d-324">El proceso Microsoft. RTC. CCE. ManagementService. exe.</span><span class="sxs-lookup"><span data-stu-id="1c60d-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
