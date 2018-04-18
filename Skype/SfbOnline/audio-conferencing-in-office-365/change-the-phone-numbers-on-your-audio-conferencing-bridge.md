---
title: Cambiar los números de teléfono en el puente de conferencia de Audio
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Al adquirir licencias de conferencias de Audio, Microsoft aloja el puente de conferencia de audio para su organización. El puente de conferencia de audio proporciona los números de teléfono para acceso desde distintas ubicaciones para que los participantes y organizadores pueden utilizarlos para unir Skype para reuniones de negocios o Teams de Microsoft mediante un teléfono.
ms.openlocfilehash: cb38da52bd2c67a66e354b21712b8cc0d986796c
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiar los números de teléfono en el puente de conferencia de Audio

Al adquirir licencias de **Conferencias de Audio** , Microsoft aloja el *puente de conferencia de audio* para su organización. El puente de conferencia de audio proporciona los números de teléfono para acceso desde distintas ubicaciones para que los participantes y organizadores pueden utilizarlos para unir Skype para reuniones de negocios o Teams de Microsoft mediante un teléfono.
  
Además de los números de teléfono ya asignados para el puente de conferencia, puede [obtener los números de servicio adicionales](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (cuota y números de teléfono gratuitos utilizados para conferencias de audio) desde otras ubicaciones y, a continuación, asignar para la conferencia de puente para que pueda ampliar la cobertura para los usuarios.
  
> [!NOTE]
> Para poder asignar o desasignar a un número de teléfono de un puente de conferencia, el número de teléfono debe ser un número de '*service*'. Puede ver el tipo de número es desplazándose a **voz** > **números de teléfono** y buscar en la columna **Tipo de número** . Office 365 créditos de comunicaciones debe establecerse primero en orden para que los usuarios de marcado en el puente en un número gratuito. 
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Paso 1: asigne al nuevo número de teléfono para el puente de conferencia de audio

1. Inicie sesión en Office 365 con su cuenta profesional.
    
2. Ir al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **voz** > **números de teléfono**.
    
3. Seleccione el número de teléfono de la lista y en el panel Acción, haga clic en **asignar**.
    
4. En la página **Asignar**, haga clic en **Guardar**.
    
    Sólo un número de teléfono de servicio puede establecerse como el número predeterminado para el puente de conferencia; **números gratuitos del servicio no se puede establecer como el número predeterminado del puente de conferencia**. Si va a asignar a un número de teléfono de servicio y que le gustaría se establece como el número del nuevo para el puente de conferencia de audio, seleccione **usar este número como el valor predeterminado**.
    
    > [!NOTE]
    > Tras asignar un nuevo número de teléfono, incluso si el número ha pasado a ser el nuevo número predeterminado, no cambiará el número predeterminado de los usuarios existentes. Para establecer el número predeterminado o un número gratuito que se agrega a la reunión del organizador invita, vea [Configurar el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md). 
  
### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Paso 2: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Cuando se programa una reunión, los números de teléfono que se incluyen en las invitaciones de reunión son los predeterminados del usuario. Para obtener más información, consulte [Configurar el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Ir al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **conferencias de Audio** > **usuarios** y seleccione los usuarios en la lista.
    
3. Haga clic en **Editar** en el panel de acciones.
    
4. En **número de peaje predeterminado** o **predeterminado de número de teléfono gratuito**, seleccione el número en la lista y haga clic en **Guardar**.
    
Cuando se han guardado los cambios, el teléfono predeterminado nuevos números se incluirán en la reunión invita a organizadores de la próxima vez que programe una nueva reunión.
  
### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Paso 3: Actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)

Para los dos pasos siguientes, debe iniciar Windows PowerShell.
  
Con el servicio de migración de la reunión, opcionalmente puede actualizar invitaciones a reuniones que se enviaron a los usuarios de su organización antes de que se han cambiado sus números de teléfono predeterminados. Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
- Ejecutar el servicio de migración de reunión (MMS) para los usuarios que tenían sus números de teléfono predeterminado se cambió en el paso 2. Para ello, ejecute el siguiente comando:
    
```
    Start-CsExMeetingMigration user@contoso.com

```

- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .
    
```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia


Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número. Dado que está cambiando el número de teléfono, es importante para actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si existe) y actualizar sus invitaciones a reuniones antes de que el número de teléfono está asignado desde el puente de conferencia de audio existentes. 
  
Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcione para unirse a las reuniones.
  
Para los primeros tres pasos, tendrá que iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic en [desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)
  
### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Paso 1: Actualizar usuarios que puedan tener el número de teléfono cuya asignación se va a cancelar como uno de sus números predeterminados

Reemplace el número de teléfono gratuito o de pago predeterminado de todos los usuarios que tengan el número cuya asignación se va a cancelar como número predeterminado e inicie el proceso de volver a programar las reuniones. Para ello, ejecute el siguiente comando:
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >También puede cambiar el número predeterminado o número gratuito de los usuarios en el Skype para el centro de administración de negocios. Sin embargo, esto no volver a programar automáticamente sus reuniones. 
 
 Para obtener información adicional, consulte [el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).

  > [!NOTE]
  > Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo. 
  
### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Se volverá a programar todas las reuniones una vez que no hay ninguna operación en estado *pendiente* o *En curso* .
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Paso 3: Cancelar al antiguo número de teléfono desde el puente de conferencia de audio

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Ir al **Centro de administración de Office 365** > **centra Admin** > **Skype for Business** > **voz** > **números de teléfono**.
    
3. Seleccione el número de teléfono de la lista y en el panel Acción, haga clic en **asignar**.
    
4. En la ventana de confirmación, haga clic en **Sí**.
    
  > [!IMPORTANT]
  > Después de un número de teléfono no está asignado de un puente de conferencia de audio, el número de teléfono ya no estará disponible para que los usuarios puedan unirse a reuniones nuevas o existentes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar que Windows PowerShell está listo

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
### <a name="to-start-windows-powershell"></a>Para iniciar Windows PowerShell

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

Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
### <a name="save-time-or-automate"></a>Ahorrar tiempo o automatizar

Para ahorrar tiempo o automatizar este proceso, puede utilizar el [Conjunto CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) o los cmdlets de **Conjunto CsOnlineDialInConferencingUserDefaultNumber** .
  
- Use el cmdlet [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.
    
  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.
    
    > [!NOTE]
    > Para encontrar el BridgeID, utilice el **Get-CsOnlineDialInConferencingBridge**.
  
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

En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See also
[Cambiar la configuración de un puente de Audioconferencia](change-the-settings-for-an-audio-conferencing-bridge.md)
