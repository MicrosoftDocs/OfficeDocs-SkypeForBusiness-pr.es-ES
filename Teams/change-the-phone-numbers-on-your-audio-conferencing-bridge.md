---
title: Cambiar los números de teléfono en Audioconferencia puente
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Obtenga información sobre los pasos necesarios para asignar un nuevo número de teléfono de servicio a su puente de conferencia para expandir la cobertura para los usuarios.
ms.openlocfilehash: 0433577334dca5f84854ba1cdc14b81e4ec37e63
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674782"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiar los números de teléfono de su puente de Audioconferencia

Al comprar licencias **de Audioconferencia**, Microsoft hospeda el puente de audioconferencia para su organización. El puente de audioconferencia proporciona números de teléfono de acceso telefónico local de diferentes ubicaciones para que los organizadores de la reunión y los participantes puedan usarlos para unirse a Skype Empresarial o Microsoft Teams reuniones con un teléfono.

Además de los números de teléfono que ya está asignados al puente de conferencia, puede [obtener números de servicio adicionales (números](./getting-service-phone-numbers.md) de pago y gratuitos que se usan para las audioconferencias) de otras ubicaciones y asignarlos al puente de conferencia para poder ampliar la cobertura para los usuarios.

> [!NOTE]
> Para poder asignar o quitar la asignación de un número de teléfono a un puente de conferencia, el número de teléfono debe ser un número de "*servicio*". Para ver el tipo de número, vaya a **Voz** >  **Teléfono números** en el centro de administración de Microsoft Teams y busque en la columna **Tipo de número**. Microsoft 365 o Office 365 créditos de comunicaciones deben configurarse primero para que los usuarios llamen al puente en un número gratuito.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia

> [!NOTE]
> Excepto donde se indique lo contrario, todos estos pasos deben realizarse en el centro de administración de Microsoft Teams.

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Paso 1: Asignar el nuevo número de teléfono a su puente de audioconferencia

1. En el panel de navegación izquierdo, vaya a **Voz** >  **Teléfono números**.

2. Seleccione el número de teléfono de la lista y haga clic en **Editar**.

3. En la página **Editar**, en **Asignado a**, expanda la lista desplegable y, a continuación, seleccione **Aplicar** puente  > **de conferencia**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Paso 2: Cambiar el número de teléfono predeterminado del puente de conferencia (opcional)

El número de teléfono predeterminado del puente de conferencia define el identificador de llamada que se usará cuando un participante o el organizador realice una llamada saliente desde una reunión.

Solo se puede establecer un número de servicio de pago como número predeterminado para el puente de conferencia; **los números gratuitos de servicio no se pueden establecer como el número predeterminado del puente de conferencia**. Si va a asignar un número de servicio de pago y desea establecerlo como el nuevo número predeterminado para el puente de audioconferencia, siga estos pasos:

1. En el panel de navegación izquierdo, vaya a **Puentes** de **conferencia de** >  reuniones.

2. Resalte el número de servicio de pago que desea configurar como predeterminado.

3. Haga clic en **Establecer como predeterminado**.

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Paso 3: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Consulte [Establecer los números de teléfono incluidos en las invitaciones de Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> También puede establecer números de teléfono agregándolos a *TeamsAudioconferencingpolicy* y asignando la directiva a los usuarios. Los números de teléfono gratuitos y de pago agregados a la directiva tienen prioridad sobre los números de teléfono establecidos individualmente para los usuarios a través del panel de configuración de audioconferencia. Si no se agrega ningún número de teléfono a *teamsaudioconferencingpolicy*, el número de teléfono configurado individualmente para los usuarios a través del panel de configuración de audioconferencia se mostrará en Microsoft Teams convocatorias de reunión. [Audioconferencia configuración de la directiva para números de pago y gratuitos](audio-conferencing-toll-free-numbers-policy.md) tiene más información.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Paso 4: Actualizar las invitaciones de reunión existentes de usuarios que usan el servicio de migración de reuniones (opcional)

Para los dos pasos siguientes, deberá iniciar Windows PowerShell.

Si ha actualizado los números de teléfono predeterminados que se incluyen en las invitaciones a la reunión para algunos o todos los usuarios, también puede actualizar las invitaciones de reunión que ya se enviaron a los usuarios de su organización antes de que se cambiaran sus números de teléfono predeterminados mediante el servicio de migración de reuniones. Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

- Ejecute el Servicio de migración de reuniones (MMS) para los usuarios que cambiaron sus números de teléfono predeterminados en el paso 2. Para ello, ejecute el siguiente comando:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia

Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número. Como el número de teléfono está cambiando, es importante actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si procede) y actualizar las invitaciones de reunión existentes antes de que el número de teléfono no se haya asignado del puente de audioconferencia.

Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcionará para unirse a sus reuniones.

Para los primeros tres pasos, tendrá que iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Paso 1: Actualizar los usuarios que tienen el número de teléfono que se va a quitar como uno de sus números predeterminados

Reemplace el número de pago o gratuito predeterminado de todos los usuarios que tengan el número que se va a cancelar como número predeterminado e inicie el proceso de volver a programar sus reuniones. Para ello, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >También puede cambiar el número gratuito o de pago predeterminado de los usuarios en el centro de administración de Microsoft Teams. No obstante, en este modo no se volverán a programar las reuniones automáticamente.

 Para obtener más información, vea [Establecer los números de teléfono incluidos en las invitaciones de Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) o [Establecer los números de teléfono incluidos en las invitaciones de Skype Empresarial En línea](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Todas las reuniones se volverán a programar cuando no haya ninguna operación en estado *Pendiente* o *En curso* .

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Paso 3: Quitar la asignación del número de teléfono antiguo del puente de audioconferencia

Usar el cmdlet Unregister-CsOnlineDialInConferencingServiceNumber para anular el registro de un número de pago o gratuito de un puente de conferencia

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

Nota: Para buscar el id. de puente de conferencia, ejecute el siguiente PowerShell: Get-CsOnlineDialInConferencingBridge.

   > [!IMPORTANT]
   > Una vez que se haya desasignado un número de teléfono de un puente de audioconferencia, el número de teléfono ya no estará disponible para que los usuarios se unan a reuniones nuevas o existentes.

### <a name="save-time-and-automate"></a>Ahorrar tiempo y automatizar

Para ahorrar tiempo automatizando este proceso, puede usar los [cmdlets Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) o **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Use el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.

  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.

    > [!NOTE]
    > Para buscar el Id. de puente, use **Get-CsOnlineDialInConferencingBridge**.

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
    > La ubicación que se usa anteriormente debe coincidir con la información de contacto de los usuarios que se establece en el Centro de administración de Microsoft 365.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="the-unassign-button-isnt-available"></a>El botón Desasignar no está disponible

Desea quitar la asignación de un número, pero el botón no está disponible y, si mantiene el puntero sobre él, se le redirige para ponerse en contacto con el soporte técnico con el siguiente mensaje: "Los números predeterminados o compartidos no se pueden quitar del puente. Para cancelar la asignación de números de pago dedicados, póngase en contacto con el servicio de soporte técnico".

Para obtener más información sobre los puentes, ejecute el siguiente Powershell:

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

El resultado, aparte de otra información como Identidad, Nombre y Región, también debe contener el DefaultServiceNumber.

**Ejemplo**, para anular la asignación, el DefaultServiceNumber "8005551234"

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234
```

## <a name="about-windows-powershell"></a>Acerca de Windows PowerShell

Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer. Windows PowerShell puede ayudarle a administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, especialmente cuando tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

- [Una introducción a Windows PowerShell y Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad con respecto al uso solo de los Centro de administración de Microsoft 365, como cuando se realizan cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

- [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- [Usar Windows PowerShell para administrar Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Temas relacionados

[Cambiar la configuración de un puente de Audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).
