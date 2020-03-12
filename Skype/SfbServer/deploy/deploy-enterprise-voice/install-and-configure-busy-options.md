---
title: Instalación y configuración de opciones de disponibilidad para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Obtenga información sobre cómo instalar y configurar opciones de disponibilidad en Skype empresarial Server.
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604217"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="c5e70-103">Instalación y configuración de opciones de disponibilidad para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c5e70-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="c5e70-104">Obtenga información sobre cómo instalar y configurar opciones de disponibilidad en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c5e70-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="c5e70-105">Opciones de disponibilidad es una nueva Directiva de voz que se incluye en la actualización acumulativa de julio de 2016 que permite configurar el modo en que se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o cuando se mantiene la llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="c5e70-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="c5e70-106">Las llamadas nuevas o entrantes pueden rechazarse con una señal de ocupado o desviarse al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="c5e70-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="c5e70-107">Si opciones de disponibilidad está habilitada para la organización, todos los usuarios de la empresa, tanto los usuarios de Enterprise Voice como los que no son de la empresa, pueden usar las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="c5e70-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="c5e70-108">Ocupado en ocupado: en el que se rechazarán las llamadas entrantes nuevas con una señal de ocupado si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="c5e70-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="c5e70-109">Correo de voz en ocupado: en el que se reenviarán las llamadas entrantes nuevas al correo de voz si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="c5e70-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="c5e70-110">Independientemente de cómo estén configuradas las opciones de disponibilidad, los usuarios de una llamada o conferencia, o aquellos que tengan una llamada en espera, no podrán iniciar nuevas llamadas o conferencias.</span><span class="sxs-lookup"><span data-stu-id="c5e70-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="c5e70-111">Para obtener más información acerca de la característica de opciones de disponibilidad, vea [Plan for busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="c5e70-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="c5e70-112">Instalación</span><span class="sxs-lookup"><span data-stu-id="c5e70-112">Install</span></span>

<span data-ttu-id="c5e70-113">Asegúrese de que tiene instalada la versión más reciente de Skype empresarial Server y de que ha instalado la revisión más reciente.</span><span class="sxs-lookup"><span data-stu-id="c5e70-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="c5e70-114">Para ello, detenga primero todos los servicios y, a continuación, ejecute el programa de instalación de la actualización de Skype empresarial Server de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c5e70-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="c5e70-115">Ejecute el comando STOP-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="c5e70-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="c5e70-116">Ejecute el instalador de instalador skypeserverupdateinstaller. exe en cada servidor front-end de un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="c5e70-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="c5e70-117">Ejecute el instalador de instalador skypeserverupdateinstaller. exe en cada servidor de sucursal con funciones de supervivencia (SBS), si desea garantizar la compatibilidad con la conmutación por error en SBS.</span><span class="sxs-lookup"><span data-stu-id="c5e70-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="c5e70-118">El instalador va a implementar la última versión de la aplicación opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c5e70-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="c5e70-119">Sin embargo, la aplicación no está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c5e70-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="c5e70-120">Para habilitar la aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c5e70-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="c5e70-121">Ejecute el cmdlet [set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente las opciones de disponibilidad, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5e70-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="c5e70-122">A continuación, si el sitio tiene una directiva de voz, debe habilitar las opciones de disponibilidad para la Directiva de voz de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c5e70-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="c5e70-123">En primer lugar, ejecute [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar el nombre del sitio:</span><span class="sxs-lookup"><span data-stu-id="c5e70-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="c5e70-124">Use el valor Identity (por ejemplo: site: Redmond1) recuperado de Get-CsSite para recuperar la Directiva de voz del sitio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c5e70-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="c5e70-125">Si existe una directiva de voz para el sitio, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c5e70-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="c5e70-126">A continuación, ejecute el cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para agregar opciones de disponibilidad a la lista de aplicaciones de servidor, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5e70-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="c5e70-127">Debe reemplazar% FQDN% por el nombre de dominio completo de un grupo de servidores específico.</span><span class="sxs-lookup"><span data-stu-id="c5e70-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="c5e70-128">A continuación, ejecute el cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para actualizar los roles de control de acceso basado en roles (RBAC) para los cmdlets de opciones de disponibilidad, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5e70-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="c5e70-129">Por último, inicie los servicios de Windows de Skype empresarial Server en todos los servidores front-end de todos los grupos donde se haya instalado y habilitado las opciones de disponibilidad ejecutando el comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c5e70-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="c5e70-130">Configurar</span><span class="sxs-lookup"><span data-stu-id="c5e70-130">Configure</span></span>

<span data-ttu-id="c5e70-131">Para configurar las opciones de disponibilidad, use el cmdlet [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c5e70-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="c5e70-132">Por ejemplo, el siguiente comando configura opciones de disponibilidad para el usuario "Ken Myer".</span><span class="sxs-lookup"><span data-stu-id="c5e70-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="c5e70-133">En esta configuración, cualquier llamada a "Ken Myer" devolverá una señal de ocupado cuando ya esté en una llamada:</span><span class="sxs-lookup"><span data-stu-id="c5e70-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="c5e70-134">En el siguiente ejemplo, el comando configura opciones de disponibilidad para el usuario "Chrystal Velasquez".</span><span class="sxs-lookup"><span data-stu-id="c5e70-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="c5e70-135">En esta configuración, se reenviarán nuevas llamadas entrantes a "Chrystal Velasquez" al correo de voz cuando ya esté en una llamada:</span><span class="sxs-lookup"><span data-stu-id="c5e70-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="c5e70-136">Puede recuperar la información de configuración de las opciones de disponibilidad con el cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c5e70-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="c5e70-137">En el siguiente ejemplo se devuelve la configuración de opciones de disponibilidad para "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="c5e70-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="c5e70-138">Puede quitar opciones de disponibilidad con el cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c5e70-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="c5e70-139">El siguiente comando quita las opciones de disponibilidad para "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="c5e70-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="c5e70-140">Para obtener información detallada acerca de los cmdlets que usa para configurar opciones de disponibilidad, consulte el contenido de referencia técnica para [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)y [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="c5e70-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="c5e70-141">Habilitar registro</span><span class="sxs-lookup"><span data-stu-id="c5e70-141">Enable logging</span></span>

<span data-ttu-id="c5e70-142">Para habilitar el registro de opciones de disponibilidad mediante el uso del servicio de registro centralizado, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5e70-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="c5e70-143">Comprobar y solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="c5e70-143">Verify and troubleshoot</span></span>

<span data-ttu-id="c5e70-144">Después de instalar las opciones de disponibilidad, puede comprobar que la instalación se ha realizado correctamente mediante el cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar la lista de aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="c5e70-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="c5e70-145">Si opciones de disponibilidad está instalado correctamente, el resultado del cmdlet debería mostrar la configuración de opciones de disponibilidad de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c5e70-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="c5e70-146">También puede usar el visor de eventos de Windows para comprobar que la instalación de opciones de disponibilidad se ha realizado correctamente y que Skype empresarial Server se cargó correctamente de las opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c5e70-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="c5e70-147">Para comprobar las opciones de disponibilidad, abra el **visor de eventos\> : registros\> de aplicaciones y servicios-servidor de Skype (o Lync)** y busque identificador de evento = 30253.</span><span class="sxs-lookup"><span data-stu-id="c5e70-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
