---
title: Establecer el teléfono los números incluidos en invitaciones en Skype para profesionales en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: cb808cb8271cfb32174106e2692793aa41a64d50
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882117"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Establecer el teléfono los números incluidos en invitaciones en Skype para profesionales en línea

> [!Note]
> Para obtener información acerca de la reunión invitar a los números de teléfono en Microsoft Teams, vea [establecer el teléfono los números incluidos en invitaciones en los equipos de Microsoft](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Conferencias de audio en Office 365 permiten a los usuarios de la organización crear Skype para reuniones de negocios y, a continuación, permitir a los usuarios para conectarse a las reuniones utilizando un teléfono. En Office 365, tendrá la opción de utilizar un puente de conferencia de audio de Microsoft o un puente de conferencia de audio de terceros que está hospedado en un proveedor de conferencias de audio aprobadas (ACP).
  
> [!NOTE]
> No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia. Si está buscando para ver si hay números de teléfono de acceso telefónico disponibles en su área o país o región, utilice la **Skype para el centro de administración de negocio** > **voz** > **Los números de teléfono**, haga clic en **Agregar** , a continuación, **los nuevos números de servicio **. Use las listas de **País o región**, provincia o región de **** y **Ciudad** para filtrar la búsqueda. > también, si busca los números de teléfono de pago servicio gratuito, seleccione **gratuito** de la provincia o región **** lista.
  
Un puente de conferencia le proporciona un conjunto de números de teléfono de acceso telefónico para su organización. Todos ellos se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar cuáles se incluirá en sus invitaciones de reunión.
  
> [!NOTE]
> Puede haber un máximo de un teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación a la reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Establecer el número de teléfono de marcado predeterminado para un organizador de la reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. Seleccione **Usuarios**.
    
    ![Selección de los usuarios en el Skype para el centro de administración de negocio de muestra](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Elija los usuarios que desea editar:
    
  - Para seleccionar un único usuario, seleccione el nombre del usuario.
    
  - Para seleccionar todos los usuarios en la página, active la casilla situada junto al **nombre para mostrar** en la parte superior de la lista.
    
  - Para seleccionar varios usuarios, active la casilla situada junto a cada nombre de usuario.
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Elija **conferencias de Audio**.
    
7. En la página de **Propiedades** , en la lista **nombre del proveedor** , seleccione el proveedor para el usuario. Dependiendo del proveedor, complete los siguientes cuadros.
    
  - **Microsoft es el proveedor**: el **número de teléfono de pago predeterminado** y **número de teléfono gratuito predeterminada** listas para seleccionar los números de forma predeterminada para el usuario.
    
    > [!NOTE]
    > Debe asignarse al menos un número de teléfono gratuito para el puente de conferencia antes de que se puede establecer como el número de teléfono gratuito predeterminado de un usuario. Para obtener un número de teléfono gratuito, vea [números de teléfono de servicio de obtención de Skype para la empresa](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
  - **Un tercero es el proveedor**: Use los campos de **número de teléfono de pago** y **número de teléfono gratuito** para escribir los números para el usuario.


## <a name="reset-audio-conferencing-phone-numbers"></a>Restablecer los números de teléfono de conferencia de audio

1. En el **Skype para el centro de administración de negocio**, elija **conferencias de Audio**.
    
2. En la parte superior de la página, elija **usuarios**.
    
3. Elija los usuarios que desea restablecer y, a continuación, en el panel de acciones, haga clic en **Borrar**.
    
De forma predeterminada, cuando se cambia la configuración de conferencia de un usuario, se envía un correo electrónico al usuario. Para cambiar esta configuración, vea [Habilitar o deshabilitar el envío por correo electrónico cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Cuando se cambia la configuración de conferencia de audio de un usuario, periódica y futuro Skype para reuniones de negocios debe actualiza y se envía a los asistentes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.
    
    Para cambiar el número gratuito predeterminado de un usuario, ejecute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.
    
    > [!NOTE]
    > Para buscar el BridgeID, use el cmdlet **Get-CsOnlineDialInConferencingBridge** .
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para establecer el número de teléfono gratuito de forma predeterminada para todos los usuarios sin uno a +18005551234, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para cambiar el número de teléfono gratuito predeterminado de todos los usuarios que tienen +18005551234 como su número de teléfono gratuito predeterminado a +18005551239, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para establecer el número de teléfono gratuito predeterminado de todos los usuarios que se encuentra en los Estados Unidos a +18005551234, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>¿Desea obtener más información acerca de Windows PowerShell?
- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
