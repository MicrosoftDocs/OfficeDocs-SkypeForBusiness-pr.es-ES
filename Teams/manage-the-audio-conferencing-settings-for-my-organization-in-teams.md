---
title: Administrar la configuración de audioconferencia
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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Consulte Microsoft Teams pasos para asignar una licencia de conferencia de acceso telefónico local e id. de conferencia a un usuario y muchas otras opciones de configuración de conferencias de acceso telefónico local. '
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101096"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Administrar la configuración de Audioconferencia para su organización en Microsoft Teams

Es posible que le resulte más fácil ver todas las opciones de configuración de audioconferencia Microsoft Teams en un solo lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de conferencia de acceso telefónico local

> [!NOTE]
> No puede asignar licencias con Teams. Debe usar el centro Microsoft 365 administración. Vea [Asignar Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **To assign a license for a user**
  
1. Inicie sesión en Microsoft 365 con su cuenta de trabajo o escuela.
    
2. En el panel de navegación izquierdo del Microsoft 365 de administración, vaya a Usuarios usuarios activos y, **a** continuación, seleccione el usuario o los usuarios de la lista  >  de usuarios disponibles.
    
    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.  
  
3. En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**. 
    
4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre las [licencias, vea Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
   > [!NOTE]
   > Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto sucede, cierre sesión en el centro de administración o presione CTRL+F5 para actualizar la ventana del explorador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Enable or disable emails sent to audio conferencing users

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.** 

3. En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambia la configuración **de acceso telefónico.**

4. Haga clic en **Guardar**.

    
Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="reset-the-meeting-conference-id"></a>Reset the meeting conference ID

![Un icono que muestra el Teams ](media/teams-logo-30x30.png) **con el Microsoft Teams de administración**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia, haga** clic **en Restablecer id. de conferencia.**  

3. En la ventana **¿Restablecer id. de conferencia?,** haga clic en **Restablecer**. Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia si el envío de correo electrónico a los usuarios está habilitado. Está habilitada de forma predeterminada.

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Se asignará un id. de conferencia único a cada reunión que programe un usuario. Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o los usuarios no puedan recordar o haber perdido su id. de conferencia. 

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia,** haga clic **en Restablecer PIN** y, a continuación, haga clic en **Restablecer**. 
  
Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará *****. 
  
Vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Send an email with Audio Conferencing information to a user

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia,** haga clic **en Enviar información de conferencia por correo electrónico.** 

    > [!NOTE]
    > When you do this, the audio conferencing PIN isn't sent to the user. 

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Establecer los números de teléfono incluidos en las invitaciones

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Junto a **Audioconferencia,** haga clic en **Editar.**
 
3. En el **panel Audioconferencia,** puede  establecer el número de pago y, si se permite, el **número gratuito**.

4. Haga clic en **Guardar**.
    
Vea [Establecer los números de teléfono incluidos en las invitaciones.](set-the-phone-numbers-included-on-invites-in-teams.md)
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Elegir la configuración del puente de audioconferencia

**Set the meeting experience when callers join a meeting**

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.** 

3. En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.

    Esta opción está habilitada de forma predeterminada. Si deshabilita esta opción, los usuarios que ya se han unido a la reunión de forma predeterminada no se les notificará cuando alguien entre o abandone la reunión.

4. En **Tipo de anuncio de entrada o salida,** elija **Tonos** o Nombres o números **de teléfono.** 

    Si elige **Nombres o números de teléfono,** también puede habilitar o deshabilitar Pedir a los autores de llamadas que graben su nombre antes de **unirse a la reunión.** 
    > [!NOTE]
    > De forma predeterminada, los participantes externos no pueden ver los números de teléfono de los participantes marcados. Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** de **entrada/salida tipo de anuncio** (esto evita que los Teams lean los números).


5. Haga clic en **Guardar**.

    
Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.** 

3. En el **panel Configuración de puente,** escriba el número de dígitos que desea para el PIN en la lista Longitud del **PIN** y, a continuación, haga clic en **Guardar.**

    The PIN must be between 4 and 12 digits. The default is 5.

    
See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.** 

3. En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambian sus opciones de **audioconferencia.**

4. Haga clic en **Guardar**. 
 
    También puede enviar correo electrónico al usuario con la configuración de audioconferencia, yendo a las propiedades de audioconferencia del usuario y haciendo clic en Enviar información de conferencia **por correo electrónico.**
    
    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Ver y establecer los idiomas principal (predeterminado) y secundario (alternativo) en un puente de audioconferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar.**

3. Elija los idiomas que desee en **Idioma predeterminado** e **Idiomas alternativos (opcional).**

4. Haga clic en **Guardar**.


También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>See audio conferencing dial-in numbers

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar.** Here you can:
    
   - Vea los números de teléfono que se van a usar para las audioconferencias. 
    
   - Vea la ubicación y el idioma principal que usará el operador automático de audioconferencias.

  
Vea [Ver una lista de números de audioconferencia.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)