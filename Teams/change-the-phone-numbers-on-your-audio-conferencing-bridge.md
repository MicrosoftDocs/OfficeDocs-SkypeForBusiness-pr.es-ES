---
title: Cambiar números de teléfono en el puente de audioconferencia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Aprenda los pasos necesarios para asignar un nuevo número de teléfono de servicio a su puente de conferencia para expandir la cobertura de los usuarios.
ms.openlocfilehash: 233678bd953046eed5e6425e0b1a36c5a39b1061
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780359"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiar los números de teléfono de su puente de Audioconferencia

Cuando compra licencias de **audioconferencia** , Microsoft hospeda su puente de audioconferencia para su organización. El puente de audioconferencia ofrece números de teléfono de acceso telefónico local de diferentes ubicaciones para que los organizadores y los participantes de las reuniones puedan usarlos para unirse a las reuniones de Skype empresarial o Microsoft Teams con un teléfono.
  
Además de los números de teléfono asignados a su puente de conferencia, puede [obtener números de servicio adicionales](/microsoftteams/getting-service-phone-numbers) (números de pago y gratuitos usados en las conferencias de audio) desde otras ubicaciones y, a continuación, asignarlos al puente de conferencia para poder ampliar la cobertura de los usuarios.
  
> [!NOTE]
> Para poder asignar o cancelar la asignación de un número de teléfono para un puente de conferencia, el número de teléfono debe ser un número de "*servicio*". Puede ver el tipo de número al que navega por los números de **Voice** > **teléfono** de voz en el portal heredado y buscando en la columna **tipo de número** . Los Créditos de comunicaciones de Office 365 deben configurarse primero para que los usuarios puedan marcar en el puente un número gratuito.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Paso 1: asignar el nuevo número de teléfono a su puente de audioconferencia

1. Inicie sesión en Office 365 con su cuenta profesional.

2. Vaya a **Microsoft 365 administración del centro** > **Admin centers** > de administración de los**equipos &** > **los números de teléfono**de**voz** > del > **portal heredado**de Skype.

3. Seleccione el número de teléfono de la lista y, en el panel de acciones, haga clic en **asignar**.

4. En la página **Asignar**, haga clic en **Guardar**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Paso 2: cambiar el número de teléfono predeterminado del puente de conferencia (opcional)

El número de teléfono predeterminado del puente de conferencia define la identificación de llamadas que se usará cuando un participante o el organizador de una reunión Coloque una llamada saliente.

Solo se puede establecer un número de teléfono de pago de servicio como número predeterminado para el puente de conferencia. los **números gratuitos de servicio no pueden establecerse como el número predeterminado del puente de conferencia**. Si va a asignar un número de teléfono de pago y desea configurarlo como el nuevo número predeterminado para su puente de audioconferencias, siga estos pasos:

1. Inicie sesión en Office 365 con su cuenta profesional.

2. Vaya a la**Administración** > del **Centro** > de administración de 365 de Microsoft**Teams &** > de**Conferencia**de**reuniones** > de Skype.

3. Resalte el número de teléfono del servicio que desea configurar como predeterminado.

4. Haga clic en **Establecer como predeterminado**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Paso 3: cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Los números de teléfono predeterminados de un usuario son los que se incluyen en sus invitaciones a reuniones al programar una reunión. Para obtener más información, como la forma en que se asignan los números de teléfono de defaul para los nuevos usuarios, vea [establecer los números de teléfono incluidos en los invitados en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o [configurar los números de teléfono incluidos en los invitados en Skype empresarial online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Inicie sesión con su cuenta profesional o educativa.

2. Vaya a los **Microsoft 365 admin center** > **centros** > de administración de centro de administración de 365 de Microsoft**Teams &** > **usuarios**de la**Conferencia** > de audio del > **portal heredado**de Skype y seleccione los usuarios de la lista.

3. Haga clic en **Editar** en el panel de acciones.

4. En número de **teléfono de pago predeterminado** o **número gratuito predeterminado**, seleccione el número en la lista y haga clic en **Guardar**.

Después de guardar los cambios, los nuevos números de teléfono predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que programen una nueva reunión.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Paso 4: actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)

Para los dos pasos siguientes, tendrá que iniciar Windows PowerShell.
  
Si ha actualizado los números de teléfono predeterminados que se inlcuded en las invitaciones a reuniones para algunos o todos los usuarios, puede actualizar, opcionalmente, las invitaciones de reunión que ya se han enviado a los usuarios de su organización antes de que se cambiaran sus números de teléfono predeterminados con el servicio de migración de reuniones. Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Ejecute el servicio de migración de reuniones (MMS) para los usuarios que han cambiado sus números de teléfono predeterminados en el paso 2. Para ello, ejecute el siguiente comando:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia


Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número. Dado que el número de teléfono está cambiando, es importante actualizar todos los usuarios que puedan tener un número de teléfono como número predeterminado (si existe) y actualizar sus invitaciones de reunión existentes antes de que el número de teléfono no se haya asignado al puente de audioconferencia.

Si el número de teléfono se quita sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcionará para unirse a sus reuniones.

Para los primeros tres pasos, tendrá que iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Paso 1: actualizar los usuarios que tienen el número de teléfono para que no se asigne como uno de sus números predeterminados

Reemplace el número de pago o el número gratuito predeterminado para todos los usuarios que tengan el número que se va a desasignar como número predeterminado e inicie el proceso de reprogramar sus reuniones. Para ello, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >También puede cambiar el número de pago predeterminado o gratuito de los usuarios en el centro de administración de Skype empresarial. No obstante, en este modo no se volverán a programar las reuniones automáticamente. 
 
 Para obtener más información, consulte [establecer los números de teléfono incluidos en los invitados en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o [configurar los números de teléfono incluidos en los invitados en Skype empresarial online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Todas las reuniones se volverán a programar una vez que no haya operaciones en estado *pendiente* o *en curso* .

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Paso 3: cancelar la asignación del número de teléfono anterior desde el puente de audioconferencia

1. Inicie sesión con su cuenta profesional o educativa.

2. Vaya a los **Microsoft 365 admin center** > **centros** > de administración de centro de administración de 365 de Microsoft**Teams &** > **números de teléfono**de**voz** > del > **portal heredado**de Skype.

3. Si el número de teléfono es un número gratuito, seleccione el número de teléfono de la lista y, en el panel de acciones, haga clic en **Cancelar asignación**. Si el número de teléfono es un número de teléfono, comunícate con el [soporte técnico de Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) para que no se haya asignado el número de teléfono.

4. Si el número de teléfono es un número fre, haga clic en **sí** en la ventana de confirmación.

   > [!IMPORTANT]
   > Una vez que se ha desasignado un número de teléfono de un puente de audioconferencia, el número dejará de estar disponible para que los usuarios puedan unirse a reuniones nuevas o existentes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar que Windows PowerShell está listo

 Estos pasos comprueban que está ejecutando Windows PowerShell versión 3,0 o posterior.

1. Escriba **menú Inicio** > **Windows PowerShell**.

2. Escriba _Get-Host_ en la ventana de **Windows PowerShell** para comprobar la versión.

3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0.
Reinicie el equipo cuando se le solicite.

4. También tiene que instalar el módulo Windows PowerShell para Skype empresarial online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype empresarial online. Este módulo solo es compatible con equipos de 64 bits y puede descargarse desde el centro de descarga de Microsoft en el [módulo de Windows PowerShell para Skype empresarial online](https://go.microsoft.com/fwlink/?LinkId=294688).
Reinicie el equipo cuando se le solicite.

Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Para iniciar Windows PowerShell

 **Iniciar una sesión de Windows PowerShell**

1. En el **menú Inicio** > **Windows PowerShell**.

2. En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [conectarse a Skype empresarial online mediante Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Ahorra tiempo y automatización

Para ahorrar tiempo automatizando este proceso, puede usar los cmdlets [set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **set-CsOnlineDialInConferencingUserDefaultNumber** .

- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.

  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.

    > [!NOTE]
    > Para encontrar la BridgeID, use el **Get-CsOnlineDialInConferencingBridge**.

  - Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que no tengan un número, ejecute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para cambiar el número gratuito predeterminado de todos los usuarios que tienen el 8005551234 como su número gratuito predeterminado al 8005551239 y volver a programar automáticamente sus reuniones, ejecute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Para establecer el 8005551234 como número gratuito predeterminado para todos los usuarios que se encuentren en EE. UU. y volver a programar automáticamente sus reuniones, ejecute:

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > La ubicación que se usa anteriormente debe coincidir con la información de contacto de los usuarios que se establecen en el centro de administración de Microsoft 365.

## <a name="troubleshooting"></a>Solución de problemas

**El botón de anulación de asignación está atenuado**

Desea cancelar la asignación de un número pero el botón está atenuado y, si mientras hoovering sobre él, se le redirige para ponerse en contacto con el soporte técnico con el siguiente mensaje: _"predeterminado o los números compartidos ́t se pueden cancelar desde el puente. Para cancelar la asignación de números de teléfono dedicados, póngase en contacto con el soporte técnico._".

Para obtener más información sobre los puentes, ejecute el siguiente PowerShell:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

El resultado, además de otra información como, por ejemplo, la identidad, el nombre y la región, debe contener el DefaultServiceNumber.

**Ejemplo**, para desasignar, el DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Acerca de Windows PowerShell

Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer. Windows PowerShell puede ayudarle a administrar Office 365 y Skype empresarial online mediante un único punto de administración que puede simplificar su trabajo diario, especialmente cuando tiene varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados
[Cambiar la configuración de un puente de Audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).
