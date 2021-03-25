---
title: Establecer los números de teléfono incluidos en las invitaciones en Skype Empresarial Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 956c2fa23f61f0c0e24cd1c2a0802bd3f1397bb1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113226"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Establecer los números de teléfono incluidos en las invitaciones en Skype Empresarial Online

> [!Note]
> Para obtener información sobre los números de teléfono de invitación a reuniones en Microsoft Teams, vea Establecer los números de teléfono [incluidos en las invitaciones en Microsoft Teams.](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)

Las audioconferencias en Microsoft 365 u Office 365 permiten a los usuarios de su organización crear reuniones de Skype Empresarial y, a continuación, permitir que los usuarios llamen a esas reuniones con un teléfono. En Microsoft 365 y Office 365, tiene la opción de usar un puente de audioconferencia de Microsoft o un puente de audioconferencia de terceros hospedado por un proveedor de audioconferencias (ACP) aprobado.
  
> [!NOTE]
> No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia. Si quiere ver si hay números de teléfono de acceso telefónico telefónico disponible en su área o país o región, use el Centro de administración de **Skype** Empresarial Números de teléfono de voz, haga clic en Agregar y, a continuación, en Nuevos números  >    >   **de servicio.**  Use las listas de **País/Región,** **Estado/Región** y **Ciudad** para filtrar la búsqueda.> Además, si  busca números de servicio gratuitos, seleccione Gratuito en la lista Estado **o** Región.
  
Un puente de conferencias le proporciona un conjunto de números de teléfono de acceso telefónico local para su organización. Todas ellas se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar las que se incluirán en sus invitaciones de reunión.
  
> [!NOTE]
> Puede haber un máximo de un número de teléfono gratuito y un número de teléfono gratuito en la invitación de reunión para un organizador de la reunión, pero también hay un vínculo situado en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Establecer el número de teléfono de acceso telefónico predeterminado para un organizador de la reunión

1. Inicie sesión con su cuenta de trabajo o escuela.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. Seleccione **Usuarios**.
    
    ![Muestra la selección de usuarios en el Centro de administración de Skype Empresarial](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Elija los usuarios que desea editar:
    
   - Para seleccionar un único usuario, seleccione el nombre del usuario.
    
   - Para seleccionar todos los usuarios de la página, seleccione el cuadro situado junto a **Mostrar nombre** en la parte superior de la lista.
    
   - Para seleccionar varios usuarios, seleccione el cuadro junto al nombre de cada usuario.
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Elija **Audioconferencia.**
    
7. En la **página Propiedades,** en la **lista Nombre del** proveedor, elija el proveedor para el usuario. Según el proveedor, complete los siguientes cuadros.
    
   - **Microsoft es el proveedor:** use  las listas Número de pago predeterminado y Número gratuito predeterminado para seleccionar los números predeterminados para el usuario. 
    
     > [!NOTE]
     > Se debe asignar al menos un número gratuito al puente de conferencias para poder establecerlo como el número gratuito predeterminado de un usuario. Para obtener un número gratuito, vea Obtener números de [teléfono de servicio para Skype Empresarial.](/microsoftteams/getting-service-phone-numbers) 
  
   - **Un tercero es el proveedor:** Use  los campos Número de pago y Número gratuito para escribir los números del usuario. 


## <a name="reset-audio-conferencing-phone-numbers"></a>Restablecer números de teléfono de audioconferencia

1. En el **Centro de administración de Skype Empresarial,** elija **Audioconferencia.**
    
2. En la parte superior de la página, elija **Usuarios.**
    
3. Elija los usuarios que desea restablecer y, a continuación, en el panel De acciones, haga clic en **Borrar**.
    
De forma predeterminada, al cambiar la configuración de conferencia de un usuario, se envía un correo electrónico al usuario. Para cambiar esto, vea Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la [configuración de audioconferencia.](enable-or-disable-sending-emails-when-their-settings-change.md)
  
> [!IMPORTANT]
> Al cambiar la configuración de audioconferencia de un usuario, las reuniones periódicas y futuras de Skype Empresarial deben actualizarse y enviarse a los asistentes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Use el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.
    
    Para cambiar el número gratuito predeterminado de un usuario, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.
    
    > [!NOTE]
    > Para buscar el BridgeID, use el cmdlet **Get-CsOnlineDialInConferencingBridge.**
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para establecer el número gratuito predeterminado para todos los usuarios sin uno en +18005551234, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para cambiar el número gratuito predeterminado de todos los usuarios que tienen +18005551234 como su número gratuito predeterminado a +18005551239, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para establecer el número gratuito predeterminado de todos los usuarios ubicados en EE. UU. en +18005551234, ejecute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>¿Desea obtener más información sobre Windows PowerShell?
- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Por qué necesita usar Microsoft 365 u Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en velocidad, sencillez y productividad sobre el uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)