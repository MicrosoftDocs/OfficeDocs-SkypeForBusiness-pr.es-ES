---
title: Administrar la configuración de conferencia de Audio de mi organización en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte los pasos de Microsoft Teams para asignar un identificador de conferencia y licencia de conferencia de acceso telefónico a un usuario y muchas otras opciones de conferencia de acceso telefónico. '
ms.openlocfilehash: b9b3198f5d66b36e986eeab72fdf5dd31521fb14
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866838"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Administrar la configuración de conferencia de Audio de mi organización en Microsoft Teams

Sería más fácil para que pueda ver toda la configuración de conferencia de audio para Microsoft Teams en un solo lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de conferencia de acceso telefónico local

> [!NOTE]
> No se puede asignar licencias de uso de los equipos. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). 
  
 Para asignar una licencia a un usuario
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. En la navegación izquierda del **Centro de administración de Office 365**, vaya a **Usuarios** > **Usuarios activos** y a continuación seleccione el usuario o los usuarios en la lista de usuarios disponibles.
    
    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.  
  
3. En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**. 
    
4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
> [!NOTE]
> Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Enable or disable emails sent to audio conferencing users

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.

4. Haga clic en **Guardar**.

    
**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**
  
Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Change the sender's contact information in email messages sent to users

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De forma predeterminada, el remitente de los mensajes de correo electrónico es Office 365, pero puede cambiar la dirección de correo electrónico y Mostrar nombre con Windows PowerShell. Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="reset-the-meeting-conference-id"></a>Restablecer el id. de conferencia de reunión

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencias de Audio**, haga clic en **Restablecer el identificador de conferencia**.  

4. En la **Restablecer el identificador de conferencia?** ventana, haga clic en **Restablecer**. Se creará automáticamente un identificador de conferencia y un correo electrónico enviado al usuario con el nuevo identificador de conferencia si está habilitado el envío de correo electrónico a los usuarios. Está habilitada de forma predeterminada.

Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Restablecer el PIN del organizador de una conferencia

Se asignará un Id. de conferencia único a cada reunión que programe un usuario. Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar este y que desea establecer para un cierto número, o los usuarios no pueden recordar o han perdido su identificador de conferencia. 

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencias de Audio**, haga clic en **Restablecer PIN**y, a continuación, haga clic en **Restablecer**. 
  
    
Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará *****. 
  
Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Send an email with Audio Conferencing information to a user

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencias de Audio**, haga clic en **Enviar información de conferencia en el correo electrónico**. 

    > [!NOTE]
    > Cuando hace esto, el PIN de audioconferencia no se envía al usuario. 

  
Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Configuración del teléfono los números incluidos en invitaciones

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Junto a **Conferencias de Audio**, haga clic en **Editar**.
 
3. En el panel de **Conferencia de Audio** , puede establecer el **número de teléfono de pago** y, si se permite, el **número de teléfono gratuito**.

4. Haga clic en **Guardar**.
    
Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Elegir la configuración de puente de conferencia de audio

Configuración del puente de audioconferencia o de conferencia de acceso telefónico local


1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar la **entrada de la reunión y salir de las notificaciones**.

    Esto está habilitado de forma predeterminada. Si deshabilita esta opción, no se le notificará a los usuarios que ya se han unido a la reunión de forma predeterminada cuando alguien entra o sale de la reunión.

4. En **tipo de anuncio de entrada o salida**, elija **tonos** o **nombres o números de teléfono**. 

    Si elige **los nombres o números de teléfono**, también puede elegir habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**. 

5. Haga clic en **Guardar**.

    
Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.

    El PIN debe tener entre 4 y 12 dígitos. El valor predeterminado es 5.

    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.[](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**


1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.

4. Haga clic en **Guardar**. 
 
    También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, vaya a las propiedades del usuario conferencias de audio y haciendo clic en **Enviar información de conferencia en el correo electrónico**.
    
    Si hace esto, se enviará un correo electrónico que incluye solo el Id. de conferencia y el número de teléfono de conferencia, pero no se incluirá el PIN.

Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Vea y establezca la primaria (valor predeterminado) y los idiomas (alternativos) secundarios en un puente de conferencia de audio

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**.

3. Elija los idiomas que desee en **idioma predeterminado** e **idiomas alternativos (opcionales)**.


También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>See audio conferencing dial-in numbers


1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**. Here you can:
    
  - View the phone numbers that are set by Office 365 to be used for Audio Conferencing. 
    
  - Ver la ubicación y el idioma principal, que se utilizará en el operador automático de conferencia de Audio.

  
Vea [una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
    
## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


