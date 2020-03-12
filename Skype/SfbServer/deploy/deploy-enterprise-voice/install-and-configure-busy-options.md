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
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Instalación y configuración de opciones de disponibilidad para Skype empresarial Server

Obtenga información sobre cómo instalar y configurar opciones de disponibilidad en Skype empresarial Server.

Opciones de disponibilidad es una nueva Directiva de voz que se incluye en la actualización acumulativa de julio de 2016 que permite configurar el modo en que se administran las llamadas entrantes cuando un usuario ya está en una llamada o conferencia o cuando se mantiene la llamada en espera. Las llamadas nuevas o entrantes pueden rechazarse con una señal de ocupado o desviarse al correo de voz.

Si opciones de disponibilidad está habilitada para la organización, todos los usuarios de la empresa, tanto los usuarios de Enterprise Voice como los que no son de la empresa, pueden usar las siguientes opciones de configuración:

- Ocupado en ocupado: en el que se rechazarán las llamadas entrantes nuevas con una señal de ocupado si el usuario está ocupado.

- Correo de voz en ocupado: en el que se reenviarán las llamadas entrantes nuevas al correo de voz si el usuario está ocupado.

Independientemente de cómo estén configuradas las opciones de disponibilidad, los usuarios de una llamada o conferencia, o aquellos que tengan una llamada en espera, no podrán iniciar nuevas llamadas o conferencias.

Para obtener más información acerca de la característica de opciones de disponibilidad, vea [Plan for busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Instalación

Asegúrese de que tiene instalada la versión más reciente de Skype empresarial Server y de que ha instalado la revisión más reciente. Para ello, detenga primero todos los servicios y, a continuación, ejecute el programa de instalación de la actualización de Skype empresarial Server de la siguiente manera:

1. Ejecute el comando STOP-CsWindowsService.

2. Ejecute el instalador de instalador skypeserverupdateinstaller. exe en cada servidor front-end de un grupo de servidores.

3. Ejecute el instalador de instalador skypeserverupdateinstaller. exe en cada servidor de sucursal con funciones de supervivencia (SBS), si desea garantizar la compatibilidad con la conmutación por error en SBS.

El instalador va a implementar la última versión de la aplicación opciones de disponibilidad. Sin embargo, la aplicación no está habilitada de forma predeterminada. Para habilitar la aplicación, siga estos pasos:

1. Ejecute el cmdlet [set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente las opciones de disponibilidad, como se muestra en el ejemplo siguiente:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. A continuación, si el sitio tiene una directiva de voz, debe habilitar las opciones de disponibilidad para la Directiva de voz de la siguiente manera:

    En primer lugar, ejecute [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar el nombre del sitio:

   ```powershell
   Get-CsSite
   ```

    Use el valor Identity (por ejemplo: site: Redmond1) recuperado de Get-CsSite para recuperar la Directiva de voz del sitio de la siguiente manera:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Si existe una directiva de voz para el sitio, ejecute el siguiente comando:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. A continuación, ejecute el cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para agregar opciones de disponibilidad a la lista de aplicaciones de servidor, como se muestra en el siguiente ejemplo:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Debe reemplazar% FQDN% por el nombre de dominio completo de un grupo de servidores específico.

4. A continuación, ejecute el cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para actualizar los roles de control de acceso basado en roles (RBAC) para los cmdlets de opciones de disponibilidad, como se muestra en el ejemplo siguiente:

   ```powershell
   Update-CsAdminRole
   ```

5. Por último, inicie los servicios de Windows de Skype empresarial Server en todos los servidores front-end de todos los grupos donde se haya instalado y habilitado las opciones de disponibilidad ejecutando el comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurar

Para configurar las opciones de disponibilidad, use el cmdlet [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Por ejemplo, el siguiente comando configura opciones de disponibilidad para el usuario "Ken Myer". En esta configuración, cualquier llamada a "Ken Myer" devolverá una señal de ocupado cuando ya esté en una llamada:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

En el siguiente ejemplo, el comando configura opciones de disponibilidad para el usuario "Chrystal Velasquez". En esta configuración, se reenviarán nuevas llamadas entrantes a "Chrystal Velasquez" al correo de voz cuando ya esté en una llamada:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Puede recuperar la información de configuración de las opciones de disponibilidad con el cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . En el siguiente ejemplo se devuelve la configuración de opciones de disponibilidad para "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Puede quitar opciones de disponibilidad con el cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . El siguiente comando quita las opciones de disponibilidad para "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Para obtener información detallada acerca de los cmdlets que usa para configurar opciones de disponibilidad, consulte el contenido de referencia técnica para [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)y [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Habilitar registro

Para habilitar el registro de opciones de disponibilidad mediante el uso del servicio de registro centralizado, especifique lo siguiente:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Comprobar y solucionar problemas

Después de instalar las opciones de disponibilidad, puede comprobar que la instalación se ha realizado correctamente mediante el cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar la lista de aplicaciones de servidor. Si opciones de disponibilidad está instalado correctamente, el resultado del cmdlet debería mostrar la configuración de opciones de disponibilidad de la siguiente manera:

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

También puede usar el visor de eventos de Windows para comprobar que la instalación de opciones de disponibilidad se ha realizado correctamente y que Skype empresarial Server se cargó correctamente de las opciones de disponibilidad. Para comprobar las opciones de disponibilidad, abra el **visor de eventos\> : registros\> de aplicaciones y servicios-servidor de Skype (o Lync)** y busque identificador de evento = 30253.
