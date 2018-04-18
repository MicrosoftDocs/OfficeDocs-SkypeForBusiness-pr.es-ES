---
title: Configurar el teléfono invita números incluidos en
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: ae0f26c02bef1262b54cd509f9e539ef68aec112
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a>Configurar el teléfono invita números incluidos en

Conferencias de audio en Office 365 permite a los usuarios de su organización crear Skype para reuniones de negocios y Teams de Microsoft y, a continuación, permitir a los usuarios llamar a esas reuniones utilizando un teléfono. En Office 365, tiene la opción de utilizar un puente de conferencia de audio de Microsoft o de un puente de conferencia de audio de terceros que está alojado en un proveedor aprobado de audioconferencias (ACP).
  
> [!NOTE]
> No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia. Si está buscando para ver si hay números de teléfono de marcado disponibles en su área o país o región, utilice el **Skype para el centro de administración de negocios** > **voz** > **Números de teléfono**, haga clic en **Agregar** nuevos números de servicio de ** **. Utilice las listas de **País o región**, estado o región de **** y **Ciudad** para filtrar su búsqueda. > también, si está buscando números de servicio gratuito de peaje, seleccione **número gratuito** desde el estado o región **** lista.
  
Un puente de conferencia ofrece un conjunto de números de teléfono de acceso telefónico para su organización. Todos ellos pueden utilizarse para unirse a las reuniones que ha creado el organizador de una reunión, pero puede seleccionar cuáles se incluirán en sus invitaciones a la reunión.
  
> [!NOTE]
> Puede haber un máximo de un teléfono y un número de teléfono gratuito en la invitación de reunión para el organizador de una reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación de reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que puede utilizarse para unirse a una reunión. 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Establecer el número de teléfono marcado predeterminado para el organizador de una reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. Seleccione **Usuarios**.
    
    ![Seleccionar los usuarios en el Skype para el centro de administración de negocio de muestra](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Seleccione los usuarios que desea editar:
    
  - Para seleccionar un único usuario, seleccione el nombre del usuario.
    
  - Para seleccionar todos los usuarios de la página, active la casilla situada junto al **nombre para mostrar** en la parte superior de la lista.
    
  - Para seleccionar varios usuarios, active la casilla situada junto a cada nombre de usuario.
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Elija la **conferencia de Audio**.
    
7. En la página de **Propiedades** , en la lista **nombre de proveedor** , seleccione el proveedor para el usuario. Dependiendo del proveedor, complete los siguientes cuadros.
    
  - **Microsoft es el proveedor**: **número gratuito predeterminada** listas para seleccionar los números predeterminados para el usuario y utilizar el **número de pago predeterminado** .
    
    > [!NOTE]
    > Debe asignarse al menos un número gratuito para el puente de conferencia antes de que se puede establecer como el número gratuito de predeterminado de un usuario. Para obtener un número de teléfono gratuito, vea [números de teléfono de servicio de obtención de Skype para empresas y equipos de Microsoft](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
  - **Un tercero es el proveedor**: utilice los campos de **número de teléfono** y **número de teléfono gratuito** para especificar los números para el usuario.
    
## <a name="reset-audio-conferencing-phone-numbers"></a>Restablecer los números de teléfono de conferencia de audio

1. En el **Skype para el centro de administración de negocios**, elija **conferencias de Audio**.
    
2. En la parte superior de la página, elija **los usuarios**.
    
3. Seleccionar los usuarios que desea restablecer y, a continuación, en el panel Acción, haga clic en **Borrar**.
    
De forma predeterminada, al cambiar la configuración de conferencia de un usuario, se envía un correo electrónico al usuario. Para cambiar esta configuración, vea [Habilitar o deshabilitar el envío correos electrónicos cuando cambie la configuración de conferencia de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Cuando se cambia la configuración de conferencia de audio de un usuario, periódica y futuro Skype para reuniones de negocios y Teams de Microsoft debe actualiza y se envía a los asistentes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.
    
    Para cambiar el número gratuito predeterminado de un usuario, ejecute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.
    
    > [!NOTE]
    > Para encontrar el BridgeID, utilice el **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para establecer el número de teléfono gratuito de forma predeterminada para todos los usuarios sin uno a +18005551234, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para cambiar el número gratuito por defecto de todos los usuarios que tienen +18005551234 como su número de llamada gratuita predeterminado a +18005551239, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para establecer el número gratuito de forma predeterminada todos los usuarios ubicados en los Estados Unidos a +18005551234, ejecute:
    
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
