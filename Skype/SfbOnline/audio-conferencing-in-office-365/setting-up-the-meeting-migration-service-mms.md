---
title: Configuración del servicio de migración de reuniones (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Servicio de migración (MMS) de la reunión es un Skype para servicio de negocios que se ejecuta en segundo plano y que automáticamente actualiza Skype para reuniones de negocios y Teams de Microsoft para los usuarios. MMS está diseñado para eliminar la necesidad de actualizar su Skype para reuniones de negocios y Teams de Microsoft para los usuarios que ejecuten la herramienta de migración de la reunión.
ms.openlocfilehash: 46f7c0223c88b7a4a3aa3a553e14df85ce86835d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configuración del servicio de migración de reuniones (MMS)

Servicio de migración (MMS) de la reunión es un Skype para servicio de negocios que se ejecuta en segundo plano y que automáticamente actualiza Skype para reuniones de negocios y Teams de Microsoft para los usuarios. MMS está diseñado para eliminar la necesidad de actualizar su Skype para reuniones de negocios y Teams de Microsoft para los usuarios que ejecuten la herramienta de migración de la reunión.
  
 **Requisitos**
  
MMS requiere que los buzones de los organizadores de las reuniones estén en Exchange Online.
  
 **Escenarios principales**
  
MMS actualiza las reuniones de Skype de un usuario en los siguientes dos escenarios principales:
  
- Cuando el usuario se migra desde locales Skype para Business Server a Skype para los negocios en línea.
    
- Cuando un administrador realiza un cambio en la configuración del usuario conferencias de audio que sería necesario actualizar la información de conferencia de audio en las reuniones del usuario.
    
 **Escenarios comunes en los que no puede usar MMS**
  
Estos son algunos de los escenarios comunes con los que puede encontrarse. Todos son escenarios admitidos para la migración, aunque en ellos no se puede ejecutar MMS y tendrá que usar en su lugar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Los buzones de los usuarios están en un servidor de Exchange local.
    
- Mediante un proveedor de conferencia de audio de terceros
    
- Migración de usuarios de Skype para los negocios en línea al servidor de Skype local
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Actualización de reuniones cuando se migra un usuario local a Skype Empresarial Online

Este es el escenario más común en el que MMS puede simplificar la transición a sus usuarios. Cuando un usuario se migra desde un local Skype para Business Server a Skype para los negocios en línea, MMS detectará el nuevo usuario y buscará calendario del usuario Skype para reuniones de negocios y Teams de Microsoft. Las reuniones futuras se actualizará con la nueva información de ese usuario.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Si actualmente utiliza Skype servidor 2015 para conferencias de audio

Le invitamos a seguir los procedimientos recomendados indicados a continuación para obtener la mejor experiencia con MMS en este escenario:
  
- Dado que MMS requiere que el buzón del usuario se encuentre en Exchange Online, si también va a realizar la migración desde un servidor de Exchange local, mueva el buzón del usuario a Exchange Online en primer lugar.
    
- Asignar la licencia de **Conferencia de Audio** al usuario antes de ejecutar el `Move-CSUser` cmdlet para migrar el usuario. Esto es porque MMS también actualiza las reuniones cuando se cambia la configuración de conferencia de audio para un usuario. Si no asigna la licencia en primer lugar, MMS actualizará todas las reuniones de nuevo cuando la asigne.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Si utiliza un proveedor de servicios de audioconferencia (ACP) de terceros

Con un ACP de terceros, o no se ejecuta MMS depende de configuración de conferencia de audio de su organización. Puede reemplazar automáticamente los números de acceso telefónico de los ACP cuando se asigna un usuario de una licencia de **Conferencia de Audio** . También es posible que deba evitar que esto suceda y que necesite conservar los números de acceso telefónico local de su ACP. Para ver la configuración de la organización, ejecute el siguiente comando de Windows PowerShell y comprobar el valor del parámetro `AutomaticallyReplaceAcpProvider`. Si necesita ayuda con PowerShell, consulte la sección [Usar PowerShell para administrar su organización de Skype Empresarial](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al final de este artículo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Si el valor de este parámetro es $true, MMS se ejecute cuando un usuario se le asigna una licencia de **Conferencias de Audio** y actualizar sus reuniones. Los números de acceso telefónico de los ACP se conservan hasta que se asigne la licencia de **Conferencia de Audio** .
    
- Si el valor de este parámetro es $false, MMS no actualizará las reuniones incluso si un usuario se le asigna una licencia de **Conferencia de Audio** . Los números de acceso telefónico de los ACP se conservan hasta que el usuario está configurado manualmente para conferencias de audio en Skype para el centro de administración de negocio o el uso de Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Actualización de reuniones cuando cambie la configuración de conferencia de audio de un usuario

MMS actualizará un Skype existente para reuniones de negocios y Teams de Microsoft en los siguientes casos:
  
- Al asignar o quitar licencias de **Conferencia de Audio** .
    
- Al habilitar o deshabilitar conferencias de audio.
    
- Al cambiar o restablecer el Id. de conferencia para un usuario configurado para utilizar reuniones públicas.
    
- Cuando el usuario se mueve a un nuevo puente de conferencia de audio.
    
- Cuando un número de teléfono es sin asignar de un puente de conferencia de audio. Este es un escenario complejo que requiere pasos adicionales. Para obtener más información, vea [cambiar el número o números libre de peaje en el puente de conferencia de Audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS solo actualiza las reuniones si se utiliza el puente de Microsoft. Si utiliza un proveedor de conferencia de audio de terceros, los usuarios tendrá que actualizar sus reuniones manualmente. En este caso, puede usar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
No todos los cambios en la configuración de conferencia de audio de un usuario desencadenan MMS. Concretamente, los siguientes cambios no provocan que MMS actualice las reuniones:
  
- Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).
    
- Cuando cambia la URL de una reunión de su organización mediante el comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>¿Qué sucede cuando MMS actualiza las reuniones?

Cuando MMS detecta que es necesario actualizar las reuniones de un usuario, realiza lo siguiente:
  
1. Identificar todos los Skype para reuniones de negocios y Teams de Microsoft el usuario haya programado en el futuro
    
  - Se pasan por alto cualquier Skype para reuniones de negocios o Teams de Microsoft ocurridos antes cuando se ejecuta MMS
    
  - Solo se actualizan las reuniones en las que el usuario es el organizador.
    
2. Sustituye el bloque de información de la reunión en línea en los detalles de la reunión.
    
3. Envía actualizaciones a todos los destinatarios de la reunión en nombre del organizador.
    
 **¿Cuánto tardará MMS en completar la operación?**
  
La cantidad de tiempo que tardará para que MMS migrar reuniones varía dependiendo de cuántos usuarios se ven afectados y el número total de Skype para reuniones de negocios o Teams Microsoft que cada usuario tiene en su calendario. Como mínimo, requerirá diez minutos. Aunque algunas migraciones de gran tamaño pueden llevar hasta 12 horas, la mayoría se completan en una hora.
  
 **Limitaciones y problemas potenciales**
  
- Sólo el Skype para reuniones de negocios o Teams de Microsoft que estaban programados haciendo clic en el botón **Agregar Skype reunión** en Outlook en el Web o mediante el complemento de Skype Meeting para Outlook se migran. En otras palabras, si un usuario copia y pega la información de una reunión en línea de Skype en otra nueva, la nueva reunión no se actualizará.
    
- Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea.
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- El contenido que se haya creado o adjuntado a la reunión (pizarras, sondeos, etc.) no se conservará tras la ejecución de MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.
    
- También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de la reunión almacenadas en OneNote no se perderán, solo se sobrescribe el vínculo que conduce a las notas compartidas.
    
- Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán.
    
- Algunos caracteres UNICODE del cuerpo de la invitación se pueden actualizar de forma incorrecta y mostrar uno de los siguientes caracteres especiales: ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>¿Qué verán los usuarios cuando MMS actualice sus reuniones?

Al igual que la Herramienta de migración de reuniones, MMS envía las actualizaciones de reuniones en nombre de los usuarios. Por lo tanto, lo único que verán los usuarios es otra ronda de notificaciones de aceptación de reunión para sus reuniones. Esto puede resultar confuso para los usuarios, por lo que recomendamos que notifique a los usuarios por adelantado no sólo cuando se migrarlos desde local a Skype para los negocios en línea, pero también cuando realice cambios de conferencias de audio que desencadenará MMS.
  
## <a name="managing-mms"></a>Administrar MMS

Debe utilizar Windows PowerShell para administrar MMS y comprobar el estado de las migraciones en curso. La información de esta sección asume que está familiarizado con el uso de PowerShell para administrar su organización de Skype Empresarial. Si nunca ha usado PowerShell con anterioridad, consulte la sección [Usar PowerShell para administrar su organización de Skype Empresarial](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al final de este artículo.
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>¿Cómo compruebo el estado de las migraciones de las reuniones?

Debe usar el cmdlet  `Get-CsMeetingMigrationStatus` para comprobar el estado de las migraciones de las reuniones. A continuación puede ver algunos ejemplos.
  
Para obtener un resumen del estado de todas las migraciones de MMS, ejecute el siguiente comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

De este modo obtendrá una vista en forma de tabla de todos los estados de migración similar a esta:
  
UserCount estado---<br/> 21 pendiente<br/>6 en curso<br/> Error 2 <br/> 131 correcta
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

MMS está habilitado de forma predeterminada para todas las organizaciones, pero se puede deshabilitar si es necesario. Por ejemplo, si desea migrar manualmente todas las reuniones o si utiliza un proveedor de conferencia de audio de terceros, no deberá MMS ejecutando. También tiene la opción de deshabilitar temporalmente MMS. Por ejemplo, se pueden realizar modificaciones sustanciales en cuanto a la configuración de conferencia de audio para su organización y no desea MMS ejecutándose hasta que se completen todos los cambios.
  
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

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Habilitación y deshabilitación de MMS sólo para cambios de conferencia de audio
<a name="Troubleshooting"> </a>

También puede deshabilitar MMS sólo para cambios de conferencia de audio. Todavía se ejecutará cuando un usuario se migra desde Skype para negocios locales a Skype para los negocios en línea. Para comprobar el estado actual de MMS para actualizaciones de conferencias de audio, ejecute el siguiente comando y comprobar el valor de la `AutomaticallyMigrateUserMeetings` parámetro. Si este parámetro se establece en true$, MMS se establece para actualizar reuniones de usuario cuando se cambia la configuración de conferencia de audio.
  
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
