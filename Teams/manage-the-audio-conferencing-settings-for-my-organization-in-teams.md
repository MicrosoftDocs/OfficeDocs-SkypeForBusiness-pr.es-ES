---
title: Administrar la configuración de Audioconferencia para mi organización en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea los pasos que hay que seguir en Microsoft Teams para asignar una licencia de conferencia de acceso telefónico local y un Id. de conferencia a un usuario y muchas otras opciones de la conferencia de acceso telefónico local. '
ms.openlocfilehash: b63650833c7c844de11ecb833288b6568604f919
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375866"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Administrar la configuración de Audioconferencia para mi organización en Microsoft Teams

Puede que le resulte más sencillo ver todas las opciones de audioconferencias para Microsoft Teams en un mismo lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de Audioconferencia

> [!NOTE]
> No es posible asignar licencias con Teams. Hay que usar el Centro de administración de Office 365. See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). 
  
 **Para asignar una licencia a un usuario**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. En la navegación izquierda del **Centro de administración de Office 365**, vaya a **Usuarios** > **Usuarios activos** y a continuación seleccione el usuario o los usuarios en la lista de usuarios disponibles.
    
    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.  
  
3. En el panel de acciones, en **Product licenses** (Licencias de producto), haga clic en **Editar**. 
    
4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
> [!NOTE]
> Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar o deshabilitar los correos electrónicos que se envían a usuarios de audioconferencias

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.

4. Haga clic en **Guardar**.

    
**Uso de Windows PowerShell**
  
Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Cambiar la información de contacto del remitente en los mensajes de correo electrónico que se envían a los usuarios

Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, incluidos la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De manera predeterminada, el remitente de los mensajes será Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell. Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="reset-the-meeting-conference-id"></a>Restablecer el Id. de conferencia de reunión

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.  

3. En la ventana **¿desea restablecer el id. de conferencia?**, haga clic en **Restablecer**. El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo siempre que el envío de correos electrónicos a los usuarios esté habilitado. Está habilitado de forma predeterminada.

Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Restablecer el PIN de un organizador de conferencia

Se asignará un id. de conferencia único a cada reunión que programe un usuario. Aunque el Id. de conferencia se crea y se asigna automáticamente a un usuario, puede suceder que un usuario no quiera usar este Id. y quiera configurar un número concreto, o que los usuarios no lo recuerden o lo hayan perdido. 

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia**, haga clic en **Restablecer PIN** y, a continuación, haga clic en **Restablecer**. 
  
Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará *****. 
  
Vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con la información de audioconferencia a un usuario

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia**, haga clic en **Enviar información de conferencia por correo electrónico**. 

    > [!NOTE]
    > Cuando hace esto, el PIN de audioconferencia no se envía al usuario. 

Consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Establecer los números de teléfono incluidos en las invitaciones

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Junto a **Conferencias de Audio**, haga clic en **Editar**.
 
3. En el panel de **Conferencia de Audio** , puede establecer el **número de teléfono de pago** y, si se permite, el **número de teléfono gratuito**.

4. Haga clic en **Guardar**.
    
Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Elija Configuración de puente de conferencia de audio

Configuración del puente de audioconferencia o de conferencia de acceso telefónico local

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.

    Esto está habilitado de forma predeterminada. Si deshabilita esta opción, no se le notificará a los usuarios que ya se han unido a la reunión de forma predeterminada cuando alguien entra o sale de la reunión.

4. En **tipo de anuncio de entrada o salida**, elija **tonos** o **nombres o números de teléfono**. 

    Si elige **los nombres o números de teléfono**, también puede elegir habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**. 

5. Haga clic en **Guardar**.

    
Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.

    El PIN debe tener entre 4 y 12 dígitos. El valor predeterminado es 5.

    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.[](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.

4. Haga clic en **Guardar**. 
 
    También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, vaya a las propiedades del usuario conferencias de audio y haciendo clic en **Enviar información de conferencia en el correo electrónico**.
    
    Si hace esto, se enviará un correo electrónico que incluye solo el Id. de conferencia y el número de teléfono de conferencia, pero no se incluirá el PIN.

Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Vea y establezca la primaria (valor predeterminado) y los idiomas (alternativos) secundarios en un puente de conferencia de audio

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**.

3. Elija los idiomas que desee en **idioma predeterminado** e **idiomas alternativos (opcionales)**.

4. Haga clic en **Guardar**.


También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>See audio conferencing dial-in numbers

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**. Here you can:
    
   - View the phone numbers that are set by Office 365 to be used for Audio Conferencing. 
    
   - Ver la ubicación y el idioma principal, que se utilizará en el operador automático de conferencia de Audio.

  
Vea [una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


