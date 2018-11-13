---
title: Cambiar los números de teléfono de su puente de Audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: When you buy Audio Conferencing licenses, Microsoft is hosting your audio conferencing bridge for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.
ms.openlocfilehash: 7bd00f23a54780c94cdebeb413a8897e572ec47d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294864"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiar los números de teléfono de su puente de Audioconferencia

Cuando comprar licencias de **Conferencias de Audio** , Microsoft hospeda el puente de conferencia de audio para su organización. El puente de conferencia de audio se ofrece a los números de teléfono de acceso telefónico desde diferentes ubicaciones para que los organizadores de reuniones y los participantes pueden utilizar para unirse a Skype para reuniones profesionales o Teams de Microsoft mediante un teléfono.
  
Además de los números de teléfono ya está asignados a su puente de conferencia, puede [obtener los números de servicio adicionales](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (teléfono de pago y los números gratuitos usados para conferencias de audio) de otras ubicaciones y, a continuación, asigne a la conferencia de puente para que pueda Expanda la cobertura para los usuarios.
  
> [!NOTE]
> Para poder asignar o quitar la asignación a un número de teléfono para un puente de conferencia, el número de teléfono debe ser un número de '*service*'. Puede ver el tipo de número es navegando a **voz** > **los números de teléfono** en el heredado del portal y aspecto en la columna **Tipo de número** . Los Créditos de comunicaciones de Office 365 deben configurarse primero para que los usuarios puedan marcar en el puente un número gratuito.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Paso 1: asignar al nuevo número de teléfono para el puente de conferencia de audio

1. Inicie sesión en Office 365 con su cuenta profesional.

2. Vaya al **Centro de administración de Office 365** > **centros de administración** > **equipos & Skype** > **portal heredado** > **voz** > **los números de teléfono**.

3. Seleccione el número de teléfono de la lista y, en el panel de acciones, haga clic en **asignar**.

4. En la página **Asignar**, haga clic en **Guardar**.

Sólo un número de teléfono de pago de servicio se puede establecer como el número predeterminado para el puente de conferencia; **números de teléfono gratuito de servicio no se puede establecer como el número predeterminado del puente de conferencia**. Si va a asignar a un número de teléfono de pago de servicio y que le gustaría establecer como el número predeterminado nuevo para el puente de conferencia de audio, siga estos pasos:

1. Inicie sesión en Office 365 con su cuenta profesional.

2. Vaya al **Centro de administración de Office 365** > **centros de administración** > **equipos & Skype** > **reuniones** > **Puentes de conferencia**.

3. Resalte el número de teléfono de pago de servicio que desea configurar como predeterminado.

4. Haga clic en **Establecer como predeterminado**.

> [!NOTE]
> Tras asignar un nuevo número de teléfono, incluso si el número ha pasado a ser el nuevo número predeterminado, no cambiará el número predeterminado de los usuarios existentes. Para establecer el pago predeterminado o un número de teléfono gratuito que se agrega a las invitaciones de reunión del organizador, consulte las instrucciones para [Los equipos de Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) o las instrucciones de [Skype para profesionales en línea](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites). 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Paso 2: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Cuando se programa una reunión, los números de teléfono que se incluyen en las invitaciones de reunión son los predeterminados del usuario. Para obtener más información, vea [Configurar el teléfono los números incluidos en invitaciones en los equipos de Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) o [el teléfono los números incluidos en invitaciones en Skype para profesionales en línea](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al **Centro de administración de Office 365** > **centros de administración** > **equipos & Skype** > **portal heredado** > **conferencias de Audio** > **a los usuarios**y seleccione los usuarios en la lista.

3. Haga clic en **Editar** en el panel de acciones.

4. En **número de teléfono de pago predeterminado** o **número gratuito predeterminado**, seleccione el número en la lista y haga clic en **Guardar**.

Después de que se han guardado los cambios, el nuevo número de teléfono de forma predeterminada los números se incluirá en la reunión invitaciones de los organizadores de la próxima vez que programan una reunión nueva.

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Paso 3: Actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)

Para los dos pasos siguientes, debe iniciar Windows PowerShell.
  
Mediante el servicio de migración de la reunión, puede actualizar, opcionalmente, las invitaciones de reunión que ya se han enviado a los usuarios de su organización antes de que se han cambiado sus números de teléfono predeterminado. Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Ejecute el servicio de migración de reunión (MMS) para los usuarios que tenían sus números de teléfono predeterminado ha cambiado en el paso 2. Para ello, ejecute el siguiente comando:

```
    Start-CsExMeetingMigration user@contoso.com
```

- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia


Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número. Debido a que se va a cambiar el número de teléfono, es importante que se debe actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si hay alguno) y para actualizar sus invitaciones a reuniones antes de que el número de teléfono sin asignar desde el puente de conferencia de audio existente.

Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, sus invitaciones a reuniones existentes podrían contener un número de teléfono que no funciona para que se unan a sus reuniones.

Para los primeros tres pasos, tendrá que iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Paso 1: los usuarios de actualización que tienen el número de teléfono para ser sin asignar como uno de sus números de forma predeterminada

Reemplace el pago predeterminado o el número de teléfono gratuito para todos los usuarios que tienen el número para ser sin asignar como un número predeterminado e iniciar el proceso de volver a programar sus reuniones. Para ello, ejecute el siguiente comando:

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >También puede cambiar el pago predeterminado o el número de teléfono gratuito de usuarios en el Skype para el centro de administración de negocio. No obstante, en este modo no se volverán a programar las reuniones automáticamente. 
 
 Para obtener más información, vea [Configurar el teléfono los números incluidos en invitaciones en los equipos de Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) o [el teléfono los números incluidos en invitaciones en Skype para profesionales en línea](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Todas las reuniones se volverá a programar una vez que no hay ninguna operación en estado *pendiente* o *En curso* .

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Paso 3: cancelar la asignación del antiguo número de teléfono desde el puente de conferencia de audio

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al **Centro de administración de Office 365** > **centros de administración** > **equipos & Skype** > **portal heredado** > **voz** > **los números de teléfono**.

3. Seleccione el número de teléfono de la lista y, en el panel de acciones, haga clic en **Cancelar asignación**.

4. En la ventana confirmación, haga clic en **Sí**.

   > [!IMPORTANT]
   > Una vez sin asignar un puente de conferencia de audio de un número de teléfono, el número de teléfono ya no estará disponible para los usuarios participar en reuniones nuevas o existentes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar que Windows PowerShell está listo

 Estos pasos comprobación que se están ejecutando Windows PowerShell versión 3.0 o posterior.

1. Escriba **menú Inicio** > **Windows PowerShell**.

2. Escriba _Get-Host_ en la ventana de **Windows PowerShell** para comprobar la versión.

3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.

4. También debe instalar el módulo de Windows PowerShell para Skype para profesionales en línea que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype para profesionales en línea. En este módulo sólo se admite en equipos de 64 bits y se puede descargar desde Microsoft Download Center en el [Módulo de Windows PowerShell para Skype para profesionales en línea](https://go.microsoft.com/fwlink/?LinkId=294688).
Reinicie el equipo cuando se le solicite.

Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Para iniciar Windows PowerShell

 **Iniciar una sesión de Windows PowerShell**

1. En el **menú Inicio** > **Windows PowerShell**.

2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [Connecting to Skype para profesionales en línea mediante Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Ahorrar tiempo y automatizar

Para ahorrar tiempo mediante la automatización de este proceso, puede usar el [Conjunto CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o los cmdlets **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.

  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.

    > [!NOTE]
    > Para buscar el BridgeID, use el **Get-CsOnlineDialInConferencingBridge**.

  - Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que no tengan un número, ejecute:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para cambiar el número gratuito predeterminado de todos los usuarios que tienen el 8005551234 como su número gratuito predeterminado al 8005551239 y volver a programar automáticamente sus reuniones, ejecute:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que se encuentren en EE. UU. y volver a programar automáticamente sus reuniones, ejecute:

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > La ubicación que se usa arriba debe coincidir con la información de contacto de los usuarios establecidos en el Centro de administración de Office 365.

## <a name="about-windows-powershell"></a>Acerca de Windows PowerShell

Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer. Windows PowerShell puede ayudarle a administrar Office 365 y Skype para profesionales Online mediante un único punto de administración que puede simplificar su trabajo diario, especialmente cuando tiene varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Cambiar la configuración de un puente de Audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md)
