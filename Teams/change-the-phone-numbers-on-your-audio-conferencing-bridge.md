---
title: Cambiar los números de teléfono en el puente de audioconferencia
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
description: Obtenga información sobre los pasos necesarios para asignar un nuevo número de teléfono de servicio al puente de conferencias para expandir la cobertura para los usuarios.
ms.openlocfilehash: e2e1aa3d5626f6592f22e0850a8c7419d7549b38
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569192"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiar los números de teléfono de su puente de Audioconferencia

Al comprar licencias **de audioconferencia,** Microsoft hospeda el puente de audioconferencia para su organización. El puente de audioconferencia proporciona números de teléfono de acceso telefónico local de diferentes ubicaciones para que los organizadores y participantes de la reunión puedan usarlos para unirse a reuniones de Skype Empresarial o Microsoft Teams con un teléfono.
  
Además de los números de teléfono ya asignados al puente de conferencias, puede obtener números de servicio adicionales [(números](/microsoftteams/getting-service-phone-numbers) gratuitos y de pago usados para audioconferencias) de otras ubicaciones y, después, asignarlos al puente de conferencias para que pueda expandir la cobertura para los usuarios.
  
> [!NOTE]
> Para poder asignar o desasignar un número de teléfono para un puente de conferencias, el número de teléfono debe ser un número *de "servicio".* Para ver el tipo de número que es, vaya a Números de teléfono de voz en el Centro de administración de Microsoft Teams y busque en  >   la columna **Tipo de** número. Los créditos de comunicaciones de Microsoft 365 u Office 365 deben configurarse primero para que los usuarios puedan llamar al puente en un número gratuito.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Paso 1: Asignar el nuevo número de teléfono al puente de audioconferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Números de teléfono** de  >  **voz.**

2. Seleccione el número de teléfono de la lista y haga clic en **Editar.**

3. En la **página Editar,** en **Asignado a**, expanda el menú desplegable y, a continuación, seleccione Aplicar **puente de**  >  **conferencia.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Paso 2: cambiar el número de teléfono predeterminado del puente de conferencia (opcional)

El número de teléfono predeterminado del puente de conferencia define el identificador de llamada que se usará cuando un participante o el organizador coloquen una llamada saliente desde una reunión.

Solo se puede establecer un número de pago de servicio como el número predeterminado para el puente de conferencias; los números gratuitos del servicio no se pueden establecer **como el número predeterminado del puente de conferencias.** Si va a asignar un número de pago de servicio y desea establecerlo como el nuevo número predeterminado para el puente de audioconferencia, siga estos pasos:

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Puentes de conferencia**  >  **reuniones.**

2. Resalte el número de pago de servicio que desea configurar como predeterminado.

3. Haga clic en **Establecer como predeterminado**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Paso 3: Cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Los números de teléfono predeterminados de un usuario son los que se incluyen en las invitaciones de reunión cuando programan una reunión. Para obtener más información, incluido cómo se asignan los números de teléfono predeterminados a los nuevos usuarios, vea Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las invitaciones en [Skype Empresarial Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Usuarios** y haga clic en el nombre para mostrar del usuario deseado en la lista.

2. Junto a **Audioconferencia,** haga clic en **Editar.**

3. En **Número de pago** o Número **gratuito,** seleccione el número de la lista desplegable y haga clic en **Aplicar.**

Una vez aplicados los cambios, los nuevos números de teléfono predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que programe una nueva reunión.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Paso 4: Actualizar las invitaciones de reunión existentes de los usuarios con el servicio de migración de reuniones (opcional)

Para los dos pasos siguientes, deberá iniciar Windows PowerShell.
  
Si actualizó los números de teléfono predeterminados que se incluyen en las invitaciones de reunión para algunos o todos los usuarios, opcionalmente puede actualizar las invitaciones a reuniones que ya se enviaron a los usuarios de su organización antes de cambiar sus números de teléfono predeterminados con el Servicio de migración de reuniones. Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Ejecute el Servicio de migración de reuniones (MMS) para los usuarios que cambiaron sus números de teléfono predeterminados en el paso 2. Para ello, ejecute el siguiente comando:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia


Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número. Dado que el número de teléfono está cambiando, es importante actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si existe) y actualizar las invitaciones a reuniones existentes antes de que el número de teléfono no esté desasignado del puente de audioconferencia.

Si el número de teléfono se quita sin actualizar los usuarios y sus reuniones, las invitaciones a reuniones existentes podrían contener un número de teléfono que no funcionará para unirse a sus reuniones.

Para los primeros tres pasos, tendrá que iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Paso 1: Actualizar los usuarios que tienen el número de teléfono para que no se les haya desasignado uno de sus números predeterminados

Reemplace el número de pago o gratuito predeterminado para todos los usuarios que tengan el número que se va a desasignar como un número predeterminado e inicie el proceso de reprogramación de sus reuniones. Para ello, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >También puede cambiar el número predeterminado de usuarios gratuitos o de pago en el Centro de administración de Microsoft Teams. No obstante, en este modo no se volverán a programar las reuniones automáticamente. 
 
 Para obtener más información, vea Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las invitaciones [en Skype Empresarial Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Todas las reuniones se reprogramarán una vez que no haya operaciones *en* estado Pendiente o *En* curso.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Paso 3: Desasignar el número de teléfono antiguo del puente de audioconferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

2. Si el número de teléfono es un número gratuito, seleccione el número de teléfono de la lista y haga clic en **Liberar.** Si el número de teléfono es un número de pago, ponte en contacto con el soporte técnico [de Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) para que el número de teléfono no esté desasignado.

3. Si el número de teléfono es un número gratuito, haga clic **en Sí** en la ventana de confirmación.

   > [!IMPORTANT]
   > Después de que un número de teléfono no se haya desasignado de un puente de audioconferencia, el número de teléfono ya no estará disponible para que los usuarios se unan a reuniones nuevas o existentes.

### <a name="save-time-and-automate"></a>Ahorrar tiempo y automatizar

Para ahorrar tiempo automatizando este proceso, puede usar los [cmdlets Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**

- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.

  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.

    > [!NOTE]
    > Para buscar el BridgeID, use **get-CsOnlineDialInConferencingBridge**.

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

**El botón Desasignación no está disponible**

Desea desasignar un número, pero el botón no está disponible y, si mientras mantiene el puntero sobre él, se le redirigirá para ponerse en contacto con el soporte técnico con el siguiente mensaje: "Los números predeterminados o compartidos no se pueden desasignar desde el _puente. Para desasignación de números de pago dedicados, póngase en contacto con el soporte técnico."._

Para obtener más información sobre los puentes, ejecute el siguiente Powershell:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

El resultado, aparte de otra información como Identidad, Nombre y Región, también debe contener defaultservicenumber.

**Ejemplo**, para desasignar, defaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Acerca de Windows PowerShell

Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer. Windows PowerShell puede ayudarle a administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, especialmente cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados
[Cambiar la configuración de un puente de Audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).
