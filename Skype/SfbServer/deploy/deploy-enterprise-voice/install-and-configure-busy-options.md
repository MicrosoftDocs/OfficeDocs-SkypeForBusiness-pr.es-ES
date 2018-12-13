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
ms.openlocfilehash: a5fdd117f2c812bba69978a7d2943321b940bcc4
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240662"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Instalar y configurar Opciones de disponibilidad para Skype Empresarial Server

Lea acerca de cómo instalar y configurar las opciones de disponibilidad en Skype para Business Server.

Opciones de disponibilidad es una nueva directiva de voz introducida en la actualización acumulativa de julio de 2016 que permite configurar el tratamiento dado a las llamadas entrantes cuando un usuario ya está al teléfono o en una conferencia, o tiene una llamada en espera. Las llamadas nuevas o entrantes pueden rechazarse con una señal de línea ocupada o desviarse al correo de voz.

Si Opciones de disponibilidad está habilitada para la organización, todos los usuarios de la empresa, tanto los que usen la telefonía IP empresarial como los que no la usen, pueden utilizar las siguientes opciones de configuración:

- Ocupado cuando ocupado: en la cual se rechazan las llamadas entrantes nuevas con una señal de línea ocupada si el usuario está ocupado.

- Correo de voz cuando ocupado: en la cual se desvían al correo de voz las llamadas entrantes nuevas si el usuario está ocupado.

Independientemente de cómo esté configurada Opciones de disponibilidad, los usuarios que estén al teléfono o en una conferencia, o bien aquellos que tengan una llamada en espera, podrán iniciar nuevas llamadas o conferencias.  

Para obtener más información acerca de la característica Opciones de disponibilidad, vea [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Instalación 

Asegúrese de que tiene la versión más reciente de Skype para Business Server instalado y que ha instalado la revisión más reciente. Para ello, en primer lugar detener todos los servicios y, a continuación, ejecute el Skype para el instalador de la actualización de Business Server como sigue:

1. Ejecute el comando Stop-CsWindowsService.

2. Ejecute el instalador SkypeServerUpdateInstaller.exe en cada uno de los servidores front-end de un grupo.

3. Ejecute el instalador SkypeServerUpdateInstaller.exe en cada servidor de sucursal con funciones de supervivencia (SBS) si quiere garantizar que se admita la conmutación por error en SBS.

El instalador implementará la última versión de la aplicación Opciones de disponibilidad, pero la aplicación no está habilitada de forma predeterminada. Para habilitarla, siga los pasos que se indican a continuación:

1. Ejecute el cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente opciones ocupado tal como se muestra en el ejemplo siguiente:

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. A continuación, si el sitio tiene una directiva de voz, debe habilitar Opciones de disponibilidad para la directiva de voz de la siguiente manera:

    En primer lugar, ejecute [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar el nombre del sitio:

   ```
   Get-CsSite
   ```

    Use el valor de identidad (por ejemplo: Site: Redmond1) recuperados de Get-CsSite para recuperar la directiva de voz del sitio de la siguiente manera:

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Si existe una directiva de voz para el sitio, ejecute el siguiente comando:

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. A continuación, ejecute el cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para agregar opciones de disponibilidad a la lista de aplicaciones de servidor tal como se muestra en el siguiente ejemplo:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Debe reemplazar % FQDN % con el nombre de dominio completo de un grupo de servidores específico.

4. A continuación, ejecute el cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para actualizar los roles de Role-based access control (RBAC) para los cmdlets de ocupado opciones tal como se muestra en el ejemplo siguiente:

   ```
   Update-CsAdminRole
   ```

5. Por último, inicie la Skype para servicios de Windows Server de negocio en todos los servidores Front-End de todos los grupos donde se ha instalado y habilitado ejecutando el comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) las opciones de disponibilidad:

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configuración

Para configurar Opciones de disponibilidad, use el cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  

Por ejemplo, el siguiente comando configura Opciones de disponibilidad para el usuario "Ken Myer". En esta configuración, cualquier llamada a "Ken Myer" devolverá una señal de línea ocupada cuando ya esté al teléfono:

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

En el siguiente ejemplo, el comando configura Opciones de disponibilidad para la usuaria "Chrystal Velasquez". En esta configuración, se enviarán al correo de voz las nuevas llamadas entrantes de "Chrystal Velasquez" cuando ya esté al teléfono:

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Puede recuperar la información de configuración acerca de Opciones de disponibilidad usando el cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx). En el ejemplo siguiente se devuelve la configuración de opciones de disponibilidad para "KenMyer@Contoso.com":

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Puede quitar Opciones de disponibilidad usando el cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx). El siguiente comando quita Opciones de disponibilidad para "Ken Myer":

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

Para obtener información detallada sobre los cmdlets de usar para configurar las opciones de disponibilidad, vea el contenido de referencia técnica para [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)y [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Habilitación del registro

Para habilitar el registro de Opciones de disponibilidad mediante el uso del servicio de registro centralizado, especifique lo siguiente:

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Verificación y solución de problemas:

Después de instalar las opciones de disponibilidad, puede comprobar que la instalación fue correcta mediante el cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar la lista de aplicaciones de servidor. Si Opciones de disponibilidad se instaló correctamente, el resultado del cmdlet deberá mostrar la configuración de Opciones de disponibilidad de la siguiente manera:

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

También puede usar el Visor de eventos de Windows para comprobar que la instalación de las opciones de disponibilidad se realizó correctamente y que Skype para Business Server cargado correctamente las opciones de disponibilidad. Para comprobar las opciones de disponibilidad, abra **Visor de eventos:\> registros de aplicación y servicios -\> Skype (o Lync) Server** y busca el identificador de evento = 30253.
