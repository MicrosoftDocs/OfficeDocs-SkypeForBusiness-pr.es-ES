---
title: "Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
description: "Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. "
---

# Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Audioconferencia en Office 365 permite a los usuarios de su organización crear un Skype para reuniones de negocios y Teams de Microsoft y, a continuación, permitir a los usuarios llaman a ella usando un teléfono. En Office 365, tendrá la opción de utilizar un puente de conferencia de audio de Microsoft o utilizar un puente de conferencia de audio de terceros que está alojado en un proveedor de servicios autorizados audioconferencia (ACP).
  
El puente de conferencias le proporciona un conjunto de números de acceso telefónico local para su organización. Todos ellos se pueden usar para unirse a las reuniones que haya creado un organizador de reuniones, pero puede seleccionar los que se incluirán en las invitaciones de la reunión.
  
> [!NOTE]
> Puede haber un máximo de una de pago y un número de teléfono gratuito en la invitación a la reunión del organizador de la reunión, pero también es un vínculo que se encuentra en la parte inferior de cada invitación a la reunión que se abre la lista completa de todos los números de teléfono que pueden utilizarse para unirse a una reunión. 
  
## Configurar el número de acceso telefónico local predeterminado para el organizador de una reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**. 
    
3. Seleccione **Usuarios**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Elija los usuarios que desea editar: 
    
  - Para seleccionar un solo usuario, elija el nombre del usuario.
    
  - Para seleccionar a todos los usuarios de la página, marque la casilla situada junto a **Nombre para mostrar**, en la parte superior de la lista.
    
  - Para seleccionar varios usuarios, mantenga presionada la tecla Ctrl y elija los usuarios que desee.
    
5. En el panel derecho, elija **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. En el **proveedor** de la lista desplegable, elija el proveedor para el usuario. Dependiendo del proveedor, complete los siguientes cuadros.
    
  - **Microsoft es el proveedor**: utilice el **número de teléfono predeterminado** y **número de teléfono gratuito predeterminado** listas para seleccionar los números de forma predeterminada para el usuario.
    
    > [!NOTE]
    > Debe asignarse al menos un número gratuito al puente de la conferencia antes de que se pueda establecer como el número gratuito predeterminado de un usuario. Para obtener un número gratuito, consulte [Obtener números de teléfono de servicio de Skype Empresarial](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). 
  
  - **El proveedor es un tercero**: use los campos **Número de pago** y **Número gratuito** para especificar los números del usuario.
    
## Restablecer números de teléfono de conferencias de audio

1. En el **Centro de administración de Skype Empresarial**, elija **conferencias de Audio**.
    
2. En la parte superior de la página, elija **usuarios de acceso telefónico**.
    
3. Elija los usuarios que desea restablecer y seleccione **Borrar**. 
    
    ![Choose Clear to reset phone numbers.](../images/28664b62-0d6f-42e1-960b-fdb1c6c14020.png)
  
De forma predeterminada, al cambiar la configuración de conferencias de un usuario, mensajes de correo electrónico se envían a los usuarios. Para cambiar esta configuración, vea [Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
  
> [!IMPORTANT]
> Al cambiar la configuración de conferencias de audio de un usuario, periódica y futuro Skype para reuniones de negocios y Teams de Microsoft debe actualizar y se envían a los asistentes. 
  
## ¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) .
    
- Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el pago predeterminado o el número de teléfono gratuito para usuarios específicos.
    
    Para cambiar el número gratuito predeterminado de un usuario, ejecute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.
    
    > [!NOTE]
    > Para buscar el id. de puente, use **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  
  ```

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para establecer el número de teléfono gratuito predeterminado para todos los usuarios sin uno a +18005551234, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para cambiar el número gratuito predeterminado de todos los usuarios que tienen +18005551234 como su número gratuito predeterminado a +18005551239, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para establecer el número de teléfono gratuito predeterminado de todos los usuarios que se encuentra en los Estados Unidos a +18005551234, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para cambiar el número de teléfono gratuito predeterminado de todos los usuarios que tienen +18005551234 como su número gratuito predeterminado para +18005551239 y reprogramar todas las reuniones con el nuevo número de teléfono gratuito, ejecute:
    
  -     > [!NOTE]
    > La ubicación que se usa arriba debe coincidir con la información de contacto de los usuarios establecidos en el Centro de administración de Office 365. 
  
- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Temas relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

