---
title: Solución de problemas con la implementación de Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solución de problemas de la implementación de nube conector Edition.
ms.openlocfilehash: 5d34cc78c7afa9a0d4e459e87d885c82b437bae0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882291"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="3dff3-103">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="3dff3-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="3dff3-104">Solución de problemas de la implementación de nube conector Edition.</span><span class="sxs-lookup"><span data-stu-id="3dff3-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="3dff3-p101">En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas en los dos sentidos de la red telefónica conmutada (RTC), puede investigar el problema siguiendo las soluciones que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="3dff3-107">En la nube conector proporciona mecanismos integrados para resolver algunos problemas de automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="3dff3-108">Un proceso de detección automática busca posibles problemas con los dispositivos de conector en la nube y, si es posible, realiza una acción correctiva para resolver estos problemas sin necesidad de intervención del administrador.</span><span class="sxs-lookup"><span data-stu-id="3dff3-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="3dff3-109">El proceso de detección funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3dff3-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="3dff3-110">**Secuencia de detección:** El servicio de administración del conector en la nube ejecuta un proceso de cada 60 segundos para detectar si un dispositivo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="3dff3-111">En el conector en la nube versión 2.0 y versiones posterior, el proceso de detección usa el Skype para modificador Corpnet empresarial para realizar conexiones de PowerShell para las máquinas de conector en la nube; para las versiones anteriores a 2.0, el proceso de detección usa el modificador de administración del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="3dff3-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3dff3-112">Para que la recuperación automática se realice correctamente, debe haber conectividad de red entre el host y máquinas virtuales a través del conmutador de red de host.</span><span class="sxs-lookup"><span data-stu-id="3dff3-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="3dff3-113">Asegúrese de comprobar la conectividad de red para asegurarse de que la detección automática y recuperación puede tener éxito.</span><span class="sxs-lookup"><span data-stu-id="3dff3-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="3dff3-114">**Supervisión:** Los siguientes servicios se supervisan en la nube Connector versión 2.0 y versiones posterior:</span><span class="sxs-lookup"><span data-stu-id="3dff3-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="3dff3-115">Las máquinas virtuales no están conectadas a la nube conector corporativo o modificadores virtuales de Internet</span><span class="sxs-lookup"><span data-stu-id="3dff3-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="3dff3-116">Las máquinas virtuales se encuentran en un estado detenido o guardado</span><span class="sxs-lookup"><span data-stu-id="3dff3-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="3dff3-117">Servicios de servidor de administración centrales: réplica, patrón</span><span class="sxs-lookup"><span data-stu-id="3dff3-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="3dff3-118">Servicios de servidor de mediación: réplica, RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="3dff3-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="3dff3-119">Servicios de servidores perimetrales: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="3dff3-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="3dff3-120">Las reglas están deshabilitadas para RTCSRV CS en servidor perimetral, CS RTCMEDSRV en el servidor de mediación de firewall de entrada</span><span class="sxs-lookup"><span data-stu-id="3dff3-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="3dff3-121">En el conector en la nube versión 1.4.2, se supervisan únicamente los servicios siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dff3-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="3dff3-122">Servicios de servidor de mediación: RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="3dff3-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="3dff3-123">Servicio de servidor perimetral: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="3dff3-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="3dff3-124">**Proceso de recuperación:** Si todos los servicios supervisados están inactivos, un dispositivo se marca hacia abajo, y servicios se ha detenido y marcados manuales hasta que se pueden resolver todos los problemas.</span><span class="sxs-lookup"><span data-stu-id="3dff3-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="3dff3-125">Esto evita que las llamadas de enrutamiento a un dispositivo que puede causar errores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3dff3-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="3dff3-126">El servicio de administración del conector en la nube se volverá a intentar la recuperación automática de manera</span><span class="sxs-lookup"><span data-stu-id="3dff3-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="3dff3-127">El intervalo de reintento inicial es cada diez segundos con un tiempo de intervalo máximo de una hora.</span><span class="sxs-lookup"><span data-stu-id="3dff3-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="3dff3-128">Para los intentos de tres en primer lugar recuperación, el intervalo de tiempo es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="3dff3-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="3dff3-129">A partir del cuarto reintento, aumenta el intervalo de tiempo por dos veces el anterior intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="3dff3-130">Por ejemplo, el cuarto reintento se se producen en 20 segundos, la quinta en 40 segundos y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="3dff3-131">Cuando se alcanza el intervalo máximo de tiempo de una hora, reintentos continuará una vez cada hora.</span><span class="sxs-lookup"><span data-stu-id="3dff3-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="3dff3-132">Cuando la recuperación es correcta, se establecen los recuentos de intervalo e inténtelo de nuevo en sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="3dff3-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="3dff3-133">Si se reinicia el servicio de administración, se restablecen los recuentos de intervalo e inténtelo de nuevo a sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="3dff3-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="3dff3-134">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="3dff3-134">Troubleshooting</span></span>

<span data-ttu-id="3dff3-135">A continuación se muestran soluciones para problemas habituales:</span><span class="sxs-lookup"><span data-stu-id="3dff3-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="3dff3-136">**Problema: la implementación presenta un error o deja de responder cuando se ejecutan los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o esta es incorrecta para la NIC externa, interna o de administración.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="3dff3-137">**Resolución:** No se puede resolver este problema automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="3dff3-138">NIC no se puede agregar a las máquinas virtuales mientras se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="3dff3-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="3dff3-139">Por favor, apagar y quitar estas máquinas virtuales en el Administrador de hyper-v, a continuación, ejecutar los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dff3-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="3dff3-140">**Problema: después de instalar el servidor de Active Directory y el bosque, el servidor CMS o el servidor de mediación no se unen al dominio correctamente.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="3dff3-141">**Resolución:** para resolver este problema, lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="3dff3-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="3dff3-142">Inicie sesión en el servidor de Active Directory y compruebe que se haya creado el dominio correctamente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="3dff3-143">Inicie sesión en el servidor CMS o de mediación, y compruebe en el NIC de red corporativa que se haya asignado una dirección IP válida y que estén configurados un DNS y una IP estática válidos como la dirección IP del servidor de AD.</span><span class="sxs-lookup"><span data-stu-id="3dff3-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="3dff3-144">Inicie sesión en el servidor de mediación/CMS y abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3dff3-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="3dff3-145">Asegúrese de que puede hacer ping a la dirección IP y FQDN del servidor de directorio activo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="3dff3-146">Si no se puede, puede haber un conflicto de dirección IP.</span><span class="sxs-lookup"><span data-stu-id="3dff3-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="3dff3-147">Intente asignar una nueva dirección IP para Active Directory y actualizar DNS en el servidor de mediación/CMS en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="3dff3-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="3dff3-148">**Problema: Recibe el siguiente mensaje de error "Remove-VMSwitch: error al eliminar la conmutación de Ethernet virtual. El modificador virtual 'Administración del conector en la nube cambiar' no pueden eliminarse porque está siendo utilizado mediante la ejecución de máquinas virtuales ni asignado a los grupos de servidores secundarios."**</span><span class="sxs-lookup"><span data-stu-id="3dff3-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="3dff3-149">**Resolución:** No se ha eliminado el "conmutador de administración de conector en la nube" después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="3dff3-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="3dff3-150">Si presiona la tecla este error, vaya al administrador de Hyper-v y compruebe que haya no sigue una máquina virtual que sigue conectada a ella.</span><span class="sxs-lookup"><span data-stu-id="3dff3-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="3dff3-151">Si hay máquinas virtuales que sigue conectadas, desconectar ellos y elimine el modificador de administración.</span><span class="sxs-lookup"><span data-stu-id="3dff3-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="3dff3-152">Si aún no se puede eliminar el modificador de administración, reinicie el servidor de host e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="3dff3-153">**Problema: Recibe el mensaje de error siguiente, "servicio RTCMRAUTH no se pudo iniciar. Compruebe que el servicio no está deshabilitado."**</span><span class="sxs-lookup"><span data-stu-id="3dff3-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3dff3-154">Este problema solo se aplica a las versiones del conector de nube anteriores a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="3dff3-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="3dff3-p110">La imposibilidad de iniciar también puede deberse a que el servidor front-end se haya conmutado previamente por error (mediante una conmutación por error del equipo), en cuyo caso debería invocar una conmutación por recuperación (mediante una conmutación por recuperación del equipo).</span><span class="sxs-lookup"><span data-stu-id="3dff3-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="3dff3-p111">**Resolución:** este problema se produce en un servidor perimetral cuando dicho servidor no confía en el certificado de CA raíz o de CA intermedia, incluso cuando pueda importarse el certificado externo, pero la cadena de certificados se vea interrumpida. En esta situación, no puede iniciarse el servicio RTCMRAUTH o RTCSRV.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="3dff3-p112">Importe en el servidor perimetral el certificado de CA raíz y todos los certificados de CA intermedia de su certificado externo de forma manual y reinicie el servidor. Después de ver que se hayan iniciado los servicios RTCMRAUTH y RTCSRV en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:</span><span class="sxs-lookup"><span data-stu-id="3dff3-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="3dff3-162">**Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows, y las llamadas a las que presta servicio el servidor están fallando.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="3dff3-p113">**Resolución:** si ha implementado un entorno de alta disponibilidad, Microsoft proporciona un cmdlet que le ayudará a mover una máquina host (instancia de implementación) dentro o fuera de la topología actual cuando compruebe e instale actualizaciones de Windows de forma manual. Use los siguientes pasos para llevar a cabo esto:</span><span class="sxs-lookup"><span data-stu-id="3dff3-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="3dff3-165">En el servidor host, inicie una consola de PowerShell como administrador y después ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3dff3-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
  ```
  Enter-CcUpdate
  ```

2. <span data-ttu-id="3dff3-166">Compruebe si existen actualizaciones e instale las que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="3dff3-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="3dff3-167">En la consola de PowerShell, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3dff3-167">In the PowerShell console, run the following cmdlet:</span></span>
    
  ```
  Exit-CcUpdate
  ```

- 
    
    <span data-ttu-id="3dff3-168">**Problema: cuando se realiza una llamada desde el cliente de Skype Empresarial con un número de RTC, la llamada no puede escalarse a conferencia invitando a otro número de RTC.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="3dff3-169">**Resolución:** Para resolver este problema, vea [Configure online híbrido configuración del servidor de mediación](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="3dff3-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="3dff3-170">**Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar un servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarse de que la característica o el rol recién instalados se actualicen automáticamente, active Windows Update en el Panel de control".**</span><span class="sxs-lookup"><span data-stu-id="3dff3-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="3dff3-171">**Resolución:** Iniciar una sesión de PowerShell remoto inquilino con Skype para credenciales de administrador de inquilinos de negocio y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ del sitio:</span><span class="sxs-lookup"><span data-stu-id="3dff3-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="3dff3-172">Si _EnableAutoUpdate_ está establecida en **True**, puede ignorar este mensaje de advertencia debido a que el servicio CCEManagement controlará la descarga e instalación de actualizaciones de Windows para las máquinas virtuales y el servidor host.</span><span class="sxs-lookup"><span data-stu-id="3dff3-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="3dff3-173">Si _EnableAutoUpdate_ está establecida en **False**, ejecute siguiente cmdlet para establecer en **True**.</span><span class="sxs-lookup"><span data-stu-id="3dff3-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="3dff3-p115">Puede también comprobar si existen actualizaciones e instalarlas manualmente. Consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p115">Alternatively, you can manually check for and install updates. See the next section.</span></span>
    
- <span data-ttu-id="3dff3-176">**Problema: Recibe un mensaje de error: no se puede registrar el dispositivo debido a que la configuración actual de entrada/ \<SiteName\> o \<ApplianceName\> o \<el FQDN del servidor de mediación\> o \<dirección IP de servidor de mediación \> entra en conflicto con appliance(s) existente. Quitar dispositivo de conflicto o actualizar la información de configuración de entrada y, a continuación, vuelva a registrar. ' cuando se ejecuta Register-CcAppliance para registrar el dispositivo actual a en línea.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="3dff3-177">**Resolución:** Los valores para la \<ApplianceName\>, \<el FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> debe ser único y sólo utilizan para el registro de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="3dff3-178">De forma predeterminada, \<ApplianceName\> proviene del nombre de host.</span><span class="sxs-lookup"><span data-stu-id="3dff3-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="3dff3-179">\<FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> definido en el archivo de configuración de ini.</span><span class="sxs-lookup"><span data-stu-id="3dff3-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="3dff3-180">Por ejemplo, se usa (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para el registro en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), experimentará el conflicto.</span><span class="sxs-lookup"><span data-stu-id="3dff3-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="3dff3-181">En primer lugar, compruebe el archivo CloudConnector.ini en la sección de directorio ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="3dff3-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="3dff3-182">Obtendrá \<SiteName\>, \<el FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> valores en el archivo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="3dff3-183">\<ApplianceName\> es el nombre del servidor host.</span><span class="sxs-lookup"><span data-stu-id="3dff3-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="3dff3-184">En segundo lugar, inicio inquilino PowerShell remoto con su Skype para credenciales de administrador de inquilinos de negocio, a continuación, ejecute el siguiente cmdlet para comprobar la appliance(s) registrados.</span><span class="sxs-lookup"><span data-stu-id="3dff3-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="3dff3-185">Después de identificar cualquier conflicto, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.</span><span class="sxs-lookup"><span data-stu-id="3dff3-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
-    <span data-ttu-id="3dff3-186">**Problema: El cmdlet Get-CcRunningVersion devuelve un valor vacío si no hay un dispositivo implementado que se ejecutan en el host.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
    <span data-ttu-id="3dff3-p118">**Resolución:** esto puede producirse cuando se actualiza de 1.3.4 o 1.3.8 a 1.4.1. Después de instalar la versión 1.4.1 con .msi, debe ejecutar `Register-CcAppliance` antes de ejecutar cualquier otro cmdlet. `Register-CcAppliance` migrará el archivo module.ini de %perfilusuario%\CloudConnector a %ProgramData%\CloudConnector. Si no se hizo esto, se creará un nuevo module.ini en la carpeta %ProgramData%\CloudConnector y se reemplazará la información de la versión de copia de seguridad/en ejecución para 1.3.4 o 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p118">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1. After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet. `Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector. If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
    <span data-ttu-id="3dff3-191">Compare los archivos module.ini files en la carpeta %perfilusuario%\CloudConnector y %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="3dff3-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="3dff3-192">Si hay diferencias, elimine el archivo module.ini en %ProgramData%\CloudConnector y volver a ejecutar `Register-CcAppliance`.</span><span class="sxs-lookup"><span data-stu-id="3dff3-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="3dff3-193">También puede modificar el archivo manualmente a la ejecución correcta y la versión de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3dff3-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="3dff3-194">**Problema: Después de ejecutar el cmdlet CcVersion de modificador para cambiar a una versión anterior que es diferente de la versión actual de secuencia de comandos, no hay ninguna compatibilidad de alta disponibilidad para esta versión anterior.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="3dff3-195">**Resolución:** Por ejemplo, ha actualizado desde 1.4.1 a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="3dff3-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="3dff3-196">La versión actual de secuencia de comandos, que se puede determinar mediante la ejecución de `Get-CcVersion`y la versión que se está ejecutando, que se puede determinar mediante la ejecución de `Get-CcRunningVersion` son ambos 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="3dff3-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="3dff3-197">En este momento, si ejecuta `Switch-CcVersion` para la versión que se está ejecutando volver a 1.4.1, a continuación, no habrá ningún soporte de alta disponibilidad para esta versión anterior.</span><span class="sxs-lookup"><span data-stu-id="3dff3-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="3dff3-p121">Para obtener compatibilidad total con alta disponibilidad, vuelva a 1.4.2 para que la versión en ejecución y la versión del script sean las mismas. Si está experimentando problemas con su implementación de 1.4.2, desinstálela y vuelva a instalarla tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="3dff3-200">**Problema: los certificados de una entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="3dff3-p122">**Resolución:** los certificados de la entidad de certificación de Skype Empresarial son válidos durante cinco años. Los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral son válidos durante dos años.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3dff3-203">En el conector en la nube versión 2.0 y versiones posterior, el cmdlet renovar CcServerCertificate ha cambiado a CcServerCertificate de actualización y el cmdlet renovar CcCACertificate ha cambiado a CcCACertificate de actualización.</span><span class="sxs-lookup"><span data-stu-id="3dff3-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="3dff3-204">Si los certificados internos emitidos para el almacén de Administración Central, el servidor de mediación y el servidor perimetral están cerca de expiración o ve comprometida, ejecutan el renovar CcServerCertificate o el cmdlet Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="3dff3-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="3dff3-205">Si los certificados de entidad de certificación son cerca de expiración, ejecute el cmdlet renovar CcCACertificate o CcCACertificate de actualización para renovar sus certificados.</span><span class="sxs-lookup"><span data-stu-id="3dff3-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="3dff3-206">**Si se ve comprometidos certificados de entidades emisoras y hay un único dispositivo en el sitio,** realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="3dff3-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="3dff3-207">Ejecute el cmdlet Enter-CcUpdate para depurar los servicios y poner el dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3dff3-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
    
2. <span data-ttu-id="3dff3-208">Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de la entidad de certificación y todos los certificados internos del servidor:</span><span class="sxs-lookup"><span data-stu-id="3dff3-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="3dff3-209">Para las versiones en la nube conector antes de 2.0:</span><span class="sxs-lookup"><span data-stu-id="3dff3-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="3dff3-210">O bien, para la versión de conector en la nube 2.0 y versiones posterior:</span><span class="sxs-lookup"><span data-stu-id="3dff3-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. <span data-ttu-id="3dff3-211">Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3dff3-211">Run the Exit-CcUpdate cmdlet to start services and and exit maintenance mode.</span></span>
    
4. <span data-ttu-id="3dff3-212">Ejecute el cmdlet Export-CcRootCertificate en el archivo local file del dispositivo y después copie e instale el certificado exportado en sus puertas de enlace de RTC.</span><span class="sxs-lookup"><span data-stu-id="3dff3-212">Run the Export-CcRootCertificate cmdlet on the local file in the appliance, and then copy and install the exported certificate to your PSTN gateways.</span></span>
    
    <span data-ttu-id="3dff3-213">**Si se ve comprometidos certificados de entidades emisoras y hay varios dispositivos en el sitio,** realice la siguiente secuencia de pasos en cada dispositivo en el sitio.</span><span class="sxs-lookup"><span data-stu-id="3dff3-213">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="3dff3-214">Microsoft recomienda que realice estos pasos durante las horas que no sean de máximo uso.</span><span class="sxs-lookup"><span data-stu-id="3dff3-214">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
  - <span data-ttu-id="3dff3-215">En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar la entidad de certificación en los archivos de copia de seguridad la \<SiteRoot\> Active directory.</span><span class="sxs-lookup"><span data-stu-id="3dff3-215">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>
    
  - <span data-ttu-id="3dff3-216">Ejecute el cmdlet de entrar CcUpdate para purgar servicios y coloque cada dispositivo en el modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3dff3-216">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>
    
  - <span data-ttu-id="3dff3-217">Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de la entidad de certificación y todos los certificados internos del servidor:</span><span class="sxs-lookup"><span data-stu-id="3dff3-217">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="3dff3-218">Para las versiones en la nube conector antes de 2.0:</span><span class="sxs-lookup"><span data-stu-id="3dff3-218">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate
    Renew-CcServerCertificate
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="3dff3-219">O bien, para la versión de conector en la nube 2.0 y versiones posterior:</span><span class="sxs-lookup"><span data-stu-id="3dff3-219">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate
    Update-CcServerCertificate
    Remove-CcLegacyServerCertificate 
    ```

  - <span data-ttu-id="3dff3-220">En el primer dispositivo, ejecute el siguiente cmdlet para realizar una copia de seguridad de los archivos de la entidad emisora de certificados para la \<SiteRoot\> carpeta.</span><span class="sxs-lookup"><span data-stu-id="3dff3-220">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span> <span data-ttu-id="3dff3-221">Más adelante, en todos los otros dispositivos en el mismo sitio, el cmdlet Reset-CcCACertificate consumirá automáticamente los archivos de copia de seguridad de la entidad emisora de certificados y dispositivos, usarán el mismo certificado raíz.</span><span class="sxs-lookup"><span data-stu-id="3dff3-221">Later, on all other appliances in the same site, the Reset-CcCACertificate cmdlet will consume the CA backup files automatically and appliances will use the same root certificate.</span></span>
    
    ```
    Backup-CcCertificationAuthority
    ```

  - <span data-ttu-id="3dff3-222">Ejecute el cmdlet de Exit CcUpdate para iniciar servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="3dff3-222">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 
    
  - <span data-ttu-id="3dff3-223">Si se utiliza TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo en el sitio y, a continuación, instale el certificado exportado a las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="3dff3-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> 
    
- <span data-ttu-id="3dff3-224">**Problema: Recibe el mensaje de error siguiente en el registro de servicio de administración del conector en la nube, "C:\Program Files\Skype para profesionales en la nube conector Edition\ManagementService\CceManagementService.log": CceService Error: 0: excepción inesperada cuando informar del estado a online: System.Management.Automation.CmdletInvocationException: error de inicio de sesión para el usuario \<Global Administrador de inquilinos\>. Cree un nuevo objeto de credencial, asegurándose de que se han utilizado el nombre de usuario correcto y la contraseña. ---\>**</span><span class="sxs-lookup"><span data-stu-id="3dff3-224">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="3dff3-225">**Resolución:** Las credenciales de administración de Office 365 inquilino global se han cambiado desde que se registró el dispositivo conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="3dff3-225">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="3dff3-226">Para actualizar las credenciales almacenadas localmente en el dispositivo de conector en la nube, ejecute lo siguiente desde el Administrador de PowerShell en el dispositivo de host:</span><span class="sxs-lookup"><span data-stu-id="3dff3-226">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="3dff3-227">**Problema: Después de cambiar la contraseña de la cuenta del servidor de host utilizados para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString: especificar la clave no es válido para su uso en estado." en %ProgramFiles%\Skype para la nube de Business Connector Edition\ManagementService\CceManagementService.log o mientras se ejecuta el cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-227">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="3dff3-228">**Resolución:** Todas las credenciales del conector en la nube se almacenan en el siguiente archivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="3dff3-228">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="3dff3-229">Cuando se cambia la contraseña en el servidor de host, debe actualizar las credenciales almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-229">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="3dff3-230">**Si ejecuta la versión 1.4.2 de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector mediante estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3dff3-230">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
    1. <span data-ttu-id="3dff3-231">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="3dff3-231">Restart the host server.</span></span>
    
    2. <span data-ttu-id="3dff3-232">Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="3dff3-232">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
    3. <span data-ttu-id="3dff3-233">Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción.</span><span class="sxs-lookup"><span data-stu-id="3dff3-233">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="3dff3-234">Escriba las mismas contraseñas que ha especificado antes de la implementación del conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="3dff3-234">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
    <span data-ttu-id="3dff3-235">**Si está ejecutando en la nube conector versión 2.0 o posterior,** vuelva a generar todas las contraseñas de conector en la nube, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3dff3-235">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
    1. <span data-ttu-id="3dff3-236">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="3dff3-236">Restart the host server.</span></span>
    
    2. <span data-ttu-id="3dff3-237">Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="3dff3-237">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
    3. <span data-ttu-id="3dff3-238">Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción.</span><span class="sxs-lookup"><span data-stu-id="3dff3-238">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="3dff3-p127">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector, use la contraseña de VMAdmin para la contraseña de CceService cuando se le solicite. Introduzca la misma contraseña que usó antes para la implementación de Cloud Connector de todas las otras cuentas.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p127">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
    <span data-ttu-id="3dff3-241">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector y las contraseñas de DomainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="3dff3-241">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
    1. <span data-ttu-id="3dff3-242">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="3dff3-242">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
    2. <span data-ttu-id="3dff3-243">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="3dff3-243">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
    3. <span data-ttu-id="3dff3-244">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="3dff3-244">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
    <span data-ttu-id="3dff3-245">Si se ha generado el archivo de contraseña almacenada en caché con el conector de nube versión 2.0 o posterior, de forma predeterminada, VmAdmin y Administrador de dominio usan la misma contraseña como CceService.</span><span class="sxs-lookup"><span data-stu-id="3dff3-245">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="3dff3-246">Si cambia la contraseña del administrador del dominio y VMAdmin, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="3dff3-246">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
    1. <span data-ttu-id="3dff3-247">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="3dff3-247">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
        1. <span data-ttu-id="3dff3-248">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="3dff3-248">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
        2. <span data-ttu-id="3dff3-249">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="3dff3-249">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
    2. <span data-ttu-id="3dff3-250">Ejecute Set-CcCredential -AccountType VmAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="3dff3-250">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
        1. <span data-ttu-id="3dff3-251">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="3dff3-251">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
        2. <span data-ttu-id="3dff3-252">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin que usó antes. </span><span class="sxs-lookup"><span data-stu-id="3dff3-252">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="3dff3-253">**Problema: Con la nube conector versión 2.1 y versiones posterior, cuando se ejecuta registrar CcAppliance u otros cmdlets en el dispositivo, recibirá un mensaje de error como: "para cada objeto: la propiedad 'Comunes' no se encuentra en este objeto. Compruebe que existe la propiedad. En C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="3dff3-253">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="3dff3-254">**Resolución:** En la nube conector 2.1 y posterior requiere .NET Framework 4.6.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3dff3-254">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="3dff3-255">Por favor, actualice .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar la cmdlet(s).</span><span class="sxs-lookup"><span data-stu-id="3dff3-255">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="3dff3-256">**Problema: Con la nube conector Edition 2.1, al ejecutar Install-CcAppliance, recibirá un mensaje de error como: "no se pudo instalar la nueva instancia con error: no se puede establecer el"Estado"porque sólo cadenas se pueden utilizar como valores para establecer las propiedades de XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="3dff3-256">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="3dff3-257">**Resolución:** En Cloudconnector.ini, en la sección [Common], agregue la configuración de "Estado" como sigue: CountryCode = US estado = ciudad WA = Redmond</span><span class="sxs-lookup"><span data-stu-id="3dff3-257">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="3dff3-258">No es obligatorio para la línea de "Estado" tiene valor, sin embargo, la línea de "Estado" no se puede quitar el archivo Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="3dff3-258">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="3dff3-259">**Problema: Recibe el siguiente mensaje de error "Dismount-WindowsImage: no se pudo Dismount-WindowsImage. Código de error = 0xc1550115 "al instalar o actualizar la edición de conector en la nube.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-259">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="3dff3-260">**Resolución:** Iniciar una consola de PowerShell como administrador, ejecute "DISM-Cleanup-Wim'".</span><span class="sxs-lookup"><span data-stu-id="3dff3-260">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="3dff3-261">Esto va a limpiar todas las imágenes con problemas.</span><span class="sxs-lookup"><span data-stu-id="3dff3-261">This will clean up all troubled images.</span></span> <span data-ttu-id="3dff3-262">Vuelva a ejecutar Install-CcAppliance o espere a que los bits actualizar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-262">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="3dff3-263">**Problema: Implementación del primer dispositivo conector en la nube en un entorno de alta disponibilidad se produce un error**</span><span class="sxs-lookup"><span data-stu-id="3dff3-263">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="3dff3-264">**Resolución:** Los pasos que seguir dependen de la razón del error en la implementación:</span><span class="sxs-lookup"><span data-stu-id="3dff3-264">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="3dff3-265">Si se produce un error en el primer dispositivo de conector en la nube y no puede determinar el motivo del error, debe instalar de nuevo el dispositivo hasta que la implementación se realizó correctamente y, a continuación, instale los demás dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3dff3-265">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="3dff3-266">Si se produce un error en el primer dispositivo de conector en la nube con un problema menor, por ejemplo, un problema de certificado externo, es posible que pueda solucionar el problema sin tener que volver a instalar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-266">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="3dff3-267">Se puede, a continuación, el uso de inquilinos PowerShell remoto para marcar la implementación como correcta de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="3dff3-267">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="3dff3-268">(También puede usar los siguientes pasos si la finalización correcta de la primera implementación, pero, por algún motivo, el conector de la nube se produce un error informar de la implementación como un éxito.)</span><span class="sxs-lookup"><span data-stu-id="3dff3-268">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="3dff3-269">Para obtener la identidad (GUID) del primer dispositivo conector en la nube, ejecute el cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="3dff3-269">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="3dff3-270">Para marcar el dispositivo implementado como correctamente, ejecute el Set-CsCceApplianceDeploymentStatus como sigue:</span><span class="sxs-lookup"><span data-stu-id="3dff3-270">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

-  <span data-ttu-id="3dff3-271">**Problema: debe comprobar si existen actualizaciones de Windows e instalarlas manualmente en el servidor host o las máquinas virtuales.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-271">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
    <span data-ttu-id="3dff3-p132">**Resolución:** recomendamos que aproveche las actualizaciones automatizadas del sistema operativo proporcionada por Skype Empresarial Cloud Connector Edition. Después de que se registre un dispositivo para administración en línea y se habilite la actualización automática del sistema operativo, el servidor host y las máquinas virtuales automáticamente comprobarán si existen actualizaciones de Windows y las instalarán de acuerdo con la configuración de la ventana de la hora de actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p132">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
    <span data-ttu-id="3dff3-p133">Si tiene que comprobar si existen actualizaciones de Windows e instalarlas manualmente, siga los pasos provistos en esta sección que se apliquen a su tipo de implementación. Debe planificar y actualizar tanto el servidor host como las máquinas virtuales que estén ejecutándose en él al mismo tiempo a fin de minimizar el tiempo de inactividad necesario para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p133">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
    <span data-ttu-id="3dff3-p134">Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones para los servidores de Cloud Connector. Solo tiene que configurar la actualización de Windows para que **no** se instale automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-p134">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
    <span data-ttu-id="3dff3-278">Para obtener información sobre cómo actualizar manualmente su implementación de Cloud Connector, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="3dff3-278">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
-   <span data-ttu-id="3dff3-279">**Problema: Al conector de la nube se actualiza a una nueva compilación, cmdlets de conector en la nube no se actualizan.**</span><span class="sxs-lookup"><span data-stu-id="3dff3-279">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="3dff3-280">En ocasiones, esto ocurre si una ventana de PowerShell se deja abierta cuando se produzca la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="3dff3-280">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
    <span data-ttu-id="3dff3-281">**Resolución:** Para cargar los cmdlets actualizados, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3dff3-281">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
     - <span data-ttu-id="3dff3-282">Cierre de PowerShell en el dispositivo de conector en la nube y, a continuación, vuelva a abrir PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dff3-282">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="3dff3-283">O bien, puede ejecutar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="3dff3-283">Or, you can run Import-Module CloudConnector -Force.</span></span> 
    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="3dff3-284">Instalar manualmente las actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="3dff3-284">Install Windows updates manually</span></span>

<span data-ttu-id="3dff3-285">Si no quiere usar actualizaciones automáticas en su entorno, siga estos pasos para comprobar si existen actualizaciones de Windows y aplicarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="3dff3-285">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="3dff3-286">Puede ser necesario reiniciar el servidor para la comprobación e instalación de actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="3dff3-286">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="3dff3-287">Cuando se reinicia un servidor de host, los usuarios no podrán utilizar el conector de la nube para realizar o recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="3dff3-287">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="3dff3-288">Puede comprobar si existen actualizaciones e instalarlas de forma manual a fin de controlar en qué momento deben producirse, y después reiniciar las máquinas según la necesidad durante los tiempos que usted elija para evitar interrupciones de los servicios.</span><span class="sxs-lookup"><span data-stu-id="3dff3-288">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="3dff3-289">Para comprobar manualmente si existen actualizaciones, conecte cada servidor host y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="3dff3-289">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="3dff3-290">Seleccione **sistema y seguridad \>Windows Update**y, a continuación, administrar las actualizaciones y se reinicia según corresponda para su entorno de servidor.</span><span class="sxs-lookup"><span data-stu-id="3dff3-290">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="3dff3-291">Si existe solo un dispositivo en el sitio, conecte cada máquina virtual y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="3dff3-291">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="3dff3-292">Seleccione **sistema y seguridad \>Windows Update**y, a continuación, configurar las actualizaciones y el servidor se reinicia según corresponda.</span><span class="sxs-lookup"><span data-stu-id="3dff3-292">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="3dff3-p139">Si hay más de un dispositivo en el sitio, los usuarios no pueden acceder a la instancia que se actualiza y reinicia durante las actualizaciones. Estos se conectarán con otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype Empresarial se inicien en las máquinas virtuales después de completadas las actualizaciones. Para evitar cualquier posible interrupción en el servicio, puede quitar la instancia de HA mientras aplica las actualizaciones y restaurarla cuando se completen. Para ello, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3dff3-p139">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="3dff3-297">En cada servidor host, abra una consola de PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="3dff3-297">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="3dff3-298">Quite la instancia de HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3dff3-298">Remove the instance from HA with the following cmdlet:</span></span>
    
  ```
  Enter-CcUpdate
  ```

3. 
    
    <span data-ttu-id="3dff3-299">Siga los pasos para una sola instancia para aplicar manualmente las actualizaciones y reinicie la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="3dff3-299">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="3dff3-300">Vuelva a configurar la instancia en HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3dff3-300">Set the instance back to HA with the following cmdlet:</span></span>
    
  ```
  Exit-CcUpdate
  ```

<span data-ttu-id="3dff3-301">Para implementaciones de varios sitios, siga los pasos destinados a un único sitio para cada sitio de la implementación aplicando las actualizaciones de a uno por vez.</span><span class="sxs-lookup"><span data-stu-id="3dff3-301">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="3dff3-302">Sugerencias al instalar el software antivirus en el equipo host de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="3dff3-302">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="3dff3-303">Si necesita instalar un software antivirus en el equipo host de conector en la nube, debe agregar las exclusiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dff3-303">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="3dff3-304">Directorio de dispositivo local en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-304">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="3dff3-305">Directorio de sitio remoto en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="3dff3-305">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="3dff3-306">Directorio de sitio local en el equipo hospeda la carpeta raíz del sitio compartido.</span><span class="sxs-lookup"><span data-stu-id="3dff3-306">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="3dff3-307">%ProgramFiles%\Skype para Business Edition de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="3dff3-307">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="3dff3-308">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="3dff3-308">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="3dff3-309">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="3dff3-309">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="3dff3-310">El proceso de Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="3dff3-310">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
