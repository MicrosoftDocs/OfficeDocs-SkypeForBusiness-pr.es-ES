---
title: Cambiar los números de teléfono de su puente de Audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
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
description: Cuando adquiere licencias de Audioconferencia, Microsoft aloja el puente de audioconferencia de su organización. El puente de audioconferencia distribuye números de teléfono de acceso telefónico local de diferentes ubicaciones, de forma que los organizadores de la reunión y los participantes puedan utilizarlos para unirse a las reuniones de Skype for Business o Microsoft Teams mediante el teléfono.
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255715"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiar los números de teléfono de su puente de Audioconferencia

Cuando adquiere **licencias de Audioconferencia**, Microsoft aloja el *puente de audioconferencia* de su organización. El puente de audioconferencia distribuye números de teléfono de acceso telefónico local de diferentes ubicaciones, de forma que los organizadores de la reunión y los participantes puedan utilizarlos para unirse a las reuniones de Skype for Business o Microsoft Teams mediante el teléfono.

Además de los números de teléfono que ya se hayan asignado al puente de conferencia, puede [Obtener números de servicio adicionales](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (números gratuitos y de pago utilizados para audioconferencias) desde otra ubicación y asignarlos al puente de conferencia, con el fin de ampliar la cobertura para los usuarios.

> [!NOTE]
> Para poder asignar o quitar la asignación de un número de teléfono a un puente de conferencia, el número de teléfono debe ser un número "*de servicio*". Puede ver qué tipo de número de teléfono yendo a **Voz** > **Números de teléfono** y mirando en la columna **Tipo de número**. Los Créditos de comunicaciones de Office 365 deben configurarse primero para que los usuarios puedan marcar en el puente un número gratuito.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Paso 1: Asignar el número de teléfono nuevo a su puente de audioconferencia

1. Inicie sesión en Office 365 con su cuenta profesional.

2. Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Voz** > **Números de teléfono**.

3. Seleccione el número de teléfono en la lista y, en el panel de Acción, haga clic en **Asignar**.

4. En la página **Asignar**, haga clic en **Guardar**.

    Solo puede establecerse un número de servicio de pago como número predeterminado para el puente de conferencia; **los números gratuitos de servicio no pueden establecerse como número predeterminado del puente de conferencia**. Si asigna un número de servicio de pago y le gustaría establecer un nuevo número predeterminado para el puente de audioconferencia, seleccione **Utilizar este número como predeterminado**.

    > [!NOTE]
    > Tras asignar un nuevo número de teléfono, incluso si el número ha pasado a ser el nuevo número predeterminado, no cambiará el número predeterminado de los usuarios existentes. Para establecer el número de pago o gratuito predeterminado que se agrega a las invitaciones de reunión del organizador, consulte [Establecer los números de teléfono que se incluyen en invitaciones](set-the-phone-numbers-included-on-invites.md).



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Paso 2: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Cuando se programa una reunión, los números de teléfono que se incluyen en las invitaciones de reunión son los predeterminados del usuario. Para obtener más información, vea [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites.md).

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Audioconferencia** > **Usuarios** y seleccione los usuarios en la lista.

3. Haga clic en **Editar** en el panel de acciones.

4. En **Número de teléfono de pago predeterminado** o **Número de teléfono gratuito predeterminado**, seleccione el número en la lista y haga clic en **Guardar**.

Cuando los cambios se hayan guardado, los números de teléfono nuevos predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que se programe una nueva reunión.

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Paso 3: Actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)

Para los siguientes dos pasos, tendrá que iniciar Windows PowerShell.

Al utilizar el servicio de migración de reuniones podrá decidir si quiere actualizar las invitaciones de reunión que se enviaron a los usuarios de su organización antes de cambiar los números de teléfono predeterminados. Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md).

- Ejecute el servicio de migración de reuniones (MMS) para los usuarios a los que se les cambiaron los números de teléfono predeterminados en el paso 2. Para ello, ejecute el siguiente comando:

```
    Start-CsExMeetingMigration user@contoso.com
```

- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia


Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número. Dado que el número de teléfono va a cambiar, es importante actualizar todos los usuarios que puedan tener un número de teléfono como su número predeterminado (en caso de tenerlo) y actualizar las invitaciones de reunión existentes antes de que se quite la asignación del número de teléfono del puente de audioconferencia.

Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcione para unirse a las reuniones.

Para los primeros tres pasos, tendrá que iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Paso 1: Actualizar usuarios que puedan tener el número de teléfono cuya asignación se va a cancelar como uno de sus números predeterminados

Reemplace el número de teléfono gratuito o de pago predeterminado de todos los usuarios que tengan el número cuya asignación se va a cancelar como número predeterminado e inicie el proceso de volver a programar las reuniones. Para ello, ejecute el siguiente comando:

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 >También puede cambiar el número gratuito o de pago predeterminado de los usuarios en el centro de administración de Skype for Business. No obstante, en este modo no se volverán a programar las reuniones automáticamente.

 Para obtener más información, vea [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites.md).

  > [!NOTE]
  > Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado *Pendiente* o *En curso*.

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md).

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Paso 3: Quitar la asignación del número de teléfono anterior del puente de audioconferencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al **Centro de administración de Office 365** > **Centros de administración** > **Skype for Business** > **Voz** > **Números de teléfono**.

3. Seleccione el número de teléfono en la lista y, en el panel de Acción, haga clic en **Quitar asignación**.

4. En la ventana confirmación, haga clic en **Sí**.

  > [!IMPORTANT]
  > Una vez quitada la asignación a un puente de audioconferencia de un número de teléfono, este dejará de estar disponible para los usuarios que se unan a reuniones nuevas o existentes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar que Windows PowerShell está listo

 Con estos pasos podrá comprobar que está ejecutando Windows PowerShell versión 3.0 o superior

1. Escriba **menú Inicio** > **Windows PowerShell**.

2. Escriba _Get-Host_ en la ventana de **Windows PowerShell** para comprobar la versión.

3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.

4. También debe instalar el módulo Windows PowerShell para Skype for Business Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype for Business Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga Microsoft en el [Módulo de Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
Reinicie el equipo cuando se le solicite.

Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Para iniciar Windows PowerShell

 **Iniciar una sesión de Windows PowerShell**

1. En el **menú Inicio** > **Windows PowerShell**.

2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:

    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype for Business Online.

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

Si desea obtener más información sobre cómo iniciar Windows PowerShell, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Conectarse a Skype for Business Online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Ahorrar tiempo y automatizar

Para ahorrar tiempo automatizando este proceso, puede utilizar los cmdlets [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber**.

- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.

  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.

    > [!NOTE]
    > Para buscar el id. de puente, use **Get-CsOnlineDialInConferencingBridge**.

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

Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer. Windows PowerShell puede ayudarlo a administrar Office 365 y Skype for Business Online mediante un único punto de administración que puede simplificar su trabajo diario, especialmente cuando deba realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Cambiar la configuración de un puente de Audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md)
