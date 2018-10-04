---
title: Instalar y configurar Opciones de disponibilidad para Skype Empresarial Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Lea acerca de cómo instalar y configurar las opciones de disponibilidad en Skype para Business Server.
ms.openlocfilehash: 3cf197f58dda13ab0c1af2077a6eb0fb59dafcc4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370811"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="f72f9-103">Instalar y configurar Opciones de disponibilidad para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f72f9-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="f72f9-104">Lea acerca de cómo instalar y configurar las opciones de disponibilidad en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="f72f9-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="f72f9-105">Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016 que permite configurar el tratamiento dado a las llamadas entrantes cuando un usuario ya está al teléfono o en una conferencia, o tiene una llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="f72f9-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="f72f9-106">Las llamadas nuevas o entrantes pueden rechazarse con una señal de línea ocupada o desviarse al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="f72f9-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="f72f9-107">Si Opciones de disponibilidad está habilitada para la organización, todos los usuarios de la empresa, tanto los que usen la telefonía IP empresarial como los que no la usen, pueden utilizar las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="f72f9-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="f72f9-108">Ocupado cuando ocupado: en la cual se rechazan las llamadas entrantes nuevas con una señal de línea ocupada si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="f72f9-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="f72f9-109">Correo de voz cuando ocupado: en la cual se desvían al correo de voz las llamadas entrantes nuevas si el usuario está ocupado.</span><span class="sxs-lookup"><span data-stu-id="f72f9-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="f72f9-110">Independientemente de cómo esté configurada Opciones de disponibilidad, los usuarios que estén al teléfono o en una conferencia, o bien aquellos que tengan una llamada en espera, podrán iniciar nuevas llamadas o conferencias.  </span><span class="sxs-lookup"><span data-stu-id="f72f9-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="f72f9-111">Para obtener más información acerca de la característica de opciones ocupado, consulte [Plan para las opciones de disponibilidad de Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="f72f9-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="f72f9-112">Instalación </span><span class="sxs-lookup"><span data-stu-id="f72f9-112">Install</span></span>

<span data-ttu-id="f72f9-113">Asegúrese de que tiene la versión más reciente de Skype para Business Server instalado y que ha instalado la revisión más reciente.</span><span class="sxs-lookup"><span data-stu-id="f72f9-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="f72f9-114">Para ello, en primer lugar detener todos los servicios y, a continuación, ejecute el Skype para el instalador de la actualización de Business Server como sigue:</span><span class="sxs-lookup"><span data-stu-id="f72f9-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="f72f9-115">Ejecute el comando Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="f72f9-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="f72f9-116">Ejecute el instalador SkypeServerUpdateInstaller.exe en cada uno de los servidores front-end de un grupo.</span><span class="sxs-lookup"><span data-stu-id="f72f9-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="f72f9-117">Ejecute el instalador SkypeServerUpdateInstaller.exe en cada servidor de sucursal con funciones de supervivencia (SBS) si quiere garantizar que se admita la conmutación por error en SBS.</span><span class="sxs-lookup"><span data-stu-id="f72f9-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="f72f9-p103">El instalador implementará la última versión de la aplicación Opciones de disponibilidad, pero la aplicación no está habilitada de forma predeterminada. Para habilitarla, siga los pasos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="f72f9-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="f72f9-121">Ejecute el cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente opciones ocupado tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f72f9-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="f72f9-122">A continuación, si el sitio tiene una directiva de voz, debe habilitar Opciones de disponibilidad para la directiva de voz de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f72f9-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="f72f9-123">En primer lugar, ejecute [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar el nombre del sitio:</span><span class="sxs-lookup"><span data-stu-id="f72f9-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```
   Get-CsSite
   ```

    <span data-ttu-id="f72f9-124">Use el valor de identidad (por ejemplo: Site: Redmond1) recuperados de Get-CsSite para recuperar la directiva de voz del sitio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f72f9-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="f72f9-125">Si existe una directiva de voz para el sitio, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f72f9-125">If a voice policy exists for the site, run the following command:</span></span>

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="f72f9-126">A continuación, ejecute el cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para agregar opciones de disponibilidad a la lista de aplicaciones de servidor tal como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f72f9-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="f72f9-127">Debe reemplazar % FQDN % con el nombre de dominio completo de un grupo de servidores específico.</span><span class="sxs-lookup"><span data-stu-id="f72f9-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="f72f9-128">A continuación, ejecute el cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para actualizar los roles de Role-based access control (RBAC) para los cmdlets de ocupado opciones tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f72f9-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="f72f9-129">Por último, inicie la Skype para servicios de Windows Server de negocio en todos los servidores Front-End de todos los grupos donde se ha instalado y habilitado ejecutando el comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) las opciones de disponibilidad:</span><span class="sxs-lookup"><span data-stu-id="f72f9-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="f72f9-130">Configurar</span><span class="sxs-lookup"><span data-stu-id="f72f9-130">Configure</span></span>

<span data-ttu-id="f72f9-131">Para configurar las opciones de disponibilidad, use el cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f72f9-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="f72f9-p104">Por ejemplo, el siguiente comando configura Opciones de disponibilidad para el usuario "Ken Myer". En esta configuración, cualquier llamada a "Ken Myer" devolverá una señal de línea ocupada cuando ya esté al teléfono:</span><span class="sxs-lookup"><span data-stu-id="f72f9-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="f72f9-p105">En el siguiente ejemplo, el comando configura Opciones de disponibilidad para la usuaria "Chrystal Velasquez". En esta configuración, se enviarán al correo de voz las nuevas llamadas entrantes de "Chrystal Velasquez" cuando ya esté al teléfono:
</span><span class="sxs-lookup"><span data-stu-id="f72f9-p105">In the next example, the command configures busy options for the user "Chrystal Velasquez". In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="f72f9-136">Puede recuperar información de configuración acerca de las opciones de disponibilidad mediante el cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f72f9-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="f72f9-137">En el ejemplo siguiente se devuelve la configuración de opciones de disponibilidad para "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="f72f9-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="f72f9-138">Puede quitar las opciones de disponibilidad mediante el cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f72f9-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="f72f9-139">El siguiente comando quita Opciones de disponibilidad para "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="f72f9-139">The following command removes Busy Options for "Ken Myer":</span></span>

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="f72f9-140">Para obtener información detallada sobre los cmdlets de usar para configurar las opciones de disponibilidad, vea el contenido de referencia técnica para [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)y [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="f72f9-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="f72f9-141">Habilitación del registro</span><span class="sxs-lookup"><span data-stu-id="f72f9-141">Enable logging</span></span>

<span data-ttu-id="f72f9-142">Para habilitar el registro de Opciones de disponibilidad mediante el uso del servicio de registro centralizado, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f72f9-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="f72f9-143">Verificación y solución de problemas:</span><span class="sxs-lookup"><span data-stu-id="f72f9-143">Verify and troubleshoot</span></span>

<span data-ttu-id="f72f9-144">Después de instalar las opciones de disponibilidad, puede comprobar que la instalación fue correcta mediante el cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar la lista de aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="f72f9-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="f72f9-145">Si Opciones de disponibilidad se instaló correctamente, el resultado del cmdlet deberá mostrar la configuración de Opciones de disponibilidad de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f72f9-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

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

<span data-ttu-id="f72f9-146">También puede usar el Visor de eventos de Windows para comprobar que la instalación de las opciones de disponibilidad se realizó correctamente y que Skype para Business Server cargado correctamente las opciones de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f72f9-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="f72f9-147">Para comprobar las opciones de disponibilidad, abra **Visor de eventos:\> registros de aplicación y servicios -\> Skype (o Lync) Server** y busca el identificador de evento = 30253.</span><span class="sxs-lookup"><span data-stu-id="f72f9-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>