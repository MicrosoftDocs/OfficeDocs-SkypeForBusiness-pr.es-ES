---
title: Configuración del servicio de migración de reuniones (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Servicio de migración (MMS) de la reunión es un Skype para servicio empresarial que se ejecuta en segundo plano y Skype se actualiza automáticamente para las reuniones de negocios y Microsoft Teams para los usuarios. MMS está diseñado para eliminar la necesidad de los usuarios ejecutar la herramienta de migración de la reunión para actualizar su Skype para las reuniones de negocios y Microsoft Teams.
ms.openlocfilehash: f81c394d676da951cf98f34f080fb26f135b9550
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501003"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configuración del servicio de migración de reuniones (MMS)

Servicio de migración (MMS) de la reunión es un Skype para servicio empresarial que se ejecuta en segundo plano y Skype se actualiza automáticamente para las reuniones de negocios y Microsoft Teams para los usuarios. MMS está diseñado para eliminar la necesidad de los usuarios ejecutar la herramienta de migración de la reunión para actualizar su Skype para las reuniones de negocios y Microsoft Teams.  Esta herramienta no migra Skype para reuniones de negocios a las reuniones de Microsoft Teams.  
  
 **Requisitos**
  
MMS requiere que los buzones de los organizadores de las reuniones estén en Exchange Online.
  
 **Escenarios principales**
  
MMS actualiza las reuniones de Skype de un usuario en los siguientes dos escenarios principales:
  
- Cuando el usuario se migra de Skype local para Business Server a Skype para profesionales en línea.
    
- Cuando un administrador realiza un cambio en la configuración del usuario conferencias de audio que sería necesario actualizar la información de conferencia de audio en las reuniones de dicho usuario.
    
 **Escenarios comunes en los que no puede usar MMS**
  
Estos son algunos de los escenarios comunes con los que puede encontrarse. Todos son escenarios admitidos para la migración, aunque en ellos no se puede ejecutar MMS y tendrá que usar en su lugar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Los buzones de los usuarios están en un servidor de Exchange local.
    
- Uso de un proveedor de conferencia de audio de terceros
    
- Migración de usuarios de Skype para empresarial en línea para el servidor local Skype
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Actualización de reuniones cuando se migra un usuario local a Skype Empresarial Online

Este es el escenario más común en el que MMS puede simplificar la transición a sus usuarios. Cuando un usuario se migra desde una Skype local para Business Server a Skype para profesionales en línea, MMS detectará el nuevo usuario y calendario de dicho usuario se analizará en busca de Skype para las reuniones de negocios y Microsoft Teams. Las reuniones futuras se actualizará con la nueva información de dicho usuario.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Si está utilizando actualmente el servidor 2015 de Skype para conferencias de audio

Le invitamos a seguir los procedimientos recomendados indicados a continuación para obtener la mejor experiencia con MMS en este escenario:
  
- Dado que MMS requiere que el buzón del usuario se encuentre en Exchange Online, si también va a realizar la migración desde un servidor de Exchange local, mueva el buzón del usuario a Exchange Online en primer lugar.
    
- Asignar la licencia de **Conferencias de Audio** al usuario antes de ejecutar el `Move-CSUser` cmdlet para migrar el usuario. Esto es debido a que MMS también actualiza las reuniones cuando se cambia la configuración de conferencia de audio para un usuario. Si no asigna la licencia en primer lugar, MMS actualizará todas las reuniones de nuevo cuando la asigne.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Si utiliza un proveedor de servicios de audioconferencia (ACP) de terceros

Con un ACP de terceros, o si no se ejecuta MMS depende de configuración de conferencia de audio de la organización. Puede elegir reemplazar automáticamente los números de acceso telefónico desde su ACP cuando se asigna a un usuario una licencia de **Conferencias de Audio** . También es posible que deba evitar que esto suceda y que necesite conservar los números de acceso telefónico local de su ACP. Para ver la configuración de la organización, ejecute el siguiente comando de Windows PowerShell y comprobar el valor del parámetro `AutomaticallyReplaceAcpProvider`. Si necesita ayuda con PowerShell, consulte la sección [Usar PowerShell para administrar su organización de Skype Empresarial](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al final de este artículo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Si el valor de este parámetro es $true, MMS va a ejecutar cuando un usuario se le asigna una licencia de **Conferencias de Audio** y actualizar sus reuniones. Los números de acceso telefónico desde su ACP se conservan hasta que se asigna la licencia de **Conferencias de Audio** .
    
- Si el valor de este parámetro es $false, a continuación, MMS no actualizarán las reuniones incluso si un usuario se le asigna una licencia de **Conferencias de Audio** . Los números de acceso telefónico desde su ACP se conservan hasta que el usuario está configurado manualmente para conferencias de audio en Skype para el centro de administración de negocio o con Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Actualización de reuniones cuando cambie la configuración de conferencia de audio de un usuario

MMS actualizará un Skype existente para las reuniones de negocios y Microsoft Teams en los siguientes casos:
  
- Al asignar o quitar la licencia de **Conferencias de Audio** .
    
- Al habilitar o deshabilitar conferencias de audio.
    
- Al cambiar o restablecer el identificador de conferencia para un usuario configurado para usar reuniones públicas.
    
- Cuando el usuario se mueve a un nuevo puente de conferencia de audio.
    
- Cuando un número de teléfono es sin asignar de un puente de conferencia de audio. Este es un escenario complejo que requiere pasos adicionales. Para obtener más información, vea [cambiar el teléfono de pago o gratuito números de teléfono de pago en el puente de conferencia de Audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS solo actualiza las reuniones si se utiliza el puente de Microsoft. Si usa un proveedor de conferencia de audio de terceros, los usuarios será necesario actualizar sus reuniones manualmente. En este caso, puede usar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
No todos los cambios a la configuración de conferencia de audio de un usuario desencadenan MMS. Concretamente, los siguientes cambios no provocan que MMS actualice las reuniones:
  
- Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).
    
- Cuando cambia la URL de una reunión de su organización mediante el comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>¿Qué sucede cuando MMS actualiza las reuniones?

Cuando MMS detecta que es necesario actualizar las reuniones de un usuario, realiza lo siguiente:
  
1. Identificar todos los Skype para profesionales y Microsoft Teams las reuniones que el usuario ha programado en el futuro
    
  - Se pasan por alto cualquier Skype para las reuniones de negocios o Teams de Microsoft que se produjo antes de cuando se ejecuta MMS
    
  - Solo se actualizan las reuniones en las que el usuario es el organizador.
    
2. Sustituye el bloque de información de la reunión en línea en los detalles de la reunión.
    
3. Envía actualizaciones a todos los destinatarios de la reunión en nombre del organizador.
    
 **¿Cuánto tardará MMS en completar la operación?**
  
La cantidad de tiempo que tarda para que MMS migrar las reuniones varía en función de cuántos usuarios se ven afectados y el número total de Skype para reuniones profesionales o Teams de Microsoft, que cada usuario tiene en su calendario. Como mínimo, requerirá diez minutos. Aunque algunas migraciones de gran tamaño pueden llevar hasta 12 horas, la mayoría se completan en una hora.
  
 **Limitaciones y problemas potenciales**
  
- Se migran sólo el Skype para las reuniones de negocios o Teams de Microsoft que se han programado haciendo clic en el botón **Agregar Skype reunión** en Outlook en el Web o mediante el complemento de reunión de Skype para Outlook. En otras palabras, si un usuario copia y pega la información de una reunión en línea de Skype en otra nueva, la nueva reunión no se actualizará.
    
- Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea.
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- El contenido que se haya creado o adjuntado a la reunión (pizarras, sondeos, etc.) no se conservará tras la ejecución de MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.
    
- También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de la reunión almacenadas en OneNote no se perderán, solo se sobrescribe el vínculo que conduce a las notas compartidas.
    
- Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán.
    
- Algunos caracteres UNICODE del cuerpo de la invitación se pueden actualizar de forma incorrecta y mostrar uno de los siguientes caracteres especiales: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>¿Qué verán los usuarios cuando MMS actualice sus reuniones?

Al igual que la Herramienta de migración de reuniones, MMS envía las actualizaciones de reuniones en nombre de los usuarios. Por lo tanto, lo único que verán los usuarios es otra ronda de notificaciones de aceptación de reunión para sus reuniones. Esto puede resultar confusa para los usuarios, por lo que recomendamos que notifique a los usuarios por adelantado no sólo cuando se migran ellos de local a Skype para profesionales en línea, pero también cuando se realizan cambios de conferencias de audio que activará MMS.
  
## <a name="managing-mms"></a>Administrar MMS

Debe usar Windows PowerShell para administrar MMS y compruebe el estado de las migraciones continuadas. La información de esta sección asume que está familiarizado con el uso de PowerShell para administrar su organización de Skype Empresarial. Si está familiarizado con PowerShell, vea la sección [Uso de PowerShell para administrar su Skype para organización empresarial](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al final de este artículo.
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>¿Cómo compruebo el estado de las migraciones de las reuniones?

Debe usar el cmdlet  `Get-CsMeetingMigrationStatus` para comprobar el estado de las migraciones de las reuniones. A continuación puede ver algunos ejemplos.
  
Para obtener un resumen del estado de todas las migraciones de MMS, ejecute el siguiente comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

De este modo obtendrá una vista en forma de tabla de todos los estados de migración similar a esta:
  
Estado UserCount---<br/> 21 pendiente<br/>6 en curso<br/> 2 con errores <br/> 131 correcta
> [!IMPORTANT]
> Si ve alguna migración que haya dado error, solucione los problemas cuanto antes. Nadie podrá acceder mediante acceso telefónico local a las reuniones organizadas por estos usuarios hasta que lo haga. Consulte la sección [¿Qué debo hacer si hay un error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) para obtener más información.
  
Para obtener información detallada de todas las migraciones realizadas en un período de tiempo específico puede usar los parámetros  `StartTime` y `EndTime`. Por ejemplo, el siguiente comando devolverá información detallada sobre todas las migraciones realizadas entre el 1 de octubre de 2016 y el 8 de octubre de 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

También puede interesarle comprobar el estado de la migración de un usuario concreto, para lo que puede usar el parámetro  `UserId`. Por ejemplo, el siguiente comando devolverá el estado del usuario ashaw@contoso.com:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>¿Qué debo hacer si hay un error?
<a name="Troubleshooting"> </a>

Si ejecuta el cmdlet  `Get-CsMeetingMigrationStatus` para obtener una vista de resumen y advierte que hay migraciones con el estado Con erroresesto es lo que tiene que hacer:
  
1. Determine a qué usuarios afecta. Ejecute el siguiente comando para obtener la lista de usuarios afectados y el error concreto registrado:
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. Ejecute la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047) para cada uno de estos usuarios, para migrar sus reuniones manualmente.
    
3. Si la migración sigue sin funcionar con la Herramienta de migración de reuniones, tiene dos opciones:
    
  - Hacer que los usuarios creen reuniones de Skype nuevas.
    
  - [Ponerse en contacto con el equipo de soporte técnico](https://go.microsoft.com/fwlink/p/?LinkID=518322).
    
### <a name="enabling-and-disabling-mms"></a>Habilitar y deshabilitar MMS
<a name="Troubleshooting"> </a>

MMS está habilitado de forma predeterminada para todas las organizaciones, pero se puede deshabilitar si es necesario. Por ejemplo, si desea migrar manualmente todas las reuniones o si usa un proveedor de conferencia de audio de terceros, es posible que no necesita MMS ejecuta. También tiene la opción de deshabilitar temporalmente MMS. Por ejemplo, se pueden realizar cambios importantes en la configuración de conferencia de audio para su organización y no desea MMS se ejecuta hasta que se hayan completado todos los cambios.
  
Para ver si MMS está habilitado en su organización, ejecute el siguiente comando y observe el valor del parámetro  `MeetingMigrationEnabled`. Si este parámetro está ajustado en $true, MMS está habilitado.
  
```
Get-CsTenantMigrationConfiguration
```

Para deshabilitar MMS, ejecute el siguiente comando:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Para habilitar MMS, ejecute el siguiente comando:
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Habilitación y deshabilitación de MMS únicamente para los cambios de conferencias de audio
<a name="Troubleshooting"> </a>

También puede deshabilitar MMS únicamente para los cambios de conferencias de audio. Aún se ejecutará cuando un usuario se migra de Skype para empresarial local a Skype para profesionales en línea. Para comprobar el estado actual de MMS para actualizaciones en las conferencias de audio, ejecute el siguiente comando y compruebe el valor de la `AutomaticallyMigrateUserMeetings` parámetro. Si este parámetro se establece en true de $, MMS se establece para actualizar las reuniones del usuario cuando se cambia la configuración de conferencias de audio.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Para deshabilitar MMS para conferencias de audio, ejecute el siguiente comando:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Para habilitar MMS para conferencias de audio, ejecute el siguiente comando:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>¿Cómo ejecuto la migración de reuniones manualmente para un usuario?
<a name="Troubleshooting"> </a>

Además de las migraciones de reuniones automáticas, puede ejecutar la migración de reuniones de forma manual para un usuario a través del cmdlet **Start-CsExMeetingMigration**. Este cmdlet agrega el usuario en la cola de migración de la reunión. El servicio de migración de reuniones leerá la solicitud del usuario y migrará sus reuniones. Puede comprobar el estado de la migración de reuniones con el cmdlet **Get-CsMeetingMigrationStatus**.
  
Aquí puede ver un ejemplo que inicia la migración de reuniones para el usuario ashaw@contoso.com:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>Usar PowerShell para administrar su organización de Skype Empresarial
<a name="WPSInfo"> </a>

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Iniciar una sesión de Windows PowerShell**
  
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
Si desea obtener más información sobre cómo iniciar Windows PowerShell, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o[Conectarse a Skype Empresarial Online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
