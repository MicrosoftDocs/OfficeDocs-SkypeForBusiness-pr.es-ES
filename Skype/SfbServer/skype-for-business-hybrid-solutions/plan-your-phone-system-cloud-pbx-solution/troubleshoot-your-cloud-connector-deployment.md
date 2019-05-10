---
title: Solución de problemas con la implementación de Cloud Connector
ms.reviewer: ''
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
ms.openlocfilehash: b9ade46f46898d22bab862c3044e045de441b007
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33864921"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="600f4-103">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="600f4-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="600f4-104">Solución de problemas de la implementación de nube conector Edition.</span><span class="sxs-lookup"><span data-stu-id="600f4-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="600f4-p101">En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition. Si tiene problemas con las llamadas en los dos sentidos de la red telefónica conmutada (RTC), puede investigar el problema siguiendo las soluciones que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="600f4-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="600f4-107">En la nube conector proporciona mecanismos integrados para resolver algunos problemas de automáticamente.</span><span class="sxs-lookup"><span data-stu-id="600f4-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="600f4-108">Un proceso de detección automática busca posibles problemas con los dispositivos de conector en la nube y, si es posible, realiza una acción correctiva para resolver estos problemas sin necesidad de intervención del administrador.</span><span class="sxs-lookup"><span data-stu-id="600f4-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="600f4-109">El proceso de detección funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="600f4-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="600f4-110">**Secuencia de detección:** El servicio de administración del conector en la nube ejecuta un proceso de cada 60 segundos para detectar si un dispositivo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="600f4-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="600f4-111">En el conector en la nube versión 2.0 y versiones posterior, el proceso de detección usa el Skype para modificador Corpnet empresarial para realizar conexiones de PowerShell para las máquinas de conector en la nube; para las versiones anteriores a 2.0, el proceso de detección usa el modificador de administración del conector de la nube.</span><span class="sxs-lookup"><span data-stu-id="600f4-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="600f4-112">Para que la recuperación automática se realice correctamente, debe haber conectividad de red entre el host y máquinas virtuales a través del conmutador de red de host.</span><span class="sxs-lookup"><span data-stu-id="600f4-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="600f4-113">Asegúrese de comprobar la conectividad de red para asegurarse de que la detección automática y recuperación puede tener éxito.</span><span class="sxs-lookup"><span data-stu-id="600f4-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="600f4-114">**Supervisión:** Los siguientes servicios se supervisan en la nube Connector versión 2.0 y versiones posterior:</span><span class="sxs-lookup"><span data-stu-id="600f4-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="600f4-115">Las máquinas virtuales no están conectadas a la nube conector corporativo o modificadores virtuales de Internet</span><span class="sxs-lookup"><span data-stu-id="600f4-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="600f4-116">Las máquinas virtuales se encuentran en un estado detenido o guardado</span><span class="sxs-lookup"><span data-stu-id="600f4-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="600f4-117">Servicios de servidor de administración centrales: réplica, patrón</span><span class="sxs-lookup"><span data-stu-id="600f4-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="600f4-118">Servicios de servidor de mediación: réplica, RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="600f4-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="600f4-119">Servicios de servidores perimetrales: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="600f4-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="600f4-120">Las reglas están deshabilitadas para RTCSRV CS en servidor perimetral, CS RTCMEDSRV en el servidor de mediación de firewall de entrada</span><span class="sxs-lookup"><span data-stu-id="600f4-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="600f4-121">En el conector en la nube versión 1.4.2, se supervisan únicamente los servicios siguientes:</span><span class="sxs-lookup"><span data-stu-id="600f4-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="600f4-122">Servicios de servidor de mediación: RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="600f4-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="600f4-123">Servicio de servidor perimetral: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="600f4-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="600f4-124">**Proceso de recuperación:** Si todos los servicios supervisados están inactivos, un dispositivo se marca hacia abajo, y servicios se ha detenido y marcados manuales hasta que se pueden resolver todos los problemas.</span><span class="sxs-lookup"><span data-stu-id="600f4-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="600f4-125">Esto evita que las llamadas de enrutamiento a un dispositivo que puede causar errores de llamadas.</span><span class="sxs-lookup"><span data-stu-id="600f4-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="600f4-126">El servicio de administración del conector en la nube se volverá a intentar la recuperación automática de manera</span><span class="sxs-lookup"><span data-stu-id="600f4-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="600f4-127">El intervalo de reintento inicial es cada diez segundos con un tiempo de intervalo máximo de una hora.</span><span class="sxs-lookup"><span data-stu-id="600f4-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="600f4-128">Para los intentos de tres en primer lugar recuperación, el intervalo de tiempo es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="600f4-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="600f4-129">A partir del cuarto reintento, aumenta el intervalo de tiempo por dos veces el anterior intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="600f4-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="600f4-130">Por ejemplo, el cuarto reintento se se producen en 20 segundos, la quinta en 40 segundos y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="600f4-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="600f4-131">Cuando se alcanza el intervalo máximo de tiempo de una hora, reintentos continuará una vez cada hora.</span><span class="sxs-lookup"><span data-stu-id="600f4-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="600f4-132">Cuando la recuperación es correcta, se establecen los recuentos de intervalo e inténtelo de nuevo en sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="600f4-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="600f4-133">Si se reinicia el servicio de administración, se restablecen los recuentos de intervalo e inténtelo de nuevo a sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="600f4-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="600f4-134">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="600f4-134">Troubleshooting</span></span>

<span data-ttu-id="600f4-135">A continuación se muestran soluciones para problemas habituales:</span><span class="sxs-lookup"><span data-stu-id="600f4-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="600f4-136">**Problema: la implementación presenta un error o deja de responder cuando se ejecutan los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o esta es incorrecta para la NIC externa, interna o de administración.**</span><span class="sxs-lookup"><span data-stu-id="600f4-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="600f4-137">**Resolución:** No se puede resolver este problema automáticamente.</span><span class="sxs-lookup"><span data-stu-id="600f4-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="600f4-138">NIC no se puede agregar a las máquinas virtuales mientras se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="600f4-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="600f4-139">Por favor, apagar y quitar estas máquinas virtuales en el Administrador de hyper-v, a continuación, ejecutar los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="600f4-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="600f4-140">**Problema: después de instalar el servidor de Active Directory y el bosque, el servidor CMS o el servidor de mediación no se unen al dominio correctamente.**</span><span class="sxs-lookup"><span data-stu-id="600f4-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="600f4-141">**Resolución:** para resolver este problema, lleve a cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="600f4-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="600f4-142">Inicie sesión en el servidor de Active Directory y compruebe que se haya creado el dominio correctamente.</span><span class="sxs-lookup"><span data-stu-id="600f4-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="600f4-143">Inicie sesión en el servidor CMS o de mediación, y compruebe en el NIC de red corporativa que se haya asignado una dirección IP válida y que estén configurados un DNS y una IP estática válidos como la dirección IP del servidor de AD.</span><span class="sxs-lookup"><span data-stu-id="600f4-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="600f4-144">Inicie sesión en el servidor de mediación/CMS y abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="600f4-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="600f4-145">Asegúrese de poder hacer ping a la dirección IP y el FQDN del servidor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="600f4-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="600f4-146">Si no puede, es posible que haya un conflicto con la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="600f4-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="600f4-147">Intente asignar una nueva IP para Active Directory y actualice en consecuencia el DNS en el servidor CMS o de mediación.</span><span class="sxs-lookup"><span data-stu-id="600f4-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="600f4-148">**Problema: Recibe el siguiente mensaje de error "Remove-VMSwitch: error al eliminar la conmutación de Ethernet virtual. El modificador virtual 'Administración del conector en la nube cambiar' no pueden eliminarse porque está siendo utilizado mediante la ejecución de máquinas virtuales ni asignado a los grupos de servidores secundarios."**</span><span class="sxs-lookup"><span data-stu-id="600f4-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="600f4-149">**Resolución:** No se ha eliminado el "conmutador de administración de conector en la nube" después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="600f4-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="600f4-150">Si presiona la tecla este error, vaya al administrador de Hyper-v y compruebe que haya no sigue una máquina virtual que sigue conectada a ella.</span><span class="sxs-lookup"><span data-stu-id="600f4-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="600f4-151">Si hay máquinas virtuales que sigue conectadas, desconectar ellos y elimine el modificador de administración.</span><span class="sxs-lookup"><span data-stu-id="600f4-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="600f4-152">Si aún no se puede eliminar el modificador de administración, reinicie el servidor de host e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="600f4-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="600f4-153">**Problema: Recibe el mensaje de error siguiente, "servicio RTCMRAUTH no se pudo iniciar. Compruebe que el servicio no está deshabilitado."**</span><span class="sxs-lookup"><span data-stu-id="600f4-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="600f4-154">Este problema solo se aplica a las versiones del conector de nube anteriores a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="600f4-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="600f4-p110">La imposibilidad de iniciar también puede deberse a que el servidor front-end se haya conmutado previamente por error (mediante una conmutación por error del equipo), en cuyo caso debería invocar una conmutación por recuperación (mediante una conmutación por recuperación del equipo).</span><span class="sxs-lookup"><span data-stu-id="600f4-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="600f4-p111">**Resolución:** este problema se produce en un servidor perimetral cuando dicho servidor no confía en el certificado de CA raíz o de CA intermedia, incluso cuando pueda importarse el certificado externo, pero la cadena de certificados se vea interrumpida. En esta situación, no puede iniciarse el servicio RTCMRAUTH o RTCSRV.</span><span class="sxs-lookup"><span data-stu-id="600f4-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="600f4-p112">Importe en el servidor perimetral el certificado de CA raíz y todos los certificados de CA intermedia de su certificado externo de forma manual y reinicie el servidor. Después de ver que se hayan iniciado los servicios RTCMRAUTH y RTCSRV en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:</span><span class="sxs-lookup"><span data-stu-id="600f4-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="600f4-162">**Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows, y las llamadas a las que presta servicio el servidor están fallando.**</span><span class="sxs-lookup"><span data-stu-id="600f4-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="600f4-p113">**Resolución:** si ha implementado un entorno de alta disponibilidad, Microsoft proporciona un cmdlet que le ayudará a mover una máquina host (instancia de implementación) dentro o fuera de la topología actual cuando compruebe e instale actualizaciones de Windows de forma manual. Use los siguientes pasos para llevar a cabo esto:</span><span class="sxs-lookup"><span data-stu-id="600f4-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="600f4-165">En el servidor host, inicie una consola de PowerShell como administrador y después ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="600f4-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```
   Enter-CcUpdate
   ```

2. <span data-ttu-id="600f4-166">Compruebe si existen actualizaciones e instale las que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="600f4-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="600f4-167">En la consola de PowerShell, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="600f4-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="600f4-168">**Problema: cuando se realiza una llamada desde el cliente de Skype Empresarial con un número de RTC, la llamada no puede escalarse a conferencia invitando a otro número de RTC.**</span><span class="sxs-lookup"><span data-stu-id="600f4-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="600f4-169">**Resolución:** Para resolver este problema, vea [Configure online híbrido configuración del servidor de mediación](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="600f4-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="600f4-170">**Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar un servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarse de que la característica o el rol recién instalados se actualicen automáticamente, active Windows Update en el Panel de control".**</span><span class="sxs-lookup"><span data-stu-id="600f4-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="600f4-171">**Resolución:** Iniciar una sesión de PowerShell remoto inquilino con Skype para credenciales de administrador de inquilinos de negocio y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ del sitio:</span><span class="sxs-lookup"><span data-stu-id="600f4-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="600f4-172">Si _EnableAutoUpdate_ está establecida en **True**, puede ignorar este mensaje de advertencia debido a que el servicio CCEManagement controlará la descarga e instalación de actualizaciones de Windows para las máquinas virtuales y el servidor host.</span><span class="sxs-lookup"><span data-stu-id="600f4-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="600f4-173">Si _EnableAutoUpdate_ está establecida en **False**, ejecute siguiente cmdlet para establecer en **True**.</span><span class="sxs-lookup"><span data-stu-id="600f4-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="600f4-174">Puede también comprobar si existen actualizaciones e instalarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="600f4-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="600f4-175">Consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="600f4-175">See the next section.</span></span>
    
- <span data-ttu-id="600f4-176">**Problema: Recibe un mensaje de error: no se puede registrar el dispositivo debido a que la configuración actual de entrada/ \<SiteName\> o \<ApplianceName\> o \<el FQDN del servidor de mediación\> o \<dirección IP de servidor de mediación \> entra en conflicto con appliance(s) existente. Quitar dispositivo de conflicto o actualizar la información de configuración de entrada y, a continuación, vuelva a registrar. ' cuando se ejecuta Register-CcAppliance para registrar el dispositivo actual a en línea.**</span><span class="sxs-lookup"><span data-stu-id="600f4-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="600f4-177">**Resolución:** Los valores para la \<ApplianceName\>, \<el FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> debe ser único y sólo utilizan para el registro de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="600f4-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="600f4-178">De forma predeterminada, \<ApplianceName\> proviene del nombre de host.</span><span class="sxs-lookup"><span data-stu-id="600f4-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="600f4-179">\<FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> definido en el archivo de configuración de ini.</span><span class="sxs-lookup"><span data-stu-id="600f4-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="600f4-180">Por ejemplo, se usa (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para el registro en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), experimentará el conflicto.</span><span class="sxs-lookup"><span data-stu-id="600f4-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="600f4-181">En primer lugar, compruebe el archivo CloudConnector.ini en la sección de directorio ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="600f4-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="600f4-182">Obtendrá \<SiteName\>, \<el FQDN del servidor de mediación\> y \<dirección IP de servidor de mediación\> valores en el archivo.</span><span class="sxs-lookup"><span data-stu-id="600f4-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="600f4-183">\<ApplianceName\> es el nombre del servidor host.</span><span class="sxs-lookup"><span data-stu-id="600f4-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="600f4-184">En segundo lugar, inicio inquilino PowerShell remoto con su Skype para credenciales de administrador de inquilinos de negocio, a continuación, ejecute el siguiente cmdlet para comprobar la appliance(s) registrados.</span><span class="sxs-lookup"><span data-stu-id="600f4-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="600f4-185">Después de identificar cualquier conflicto, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.</span><span class="sxs-lookup"><span data-stu-id="600f4-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="600f4-186">**Problema: El cmdlet Get-CcRunningVersion devuelve un valor vacío si no hay un dispositivo implementado que se ejecutan en el host.**</span><span class="sxs-lookup"><span data-stu-id="600f4-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="600f4-187">**Resolución:** Esto puede ocurrir cuando se actualiza desde 1.3.4 o 1.3.8 a 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="600f4-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="600f4-188">Después de instalar la versión 1.4.1 con el archivo .msi, debe ejecutar `Register-CcAppliance` antes de ejecutar cualquier otro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="600f4-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="600f4-189">`Register-CcAppliance`va a migrar el archivo module.ini desde %UserProfile%\CloudConnector a % ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="600f4-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="600f4-190">Si se lo haya perdido, un module.ini nueva se creará en la carpeta %ProgramData%\CloudConnector y reemplace la información de versión de copia de seguridad o ejecución para 1.3.4 o 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="600f4-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="600f4-191">Compare los archivos module.ini files en la carpeta %perfilusuario%\CloudConnector y %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="600f4-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="600f4-192">Si hay diferencias, elimine el archivo module.ini en %ProgramData%\CloudConnector y volver a ejecutar `Register-CcAppliance`.</span><span class="sxs-lookup"><span data-stu-id="600f4-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="600f4-193">También puede modificar el archivo manualmente a la ejecución correcta y la versión de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="600f4-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="600f4-194">**Problema: Después de ejecutar el cmdlet CcVersion de modificador para cambiar a una versión anterior que es diferente de la versión actual de secuencia de comandos, no hay ninguna compatibilidad de alta disponibilidad para esta versión anterior.**</span><span class="sxs-lookup"><span data-stu-id="600f4-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="600f4-195">**Resolución:** Por ejemplo, ha actualizado desde 1.4.1 a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="600f4-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="600f4-196">La versión actual de secuencia de comandos, que se puede determinar mediante la ejecución de `Get-CcVersion`y la versión que se está ejecutando, que se puede determinar mediante la ejecución de `Get-CcRunningVersion` son ambos 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="600f4-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="600f4-197">En este momento, si ejecuta `Switch-CcVersion` para la versión que se está ejecutando volver a 1.4.1, a continuación, no habrá ningún soporte de alta disponibilidad para esta versión anterior.</span><span class="sxs-lookup"><span data-stu-id="600f4-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="600f4-p121">Para obtener compatibilidad total con alta disponibilidad, vuelva a 1.4.2 para que la versión en ejecución y la versión del script sean las mismas. Si está experimentando problemas con su implementación de 1.4.2, desinstálela y vuelva a instalarla tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="600f4-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="600f4-200">**Problema: los certificados de una entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**</span><span class="sxs-lookup"><span data-stu-id="600f4-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="600f4-p122">**Resolución:** los certificados de la entidad de certificación de Skype Empresarial son válidos durante cinco años. Los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral son válidos durante dos años.</span><span class="sxs-lookup"><span data-stu-id="600f4-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="600f4-203">En el conector en la nube versión 2.0 y versiones posterior, el cmdlet renovar CcServerCertificate ha cambiado a CcServerCertificate de actualización y el cmdlet renovar CcCACertificate ha cambiado a CcCACertificate de actualización.</span><span class="sxs-lookup"><span data-stu-id="600f4-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="600f4-204">Si los certificados internos emitidos para el almacén de Administración Central, el servidor de mediación y el servidor perimetral están cerca de expiración o ve comprometida, ejecutan el renovar CcServerCertificate o el cmdlet Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="600f4-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="600f4-205">Si los certificados de entidad de certificación son cerca de expiración, ejecute el cmdlet renovar CcCACertificate o CcCACertificate de actualización para renovar sus certificados.</span><span class="sxs-lookup"><span data-stu-id="600f4-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="600f4-206">**Si se ve comprometidos certificados de entidades emisoras y hay un único dispositivo en el sitio,** realice los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="600f4-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="600f4-207">Ejecute el cmdlet Enter-CcUpdate para depurar los servicios y poner el dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="600f4-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="600f4-208">Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de la entidad de certificación y todos los certificados internos del servidor:</span><span class="sxs-lookup"><span data-stu-id="600f4-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="600f4-209">Para las versiones en la nube conector antes de 2.0:</span><span class="sxs-lookup"><span data-stu-id="600f4-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="600f4-210">O bien, para la versión de conector en la nube 2.0 y versiones posterior:</span><span class="sxs-lookup"><span data-stu-id="600f4-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="600f4-211">Si se utiliza TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado a las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="600f4-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="600f4-212">También es posible que requiera para volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="600f4-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="600f4-213">Ejecute el cmdlet de Exit CcUpdate para iniciar servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="600f4-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```
   Exit-CcUpdate
   ```


    <span data-ttu-id="600f4-214">**Si se ve comprometidos certificados de entidades emisoras y hay varios dispositivos en el sitio,** realice la siguiente secuencia de pasos en cada dispositivo en el sitio.</span><span class="sxs-lookup"><span data-stu-id="600f4-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="600f4-215">Microsoft recomienda que realice estos pasos durante las horas que no sean de máximo uso.</span><span class="sxs-lookup"><span data-stu-id="600f4-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="600f4-216">En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar la entidad de certificación en los archivos de copia de seguridad la \<SiteRoot\> Active directory.</span><span class="sxs-lookup"><span data-stu-id="600f4-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="600f4-217">Ejecute el cmdlet de entrar CcUpdate para purgar servicios y coloque cada dispositivo en el modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="600f4-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="600f4-218">En el primer dispositivo, ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="600f4-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="600f4-219">Para las versiones en la nube conector antes de 2.0:</span><span class="sxs-lookup"><span data-stu-id="600f4-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="600f4-220">O bien, para la versión de conector en la nube 2.0 y versiones posterior:</span><span class="sxs-lookup"><span data-stu-id="600f4-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="600f4-221">En el primer dispositivo, ejecute el siguiente cmdlet para realizar una copia de seguridad de los archivos de la entidad emisora de certificados para la \<SiteRoot\> carpeta.</span><span class="sxs-lookup"><span data-stu-id="600f4-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="600f4-222">En todos los demás del dispositivo en el mismo sitio, ejecute los siguientes comandos para consumir los archivos de copia de seguridad de la entidad emisora de certificados, de modo que los dispositivos todos usan el mismo certificado raíz y, a continuación, solicitar certificados nuevos.</span><span class="sxs-lookup"><span data-stu-id="600f4-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="600f4-223">Si se utiliza TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo en el sitio y, a continuación, instale el certificado exportado a las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="600f4-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="600f4-224">También es posible que requiera para volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="600f4-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="600f4-225">Ejecute el cmdlet de Exit CcUpdate para iniciar servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="600f4-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="600f4-226">**Problema: Recibe el mensaje de error siguiente en el registro de servicio de administración del conector en la nube, "C:\Program Files\Skype para profesionales en la nube conector Edition\ManagementService\CceManagementService.log": CceService Error: 0: excepción inesperada cuando informar del estado a online: System.Management.Automation.CmdletInvocationException: error de inicio de sesión para el usuario \<Global Administrador de inquilinos\>. Cree un nuevo objeto de credencial, asegurándose de que se han utilizado el nombre de usuario correcto y la contraseña. ---\>**</span><span class="sxs-lookup"><span data-stu-id="600f4-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="600f4-227">**Resolución:** Las credenciales de administración de Office 365 inquilino global se han cambiado desde que se registró el dispositivo conector en la nube.</span><span class="sxs-lookup"><span data-stu-id="600f4-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="600f4-228">Para actualizar las credenciales almacenadas localmente en el dispositivo de conector en la nube, ejecute lo siguiente desde el Administrador de PowerShell en el dispositivo de host:</span><span class="sxs-lookup"><span data-stu-id="600f4-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="600f4-229">**Problema: Después de cambiar la contraseña de la cuenta del servidor de host utilizados para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString: especificar la clave no es válido para su uso en estado." en %ProgramFiles%\Skype para la nube de Business Connector Edition\ManagementService\CceManagementService.log o mientras se ejecuta el cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="600f4-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="600f4-230">**Resolución:** Todas las credenciales del conector en la nube se almacenan en el siguiente archivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="600f4-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="600f4-231">Cuando se modifica la contraseña en el servidor host, tendrá que actualizar las credenciales que hay almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="600f4-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="600f4-232">**Si ejecuta la versión 1.4.2 de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector mediante estos pasos:</span><span class="sxs-lookup"><span data-stu-id="600f4-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="600f4-233">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="600f4-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="600f4-234">Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="600f4-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="600f4-235">Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción.</span><span class="sxs-lookup"><span data-stu-id="600f4-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="600f4-236">Introduzca las mismas contraseñas que usó antes para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="600f4-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="600f4-237">**Si está ejecutando en la nube conector versión 2.0 o posterior,** vuelva a generar todas las contraseñas de conector en la nube, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="600f4-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="600f4-238">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="600f4-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="600f4-239">Elimine el archivo siguiente: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".</span><span class="sxs-lookup"><span data-stu-id="600f4-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="600f4-240">Iniciar una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance-Local" para volver a escribir las contraseñas que sigue a la descripción.</span><span class="sxs-lookup"><span data-stu-id="600f4-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="600f4-p128">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector, use la contraseña de VMAdmin para la contraseña de CceService cuando se le solicite. Introduzca la misma contraseña que usó antes para la implementación de Cloud Connector de todas las otras cuentas.</span><span class="sxs-lookup"><span data-stu-id="600f4-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="600f4-243">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector y las contraseñas de DomainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="600f4-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="600f4-244">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="600f4-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="600f4-245">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="600f4-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="600f4-246">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="600f4-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="600f4-247">Si se ha generado el archivo de contraseña almacenada en caché con el conector de nube versión 2.0 o posterior, de forma predeterminada, VmAdmin y Administrador de dominio usan la misma contraseña como CceService.</span><span class="sxs-lookup"><span data-stu-id="600f4-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="600f4-248">Si ha cambiado las contraseñas de DomainAdmin y VMAdmin, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="600f4-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="600f4-249">Ejecute Set-CcCredential -AccountType DomainAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="600f4-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="600f4-250">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="600f4-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="600f4-251">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="600f4-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="600f4-252">Ejecute Set-CcCredential -AccountType VmAdmin como sigue:</span><span class="sxs-lookup"><span data-stu-id="600f4-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="600f4-253">Cuando se soliciten las credenciales de cuenta anteriores, introduzca las credenciales que ha utilizado para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="600f4-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="600f4-254">Cuando se soliciten las credenciales de cuenta nuevas, introduzca la contraseña para la contraseña de VmAdmin que usó antes. </span><span class="sxs-lookup"><span data-stu-id="600f4-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="600f4-255">**Problema: Con la nube conector versión 2.1 y versiones posterior, cuando se ejecuta registrar CcAppliance u otros cmdlets en el dispositivo, recibirá un mensaje de error como: "para cada objeto: la propiedad 'Comunes' no se encuentra en este objeto. Compruebe que existe la propiedad. En C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="600f4-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="600f4-256">**Resolución:** En la nube conector 2.1 y posterior requiere .NET Framework 4.6.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="600f4-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="600f4-257">Por favor, actualice .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar la cmdlet(s).</span><span class="sxs-lookup"><span data-stu-id="600f4-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="600f4-258">**Problema: Con la nube conector Edition 2.1, al ejecutar Install-CcAppliance, recibirá un mensaje de error como: "no se pudo instalar la nueva instancia con error: no se puede establecer el"Estado"porque sólo cadenas se pueden utilizar como valores para establecer las propiedades de XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="600f4-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="600f4-259">**Resolución:** En Cloudconnector.ini, en la sección [Common], agregue la configuración de "Estado" como sigue: CountryCode = US estado = ciudad WA = Redmond</span><span class="sxs-lookup"><span data-stu-id="600f4-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="600f4-260">No es obligatorio para la línea de "Estado" tiene valor, sin embargo, la línea de "Estado" no se puede quitar el archivo Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="600f4-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="600f4-261">**Problema: Recibe el siguiente mensaje de error "Dismount-WindowsImage: no se pudo Dismount-WindowsImage. Código de error = 0xc1550115 "al instalar o actualizar la edición de conector en la nube.**</span><span class="sxs-lookup"><span data-stu-id="600f4-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="600f4-262">**Resolución:** Iniciar una consola de PowerShell como administrador, ejecute "DISM-Cleanup-Wim'".</span><span class="sxs-lookup"><span data-stu-id="600f4-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="600f4-263">Esto va a limpiar todas las imágenes con problemas.</span><span class="sxs-lookup"><span data-stu-id="600f4-263">This will clean up all troubled images.</span></span> <span data-ttu-id="600f4-264">Vuelva a ejecutar Install-CcAppliance o espere a que los bits actualizar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="600f4-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="600f4-265">**Problema: Implementación del primer dispositivo conector en la nube en un entorno de alta disponibilidad se produce un error**</span><span class="sxs-lookup"><span data-stu-id="600f4-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="600f4-266">**Resolución:** Los pasos que seguir dependen de la razón del error en la implementación:</span><span class="sxs-lookup"><span data-stu-id="600f4-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="600f4-267">Si se produce un error en el primer dispositivo de conector en la nube y no puede determinar el motivo del error, debe instalar de nuevo el dispositivo hasta que la implementación se realizó correctamente y, a continuación, instale los demás dispositivos.</span><span class="sxs-lookup"><span data-stu-id="600f4-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="600f4-268">Si se produce un error en el primer dispositivo de conector en la nube con un problema menor, por ejemplo, un problema de certificado externo, es posible que pueda solucionar el problema sin tener que volver a instalar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="600f4-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="600f4-269">Se puede, a continuación, el uso de inquilinos PowerShell remoto para marcar la implementación como correcta de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="600f4-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="600f4-270">(También puede usar los siguientes pasos si la finalización correcta de la primera implementación, pero, por algún motivo, el conector de la nube se produce un error informar de la implementación como un éxito.)</span><span class="sxs-lookup"><span data-stu-id="600f4-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="600f4-271">Para obtener la identidad (GUID) del primer dispositivo conector en la nube, ejecute el cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="600f4-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="600f4-272">Para marcar el dispositivo implementado como correctamente, ejecute el Set-CsCceApplianceDeploymentStatus como sigue:</span><span class="sxs-lookup"><span data-stu-id="600f4-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="600f4-273">**Problema: debe comprobar si existen actualizaciones de Windows e instalarlas manualmente en el servidor host o las máquinas virtuales.**</span><span class="sxs-lookup"><span data-stu-id="600f4-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="600f4-p133">**Resolución:** recomendamos que aproveche las actualizaciones automatizadas del sistema operativo proporcionada por Skype Empresarial Cloud Connector Edition. Después de que se registre un dispositivo para administración en línea y se habilite la actualización automática del sistema operativo, el servidor host y las máquinas virtuales automáticamente comprobarán si existen actualizaciones de Windows y las instalarán de acuerdo con la configuración de la ventana de la hora de actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="600f4-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="600f4-p134">Si tiene que comprobar si existen actualizaciones de Windows e instalarlas manualmente, siga los pasos provistos en esta sección que se apliquen a su tipo de implementación. Debe planificar y actualizar tanto el servidor host como las máquinas virtuales que estén ejecutándose en él al mismo tiempo a fin de minimizar el tiempo de inactividad necesario para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="600f4-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="600f4-p135">Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones para los servidores de Cloud Connector. Solo tiene que configurar la actualización de Windows para que **no** se instale automáticamente.</span><span class="sxs-lookup"><span data-stu-id="600f4-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="600f4-280">Para obtener información sobre cómo actualizar manualmente su implementación de Cloud Connector, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="600f4-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="600f4-281">**Problema: Al conector de la nube se actualiza a una nueva compilación, cmdlets de conector en la nube no se actualizan.**</span><span class="sxs-lookup"><span data-stu-id="600f4-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="600f4-282">En ocasiones, esto ocurre si una ventana de PowerShell se deja abierta cuando se produzca la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="600f4-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="600f4-283">**Resolución:** Para cargar los cmdlets actualizados, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="600f4-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="600f4-284">Cierre de PowerShell en el dispositivo de conector en la nube y, a continuación, vuelva a abrir PowerShell.</span><span class="sxs-lookup"><span data-stu-id="600f4-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="600f4-285">O bien, puede ejecutar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="600f4-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="600f4-286">**Problema: "el término 'Stop-CsWindowsService' no se reconoce como el nombre de un cmdlet, función, archivo de secuencia de comandos o programa ejecutable." error al intentar ejecutar el cmdlet CcUpdate de ENTRAR.**</span><span class="sxs-lookup"><span data-stu-id="600f4-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="600f4-287">**Resolución:** Elimine el archivo de HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $.</span><span class="sxs-lookup"><span data-stu-id="600f4-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="600f4-288">PowerShell crea este archivo como una memoria caché de los cmdlets de los módulos que se encuentre por lo que no es necesario que volver a analizar cada vez como de todos los módulos que puedan hacer cosas realmente lento.</span><span class="sxs-lookup"><span data-stu-id="600f4-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="600f4-289">Probablemente, hubo algunos daños en el archivo que proporcionan resultados engañosos para PowerShell cuando estaba leyendo de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="600f4-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="600f4-290">**Problema: "Import-Module CloudConnector" genera error "Import-Module: el módulo especificado"CloudConnector"no se cargó porque se encontró ningún archivo de módulo válido en cualquier directorio module"**</span><span class="sxs-lookup"><span data-stu-id="600f4-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="600f4-291">**Solución:**</span><span class="sxs-lookup"><span data-stu-id="600f4-291">**Resolution:**</span></span>
    - <span data-ttu-id="600f4-292">Validar que en realidad el módulo CloudConnector existe en c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="600f4-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="600f4-293">Después de validar ese módulo CloudConnector existe en esta ubicación, se puede cambiar la variable de entorno PSModulePath almacenar la ruta de acceso a las ubicaciones de los módulos:</span><span class="sxs-lookup"><span data-stu-id="600f4-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="600f4-294">a.</span><span class="sxs-lookup"><span data-stu-id="600f4-294">a.</span></span> <span data-ttu-id="600f4-295">Cambio temporal: inicio Powershell como administrador y ejecute el comando siguiente: $env: PSModulePath = $env: PSModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="600f4-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="600f4-296">b.</span><span class="sxs-lookup"><span data-stu-id="600f4-296">b.</span></span> <span data-ttu-id="600f4-297">Para cambiar persistente, inicie PowerShell como administrador y ejecutar los siguientes comandos, uno a uno: $CurrentValue = [Environment]:: GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules","Equipo")</span><span class="sxs-lookup"><span data-stu-id="600f4-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="600f4-298">Instalar manualmente las actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="600f4-298">Install Windows updates manually</span></span>

<span data-ttu-id="600f4-299">Si no quiere usar actualizaciones automáticas en su entorno, siga estos pasos para comprobar si existen actualizaciones de Windows y aplicarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="600f4-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="600f4-300">Puede ser necesario reiniciar el servidor para la comprobación e instalación de actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="600f4-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="600f4-301">Cuando se reinicia un servidor de host, los usuarios no podrán utilizar el conector de la nube para realizar o recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="600f4-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="600f4-302">Puede comprobar si existen actualizaciones e instalarlas de forma manual a fin de controlar en qué momento deben producirse, y después reiniciar las máquinas según la necesidad durante los tiempos que usted elija para evitar interrupciones de los servicios.</span><span class="sxs-lookup"><span data-stu-id="600f4-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="600f4-303">Para comprobar manualmente si existen actualizaciones, conecte cada servidor host y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="600f4-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="600f4-304">Seleccione **sistema y seguridad \>Windows Update**y, a continuación, administrar las actualizaciones y se reinicia según corresponda para su entorno de servidor.</span><span class="sxs-lookup"><span data-stu-id="600f4-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="600f4-305">Si existe solo un dispositivo en el sitio, conecte cada máquina virtual y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="600f4-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="600f4-306">Seleccione **sistema y seguridad \>Windows Update**y, a continuación, configurar las actualizaciones y el servidor se reinicia según corresponda.</span><span class="sxs-lookup"><span data-stu-id="600f4-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="600f4-p143">Si hay más de un dispositivo en el sitio, los usuarios no pueden acceder a la instancia que se actualiza y reinicia durante las actualizaciones. Estos se conectarán con otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype Empresarial se inicien en las máquinas virtuales después de completadas las actualizaciones. Para evitar cualquier posible interrupción en el servicio, puede quitar la instancia de HA mientras aplica las actualizaciones y restaurarla cuando se completen. Para ello, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="600f4-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="600f4-311">En cada servidor host, abra una consola de PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="600f4-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="600f4-312">Quite la instancia de HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="600f4-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="600f4-313">Siga los pasos para una sola instancia para aplicar manualmente las actualizaciones y reinicie la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="600f4-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="600f4-314">Vuelva a configurar la instancia en HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="600f4-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

<span data-ttu-id="600f4-315">Para implementaciones de varios sitios, siga los pasos destinados a un único sitio para cada sitio de la implementación aplicando las actualizaciones de a uno por vez.</span><span class="sxs-lookup"><span data-stu-id="600f4-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="600f4-316">Sugerencias al instalar el software antivirus en el equipo host de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="600f4-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="600f4-317">Si necesita instalar un software antivirus en el equipo host de conector en la nube, debe agregar las exclusiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="600f4-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="600f4-318">Directorio de dispositivo local en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="600f4-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="600f4-319">Directorio de sitio remoto en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="600f4-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="600f4-320">Directorio de sitio local en el equipo hospeda la carpeta raíz del sitio compartido.</span><span class="sxs-lookup"><span data-stu-id="600f4-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="600f4-321">%ProgramFiles%\Skype para Business Edition de conector en la nube</span><span class="sxs-lookup"><span data-stu-id="600f4-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="600f4-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="600f4-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="600f4-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="600f4-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="600f4-324">El proceso de Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="600f4-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
