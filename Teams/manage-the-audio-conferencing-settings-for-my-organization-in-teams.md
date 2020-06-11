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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Vea los pasos que hay que seguir en Microsoft Teams para asignar una licencia de conferencia de acceso telefónico local y un Id. de conferencia a un usuario y muchas otras opciones de la conferencia de acceso telefónico local. '
ms.openlocfilehash: 1cf51db4bd2ba4e6fb29d7301cb2ad46d4afb2f4
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691216"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Administrar la configuración de Audioconferencia para su organización en Microsoft Teams

Puede que le resulte más sencillo ver todas las opciones de audioconferencias para Microsoft Teams en un mismo lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de Audioconferencia

> [!NOTE]
> No es posible asignar licencias con Teams. Debe usar el centro de administración de Microsoft 365. Consulte [asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md). 
  
 **Para asignar una licencia a un usuario**
  
1. Inicie sesión en Microsoft 365 con su cuenta profesional o educativa.
    
2. En el centro de navegación izquierdo del **centro de administración de Microsoft 365**, **vaya a usuarios**  >  **activos**y, a continuación, seleccione el usuario o los usuarios de la lista de usuarios disponibles.
    
    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.  
  
3. En el panel de acciones, en **Product licenses** (Licencias de producto), haga clic en **Editar**. 
    
4. En la página **licencias de producto** , Active **Conferencia de audio** y, a continuación, haga clic en **Guardar**. Para obtener más información sobre las licencias, vea [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
   > [!NOTE]
   > Después de asignar la licencia, es posible que Microsoft no aparezca inicialmente en la lista como un proveedor de servicios de audioconferencia. Si esto sucede, cierre sesión en el centro de administración o presione CTRL + F5 para actualizar la ventana del explorador. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar o deshabilitar los correos electrónicos que se envían a usuarios de audioconferencias

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.

4. Haga clic en **Guardar**.

    
**Uso de Windows PowerShell**
  
Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="reset-the-meeting-conference-id"></a>Reset the meeting conference ID

![Un icono que muestra el logotipo de Teams ](media/teams-logo-30x30.png) **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **audioconferencia**, haga clic en **restablecer ID de conferencia**.  

3. En la ventana **restablecer ID de conferencia** , haga clic en **restablecer**. Se creará automáticamente un identificador de conferencia y un correo electrónico que se enviará al usuario con el nuevo identificador de conferencia si se habilita el envío de correo electrónico a los usuarios. Está habilitado de forma predeterminada.

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Se asignará un id. de conferencia único a cada reunión que programe un usuario. Aunque se creará automáticamente un identificador de conferencia y se le asignará a un usuario, puede haber ocasiones en las que un usuario no desee usarlo y usted quiera establecerlo en un número determinado, o los usuarios no podrán recordar o perder su identificador de conferencia. 

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **audioconferencia**, haga clic en **restablecer PIN**y, a continuación, haga clic en **restablecer**. 
  
Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará *****. 
  
Consulte [restablecer el PIN de audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Send an email with Audio Conferencing information to a user

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Conferencia de audio**, haga clic en **enviar información de conferencia por correo electrónico**. 

    > [!NOTE]
    > When you do this, the audio conferencing PIN isn't sent to the user. 

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Establecer los números de teléfono incluidos en las invitaciones

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Junto a **audioconferencia**, haga clic en **Editar**.
 
3. En el panel **audioconferencia** , puedes establecer el número de **pago** y, si es posible, el **número**gratuito.

4. Haga clic en **Guardar **.
    
Consulte [establecer los números de teléfono incluidos en los invitados](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Elegir la configuración del puente de audioconferencia

**Set the meeting experience when callers join a meeting**

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **puentes de conferencia** , haga clic en **configuración del puente**. 

3. En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.

    Esta opción está habilitada de forma predeterminada. Si deshabilita esta opción, los usuarios que ya se hayan Unido de forma predeterminada no recibirán una notificación cuando alguien entre o salga de la reunión.

4. En **entrada/salida de tipo de anuncio**, seleccione **tonos** o **nombres o números de teléfono**. 

    Si elige **nombres o números de teléfono**, también puede habilitar o deshabilitar que los **autores de las llamadas pidan que graben su nombre antes de unirse a la reunión**. 
    > [!NOTE]
    > De forma predeterminada, los participantes externos no pueden ver los números de teléfono de los participantes marcados. Si desea mantener la privacidad de estos números de teléfono, seleccione **tonos** para **tipo de anuncio de entrada/salida** (esto impide que Teams Lea los números).


5. Haga clic en **Guardar**.

    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.
  
 **Configurar la longitud del PIN para las reuniones**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En **Seguridad**, introduzca el número de dígitos que quiere para el PIN en la lista **Longitud del PIN** y después haga clic en **Guardar**.

    El PIN debe ser un valor entre 4 y 12 dígitos. El valor predeterminado es 5.

    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.[](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Habilitar o deshabilitar que el correo electrónico se envíe a los usuarios de audioconferencias**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de audioconferencia**.

4. Haga clic en **Guardar**. 
 
    También puede enviar un correo electrónico al usuario con la configuración de la audioconferencia. Para ello, tiene que ir a las propiedades de la audioconferencia para el usuario y hacer clic en **Enviar la información de conferencia por correo electrónico**.
    
    Si hace esto, se enviará un correo electrónico que incluye solo el Id. de conferencia y el número de teléfono de conferencia, pero no se incluirá el PIN.

Consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Ver y establecer los idiomas principales (predeterminados) y secundarios (alternativos) en un puente de audioconferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**.

3. Elija los idiomas que desee en **idioma predeterminado** y **idiomas alternativos (opcional)**.

4. Haga clic en **Guardar **.


También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>See audio conferencing dial-in numbers

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**. Here you can:
    
   - Ver los números de teléfono que se usarán para las conferencias de audio. 
    
   - Ver la ubicación y el idioma principal que usará el operador automático de audioconferencia.

  
Consulte [ver una lista de números de audioconferencia](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


