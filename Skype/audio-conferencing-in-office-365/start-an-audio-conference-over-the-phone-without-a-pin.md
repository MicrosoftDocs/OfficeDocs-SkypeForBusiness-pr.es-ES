---
title: "Iniciar una conferencia de Audio por teléfono sin un PIN"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: c77921af87cab23b475c31205da4661755c56961
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>Iniciar una conferencia de Audio por teléfono sin un PIN

Puede ser frustrante para los usuarios que llamen a una reunión que se celebrará en la sala de la reunión escuchar música porque el Skype para el organizador de la reunión de negocios o Teams de Microsoft no ha comenzado la reunión. 
  
Si llama a un organizador de la reunión la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión. Puede configurar, por lo que cualquiera puede llamar a una reunión y no se le pida un PIN iniciar la reunión. Puede utilizar el Skype para el centro de administración de negocios para habilitar o deshabilitar a esta configuración para un único usuario.
  
Un PIN no es necesario para el organizador de la reunión si alguien ha iniciado la conferencia desde un Skype para la aplicación de negocios o Teams de Microsoft. Un PIN sólo es necesario cuando el organizador de una reunión se une a la reunión a través de un teléfono. El NIP de reuniones se envía al usuario audio cuando se asignan a la licencia de **Conferencias de Audio** y están habilitados para conferencias de Audio. Ver [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md)y [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**. 
    
4. En la lista, seleccione el usuario y en el panel Acción, haga clic en **Editar**. 
    
5. En la página de propiedades del usuario, en **Opciones de la reunión**, active o desactive Permitir no autenticado a **quienes llaman para ser los primeros en una reunión. Si no, a continuación, esperan en la sala de espera hasta que un usuario autenticado se une**.
    
6. Haga clic en **Guardar**. 
    
 **Para habilitar o deshabilitar a los llamadores anónimos a todas las reuniones, del usuario con Windows Powershell**
  
- Ejecute lo siguiente: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, consulte [Restablecer el PIN de conferencia de Audio para un usuario](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Si está habilitado el acceso anónimo o que no requiere un PIN iniciar una reunión:
    
  - Si no ha iniciado la reunión (hay nadie en la reunión todavía): un llamador se preguntará si es el organizador; Si contesta Sí, pedirá su PIN y después de él escribe el NIP, se iniciará la sesión y el usuario unirá a la reunión.
    
  - Si la reunión ya inició (alguien ya está en la reunión): no se solicita un llamador si es el organizador y nunca se pedirá el PIN; ya se ha iniciado la sesión y unirá a la persona que llama.
    
- Si se deshabilita el acceso anónimo o que no requiere un PIN iniciar una reunión:
    
  - Si no ha iniciado la reunión (hay nadie en la reunión aún): no se solicita un llamador si es el organizador y nunca se pedirá el PIN. Debido a la configuración del organizador se establece en off, se iniciará la reunión y los llamadores anónimos se unirá a la reunión.
    
  - Si la reunión ya inició (alguien ya está en la reunión): no se solicita un llamador si es el organizador y nunca se pedirá el PIN; ya se ha iniciado la sesión y unirá a la persona que llama.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo. Obtenga información acerca de estas ventajas en los siguientes temas: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](set-up-audio-conferencing.md)
