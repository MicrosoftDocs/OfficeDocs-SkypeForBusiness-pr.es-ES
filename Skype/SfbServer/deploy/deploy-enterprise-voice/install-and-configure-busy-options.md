---
title: Instalar y configurar opciones de disponibilidad para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Obtenga información sobre cómo instalar y configurar opciones de disponibilidad en Skype Empresarial Server.
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830810"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Instalar y configurar opciones de disponibilidad para Skype Empresarial Server

Obtenga información sobre cómo instalar y configurar opciones de disponibilidad en Skype Empresarial Server.

Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016 que le permite configurar cómo se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o tiene una llamada en espera. Las llamadas nuevas o entrantes pueden rechazarse con una señal de disponibilidad o reenviarse al correo de voz.

Si Opciones de disponibilidad está habilitada para la organización, todos los usuarios de la empresa, tanto los Telefonía IP empresarial como los que no Telefonía IP empresarial, pueden usar las siguientes opciones de configuración:

- Ocupado en Ocupado: en el que se rechazarán las nuevas llamadas entrantes con una señal de ocupado si el usuario está ocupado.

- Correo de voz en Ocupado: en el que las nuevas llamadas entrantes se reenviarán al correo de voz si el usuario está ocupado.

Independientemente de cómo se configuren sus opciones de disponibilidad, los usuarios de una llamada o conferencia, o aquellos con una llamada en espera, no se les impide iniciar nuevas llamadas o conferencias.

Para obtener más información acerca de la característica Opciones de disponibilidad, consulte [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Instalar

Asegúrese de tener instalada la versión más reciente de Skype Empresarial Server y de haber instalado la revisión más reciente. Para ello, primero detenga todos los servicios y, a continuación, ejecute el instalador de actualización de Skype Empresarial Server de la siguiente manera:

1. Ejecute el Stop-CsWindowsService comando.

2. Ejecute el instalador SkypeServerUpdateInstaller.exe en cada servidor front-end de un grupo de servidores.

3. Ejecute el instalador SkypeServerUpdateInstaller.exe en cada servidor de sucursal con funciones de supervivencia (SBS), si desea garantizar la compatibilidad con la conmutación por error en SBS.

El instalador implementará la versión más reciente de la aplicación Opciones de disponibilidad. Sin embargo, la aplicación no está habilitada de forma predeterminada. Para habilitar la aplicación, siga estos pasos:

1. Ejecute el cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente Opciones de disponibilidad, como se muestra en el siguiente ejemplo:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. A continuación, si el sitio tiene una directiva de voz, debe habilitar Opciones de disponibilidad para la directiva de voz de la siguiente manera:

    En primer lugar, [ejecute Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar el nombre del sitio:

   ```powershell
   Get-CsSite
   ```

    Use el valor identity (por ejemplo: Site:Redmond1) recuperado de Get-CsSite para recuperar la directiva de voz del sitio de la siguiente manera:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Si existe una directiva de voz para el sitio, ejecute el siguiente comando:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. A continuación, ejecute el cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para agregar Opciones de disponibilidad a la lista de aplicaciones de servidor, como se muestra en el siguiente ejemplo:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Debe reemplazar %FQDN% por el nombre de dominio completo de un grupo de servidores específico.

4. A continuación, ejecute el cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para actualizar los roles de control de acceso basado en roles (RBAC) para los cmdlets Opciones de disponibilidad, como se muestra en el ejemplo siguiente:

   ```powershell
   Update-CsAdminRole
   ```

5. Por último, inicie los servicios de Windows de Skype Empresarial Server en todos los servidores front-end de todos los grupos donde se instalaron y habilitaron opciones de disponibilidad ejecutando el comando [Start-CsWindowsService:](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurar

Para configurar Opciones de disponibilidad, use el cmdlet [Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)

Por ejemplo, el siguiente comando configura las opciones de disponibilidad para el usuario "Ken Myer". En esta configuración, cualquier llamada a "Ken Myer" devolverá una señal de ocupado cuando ya esté en una llamada:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

En el siguiente ejemplo, el comando configura las opciones de disponibilidad para el usuario "Chrystal Entrelaz". En esta configuración, las nuevas llamadas entrantes a "Chrystal Selávía" se reenviarán al correo de voz cuando ya esté en una llamada:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Puede recuperar información de configuración sobre Opciones de disponibilidad mediante el cmdlet [Get-CsBusyOptions.](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) En el siguiente ejemplo se devuelve el valor de Opciones de disponibilidad para "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Puede quitar Opciones de disponibilidad con el cmdlet [Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) El siguiente comando quita Opciones de disponibilidad para "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Para obtener información detallada acerca de los cmdlets que usa para configurar Opciones de disponibilidad, consulte el contenido de referencia técnica de [Set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)y [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Habilitar el registro

Para habilitar el registro de Opciones de disponibilidad mediante el servicio de registro centralizado, especifique lo siguiente:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Comprobar y solucionar problemas

Después de instalar Opciones de disponibilidad, puede comprobar que la instalación se ha realizado correctamente con el cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar la lista de aplicaciones de servidor. Si Opciones de disponibilidad está instalado correctamente, el resultado del cmdlet debe mostrar la configuración de Opciones de disponibilidad de la siguiente manera:

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

También puede usar el Visor de eventos de Windows para comprobar que la instalación de Opciones de disponibilidad se ha realizado correctamente y que Skype Empresarial Server cargó correctamente Opciones de disponibilidad. Para comprobar opciones de disponibilidad, abra el Visor de eventos - Registros de aplicaciones y servicios **\> - Skype \> (o Lync) Server** y busque el identificador de evento = 30253.
