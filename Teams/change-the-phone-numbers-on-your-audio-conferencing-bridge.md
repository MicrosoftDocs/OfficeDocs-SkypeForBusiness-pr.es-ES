---
title: Cambiar los números de teléfono en el puente de Audioconferencia
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
description: Conozca los pasos necesarios para asignar un nuevo número de teléfono de servicio a su puente de conferencia para ampliar la cobertura para los usuarios.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918756"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Cambiar los números de teléfono de su puente de Audioconferencia

Cuando compra licencias **de Audioconferencia,** Microsoft hospeda el puente de audioconferencia para su organización. El puente de audioconferencia proporciona números de teléfono de acceso telefónico local de diferentes ubicaciones para que los organizadores y participantes de la reunión puedan usarlos para unirse a las reuniones de Skype Empresarial o Microsoft Teams con un teléfono.
  
Además de los números de teléfono ya asignados al puente de conferencia, puede obtener números de servicio adicionales [(números](/microsoftteams/getting-service-phone-numbers) de pago y gratuitos utilizados para audioconferencias) desde otras ubicaciones y asignarlos al puente de conferencia para que pueda ampliar la cobertura para los usuarios.
  
> [!NOTE]
> Para poder asignar o desasignar un número de teléfono a un puente de conferencia, el número de teléfono debe ser un número *de* servicio '. Para ver el tipo de número, vaya a Números de teléfono de voz en el Centro de administración de Microsoft Teams y busque en la  >   columna **Tipo de** número. Los créditos de comunicaciones de Microsoft 365 u Office 365 deben configurarse primero para que los usuarios puedan llamar al puente desde un número gratuito.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Pasos para asignar un número de teléfono de servicio nuevo a su puente de conferencia

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Paso 1: Asignar el nuevo número de teléfono al puente de audioconferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a Números **de teléfono de**  >  **voz.**

2. Seleccione el número de teléfono de la lista y haga clic en **Editar.**

3. En la **página Editar,** en **Asignado a,** expanda la lista desplegable y, después, seleccione **Aplicar puente de**  >  **conferencia.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Paso 2: Cambiar el número de teléfono predeterminado del puente de conferencia (opcional)

El número de teléfono predeterminado del puente de conferencia define el identificador de llamada que se usará cuando un participante o el organizador realizará una llamada saliente desde dentro de una reunión.

Solo se puede establecer un número de servicio de pago como número predeterminado para el puente de conferencia; los números de servicio gratuitos no se pueden establecer **como el número predeterminado del puente de conferencia.** Si asigna un número de servicio de pago y le gustaría establecerlo como el nuevo número predeterminado para el puente de audioconferencia, realice estos pasos:

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya **a Puentes de conferencia de**  >  **reuniones.**

2. Resalte el número de servicio de pago que desea configurar como predeterminado.

3. Haga clic en **Establecer como predeterminado**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Paso 3: cambiar los números de teléfono predeterminados que se incluyen en las invitaciones de reunión de los usuarios (opcional)

Cuando se programa una reunión, los números de teléfono predeterminados de un usuario son los que se incluyen en las invitaciones a la reunión. Para obtener más información, incluido cómo se asignan los números de teléfono predeterminados a los nuevos usuarios, vea Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las invitaciones [en Skype Empresarial Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya **a Usuarios** y haga clic en el nombre para mostrar del usuario deseado en la lista.

2. Junto a **Audioconferencia,** haga clic en **Editar.**

3. En **Número de pago** o Número **gratuito,** seleccione el número en la lista desplegable y haga clic en **Aplicar.**

Una vez que se hayan aplicado los cambios, los nuevos números de teléfono predeterminados se incluirán en las invitaciones de reunión de los organizadores la próxima vez que se programe una nueva reunión.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Paso 4: Actualizar las invitaciones de reunión existentes de los usuarios que usan el servicio de migración de reuniones (opcional)

Para los dos pasos siguientes, deberá iniciar la Windows PowerShell.
  
Si ha actualizado los números de teléfono predeterminados que se incluyen en las invitaciones de reunión para algunos o todos los usuarios, puede actualizar las invitaciones de reunión que ya se enviaron a los usuarios de su organización antes de que se cambiaran sus números de teléfono predeterminados con el servicio de migración de reuniones. Para obtener información adicional, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Ejecute el Servicio de migración de reuniones (MMS) para los usuarios a los que se les cambiaron los números de teléfono predeterminados en el paso 2. Para ello, ejecute el siguiente comando:

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- También puede ver el estado de migración de las reuniones. Todas las reuniones se volverán a programar cuando no quede ninguna operación con el estado  *Pendiente*  o *En curso*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Pasos para quitar la asignación de un número de teléfono de servicio de su puente de conferencia


Cuando quite la asignación de un número de teléfono de un puente de conferencia, los usuarios ya no podrán volver a unirse a las reuniones con ese número. Como el número de teléfono va a cambiar, es importante actualizar todos los usuarios que podrían tener un número de teléfono como su número predeterminado (si los hay) y actualizar las invitaciones de reunión existentes antes de que se desasigne el número de teléfono del puente de audioconferencia.

Si se quita el número de teléfono sin actualizar los usuarios y sus reuniones, las invitaciones de reunión existentes podrían contener un número de teléfono que no funcionará para unirse a sus reuniones.

Para los primeros tres pasos, tendrá que iniciar Windows PowerShell. Para ver cómo hacerlo, haga clic en [¿Desea saber cómo administrar con Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Paso 1: Actualizar los usuarios que tienen el número de teléfono para que se les desasigne como uno de sus números predeterminados

Reemplace el número de teléfono gratuito o de pago predeterminado de todos los usuarios que tengan el número para el que se va a eliminar la firma como un número predeterminado e inicie el proceso de volver a programar sus reuniones. Para ello, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >También puede cambiar el número gratuito o de pago predeterminado de los usuarios en el Centro de administración de Microsoft Teams. No obstante, en este modo no se volverán a programar las reuniones automáticamente. 
 
 Para obtener información adicional, consulte Establecer los números de teléfono [incluidos](set-the-phone-numbers-included-on-invites-in-teams.md) en las invitaciones en Microsoft Teams o Establecer los números de teléfono incluidos en las [invitaciones en Skype Empresarial Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > Dependiendo de cuál sea el tamaño de su organización, este proceso podría llevar algún tiempo.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Paso 2: Ver el estado de migración de las reuniones con Windows PowerShell

Todas las reuniones se volverán a programar cuando no haya ninguna operación con *estado* pendiente o *en* curso.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Para obtener más información sobre el servicio de migración de reuniones, consulte [Configuración del servicio de migración de reuniones (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Paso 3: Desasignar el número de teléfono anterior del puente de audioconferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Voz** > **Números de teléfono**.

2. Si el número de teléfono es gratuito, selecciónelo de la lista y haga clic en **Liberar.** Si el número de teléfono es un número de pago, ponte en contacto con el soporte técnico de [Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) para que se desasigne el número de teléfono.

3. Si el número de teléfono es gratuito, haga clic en **Sí en** la ventana de confirmación.

   > [!IMPORTANT]
   > Una vez que se desasigne un número de teléfono a un puente de audioconferencia, el número de teléfono ya no estará disponible para los usuarios que se unan a reuniones nuevas o existentes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Para verificar que Windows PowerShell está listo

 Estos pasos comprueban que está ejecutando Windows PowerShell versión 3.0 o superior.

1. Escriba **menú Inicio** > **Windows PowerShell**.

2. Escriba _Get-Host_ en la ventana de **Windows PowerShell** para comprobar la versión.

3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0.
Reinicie el equipo cuando se le solicite.

4. También debe instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online. Este módulo solo es compatible con equipos de 64 bits y se puede descargar desde el Centro de descarga de Microsoft en [Windows PowerShell Module para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
Reinicie el equipo cuando se le solicite.

Si necesita más información, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.

### <a name="to-start-windows-powershell"></a>Para iniciar Windows PowerShell

 **Iniciar una sesión de Windows PowerShell**

1. En el **menú Inicio** > **Windows PowerShell**.

2. En la **Windows PowerShell** de correo electrónico, conéctese a Microsoft 365 u Office 365 ejecutando:

> [!NOTE]
> Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
>
> Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Conectarse a Skype Empresarial [Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)mediante el Windows PowerShell.

### <a name="save-time-and-automate"></a>Ahorre tiempo y automatice

Para ahorrar tiempo mediante la automatización de este proceso, puede usar [los cmdlet Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) o **Set-CsOnlineDialInConferencingUserDefaultNumber.**

- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.

  - Para cambiar el número gratuito predeterminado de un usuario, ejecute:

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.

    > [!NOTE]
    > Para buscar el Id. de puente, use **Get-CsOnlineDialInConferencingBridge.**

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
    > La ubicación que se usa arriba debe coincidir con la información de contacto de los usuarios establecidos en el Centro de administración de Microsoft 365.

## <a name="troubleshooting"></a>Solución de problemas

**El botón Desasignación no está disponible**

Quiere cancelar lasignación de un número, pero el botón no está disponible y, si al mantener el puntero sobre él, se le redirige al soporte técnico con el siguiente mensaje: "No se puede cancelar la firma de los números predeterminados o compartidos del _puente. Para desasignir números de pago dedicados, póngase en contacto con el soporte técnico._".

Para obtener más información sobre los puentes, ejecute el siguiente PowerShell:
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

El resultado, salvo otra información como Identidad, Nombre y Región, también debe contener el DefaultServiceNumber.

**Ejemplo,** para desasignar, el valor DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Acerca de Windows PowerShell

Con Windows PowerShell puede administrar los usuarios y lo que pueden o no pueden hacer. Windows PowerShell puede ayudarle a administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, especialmente si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Temas relacionados
[Cambiar la configuración de un puente de Audioconferencias](change-the-settings-for-an-audio-conferencing-bridge.md).
