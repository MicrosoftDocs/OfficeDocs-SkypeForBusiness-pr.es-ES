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
description: Solucione los problemas de la implementación de Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359336"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="0773e-103">Solución de problemas con la implementación de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="0773e-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="0773e-104">Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="0773e-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="0773e-105">Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [el enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="0773e-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="0773e-106">Solucione los problemas de la implementación de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0773e-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="0773e-107">En este tema se describen soluciones a problemas comunes con las implementaciones de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0773e-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="0773e-108">Si tiene problemas con las llamadas a y desde la red telefónica conmutada (RTC), puede investigar siguiendo las soluciones descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="0773e-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="0773e-109">Cloud Connector proporciona mecanismos integrados para resolver automáticamente algunos problemas.</span><span class="sxs-lookup"><span data-stu-id="0773e-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="0773e-110">Un proceso de detección automática busca posibles problemas con los dispositivos de Cloud Connector y, si es posible, toma medidas correctivas para resolver esos problemas sin necesidad de la intervención del administrador.</span><span class="sxs-lookup"><span data-stu-id="0773e-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="0773e-111">El proceso de detección funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0773e-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="0773e-112">**Secuencia de detección:** El servicio de administración de Cloud Connector ejecuta un proceso cada 60 segundos para detectar si un dispositivo está abajo.</span><span class="sxs-lookup"><span data-stu-id="0773e-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="0773e-113">En Cloud Connector versión 2.0 y versiones posteriores, el proceso de detección usa el conmutador corpnet de Skype Empresarial para realizar conexiones de PowerShell a las máquinas de Cloud Connector; para versiones anteriores a 2.0, el proceso de detección usa el conmutador de administración de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0773e-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0773e-114">Para que la recuperación automática se pueda realizar correctamente, debe haber conectividad de red entre el host y las máquinas virtuales a través del conmutador de red host.</span><span class="sxs-lookup"><span data-stu-id="0773e-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="0773e-115">Asegúrese de comprobar la conectividad de red para asegurarse de que la detección y recuperación automáticas puedan ser correctas.</span><span class="sxs-lookup"><span data-stu-id="0773e-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="0773e-116">**Supervisión:** Los siguientes servicios se supervisan en Cloud Connector versión 2.0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="0773e-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="0773e-117">Las máquinas virtuales no están conectadas a los conmutadores virtuales corporativos o de Internet de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="0773e-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="0773e-118">Las máquinas virtuales están en un estado guardado o detenido</span><span class="sxs-lookup"><span data-stu-id="0773e-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="0773e-119">Servicios del servidor de administración central: REPLICA, MASTER</span><span class="sxs-lookup"><span data-stu-id="0773e-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="0773e-120">Servicios del servidor de mediación: REPLICA, RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="0773e-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="0773e-121">Servicios del servidor perimetral: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="0773e-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="0773e-122">Las reglas de firewall de entrada están deshabilitadas para RTCSRV de CS en el servidor perimetral, RTCMEDSRV de CS en el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="0773e-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="0773e-123">En Cloud Connector versión 1.4.2, solo se supervisan los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="0773e-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="0773e-124">Servicios del servidor de mediación: RTCSRV y MEDSVC</span><span class="sxs-lookup"><span data-stu-id="0773e-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="0773e-125">Servicio de servidor perimetral: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="0773e-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="0773e-126">**Proceso de recuperación:** Si alguno de los servicios supervisados no está disponible, se marca un dispositivo y los servicios se detienen y se marcan manualmente hasta que se pueden resolver todos los problemas.</span><span class="sxs-lookup"><span data-stu-id="0773e-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="0773e-127">Esto impedirá que las llamadas se enrutar a un dispositivo que pueda causar errores de llamada.</span><span class="sxs-lookup"><span data-stu-id="0773e-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="0773e-128">El servicio de administración de Cloud Connector reintentará la recuperación automática de la siguiente manera</span><span class="sxs-lookup"><span data-stu-id="0773e-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="0773e-129">El intervalo de reintento inicial es cada diez segundos con un intervalo máximo de una hora.</span><span class="sxs-lookup"><span data-stu-id="0773e-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="0773e-130">Para los tres primeros intentos de recuperación, el tiempo de intervalo es de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="0773e-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="0773e-131">A partir del cuarto reintento, el tiempo de intervalo aumenta dos veces el tiempo del intervalo anterior.</span><span class="sxs-lookup"><span data-stu-id="0773e-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="0773e-132">Por ejemplo, el cuarto reintento se producirá en 20 segundos, el quinto en 40 segundos, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="0773e-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="0773e-133">Cuando se alcanza el intervalo máximo de una hora, los reintentos continuarán una vez por hora.</span><span class="sxs-lookup"><span data-stu-id="0773e-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="0773e-134">Cuando la recuperación se realiza correctamente, el intervalo y los recuentos de reintentos se establecen en sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="0773e-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="0773e-135">Si se reinicia el servicio de administración, el intervalo y los recuentos de reintentos se restablecen a sus valores iniciales.</span><span class="sxs-lookup"><span data-stu-id="0773e-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="0773e-136">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="0773e-136">Troubleshooting</span></span>

<span data-ttu-id="0773e-137">A continuación se ofrecen soluciones a los problemas que se encuentran habitualmente:</span><span class="sxs-lookup"><span data-stu-id="0773e-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="0773e-138">**Problema: la implementación produce un error o deja de responder al ejecutar los scripts de implementación. Después de iniciar sesión en cada máquina virtual, falta la dirección IP o es incorrecta para la NIC de administración/interna/externa.**</span><span class="sxs-lookup"><span data-stu-id="0773e-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="0773e-139">**Solución:** Este problema no se puede resolver automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0773e-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="0773e-140">Las NIC no se pueden agregar a las máquinas virtuales mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="0773e-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="0773e-141">Cierre y quite estas máquinas virtuales en el administrador de hyper-v y, a continuación, ejecute los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="0773e-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="0773e-142">**Problema: después de instalar el servidor de Active Directory y el bosque, el servidor CMS o el servidor de mediación no se unieron al dominio correctamente.**</span><span class="sxs-lookup"><span data-stu-id="0773e-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="0773e-143">**Solución:** Para resolver este problema, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="0773e-144">Inicie sesión en el servidor de Active Directory y compruebe que el dominio se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0773e-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="0773e-145">Inicie sesión en el servidor cms/de mediación y compruebe que en la NIC de la red corpnet se haya asignado una dirección IP válida y que el DNS y la IP estática válidos estén configurados como la dirección IP del servidor de AD.</span><span class="sxs-lookup"><span data-stu-id="0773e-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="0773e-146">Inicie sesión en el servidor CMS/Mediation y abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0773e-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="0773e-147">Asegúrese de que puede hacer ping al FQDN y la dirección IP del servidor de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0773e-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="0773e-148">Si no puede, puede haber un conflicto de direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="0773e-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="0773e-149">Intente asignar una nueva DIRECCIÓN IP para Active Directory y actualice DNS en el servidor CMS/Mediation según corresponda.</span><span class="sxs-lookup"><span data-stu-id="0773e-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="0773e-150">**Problema: Recibe el siguiente mensaje de error: "Remove-VMSwitch : Failed while removing virtual Ethernet switch. El conmutador virtual "Conmutador de administración de Cloud Connector" no se puede eliminar porque se usa ejecutando máquinas virtuales o se asigna a grupos de servidores secundarios".**</span><span class="sxs-lookup"><span data-stu-id="0773e-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="0773e-151">**Solución:** El "Conmutador de administración de Cloud Connector" no se eliminó después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="0773e-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="0773e-152">Si se produce este error, vaya al administrador de Hyper-v y compruebe que aún no haya una máquina virtual conectada a él.</span><span class="sxs-lookup"><span data-stu-id="0773e-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="0773e-153">Si todavía hay máquinas virtuales conectadas, desconéctelas y elimine el conmutador de administración.</span><span class="sxs-lookup"><span data-stu-id="0773e-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="0773e-154">Si el conmutador de administración aún no se puede eliminar, reinicie el servidor host e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0773e-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="0773e-155">**Problema: Recibe el siguiente mensaje de error: "No se pudo iniciar el servicio RTCMRAUTH. Compruebe que el servicio no está deshabilitado".**</span><span class="sxs-lookup"><span data-stu-id="0773e-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0773e-156">Este problema solo se aplica a las versiones de Cloud Connector anteriores a la 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0773e-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="0773e-157">El error de inicio también podría deberse a que anteriormente se conmutación por error de este servidor front-end (mediante la conmutación por error del equipo).</span><span class="sxs-lookup"><span data-stu-id="0773e-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="0773e-158">Si ese es el caso, invoque la conmutación por recuperación (con la conmutación por recuperación del equipo).</span><span class="sxs-lookup"><span data-stu-id="0773e-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="0773e-159">**Solución:** Este problema se produce en un servidor perimetral cuando el servidor perimetral no confía en el certificado de ca raíz o en el certificado de ca intermedia.</span><span class="sxs-lookup"><span data-stu-id="0773e-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="0773e-160">Incluso si se puede importar el certificado externo, pero la cadena de certificados está rota.</span><span class="sxs-lookup"><span data-stu-id="0773e-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="0773e-161">En esta condición, el servicio RTCMRAUTH o RTCSRV no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="0773e-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="0773e-162">Importe manualmente el certificado de ca raíz y todos los certificados de CA intermedias del certificado externo en el servidor perimetral y, a continuación, reinicie el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0773e-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="0773e-163">Cuando vea los servicios RTCMRAUTH y RTCSRV iniciados en el servidor perimetral, vuelva al servidor host, inicie una consola de PowerShell como administrador y ejecute el siguiente cmdlet para cambiar a la nueva implementación:</span><span class="sxs-lookup"><span data-stu-id="0773e-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="0773e-164">**Problema: el servidor host se reinició cuando se aplicaron las actualizaciones de Windows y se han fallado las llamadas a las que presta servicio el servidor.**</span><span class="sxs-lookup"><span data-stu-id="0773e-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="0773e-165">**Solución:** Si implementó un entorno de alta disponibilidad, Microsoft proporciona un cmdlet para ayudar a mover una máquina host (instancia de implementación) dentro o fuera de la topología actual al comprobar e instalar la actualización de Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="0773e-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="0773e-166">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="0773e-167">En el servidor host, inicie una consola de PowerShell como administrador y, a continuación, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0773e-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="0773e-168">Compruebe si hay actualizaciones e instale las que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="0773e-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="0773e-169">En la consola de PowerShell, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0773e-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="0773e-170">**Problema: cuando se realiza una llamada desde un cliente de Skype Empresarial mediante un número RTC, la llamada no se puede escalar a una conferencia invitando a otro número RTC.**</span><span class="sxs-lookup"><span data-stu-id="0773e-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="0773e-171">**Solución:** Para resolver este problema, consulte [Configuración del servidor de mediación híbrido en línea.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)</span><span class="sxs-lookup"><span data-stu-id="0773e-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="0773e-172">**Problema: se muestra un mensaje de advertencia sobre Windows Update al instalar el servidor de Active Directory: "La actualización automática de Windows no está habilitada. Para asegurarte de que tu función o característica recién instalada se actualice automáticamente, activa Windows Update".**</span><span class="sxs-lookup"><span data-stu-id="0773e-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="0773e-173">**Solución:** Inicie una sesión de PowerShell remoto de inquilino con credenciales de administrador de inquilinos de Skype Empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar la configuración de _EnableAutoUpdate_ de su sitio:</span><span class="sxs-lookup"><span data-stu-id="0773e-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="0773e-174">Si  _EnableAutoUpdate_ está establecido en **True,** puede omitir este mensaje de advertencia de forma segura porque el servicio CCEManagement controlará la descarga e instalación de actualizaciones de Windows para las máquinas virtuales y el servidor host.</span><span class="sxs-lookup"><span data-stu-id="0773e-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="0773e-175">Si  _EnableAutoUpdate está_ establecido en **False**, ejecute el siguiente cmdlet para establecerlo en **True**.</span><span class="sxs-lookup"><span data-stu-id="0773e-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="0773e-176">Como alternativa, puede buscar e instalar actualizaciones manualmente.</span><span class="sxs-lookup"><span data-stu-id="0773e-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="0773e-177">Vea la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="0773e-177">See the next section.</span></span>
    
- <span data-ttu-id="0773e-178">**Problema: recibe un mensaje de error: No se puede registrar el dispositivo porque la entrada o configuración actuales o porque está en conflicto con los \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> dispositivos existentes. Quite el dispositivo en conflicto o actualice la información de entrada y configuración y vuelva a registrarse. ' when run Register-CcAppliance to register current appliance to online.**</span><span class="sxs-lookup"><span data-stu-id="0773e-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="0773e-179">**Solución:** Valores para el registro de un dispositivo y deben \<ApplianceName\> \<Mediation Server FQDN\> ser \<Mediation Server IP Address\> únicos y usarse únicamente para el registro de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0773e-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="0773e-180">De forma predeterminada, \<ApplianceName\> proviene del nombre de host.</span><span class="sxs-lookup"><span data-stu-id="0773e-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="0773e-181">\<Mediation Server FQDN\> y \<Mediation Server IP Address\> se define en el archivo ini de configuración.</span><span class="sxs-lookup"><span data-stu-id="0773e-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="0773e-182">Por ejemplo, si usa (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para registrarse en SiteName=MySite, pero si hay un dispositivo registrado (ApplianceName= Myserver, MEDIATION Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), tendrá el conflicto.</span><span class="sxs-lookup"><span data-stu-id="0773e-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="0773e-183">En primer lugar, compruebe el archivo CloudConnector.ini en la sección del directorio ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="0773e-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="0773e-184">You will get \<SiteName\> , and values in the \<Mediation Server FQDN\> \<Mediation Server IP Address\> file.</span><span class="sxs-lookup"><span data-stu-id="0773e-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="0773e-185">\<ApplianceName\> es el nombre del servidor host.</span><span class="sxs-lookup"><span data-stu-id="0773e-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="0773e-186">En segundo lugar, inicie El PowerShell remoto del inquilino con sus credenciales de administrador de inquilinos de Skype Empresarial y, a continuación, ejecute el siguiente cmdlet para comprobar los dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="0773e-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="0773e-187">Después de identificar los conflictos, puede actualizar el archivo CloudConnector.ini con información que coincida con el dispositivo registrado o anular el registro del dispositivo existente para resolver los conflictos.</span><span class="sxs-lookup"><span data-stu-id="0773e-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="0773e-188">**Problema: el cmdlet Get-CcRunningVersion devuelve un valor vacío si hay un dispositivo implementado ejecutándose en el host.**</span><span class="sxs-lookup"><span data-stu-id="0773e-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="0773e-189">**Solución:** Esto puede suceder cuando actualiza de 1.3.4 o 1.3.8 a 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="0773e-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="0773e-190">Después de instalar la versión 1.4.1 con el archivo .msi, debe ejecutar antes de `Register-CcAppliance` ejecutar cualquier otro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0773e-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="0773e-191">`Register-CcAppliance` migrará el archivo module.ini de %UserProfile%\CloudConnector a %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="0773e-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="0773e-192">Si no lo ha hecho, se creará un nuevo module.ini en la carpeta %ProgramData%\CloudConnector y se reemplazará la información de la versión de ejecución/copia de seguridad para la versión 1.3.4 o 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="0773e-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="0773e-193">Compare module.ini archivos en la carpeta %UserProfile%\CloudConnector y %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="0773e-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="0773e-194">Si hay diferencias, elimine el archivo module.ini en %ProgramData%\CloudConnector y vuelva a  `Register-CcAppliance` ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="0773e-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="0773e-195">También puede modificar el archivo manualmente a la versión correcta en ejecución y de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0773e-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="0773e-196">**Problema: después de ejecutar el cmdlet Switch-CcVersion para cambiar a una versión anterior que es diferente de la versión actual del script, no hay compatibilidad de alta disponibilidad para esta versión anterior.**</span><span class="sxs-lookup"><span data-stu-id="0773e-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="0773e-197">**Solución:** Por ejemplo, ha actualizado de 1.4.1 a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0773e-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="0773e-198">La versión actual del script, que puede determinarse mediante la ejecución, y la versión en ejecución, que se puede determinar mediante la ejecución son `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="0773e-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="0773e-199">En este momento, si ejecuta para volver a cambiar la versión en ejecución a 1.4.1, no habrá compatibilidad de alta disponibilidad para esta `Switch-CcVersion` versión anterior.</span><span class="sxs-lookup"><span data-stu-id="0773e-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="0773e-200">Para obtener compatibilidad completa con alta disponibilidad, vuelva a la versión 1.4.2, para que la versión en ejecución y la versión de script sean las mismas.</span><span class="sxs-lookup"><span data-stu-id="0773e-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="0773e-201">Si tiene problemas con la implementación 1.4.2, desinstale y vuelva a instalarla lo antes posible.</span><span class="sxs-lookup"><span data-stu-id="0773e-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="0773e-202">**Problema: los certificados de entidad de certificación o los certificados internos emitidos al almacén de administración central, al servidor de mediación y al servidor perimetral están a punto de expirar o están en peligro.**</span><span class="sxs-lookup"><span data-stu-id="0773e-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="0773e-203">**Solución:** Los certificados de entidad de certificación de Skype Empresarial son válidos durante cinco años.</span><span class="sxs-lookup"><span data-stu-id="0773e-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="0773e-204">Los certificados internos emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral son válidos durante dos años.</span><span class="sxs-lookup"><span data-stu-id="0773e-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0773e-205">En Cloud Connector versión 2.0 y versiones posteriores, el cmdlet Renew-CcServerCertificate ha cambiado a Update-CcServerCertificate y el cmdlet Renew-CcCACertificate ha cambiado a Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="0773e-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="0773e-206">Si los certificados internos emitidos para el almacén de administración central, el servidor de mediación y el servidor perimetral están a punto de expirar o están en peligro, ejecute el cmdlet Renew-CcServerCertificate o Update-CcServerCertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="0773e-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="0773e-207">Si los certificados de la entidad de certificación están a punto de expirar, ejecute el cmdlet Renew-CcCACertificate o Update-CcCACertificate para renovar los certificados.</span><span class="sxs-lookup"><span data-stu-id="0773e-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="0773e-208">**Si los certificados de la entidad de certificación están** en peligro y solo hay un dispositivo en el sitio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="0773e-209">Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner el dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0773e-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="0773e-210">Ejecute los siguientes cmdlets para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:</span><span class="sxs-lookup"><span data-stu-id="0773e-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="0773e-211">Para las versiones de Cloud Connector anteriores a 2.0:</span><span class="sxs-lookup"><span data-stu-id="0773e-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="0773e-212">O para Cloud Connector versión 2.0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="0773e-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="0773e-213">Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde el dispositivo y, a continuación, instale el certificado exportado en las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="0773e-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="0773e-214">Es posible que también deba volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="0773e-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="0773e-215">Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0773e-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="0773e-216">**Si los certificados de la entidad de certificación** están en peligro y hay varios dispositivos en el sitio, realice los siguientes pasos secuenciales en cada dispositivo del sitio.</span><span class="sxs-lookup"><span data-stu-id="0773e-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="0773e-217">Microsoft recomienda realizar estos pasos durante los períodos de uso no pico.</span><span class="sxs-lookup"><span data-stu-id="0773e-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="0773e-218">En el primer dispositivo, ejecute el cmdlet Remove-CcCertificationAuthorityFile para limpiar los archivos de copia de seguridad de ca en el \<SiteRoot\> directorio.</span><span class="sxs-lookup"><span data-stu-id="0773e-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="0773e-219">Ejecute el cmdlet Enter-CcUpdate para purgar los servicios y poner cada dispositivo en modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0773e-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="0773e-220">En el primer dispositivo, ejecute los cmdlets siguientes para restablecer y crear nuevos certificados de entidad de certificación y todos los certificados de servidor internos:</span><span class="sxs-lookup"><span data-stu-id="0773e-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="0773e-221">Para las versiones de Cloud Connector anteriores a 2.0:</span><span class="sxs-lookup"><span data-stu-id="0773e-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="0773e-222">O para Cloud Connector versión 2.0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="0773e-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="0773e-223">En el primer dispositivo, ejecute el siguiente cmdlet para hacer una copia de seguridad de los archivos de ca en la \<SiteRoot\> carpeta.</span><span class="sxs-lookup"><span data-stu-id="0773e-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="0773e-224">En todos los demás dispositivos del mismo sitio, ejecute los siguientes comandos para consumir los archivos de copia de seguridad de ca, de modo que todos los dispositivos usen el mismo certificado raíz y, a continuación, soliciten nuevos certificados.</span><span class="sxs-lookup"><span data-stu-id="0773e-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="0773e-225">Si se usa TLS entre la puerta de enlace y el servidor de mediación, ejecute el cmdlet Export-CcRootCertificate desde cualquier dispositivo del sitio y, a continuación, instale el certificado exportado en las puertas de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="0773e-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="0773e-226">Es posible que también deba volver a emitir el certificado en la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="0773e-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="0773e-227">Ejecute el cmdlet Exit-CcUpdate para iniciar los servicios y salir del modo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0773e-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="0773e-228">**Problema: Recibe el siguiente mensaje de error en el registro del servicio de administración de Cloud Connector, "C:\Archivos de programa\Skype Empresarial Cloud Connector Edition\ManagementService\CceManagementService.log": Error de CceService: 0 : Excepción inesperada al notificar el estado en línea: System.Management.Automation.CmdletInvocationException: Error de inicio de sesión para el \<Global Tenant Admin\> usuario. Cree un nuevo objeto de credenciales y asegúrese de que ha usado el nombre de usuario y la contraseña correctos. ---\>**</span><span class="sxs-lookup"><span data-stu-id="0773e-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="0773e-229">**Solución:** Las credenciales de administrador global de inquilinos de Microsoft 365 u Office 365 se han cambiado desde que se registró el dispositivo de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0773e-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="0773e-230">Para actualizar las credenciales almacenadas localmente en el dispositivo de Cloud Connector, ejecute lo siguiente desde PowerShell de administrador en el dispositivo host:</span><span class="sxs-lookup"><span data-stu-id="0773e-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="0773e-231">**Problema: Después de cambiar la contraseña de la cuenta del servidor host que usó para la implementación, recibirá el siguiente mensaje de error: "ConvertTo-SecureString : Clave no válida para su uso en el estado especificado". En %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log o mientras se ejecuta el cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="0773e-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="0773e-232">**Solución:** Todas las credenciales de Cloud Connector se almacenan en el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="0773e-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="0773e-233">Cuando cambie la contraseña del servidor host, deberá actualizar las credenciales almacenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="0773e-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="0773e-234">**Si ejecuta Cloud Connector versión 1.4.2,** vuelva a generar todas las contraseñas de Cloud Connector siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="0773e-235">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="0773e-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="0773e-236">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="0773e-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="0773e-237">Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción.</span><span class="sxs-lookup"><span data-stu-id="0773e-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="0773e-238">Escriba las mismas contraseñas que escribió antes para la implementación de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0773e-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="0773e-239">**Si ejecuta Cloud Connector versión 2.0** o posterior, vuelva a generar todas las contraseñas de Cloud Connector siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="0773e-240">Reinicie el servidor host.</span><span class="sxs-lookup"><span data-stu-id="0773e-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="0773e-241">Elimine el siguiente archivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" .</span><span class="sxs-lookup"><span data-stu-id="0773e-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="0773e-242">Inicie una consola de PowerShell como administrador y, a continuación, ejecute "Register-CcAppliance -Local" para volver a escribir las contraseñas después de la descripción.</span><span class="sxs-lookup"><span data-stu-id="0773e-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="0773e-243">Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 1.4.2, use la contraseña de VMAdmin para la contraseña de CceService cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="0773e-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="0773e-244">Escriba la misma contraseña que escribió antes para la implementación de Cloud Connector para todas las demás cuentas.</span><span class="sxs-lookup"><span data-stu-id="0773e-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="0773e-245">Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 1.4.2 y las contraseñas domainAdmin y VMAdmin son diferentes, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="0773e-246">Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0773e-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="0773e-247">Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="0773e-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="0773e-248">Cuando se le solicite la credencial de la nueva cuenta, escriba la contraseña de la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="0773e-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="0773e-249">Si el archivo de contraseña almacenado en caché se generó con Cloud Connector versión 2.0 o posterior, de forma predeterminada, VmAdmin y DomainAdmin usan la misma contraseña que CceService.</span><span class="sxs-lookup"><span data-stu-id="0773e-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="0773e-250">Si cambió las contraseñas de DomainAdmin y VMAdmin, debe realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="0773e-251">Ejecute Set-CcCredential -AccountType DomainAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0773e-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="0773e-252">Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="0773e-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="0773e-253">Cuando se le solicite la credencial de la nueva cuenta, escriba la contraseña de la contraseña de DomainAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="0773e-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="0773e-254">Ejecute Set-CcCredential -AccountType VmAdmin de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0773e-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="0773e-255">Cuando se le solicite la credencial de cuenta antigua, escriba la credencial que usó para la contraseña de CceService.</span><span class="sxs-lookup"><span data-stu-id="0773e-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="0773e-256">Cuando se le solicite la nueva credencial de cuenta, escriba la contraseña de la contraseña de VmAdmin que usó antes.</span><span class="sxs-lookup"><span data-stu-id="0773e-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="0773e-257">**Problema: con Cloud Connector versión 2.1 y versiones posteriores, al ejecutar Register-CcAppliance u otros cmdlets en el dispositivo, recibe un mensaje de error como: "For Each-Object : The property 'Common' cannot be found on this object. Compruebe que la propiedad existe. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span><span class="sxs-lookup"><span data-stu-id="0773e-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="0773e-258">**Solución:** Cloud Connector 2.1 y versiones posteriores requiere .NET Framework 4.6.1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0773e-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="0773e-259">Actualice .NET Framework en el dispositivo a la versión 4.6.1 o posterior y vuelva a ejecutar los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0773e-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="0773e-260">**Problema: Con Cloud Connector Edition 2.1, al ejecutar Install-CcAppliance, recibe un mensaje de error como: "Error al instalar una nueva instancia con el error: No se puede establecer "State" porque solo se pueden usar cadenas como valores para establecer propiedades XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="0773e-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="0773e-261">**Solución:** En Cloudconnector.ini, en la sección [Común], agregue la configuración "Estado" como se muestra a continuación: CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="0773e-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="0773e-262">No es obligatorio que la línea "Estado" tenga valor, pero no se puede quitar la línea "Estado" del archivo Cloudconnector.ini estado.</span><span class="sxs-lookup"><span data-stu-id="0773e-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="0773e-263">**Problema: recibe el siguiente mensaje de error "Dismount-WindowsImage : Dismount-WindowsImage error. Código de error = 0xc1550115" al instalar o actualizar Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="0773e-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="0773e-264">**Solución:** Inicia una consola de PowerShell como administrador y ejecuta "DISM -Cleanup-Wim'".</span><span class="sxs-lookup"><span data-stu-id="0773e-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="0773e-265">Esto limpiará todas las imágenes con problemas.</span><span class="sxs-lookup"><span data-stu-id="0773e-265">This will clean up all troubled images.</span></span> <span data-ttu-id="0773e-266">Ejecute Install-CcAppliance o espere a que los bits se actualicen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0773e-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="0773e-267">**Problema: se produce un error en la implementación del primer dispositivo de Cloud Connector en un entorno ha**</span><span class="sxs-lookup"><span data-stu-id="0773e-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="0773e-268">**Solución:** Los pasos que siga dependen del motivo por el que se ha fallado la implementación:</span><span class="sxs-lookup"><span data-stu-id="0773e-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="0773e-269">Si se produce un error en el primer dispositivo de Cloud Connector y no se puede determinar el motivo del error, debe instalarlo de nuevo hasta que la implementación se haya realizado correctamente y, a continuación, instalar los demás dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0773e-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="0773e-270">Si se produce un error en el primer dispositivo de Cloud Connector con un problema menor, como un problema de certificado externo, es posible que pueda solucionar el problema sin volver a instalar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0773e-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="0773e-271">A continuación, puede usar PowerShell remoto de inquilino para marcar la implementación como correcta de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="0773e-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="0773e-272">(También puede seguir los pasos siguientes si la primera implementación se ha realizado correctamente, pero, por algún motivo, Cloud Connector no puede informar de que la implementación se ha realizado correctamente).</span><span class="sxs-lookup"><span data-stu-id="0773e-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="0773e-273">Para obtener la identidad (GUID) del primer dispositivo de Cloud Connector, ejecute Get-CsHybridPSTNAppliance cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0773e-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="0773e-274">Para marcar el dispositivo como implementado correctamente, ejecute el Set-CsCceApplianceDeploymentStatus como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="0773e-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="0773e-275">**Problema: debe comprobar e instalar las actualizaciones de Windows manualmente en el servidor host o en las máquinas virtuales.**</span><span class="sxs-lookup"><span data-stu-id="0773e-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="0773e-276">**Solución:** Le recomendamos que aproveche las actualizaciones automatizadas del sistema operativo proporcionadas por Skype Empresarial Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0773e-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="0773e-277">Después de registrar un dispositivo para la administración en línea y habilitar la actualización automática del sistema operativo, el servidor host y las máquinas virtuales comprobarán e instalarán actualizaciones de Windows automáticamente de acuerdo con la configuración de la ventana de tiempo de actualización del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0773e-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="0773e-278">Si necesitas comprobar e instalar actualizaciones de Windows manualmente, sigue los pasos de esta sección que se aplican a tu tipo de implementación.</span><span class="sxs-lookup"><span data-stu-id="0773e-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="0773e-279">Debe planear la actualización del servidor host y de las máquinas virtuales que se ejecutan en él al mismo tiempo para minimizar la cantidad de tiempo de in corriente necesario para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0773e-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="0773e-280">Si lo prefiere, puede usar un servidor de Windows Server Update Services (WSUS) para proporcionar actualizaciones a los servidores de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0773e-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="0773e-281">Asegúrate de configurar Windows Update para **que no se instale** automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0773e-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="0773e-282">Para obtener información sobre cómo actualizar manualmente la implementación de Cloud Connector, consulte la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="0773e-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="0773e-283">**Problema: cuando Cloud Connector se actualiza a una nueva compilación, los cmdlets de Cloud Connector no se actualizan.**</span><span class="sxs-lookup"><span data-stu-id="0773e-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="0773e-284">Esto a veces sucede si se deja abierta una ventana de PowerShell cuando se produce una actualización automática.</span><span class="sxs-lookup"><span data-stu-id="0773e-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="0773e-285">**Solución:** Para cargar los cmdlets actualizados, puede realizar uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0773e-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="0773e-286">Cierre PowerShell en el dispositivo de Cloud Connector y vuelva a abrir PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0773e-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="0773e-287">O bien, puede ejecutar Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="0773e-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="0773e-288">**Problema: "El término 'Stop-CsWindowsService' no se reconoce como el nombre de un cmdlet, una función, un archivo de script o un programa operable". Al intentar ejecutar Enter-CcUpdate cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="0773e-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="0773e-289">**Solución:** Elimine el $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="0773e-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="0773e-290">PowerShell crea este archivo como una memoria caché de cmdlets a partir de los módulos que encuentra para que no tenga que volver a analizar todos los módulos cada vez, ya que esto haría que las cosas se ralentizase mucho.</span><span class="sxs-lookup"><span data-stu-id="0773e-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="0773e-291">Lo más probable es que haya algunos daños en el archivo que proporcionaron resultados engañosos a PowerShell cuando estaba leyendo de esa memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0773e-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="0773e-292">**Problema: "Import-Module CloudConnector" genera el error "Import-Module: El módulo especificado "CloudConnector" no se cargó porque no se encontró ningún archivo de módulo válido en ningún directorio de módulos"**</span><span class="sxs-lookup"><span data-stu-id="0773e-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="0773e-293">**Resolución:**</span><span class="sxs-lookup"><span data-stu-id="0773e-293">**Resolution:**</span></span>
    - <span data-ttu-id="0773e-294">Valide que realmente el módulo CloudConnector existe en c:\Archivos de programa\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="0773e-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="0773e-295">Después de validar que el módulo CloudConnector existe en esta ubicación, se puede cambiar la variable de entorno PSModulePath que almacena la ruta de acceso a las ubicaciones de los módulos:</span><span class="sxs-lookup"><span data-stu-id="0773e-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="0773e-296">a.</span><span class="sxs-lookup"><span data-stu-id="0773e-296">a.</span></span> <span data-ttu-id="0773e-297">Cambio temporal: inicie PowerShell como administrador y ejecute el siguiente comando: $env:PSModulePath = $env:PSModulePath + "; C:\Archivos de programa\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="0773e-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="0773e-298">b.</span><span class="sxs-lookup"><span data-stu-id="0773e-298">b.</span></span> <span data-ttu-id="0773e-299">Para el cambio persistente, inicie PowerShell como administrador y ejecute los siguientes comandos, uno a uno: $CurrentValue = [Entorno]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Archivos de programa\WindowsPowerShell\Modules", "Machine")</span><span class="sxs-lookup"><span data-stu-id="0773e-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="0773e-300">Instalar las actualizaciones de Windows manualmente</span><span class="sxs-lookup"><span data-stu-id="0773e-300">Install Windows updates manually</span></span>

<span data-ttu-id="0773e-301">Si no quieres usar actualizaciones automáticas en tu entorno, sigue estos pasos para comprobar y aplicar manualmente las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="0773e-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="0773e-302">La comprobación e instalación de actualizaciones de Windows puede requerir un reinicio del servidor.</span><span class="sxs-lookup"><span data-stu-id="0773e-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="0773e-303">Cuando se reinicia un servidor host, los usuarios no podrán usar Cloud Connector para realizar o recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="0773e-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="0773e-304">Puedes comprobar e instalar actualizaciones manualmente para controlar cuándo se llevan a cabo las actualizaciones y, a continuación, reiniciar las máquinas según sea necesario durante las horas que elijas para evitar la interrupción de los servicios.</span><span class="sxs-lookup"><span data-stu-id="0773e-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="0773e-305">Para comprobar manualmente si hay actualizaciones, conéctese a cada servidor host y abra el **Panel de control.**</span><span class="sxs-lookup"><span data-stu-id="0773e-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="0773e-306">Seleccione **Sistema y seguridad de Windows \> Update** y, a continuación, administre las actualizaciones y los reinicios del servidor según corresponda a su entorno.</span><span class="sxs-lookup"><span data-stu-id="0773e-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="0773e-307">Si solo hay un dispositivo en el sitio, conéctese a cada máquina virtual y abra el **Panel de control.**</span><span class="sxs-lookup"><span data-stu-id="0773e-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="0773e-308">Selecciona **Sistema y seguridad de Windows \> Update** y, a continuación, configura las actualizaciones y los reinicios del servidor según corresponda.</span><span class="sxs-lookup"><span data-stu-id="0773e-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="0773e-309">Si hay más de un dispositivo en el sitio, los usuarios no pueden tener acceso a la instancia que se actualiza y reinicia durante las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0773e-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="0773e-310">Los usuarios se conectarán a otras instancias de la implementación hasta que todas las máquinas virtuales y todos los servicios de Skype Empresarial comiencen en las máquinas virtuales una vez completadas las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0773e-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="0773e-311">Para evitar cualquier posible interrupción del servicio, puede quitar la instancia de HA mientras aplica las actualizaciones y, a continuación, restaurarla cuando se complete.</span><span class="sxs-lookup"><span data-stu-id="0773e-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="0773e-312">Para ello:</span><span class="sxs-lookup"><span data-stu-id="0773e-312">To do so:</span></span>
    
1. <span data-ttu-id="0773e-313">En cada servidor host, abra una consola de PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="0773e-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="0773e-314">Quite la instancia de HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0773e-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="0773e-315">Siga los pasos para que una sola instancia aplique manualmente las actualizaciones y reinicie la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="0773e-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="0773e-316">Vuelva a establecer la instancia en HA con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0773e-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="0773e-317">Para las implementaciones de varios sitios, siga los pasos para un solo sitio para cada sitio de la implementación, aplicando actualizaciones a un sitio cada vez.</span><span class="sxs-lookup"><span data-stu-id="0773e-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="0773e-318">Sugerencias al instalar software antivirus en el equipo host de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="0773e-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="0773e-319">Si necesita instalar software antivirus en el equipo host de Cloud Connector, debe agregar las siguientes exclusiones:</span><span class="sxs-lookup"><span data-stu-id="0773e-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="0773e-320">Directorio de dispositivos local en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="0773e-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="0773e-321">Directorio de sitios remoto en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="0773e-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="0773e-322">El Directorio de sitios local del equipo hospeda la carpeta raíz del sitio compartido.</span><span class="sxs-lookup"><span data-stu-id="0773e-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="0773e-323">%ProgramFiles%\Skype Empresarial Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="0773e-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="0773e-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="0773e-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="0773e-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="0773e-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="0773e-326">El proceso Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="0773e-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
