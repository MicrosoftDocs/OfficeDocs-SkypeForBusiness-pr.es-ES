---
title: "Configuración del servicio de migración de reuniones (MMS)"
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
description: "Servicio de migración (MMS) de la reunión es un Skype para servicio de empresa que se ejecuta en segundo plano y se actualiza automáticamente Skype para reuniones de negocios y Teams de Microsoft para los usuarios. MMS está diseñado para eliminar la necesidad de los usuarios ejecutar la herramienta de migración de reunión para actualizar su Skype para reuniones de negocios y Teams de Microsoft."
---

# Configuración del servicio de migración de reuniones (MMS)

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Servicio de migración (MMS) de la reunión es un Skype para servicio de empresa que se ejecuta en segundo plano y se actualiza automáticamente Skype para reuniones de negocios y Teams de Microsoft para los usuarios. MMS está diseñado para eliminar la necesidad de los usuarios ejecutar la herramienta de migración de reunión para actualizar su Skype para reuniones de negocios y Teams de Microsoft.
  
 **Requisitos**
  
MMS requiere que los buzones de los organizadores de las reuniones estén en Exchange Online.
  
 **Escenarios principales**
  
MMS actualiza las reuniones de Skype de un usuario en los siguientes dos escenarios principales: 
  
- Cuando el usuario se migra de local Skype empresarial Server a Skype empresarial Online.
    
- Cuando un administrador realiza un cambio en la configuración del usuario conferencias de audio que se requeriría actualiza la información de conferencias de audio en una reunión de ese usuario.
    
 **Escenarios comunes en los que no puede usar MMS**
  
Estos son algunos de los escenarios comunes con los que puede encontrarse. Todos son escenarios admitidos para la migración, aunque en ellos no se puede ejecutar MMS y tendrá que usar en su lugar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Los buzones de los usuarios están en un servidor de Exchange local.
    
- Usar un proveedor de servicios de audioconferencia de terceros
    
- Migrar usuarios de Skype empresarial Online a servidor de Skype local
    
## Actualización de reuniones cuando se migra un usuario local a Skype Empresarial Online

Este es el caso más frecuente donde MMS pueden ayudar a crear una transición suave para sus usuarios. Cuando un usuario se migra de un local Skype empresarial Server a Skype empresarial Online, MMS detecta el nuevo usuario y buscará calendario del usuario Skype para reuniones de negocios y Teams de Microsoft. Las reuniones futuras se actualizará con la nueva información para ese usuario.
  
### Si actualmente usa Skype Server 2015 para conferencias de audio

Le invitamos a seguir los procedimientos recomendados indicados a continuación para obtener la mejor experiencia con MMS en este escenario:
  
- Dado que MMS requiere que el buzón del usuario se encuentre en Exchange Online, si también va a realizar la migración desde un servidor de Exchange local, mueva el buzón del usuario a Exchange Online en primer lugar.
    
- Asignar la licencia de **Conferencias de Audio** al usuario antes de ejecutar el cmdlet `Move-CSUser` para migrar el usuario. Esto es porque MMS también actualiza las reuniones cuando se cambia la configuración de conferencias de audio para un usuario. Si no asigna la licencia en primer lugar, MMS actualizarán todas las reuniones de nuevo cuando se asigna la licencia.
    
### Si utiliza un proveedor de servicios de audioconferencia (ACP) de terceros

Con un ACP de terceros, o no se ejecuta MMS depende de la configuración de conferencias de audio de su organización. Puede elegir sustituir automáticamente los números de acceso telefónico desde su ACP cuando se asigna a un usuario una licencia de **Conferencias de Audio**. Por otro lado, debe evitar que ocurra y conservar los números de acceso telefónico desde su ACP. Para ver la configuración de su organización, ejecute el siguiente comando de Windows PowerShell y compruebe el valor de los parámetros  `AutomaticallyReplaceAcpProvider`. Si necesita ayuda con PowerShell, vea la sección [Usar PowerShell para administrar su organización de Skype Empresarial](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) al final de este artículo.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Si el valor de este parámetro es $true, MMS se ejecute cuando un usuario se asigna una licencia de **Conferencias de Audio** y actualizar sus reuniones. Los números de acceso telefónico desde su ACP se conservan hasta que se asigna la licencia de **Conferencias de Audio**.
    
- Si el valor de este parámetro es $false, MMS no actualizará las reuniones incluso si un usuario se ha asignado una licencia de **Conferencias de Audio**. Los números de acceso telefónico desde su ACP se conservan hasta que el usuario está configurado manualmente para conferencias de audio de Skype para el centro de administración de la empresa o con Windows PowerShell.
    
## Actualización de reuniones cuando cambie la configuración de conferencias de audio de un usuario

MMS actualizará una existente Skype para reuniones de negocios y Teams de Microsoft en los siguientes casos:
  
- Al asignar o quitar la licencia de **Conferencias de Audio**.
    
- Al habilitar o deshabilitar las conferencias de audio.
    
- Al cambiar o restablecer el identificador de conferencia para un usuario configurado para usar reuniones públicas.
    
- Cuando el usuario se mueve a un nuevo puente de conferencia de audio.
    
- Cuando un número de teléfono es sin asignar de un puente de conferencia de audio. Este es un escenario complejo que requiere pasos adicionales. Para obtener más información, consulte [Cambiar el pago o gratuito números de pago en el puente de conferencia de Audio](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS sólo actualiza las reuniones cuando usa el puente de Microsoft. Si está utilizando un proveedor de servicios de audioconferencia de terceros, los usuarios tendrán que actualizar sus reuniones manualmente. En este caso, puede usar la [Herramienta de migración de reuniones](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
No todos los cambios de configuración de conferencias de audio de un usuario desencadenan MMS. Más concretamente, los siguientes dos cambios no como resultado MMS actualizar reuniones:
  
- Cuando cambia la dirección SIP del organizador de la reunión (tanto el nombre de usuario SIP como el dominio SIP).
    
- Cuando cambia la URL de una reunión de su organización mediante el comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## ¿Qué sucede cuando MMS actualiza las reuniones?

Cuando MMS detecta que es necesario actualizar las reuniones de un usuario, realiza lo siguiente:
  
1. Identificar todos los Skype para reuniones de empresa y Microsoft Teams el usuario haya programado en el futuro
    
  - Se pasan por alto cualquier Skype para reuniones de empresa o Teams de Microsoft que ocurrieron antes cuando se ejecuta MMS
    
  - Solo se actualizan las reuniones en las que el usuario es el organizador.
    
2. Sustituye el bloque de información de la reunión en línea en los detalles de la reunión.
    
3. Envía actualizaciones a todos los destinatarios de la reunión en nombre del organizador.
    
 **¿Cuánto tardará MMS en completar la operación?**
  
La cantidad de tiempo necesario para que MMS migrar reuniones varía dependiendo de cuántos usuarios se ven afectados y el número total de Skype para empresas o Microsoft Teams reuniones que cada usuario tiene en su calendario. Como mínimo, esta acción tardará 10 minutos para que se ejecute. Mientras algunas migraciones grandes pueden tardar hasta 12 horas, debe completar la mayoría de las migraciones en 1 hora.
  
 **Limitaciones y problemas potenciales**
  
- Solo el Skype para reuniones de empresa o Teams de Microsoft que se han programado haciendo clic en el botón **Agregar Skype reunión** en Outlook en la Web o mediante el complemento de reuniones de Skype para Outlook se migran. En otras palabras, si un usuario copia y pega la información de reunión en línea de Skype de una reunión a una nueva reunión, dicha reunión nueva no se actualizarán.
    
- Cuando migra una reunión, MMS sustituye todo el contenido del bloque de información de la reunión en línea. Por lo tanto, si el usuario ha editado ese bloque, los cambios se sobrescriben. No se verá afectado por esta acción ningún contenido que el usuario tenga en los detalles de la reunión, fuera del bloque de información de la reunión en línea. 
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- El contenido que se haya creado o adjuntado a la reunión (pizarras, sondeos, etc.) no se conservará tras la ejecución de MMS. Si sus organizadores de reuniones adjuntaron contenido a las reuniones antes de la ejecución de MMS, será necesario volver a crear el contenido una vez finalizada la operación.
    
- También se sobrescribirá el vínculo a las notas de la reunión compartidas en el elemento de calendario y en la reunión de Skype. Tenga en cuenta que las notas de la reunión almacenadas en OneNote no se perderán, solo se sobrescribe el vínculo que conduce a las notas compartidas.
    
- Las reuniones que tengan más de 250 participantes (incluido el organizador) no se migrarán. 
    
- Algunos caracteres UNICODE del cuerpo de la invitación se pueden actualizar de forma incorrecta y mostrar uno de los siguientes caracteres especiales: ï, ¿, ½, �.
    
### ¿Qué verán los usuarios cuando MMS actualice sus reuniones?

Al igual que la herramienta de migración de la reunión, MMS envía actualizaciones de reunión en nombre de los usuarios. Por lo tanto, lo único que los usuarios verán es redondear otra de las notificaciones de aceptación de sus reuniones de la reunión. Esto puede resultar confuso para los usuarios, por lo que recomendamos que notifique a los usuarios por adelantado no solo cuando se migrarlas locales a Skype empresarial Online, pero también cuando realice cambios de conferencias de audio que activará MMS.
  
## Administrar MMS

Debe utilizar Windows PowerShell para administrar MMS y comprobar el estado de las migraciones en curso. La información de esta sección asume que está familiarizado con el uso de PowerShell para administrar su organización de Skype Empresarial. Si nunca ha usado PowerShell con anterioridad, consulte la sección [Usar PowerShell para administrar su organización de Skype Empresarial](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) al final de este artículo.
  
### ¿Cómo compruebo el estado de las migraciones de las reuniones?

Debe usar el cmdlet  `Get-CsMeetingMigrationStatus` para comprobar el estado de las migraciones de las reuniones. A continuación puede ver algunos ejemplos.
  
Para obtener un resumen del estado de todas las migraciones de MMS, ejecute el siguiente comando:
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

De este modo obtendrá una vista en forma de tabla de todos los estados de migración similar a esta:
  
Estado UserCount----- ---------Pendiente 21En curso 6Con errores 2Correcto 131
> [!IMPORTANT]
> Si ve alguna migración que haya dado error, solucione los problemas cuanto antes. Nadie podrá acceder mediante acceso telefónico local a las reuniones organizadas por estos usuarios hasta que lo haga. Consulte la sección [¿Qué debo hacer si hay un error?](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#Troubleshooting) para obtener más información.
  
Para obtener información detallada de todas las migraciones realizadas en un período de tiempo específico puede usar los parámetros  `StartTime` y `EndTime`. Por ejemplo, el siguiente comando devolverá información detallada sobre todas las migraciones realizadas entre el 1 de octubre de 2016 y el 8 de octubre de 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

También puede interesarle comprobar el estado de la migración de un usuario concreto, para lo que puede usar el parámetro  `UserId`. Por ejemplo, el siguiente comando devolverá el estado del usuario ashaw@contoso.com:
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### ¿Qué debo hacer si hay un error?
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
    
### Habilitar y deshabilitar MMS
<a name="Troubleshooting"> </a>

MMS está habilitado para todas las organizaciones de forma predeterminada, pero puede deshabilitarse según sea necesario. Por ejemplo, si desea migrar manualmente todas las reuniones o usar un proveedor de servicios de audioconferencia de terceros, no tendrá MMS ejecutando. También puede deshabilitar temporalmente MMS. Por ejemplo, que puede realizar cambios importantes en la configuración de conferencias de audio para su organización y no desea MMS hasta que se completan todos los cambios.
  
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

### Habilitar y deshabilitar MMS solo para los cambios de conferencias de audio
<a name="Troubleshooting"> </a>

También puede deshabilitar MMS solo para los cambios de audioconferencia. Aún se ejecutará cuando un usuario se migra de Skype para Business local a Skype empresarial Online. Para comprobar el estado actual de MMS actualizaciones de conferencias de audio, ejecute el siguiente comando y compruebe el valor del parámetro  `AutomaticallyMigrateUserMeetings` . Si este parámetro se establece en$true, MMS se establece en actualizar reuniones de usuario cuando se cambia la configuración de conferencias de audio.
  
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

### ¿Cómo ejecuto la migración de reuniones manualmente para un usuario?
<a name="Troubleshooting"> </a>

Además de las migraciones automáticos de reuniones, también puede ejecutar la migración de la reunión manualmente para un usuario, ejecute el cmdlet **Start-CsExMeetingMigration**. Este cmdlet agrega el usuario en cola de migración de la reunión. Servicio de migración de la reunión leerá la solicitud del usuario y migrar sus reuniones. Puede comprobar el estado de la reunión migración cmdlet **Get-CsMeetingMigrationStatus**.
  
Aquí puede ver un ejemplo que inicia la migración de reuniones para el usuario ashaw@contoso.com:
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## Usar PowerShell para administrar su organización de Skype Empresarial
<a name="WPSInfo"> </a>

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
 **Iniciar una sesión de Windows PowerShell**
  
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Si desea obtener más información sobre cómo iniciar Windows PowerShell, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[Conectarse a Skype Empresarial Online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

