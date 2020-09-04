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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de la implementación de Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359336"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="015d6-103">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="015d6-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="015d6-104">Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="015d6-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="015d6-105">Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="015d6-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="015d6-106">Solucionar problemas de la implementación de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="015d6-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="015d6-107">En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="015d6-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="015d6-108">Si tiene problemas con las llamadas a y desde la red telefónica conmutada (RTC), puede investigarlo siguiendo las soluciones que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="015d6-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="015d6-109">Cloud Connector proporciona mecanismos integrados para resolver algunos problemas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="015d6-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="015d6-110">Un proceso de detección automática busca posibles problemas con los dispositivos de Cloud Connector y, si es posible, emprende acciones correctivas para resolver esos problemas sin necesidad de que intervenga el administrador.</span><span class="sxs-lookup"><span data-stu-id="015d6-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="015d6-111">El proceso de detección funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="015d6-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="015d6-112">**Secuencia de detección:** El servicio de administración de Cloud Connector ejecuta un proceso cada 60 segundos para detectar si un dispositivo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="015d6-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="015d6-113">En la versión 2,0 de Cloud Connector y versiones posteriores, el proceso de detección usa el conmutador de red corporativa de Skype empresarial para realizar conexiones de PowerShell a los equipos de Cloud Connector; para las versiones anteriores a 2,0, el proceso de detección usa el conmutador de administración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="015d6-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="015d6-114">Para que la recuperación automática se realice correctamente, debe haber conectividad de red entre el host y las máquinas virtuales a través del conmutador de red de host.</span><span class="sxs-lookup"><span data-stu-id="015d6-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="015d6-115">Asegúrese de comprobar la conectividad de red para asegurarse de que la detección y la recuperación automáticas se puedan realizar correctamente.</span><span class="sxs-lookup"><span data-stu-id="015d6-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="015d6-116">**Supervisión:** Los siguientes servicios se supervisan en la versión 2,0 de Cloud Connector y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="015d6-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="015d6-117">Las máquinas virtuales no están conectadas a los conmutadores virtuales corporativos o de Internet de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="015d6-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="015d6-118">Las máquinas virtuales se encuentran en estado guardado o detenido</span><span class="sxs-lookup"><span data-stu-id="015d6-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="015d6-119">Servicios del servidor de administración central: réplica, patrón</span><span class="sxs-lookup"><span data-stu-id="015d6-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="015d6-120">Servicios del servidor de mediación: REPLICA, RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="015d6-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="015d6-121">Servicios del servidor perimetral: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="015d6-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="015d6-122">Las reglas de Firewall de entrada están deshabilitadas para CS RTCSRV en el servidor perimetral, CS RTCMEDSRV en el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="015d6-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="015d6-123">En la versión 1.4.2 de Cloud Connector, solo se supervisan los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="015d6-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="015d6-124">Servicios del servidor de mediación: RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="015d6-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="015d6-125">Servicio de servidor perimetral: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="015d6-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="015d6-126">**Proceso de recuperación:** Si alguno de los servicios supervisados está inactivo, se marca un dispositivo y los servicios se detienen y se marcan como manuales hasta que se puedan resolver todos los problemas.</span><span class="sxs-lookup"><span data-stu-id="015d6-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="015d6-127">Esto impedirá que las llamadas se enruten a un dispositivo que puede causar errores de llamada.</span><span class="sxs-lookup"><span data-stu-id="015d6-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="015d6-128">El servicio de administración de Cloud Connector volverá a intentar la recuperación automática de la siguiente manera</span><span class="sxs-lookup"><span data-stu-id="015d6-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="015d6-129">El intervalo de reintento inicial es cada diez segundos con un intervalo de tiempo máximo de una hora.</span><span class="sxs-lookup"><span data-stu-id="015d6-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="015d6-130">Para los tres primeros intentos de recuperación, el tiempo de intervalo es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="015d6-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="015d6-131">A partir del cuarto reintento, el tiempo del intervalo aumenta en dos veces el tiempo del intervalo anterior.</span><span class="sxs-lookup"><span data-stu-id="015d6-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="015d6-132">Por ejemplo, el cuarto reintento se producirá en 20 segundos, el quinto en 40 segundos, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="015d6-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="015d6-133">Cuando se alcanza el tiempo máximo de intervalo de una hora, los reintentos continuarán una vez por hora.</span><span class="sxs-lookup"><span data-stu-id="015d6-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="015d6-134">Cuando la recuperación se realiza correctamente, el intervalo y los contadores de reintentos se establecen en sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="015d6-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="015d6-135">Si se reinicia el servicio de administración, el intervalo y los números de reintentos se restablecen a sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="015d6-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="015d6-136">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="015d6-136">Troubleshooting</span></span>

<span data-ttu-id="015d6-137">A continuación se muestran soluciones a los problemas más comunes:</span><span class="sxs-lookup"><span data-stu-id="015d6-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="015d6-138">**Problema: se produce un error en la implementación o deja de responder cuando se ejecutan los scripts de implementación. Después de iniciar sesión en cada máquina virtual, la dirección IP falta o es incorrecta para la NIC de administración/interno/externo.**</span><span class="sxs-lookup"><span data-stu-id="015d6-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="015d6-139">**Solución:** Este problema no se puede resolver automáticamente.</span><span class="sxs-lookup"><span data-stu-id="015d6-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="015d6-140">Las NICs no se pueden agregar a las máquinas virtuales mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="015d6-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="015d6-141">Cierre y quite estas máquinas virtuales en el administrador de Hyper-v y, a continuación, ejecute los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="015d6-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="015d6-142">**Problema: después de instalar el servidor y el bosque de Active Directory, el servidor CMS o el servidor de mediación no se unen al dominio correctamente.**</span><span class="sxs-lookup"><span data-stu-id="015d6-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="015d6-143">**Solución:** Para resolver este problema, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="015d6-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="015d6-144">Inicie sesión en el servidor de Active Directory y compruebe que el dominio se haya creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="015d6-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="015d6-145">Inicie sesión en el servidor CMS o de mediación y compruebe que en la NIC de la red corporativa se ha asignado una dirección IP válida y que la dirección IP estática válida y el DNS están configurados como la dirección IP del servidor de AD.</span><span class="sxs-lookup"><span data-stu-id="015d6-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="015d6-146">Inicie sesión en el servidor CMS o de mediación y abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="015d6-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="015d6-147">Asegúrese de que puede hacer ping en el FQDN y la dirección IP del servidor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="015d6-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="015d6-148">Si no puede, es posible que haya un conflicto de direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="015d6-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="015d6-149">Intente asignar una nueva IP para Active Directory y actualice DNS en el servidor CMS o de mediación en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="015d6-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="015d6-150">**Problema: recibe el mensaje de error siguiente: "Remove-VMSwitch: error al quitar el conmutador Ethernet virtual. El conmutador virtual "conmutador de administración del conector de nube" no se puede eliminar porque lo están usando máquinas virtuales en ejecución o se han asignado a grupos secundarios ".**</span><span class="sxs-lookup"><span data-stu-id="015d6-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="015d6-151">**Solución:** El "conmutador de administración del conector de nube" no se eliminó tras la implementación.</span><span class="sxs-lookup"><span data-stu-id="015d6-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="015d6-152">Si ha encontrado este error, vaya a administrador de Hyper-v y compruebe que aún no hay una máquina virtual todavía conectada a ella.</span><span class="sxs-lookup"><span data-stu-id="015d6-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="015d6-153">Si hay máquinas virtuales todavía conectadas, elimínelas y elimine el conmutador de administración.</span><span class="sxs-lookup"><span data-stu-id="015d6-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="015d6-154">Si sigue sin poder eliminar el conmutador de administración, reinicie el servidor host y vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="015d6-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="015d6-155">**Problema: recibe el mensaje de error siguiente: "no se pudo iniciar el servicio RTCMRAUTH. Asegúrese de que el servicio no está deshabilitado. "**</span><span class="sxs-lookup"><span data-stu-id="015d6-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="015d6-156">Este problema solo se aplica a las versiones de Cloud Connector anteriores a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="015d6-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="015d6-157">El error de inicio también podría deberse a que el servidor front-end se conmute previamente por error (con la conmutación por error del equipo).</span><span class="sxs-lookup"><span data-stu-id="015d6-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="015d6-158">Si es así, invocar conmutación por recuperación (con conmutación por recuperación del equipo).</span><span class="sxs-lookup"><span data-stu-id="015d6-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="015d6-159">**Solución:** Este problema se produce en un servidor perimetral cuando el servidor perimetral no confía en el certificado de CA raíz o en el certificado de CA intermedio.</span><span class="sxs-lookup"><span data-stu-id="015d6-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="015d6-160">Incluso si el certificado externo se puede importar pero la cadena de certificados está dañada.</span><span class="sxs-lookup"><span data-stu-id="015d6-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="015d6-161">En esta condición, el servicio RTCMRAUTH o RTCSRV no puede iniciarse.</span><span class="sxs-lookup"><span data-stu-id="015d6-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="015d6-162">Importe manualmente el certificado de CA raíz y todos los certificados de CA intermedios del certificado externo en el servidor perimetral y, a continuación, reinicie el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="015d6-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="015d6-163">Después de ver los servicios RTCMRAUTH y RTCSRV iniciados en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:</span><span class="sxs-lookup"><span data-stu-id="015d6-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="015d6-164">**Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows y las llamadas a las que presta servicio el servidor están fallando.**</span><span class="sxs-lookup"><span data-stu-id="015d6-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="015d6-165">**Solución:** Si ha implementado un entorno de alta disponibilidad, Microsoft proporciona un cmdlet para ayudar a mover un equipo host (instancia de implementación) hacia dentro o fuera de la topología actual al comprobar e instalar manualmente Windows Update.</span><span class="sxs-lookup"><span data-stu-id="015d6-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="015d6-166">Siga estos pasos para hacerlo:</span><span class="sxs-lookup"><span data-stu-id="015d6-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="015d6-167">En el servidor host, inicie una consola de PowerShell como administrador y, a continuación, ejecute:</span><span class="sxs-lookup"><span data-stu-id="015d6-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="015d6-168">Compruebe si hay actualizaciones e instale las que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="015d6-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="015d6-169">En la consola de PowerShell, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="015d6-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="015d6-170">**Problema: cuando se realiza una llamada desde un cliente de Skype empresarial con un número de RTC, la llamada no se puede escalar a una conferencia invitando a otro número de RTC.**</span><span class="sxs-lookup"><span data-stu-id="015d6-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="015d6-171">**Solución:** Para resolver este problema, vea [Configure online Hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="015d6-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="015d6-172">**Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar el servidor de Active Directory: "la actualización automática de Windows no está habilitada. Para asegurarse de que el rol o la característica recién instalados se actualizan automáticamente, Active Windows Update.**</span><span class="sxs-lookup"><span data-stu-id="015d6-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="015d6-173">**Solución:** Inicie una sesión remota de PowerShell de inquilino con credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ del sitio:</span><span class="sxs-lookup"><span data-stu-id="015d6-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="015d6-174">Si  _EnableAutoUpdate_ se establece en **true**, puede pasar por alto este mensaje de advertencia sin ningún problema porque el servicio CCEManagement va a controlar la descarga e instalación de las actualizaciones de Windows tanto para las máquinas virtuales como para el servidor host.</span><span class="sxs-lookup"><span data-stu-id="015d6-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="015d6-175">Si  _EnableAutoUpdate_ se establece en **false**, ejecute el siguiente cmdlet para establecerlo en **true**.</span><span class="sxs-lookup"><span data-stu-id="015d6-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="015d6-176">Como alternativa, puede buscar e instalar actualizaciones manualmente.</span><span class="sxs-lookup"><span data-stu-id="015d6-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="015d6-177">Vea la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="015d6-177">See the next section.</span></span>
    
- <span data-ttu-id="015d6-178">**Problema: recibe un mensaje de error: no se puede registrar el dispositivo porque la entrada o configuración actual, o o \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> conflictos con los dispositivos existentes. Quitar el dispositivo de conflicto o actualizar la información de entrada o configuración y volver a registrarse. ' cuando se ejecute Register-CcAppliance para registrar el dispositivo actual en línea.**</span><span class="sxs-lookup"><span data-stu-id="015d6-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="015d6-179">**Solución:** Los valores para \<ApplianceName\> el \<Mediation Server FQDN\> y \<Mediation Server IP Address\> deben ser únicos y solo se usan para el registro de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="015d6-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="015d6-180">De forma predeterminada, \<ApplianceName\> procede del nombre de host.</span><span class="sxs-lookup"><span data-stu-id="015d6-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="015d6-181">\<Mediation Server FQDN\> y se \<Mediation Server IP Address\> define en el archivo ini de configuración.</span><span class="sxs-lookup"><span data-stu-id="015d6-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="015d6-182">Por ejemplo, usar (ApplianceName = MyserverNew, Mediation Server FQDN = ms. contoso. com, Mediation Server IP address = 10.10.10.10) para registrarse en SiteName =, pero si hay un dispositivo registrado (ApplianceName = mi servidor, Mediation Server FQDN = ms. contoso. com, Mediation Server address = 10.10.10.10), tendrá el conflicto.</span><span class="sxs-lookup"><span data-stu-id="015d6-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="015d6-183">En primer lugar, consulte el archivo de CloudConnector.ini en la sección directorio de ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="015d6-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="015d6-184">Obtendrá \<SiteName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> los valores y los valores del archivo.</span><span class="sxs-lookup"><span data-stu-id="015d6-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="015d6-185">\<ApplianceName\> es el nombre del servidor host.</span><span class="sxs-lookup"><span data-stu-id="015d6-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="015d6-186">Segundo, inicie el PowerShell remoto del inquilino con sus credenciales de administrador de inquilinos de Skype empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar los dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="015d6-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="015d6-187">Después de identificar los conflictos, puede actualizar el archivo de CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.</span><span class="sxs-lookup"><span data-stu-id="015d6-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="015d6-188">**Problema: el cmdlet Get-CcRunningVersion devuelve un valor vacío si hay un dispositivo implementado en ejecución en el host.**</span><span class="sxs-lookup"><span data-stu-id="015d6-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="015d6-189">**Solución:** Esto puede ocurrir cuando se actualiza de 1.3.4 o de 1.3.8 a 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="015d6-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="015d6-190">Después de instalar la versión 1.4.1 con el. msi, debe ejecutar `Register-CcAppliance` antes de ejecutar cualquier otro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="015d6-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="015d6-191">`Register-CcAppliance` migrará el archivo de module.ini de%UserProfile%\CloudConnector a%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="015d6-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="015d6-192">Si se perdió, se creará una nueva module.ini en la carpeta%ProgramData%\CloudConnector y se reemplazará la información de la versión de ejecución/copia de seguridad para 1.3.4 o 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="015d6-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="015d6-193">Compare module.ini archivos de la carpeta%UserProfile%\CloudConnector y%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="015d6-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="015d6-194">Si hay diferencias, elimine el archivo module.ini en%ProgramData%\CloudConnector y vuelva a ejecutar  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="015d6-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="015d6-195">También puede modificar el archivo manualmente a la versión correcta de ejecución y copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="015d6-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="015d6-196">**Problema: después de ejecutar el cmdlet switch-CcVersion para cambiar a una versión anterior que sea diferente de la versión de script actual, no hay compatibilidad de alta disponibilidad para esta versión anterior.**</span><span class="sxs-lookup"><span data-stu-id="015d6-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="015d6-197">**Solución:** Por ejemplo, ha actualizado de 1.4.1 a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="015d6-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="015d6-198">La versión de script actual, que se puede determinar mediante `Get-CcVersion` la ejecución, y la versión en ejecución, que se puede determinar mediante la ejecución,  `Get-CcRunningVersion` son las dos 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="015d6-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="015d6-199">En este momento, si ejecuta `Switch-CcVersion` para cambiar la versión en marcha a la versión 1.4.1, no habrá compatibilidad con alta disponibilidad para esta versión anterior.</span><span class="sxs-lookup"><span data-stu-id="015d6-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="015d6-200">Para obtener compatibilidad total con alta disponibilidad, vuelva a 1.4.2, de modo que la versión en ejecución y la versión de script sean las mismas.</span><span class="sxs-lookup"><span data-stu-id="015d6-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="015d6-201">Si tiene problemas con la implementación de 1.4.2, desinstálelo y vuelva a instalarlo tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="015d6-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="015d6-202">**Problema: los certificados de la entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**</span><span class="sxs-lookup"><span data-stu-id="015d6-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="015d6-203">**Solución:** Los certificados de la entidad de certificación de Skype empresarial son válidos durante cinco años.</span><span class="sxs-lookup"><span data-stu-id="015d6-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="015d6-204">Los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral son válidos durante dos años.</span><span class="sxs-lookup"><span data-stu-id="015d6-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="015d6-205">En la versión 2,0 de Cloud Connector y versiones posteriores, el cmdlet Renew-CcServerCertificate ha cambiado a Update-CcServerCertificate y el cmdlet Renew-CcCACertificate ha cambiado a Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="015d6-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="015d6-206">Si los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro, ejecute el cmdlet Renew-CcServerCertificate o Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="015d6-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="015d6-207">Si los certificados de la entidad de certificación están a punto de expirar, ejecute el cmdlet Renew-CcCACertificate o Update-CcCACertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="015d6-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="015d6-208">**Si los certificados de la entidad de certificación están en peligro y solo hay un dispositivo en el sitio, lleve a** cabo los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="015d6-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="015d6-209">Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner el dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="015d6-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="015d6-210">Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:</span><span class="sxs-lookup"><span data-stu-id="015d6-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="015d6-211">Para las versiones de Cloud Connector antes del 2,0:</span><span class="sxs-lookup"><span data-stu-id="015d6-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="015d6-212">O para Cloud Connector Release 2,0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="015d6-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="015d6-213">Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado en sus puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="015d6-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="015d6-214">Es posible que también deba volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="015d6-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="015d6-215">Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="015d6-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="015d6-216">**Si los certificados de la entidad de certificación están en peligro y hay varios dispositivos en el sitio,** lleve a cabo los siguientes pasos secuenciales en cada dispositivo del sitio.</span><span class="sxs-lookup"><span data-stu-id="015d6-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="015d6-217">Microsoft recomienda que realice estos pasos durante los períodos de uso no máximos.</span><span class="sxs-lookup"><span data-stu-id="015d6-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="015d6-218">En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar los archivos de copia de seguridad de la entidad de certificación en el \<SiteRoot\> directorio.</span><span class="sxs-lookup"><span data-stu-id="015d6-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="015d6-219">Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner cada dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="015d6-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="015d6-220">En el primer dispositivo, ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:</span><span class="sxs-lookup"><span data-stu-id="015d6-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="015d6-221">Para las versiones de Cloud Connector antes del 2,0:</span><span class="sxs-lookup"><span data-stu-id="015d6-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="015d6-222">O para Cloud Connector Release 2,0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="015d6-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="015d6-223">En el primer dispositivo, ejecute el siguiente cmdlet para realizar una copia de seguridad de los archivos de la entidad de certificación en la \<SiteRoot\> carpeta.</span><span class="sxs-lookup"><span data-stu-id="015d6-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="015d6-224">En el resto de los dispositivos del mismo sitio, ejecute los comandos siguientes para consumir los archivos de copia de seguridad de la entidad de certificación, de modo que todos los dispositivos usen el mismo certificado raíz y, a continuación, solicite nuevos certificados.</span><span class="sxs-lookup"><span data-stu-id="015d6-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="015d6-225">Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo del sitio y, a continuación, instale el certificado exportado en sus puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="015d6-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="015d6-226">Es posible que también deba volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="015d6-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="015d6-227">Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="015d6-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="015d6-228">**Problema: recibe el siguiente mensaje de error en el registro del servicio de administración de Cloud Connector, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService error: 0: excepción inesperada al notificar el estado a en línea: System. Management. Automation. CmdletInvocationException: error de inicio de sesión para el usuario \<Global Tenant Admin\> . Cree un nuevo objeto Credential, asegurándose de que ha usado el nombre de usuario y la contraseña correctos. ---\>**</span><span class="sxs-lookup"><span data-stu-id="015d6-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="015d6-229">**Solución:** Se han cambiado las credenciales globales de administrador de inquilinos de Microsoft 365 u Office 365 desde que se registró el dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="015d6-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="015d6-230">Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, ejecute lo siguiente desde el administrador de PowerShell en el dispositivo de host:</span><span class="sxs-lookup"><span data-stu-id="015d6-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="015d6-231">**Problema: después de cambiar la contraseña de la cuenta del servidor host usada para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString: clave no válida para usarla en el estado especificado" en%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o mientras ejecutamos el cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="015d6-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="015d6-232">**Solución:** Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="015d6-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="015d6-233">Cuando cambie la contraseña en el servidor host, tendrá que actualizar las credenciales almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="015d6-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="015d6-234">**Si ejecuta la versión 1.4.2 de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector; para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="015d6-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="015d6-235">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="015d6-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="015d6-236">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="015d6-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="015d6-237">Inicie una consola de PowerShell como administrador y, después, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas después de la descripción.</span><span class="sxs-lookup"><span data-stu-id="015d6-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="015d6-238">Escriba las mismas contraseñas que especificó antes para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="015d6-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="015d6-239">**Si ejecuta la versión 2,0 o posterior de Cloud Connector,** vuelva a generar todas las contraseñas de Cloud Connector; para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="015d6-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="015d6-240">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="015d6-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="015d6-241">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="015d6-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="015d6-242">Inicie una consola de PowerShell como administrador y, después, ejecute "Register-CcAppliance-local" para volver a escribir las contraseñas después de la descripción.</span><span class="sxs-lookup"><span data-stu-id="015d6-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="015d6-243">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector, use la contraseña VMAdmin para la contraseña CceService cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="015d6-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="015d6-244">Escriba la misma contraseña que escribió antes para la implementación de Cloud Connector en todas las demás cuentas.</span><span class="sxs-lookup"><span data-stu-id="015d6-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="015d6-245">Si el archivo de contraseñas almacenadas en caché se generó con la versión 1.4.2 de Cloud Connector y las contraseñas del usuario e VMAdmin son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="015d6-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="015d6-246">Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="015d6-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="015d6-247">Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="015d6-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="015d6-248">Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña para la contraseña de la cuenta de usuario que usó antes.</span><span class="sxs-lookup"><span data-stu-id="015d6-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="015d6-249">Si el archivo de contraseñas almacenadas en caché se generó con la versión 2,0 de Cloud Connector o una versión posterior, de forma predeterminada, VmAdmin y el ID detor usan la misma contraseña que CceService.</span><span class="sxs-lookup"><span data-stu-id="015d6-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="015d6-250">Si ha cambiado las contraseñas del usuario y el VMAdmin, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="015d6-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="015d6-251">Ejecute Set-CcCredential-AccountType preestablecido de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="015d6-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="015d6-252">Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService</span><span class="sxs-lookup"><span data-stu-id="015d6-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="015d6-253">Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña para la contraseña de la cuenta de usuario que usó antes.</span><span class="sxs-lookup"><span data-stu-id="015d6-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="015d6-254">Ejecute Set-CcCredential-AccountType VmAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="015d6-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="015d6-255">Cuando se le pida la antigua credencial de cuenta, escriba la credencial que usó para la contraseña de CceService</span><span class="sxs-lookup"><span data-stu-id="015d6-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="015d6-256">Cuando se le soliciten las credenciales de cuenta nuevas, escriba la contraseña para la contraseña de VmAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="015d6-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="015d6-257">**Problema: con Cloud Connector versión 2,1 y posteriores, cuando se ejecuta Register-CcAppliance u otros cmdlets en el dispositivo, recibe un mensaje de error como: "para cada objeto: no se encuentra la propiedad ' Common ' en este objeto. Compruebe que la propiedad existe. En C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="015d6-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="015d6-258">**Solución:** Cloud Connector 2,1 y versiones posteriores requieren .NET Framework 4.6.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="015d6-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="015d6-259">Actualice .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="015d6-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="015d6-260">**Problema: con Cloud Connector Edition 2,1, cuando se ejecuta install-CcAppliance, recibe un mensaje de error como el siguiente: "error al instalar una nueva instancia con error: no se puede establecer" State "porque solo se pueden usar cadenas como valores para establecer las propiedades de XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="015d6-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="015d6-261">**Solución:** En Cloudconnector.ini, en la sección [común], agregue el config "State" como sigue: CountryCode = US State = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="015d6-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="015d6-262">No es obligatorio que la línea "State" tenga valor, pero la línea "State" no se puede quitar del archivo de Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="015d6-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="015d6-263">**Problema: recibe el siguiente mensaje de error "Dismount-WindowsImage: Dismount-WindowsImage failed. Código de error = 0xc1550115 "al instalar o actualizar Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="015d6-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="015d6-264">**Solución:** Inicie una consola de PowerShell como administrador, ejecute "DISM-Cleanup-Wim" ".</span><span class="sxs-lookup"><span data-stu-id="015d6-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="015d6-265">Esto hará que se limpien todas las imágenes con problemas.</span><span class="sxs-lookup"><span data-stu-id="015d6-265">This will clean up all troubled images.</span></span> <span data-ttu-id="015d6-266">Vuelva a ejecutar install-CcAppliance o espere a que los bits se actualicen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="015d6-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="015d6-267">**Problema: se produce un error en la implementación del primer dispositivo de Cloud Connector en un entorno de alta disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="015d6-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="015d6-268">**Solución:** Los pasos que debe seguir dependen de la razón por la que se produjo el error en la implementación:</span><span class="sxs-lookup"><span data-stu-id="015d6-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="015d6-269">Si se produce un error en el primer dispositivo de Cloud Connector y no puede determinar el motivo del error, debe instalar el dispositivo de nuevo hasta que la implementación se haya realizado correctamente y, a continuación, instalar el resto de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="015d6-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="015d6-270">Si se produce un error leve en el primer dispositivo de Cloud Connector, como un problema de certificado externo, es posible que pueda solucionar el problema sin volver a instalar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="015d6-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="015d6-271">A continuación, puede usar PowerShell remoto de inquilino para marcar la implementación como correcta de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="015d6-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="015d6-272">(También puede seguir estos pasos si la primera implementación se realizó correctamente, pero, por algún motivo, Cloud Connector no puede informar de la implementación como correcta).</span><span class="sxs-lookup"><span data-stu-id="015d6-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="015d6-273">Para obtener la identidad (GUID) del primer dispositivo de Cloud Connector, ejecute el cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="015d6-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="015d6-274">Para marcar el dispositivo como implementado correctamente, ejecute Set-CsCceApplianceDeploymentStatus de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="015d6-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="015d6-275">**Problema: debe comprobar e instalar las actualizaciones de Windows de forma manual en el servidor host o las máquinas virtuales.**</span><span class="sxs-lookup"><span data-stu-id="015d6-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="015d6-276">**Solución:** Le recomendamos que aproveche las ventajas de las actualizaciones del sistema operativo automatizado que proporciona Skype empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="015d6-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="015d6-277">Una vez que se ha registrado un dispositivo para la administración en línea y la actualización automática del sistema operativo está habilitada, el servidor host y las máquinas virtuales comprobarán e instalarán automáticamente las actualizaciones de Windows según la configuración de la ventana de tiempo de actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="015d6-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="015d6-278">Si necesita buscar e instalar actualizaciones de Windows manualmente, siga los pasos de esta sección que se aplican a su tipo de implementación.</span><span class="sxs-lookup"><span data-stu-id="015d6-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="015d6-279">Debe planear la actualización del servidor host y de las máquinas virtuales que se ejecutan al mismo tiempo para minimizar la cantidad de tiempo de inactividad necesario para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="015d6-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="015d6-280">Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones a los servidores de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="015d6-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="015d6-281">Solo Asegúrese de configurar la actualización de Windows para que **no** se instale automáticamente.</span><span class="sxs-lookup"><span data-stu-id="015d6-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="015d6-282">Para obtener información sobre cómo actualizar manualmente la implementación de Cloud Connector, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="015d6-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="015d6-283">**Problema: cuando Cloud Connector se actualiza a una nueva compilación, los cmdlets de Cloud Connector no se actualizan.**</span><span class="sxs-lookup"><span data-stu-id="015d6-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="015d6-284">Esto ocurre a veces si se deja abierta una ventana de PowerShell cuando se produce la actualización automática.</span><span class="sxs-lookup"><span data-stu-id="015d6-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="015d6-285">**Solución:** Para cargar los cmdlets actualizados, puede realizar cualquiera de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="015d6-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="015d6-286">Cierre PowerShell en el dispositivo de Cloud Connector y, a continuación, vuelva a abrir PowerShell.</span><span class="sxs-lookup"><span data-stu-id="015d6-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="015d6-287">O bien, puede ejecutar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="015d6-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="015d6-288">**Problema: "el término ' Stop-CsWindowsService ' no se reconoce como nombre de un cmdlet, función, archivo de script o programa ejecutable". error al intentar ejecutar el cmdlet Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="015d6-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="015d6-289">**Solución:** Elimine el archivo $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="015d6-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="015d6-290">PowerShell crea este archivo como una memoria caché de cmdlets a partir de los módulos que encuentra para que no tenga que volver a analizar todos los módulos cada vez, ya que esto haría que las cosas se ralentizarían realmente.</span><span class="sxs-lookup"><span data-stu-id="015d6-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="015d6-291">Lo más probable es que haya daños en los archivos que hayan proporcionado resultados engañosos a PowerShell cuando se leían de nuevo desde esa memoria caché.</span><span class="sxs-lookup"><span data-stu-id="015d6-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="015d6-292">**Problema: "Import-Module CloudConnector" genera el error "Import-Module: el módulo especificado" CloudConnector "no se cargó porque no se encontró ningún archivo de módulo válido en ningún directorio de módulo"**</span><span class="sxs-lookup"><span data-stu-id="015d6-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="015d6-293">**Resolución:**</span><span class="sxs-lookup"><span data-stu-id="015d6-293">**Resolution:**</span></span>
    - <span data-ttu-id="015d6-294">Compruebe que el módulo CloudConnector existe en c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="015d6-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="015d6-295">Después de comprobar que el módulo CloudConnector existe en esta ubicación, se puede cambiar la variable de entorno PSModulePath que almacena la ruta de acceso a las ubicaciones de los módulos:</span><span class="sxs-lookup"><span data-stu-id="015d6-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="015d6-296">a.</span><span class="sxs-lookup"><span data-stu-id="015d6-296">a.</span></span> <span data-ttu-id="015d6-297">Cambio temporal: inicie PowerShell como administrador y ejecute el comando siguiente: $env:P SModulePath = $env:P SModulePath + "; C:\Archivos de Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="015d6-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="015d6-298">b.</span><span class="sxs-lookup"><span data-stu-id="015d6-298">b.</span></span> <span data-ttu-id="015d6-299">Para el cambio persistente, inicie PowerShell como administrador y ejecute los siguientes comandos, uno por uno: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Archivos de Files\WindowsPowerShell\Modules "," equipo ")</span><span class="sxs-lookup"><span data-stu-id="015d6-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="015d6-300">Instalar actualizaciones de Windows de forma manual</span><span class="sxs-lookup"><span data-stu-id="015d6-300">Install Windows updates manually</span></span>

<span data-ttu-id="015d6-301">Si no desea usar actualizaciones automáticas en su entorno, siga estos pasos para buscar y aplicar manualmente las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="015d6-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="015d6-302">La comprobación e instalación de actualizaciones de Windows puede requerir el reinicio del servidor.</span><span class="sxs-lookup"><span data-stu-id="015d6-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="015d6-303">Cuando se reinicia un servidor host, los usuarios no podrán usar Cloud Connector para realizar o recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="015d6-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="015d6-304">Puede buscar e instalar actualizaciones manualmente para controlar cuándo se realizan las actualizaciones y, a continuación, reiniciar los equipos según sea necesario durante las horas que elija para evitar interrupciones en los servicios.</span><span class="sxs-lookup"><span data-stu-id="015d6-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="015d6-305">Para comprobar manualmente si hay actualizaciones, conéctese a cada servidor host y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="015d6-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="015d6-306">Seleccione \*\* \> Windows Update System and Security\*\*y, a continuación, administre las actualizaciones y los reinicios de servidor según corresponda para su entorno.</span><span class="sxs-lookup"><span data-stu-id="015d6-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="015d6-307">Si solo hay un dispositivo en el sitio, conéctese a cada máquina virtual y abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="015d6-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="015d6-308">Seleccione \*\* \> Windows Update System and Security\*\*y, a continuación, configure las actualizaciones y los reinicios de servidor según corresponda.</span><span class="sxs-lookup"><span data-stu-id="015d6-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="015d6-309">Si hay más de un dispositivo en el sitio, los usuarios no pueden acceder a la instancia que se actualiza y reinicia durante las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="015d6-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="015d6-310">Los usuarios se conectarán a otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype empresarial se inicien en las máquinas virtuales después de que se hayan completado las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="015d6-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="015d6-311">Para evitar cualquier posible interrupción del servicio, puede quitar la instancia de HA al aplicar las actualizaciones y, a continuación, restaurarla cuando haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="015d6-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="015d6-312">Para ello:</span><span class="sxs-lookup"><span data-stu-id="015d6-312">To do so:</span></span>
    
1. <span data-ttu-id="015d6-313">En cada servidor host, abra una consola de PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="015d6-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="015d6-314">Quite la instancia de HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="015d6-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="015d6-315">Siga los pasos para una única instancia para aplicar manualmente las actualizaciones y reiniciar la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="015d6-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="015d6-316">Vuelva a establecer la instancia en HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="015d6-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="015d6-317">Para implementaciones de varios sitios, siga los pasos para un sitio único para cada sitio de la implementación y aplique las actualizaciones a un sitio cada vez.</span><span class="sxs-lookup"><span data-stu-id="015d6-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="015d6-318">Sugerencias al instalar software antivirus en el equipo host de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="015d6-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="015d6-319">Si necesita instalar software antivirus en el equipo host de Cloud Connector, debe agregar las siguientes exclusiones:</span><span class="sxs-lookup"><span data-stu-id="015d6-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="015d6-320">Directorio local de la aplicación en cada máquina.</span><span class="sxs-lookup"><span data-stu-id="015d6-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="015d6-321">Directorio de sitios remotos en cada máquina.</span><span class="sxs-lookup"><span data-stu-id="015d6-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="015d6-322">Directorio de sitios local en el equipo hospeda la carpeta raíz del sitio compartido.</span><span class="sxs-lookup"><span data-stu-id="015d6-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="015d6-323">%ProgramFiles%\Skype para Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="015d6-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="015d6-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="015d6-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="015d6-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="015d6-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="015d6-326">El proceso Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="015d6-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
