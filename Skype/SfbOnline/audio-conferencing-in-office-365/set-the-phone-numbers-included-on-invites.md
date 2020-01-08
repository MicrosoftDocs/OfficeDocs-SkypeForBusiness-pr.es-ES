---
title: Configurar los números de teléfono incluidos en los invitados en Skype empresarial online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 33c2f69cbd05efedf5af1bb35c7ea5d560930da4
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962518"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Configurar los números de teléfono incluidos en los invitados en Skype empresarial online

> [!Note]
> Para obtener más información sobre los números de teléfono de las invitaciones a reuniones en Microsoft Teams, consulte [configurar los números de teléfono incluidos en los invitados en Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Las conferencias de audio en Office 365 permiten a los usuarios de su organización crear reuniones de Skype empresarial y, a continuación, permitir que los usuarios llamen a esas reuniones con un teléfono. En Office 365, tiene la opción de usar un puente de conferencias de audio de Microsoft o un puente de conferencias de audio de terceros hospedado por un proveedor de servicios de audioconferencia (ACP) aprobado.
  
> [!NOTE]
> No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia. Si desea ver si hay números de teléfono de acceso telefónico local disponibles en su zona o país o región, use los > **números de teléfono****de telefonía del** **Centro** > de administración de Skype empresarial, haga clic en **Agregar** y luego en **nuevos números de servicio**. Use las listas de **país o región**, **Estado o región** y **ciudad** para filtrar la búsqueda. > también, si busca **números de servicio gratuitos, seleccione gratuito** en la lista **Estado o región** .
  
Un puente de conferencia le ofrece un conjunto de números de teléfono de acceso telefónico local para su organización. Todas ellas se pueden usar para unirse a las reuniones que ha creado el organizador de la reunión, pero puede seleccionar cuáles se incluirán en sus invitaciones a reuniones.
  
> [!NOTE]
> Puede haber un máximo de un número de teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Establecer el número de acceso telefónico local predeterminado para un organizador de la reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. Seleccione **Usuarios**.
    
    ![Muestra la selección de usuarios en el centro de administración de Skype empresarial](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Elija los usuarios que desea editar:
    
   - Para seleccionar un solo usuario, seleccione el nombre del usuario.
    
   - Para seleccionar todos los usuarios de la página, seleccione el cuadro que se encuentra junto a **nombre para mostrar** , en la parte superior de la lista.
    
   - Para seleccionar varios usuarios, seleccione el cuadro situado junto al nombre de cada usuario.
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Seleccione **audioconferencia**.
    
7. En la página **propiedades** , en la lista **nombre del proveedor** , elija el proveedor para el usuario. Según el proveedor, complete los siguientes cuadros.
    
   - **Microsoft es el proveedor**: usa el **número de pago predeterminado** y las listas de números gratuitos **predeterminadas** para seleccionar los números predeterminados para el usuario.
    
     > [!NOTE]
     > Se debe asignar al menos un número gratuito al puente de conferencia antes de que se pueda establecer como el número de teléfono gratuito predeterminado de un usuario. Para obtener un número gratuito, consulte [obtener números de teléfono de servicio para Skype empresarial](/microsoftteams/getting-service-phone-numbers). 
  
   - **Un tercero es el proveedor**: Use los campos **número de pago** y **número** gratuito para introducir los números del usuario.


## <a name="reset-audio-conferencing-phone-numbers"></a>Restablecer números de teléfono de audioconferencia

1. En el **centro de administración de Skype empresarial**, seleccione **audioconferencia**.
    
2. En la parte superior de la página, elija **usuarios**.
    
3. Elija los usuarios que desea restablecer y, a continuación, en el panel de acciones, haga clic en **Borrar**.
    
De forma predeterminada, al cambiar la configuración de conferencia de un usuario, se envía un correo electrónico al usuario. Para cambiar esto, vea [habilitar o deshabilitar el envío de correos electrónicos cuando cambia la configuración](enable-or-disable-sending-emails-when-their-settings-change.md)de las conferencias de audio.
  
> [!IMPORTANT]
> Al cambiar la configuración de la Conferencia de audio de un usuario, las reuniones periódicas y futuras de Skype empresarial deben actualizarse y enviarse a los asistentes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.
    
    Para cambiar el número gratuito predeterminado de un usuario, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.
    
    > [!NOTE]
    > Para encontrar el BridgeID, use el cmdlet **Get-CsOnlineDialInConferencingBridge** .
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para establecer el número gratuito predeterminado para todos los usuarios que no tengan entre 1 y + 18005551234, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para cambiar el número gratuito predeterminado de todos los usuarios que tienen + 18005551234 como su número gratuito predeterminado a + 18005551239, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para establecer el número gratuito predeterminado de todos los usuarios de Estados Unidos a + 18005551234, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>¿Quiere obtener más información sobre Windows PowerShell?
- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
