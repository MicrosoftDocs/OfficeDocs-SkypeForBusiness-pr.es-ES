---
title: Establecer la longitud del perno para las reuniones de conferencia de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: "Obtenga información acerca de los parámetros para los requisitos de un PIN y longitud y consulte cómo establecer la duración de las reuniones en Skype para el negocio."
ms.openlocfilehash: 853a8ed74377dd76b38eab62b04fc75e3295df2d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Establecer la longitud del perno para las reuniones de conferencia de Audio

Cuando se configure en conferencias de audio por Skype para negocios o Teams de Microsoft, obtendrá un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Establece el número de teléfono se incluyen en las invitaciones de la reunión de Skype para aplicaciones de negocios y Teams de Microsoft.
  
El puente de conferencia de audio responde a una llamada para las personas que llaman a una reunión mediante un teléfono. Responde al llamador con indicaciones de voz de un operador automático y a continuación, dependiendo de la configuración, puede reproducir las notificaciones y solicitar los llamadores para registrar su nombre. **Configuración de puente de Microsoft** le permiten cambiar la configuración de notificaciones de la reunión y unirse a la experiencia de la reunión y establecer la longitud de las clavijas que son utilizados por los organizadores de la reunión. Organizadores de reuniones Utilice pines para iniciar reuniones si ellos no pueden unirse a la reunión mediante el Skype para la aplicación de negocios o Teams de Microsoft.
  
## <a name="setting-the-pin-length"></a>Establecer la longitud del perno

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En **seguridad** > **longitud PIN**, seleccione el número de dígitos que desee para el PIN y, a continuación, haga clic en **Guardar**.
    
> [!NOTE]
> Un PIN es diferente de un identificador de la conferencia. Los llamadores utilizan identificadores de conferencia cuando se unen a la reunión. Se utilizan para identificar la reunión. El PIN se utiliza para autenticar un llamador como organizador de la reunión. 
  
## <a name="want-to-know-more-about-pin-settings"></a>¿Desea saber más acerca de la configuración de PIN?

- Pines pueden oscilar entre 4 y 12 dígitos; el valor predeterminado es 5. Los números sólo se utilizan al crear pines. No se utilizan letras y caracteres especiales.
    
- Un PIN sólo es necesario para el organizador de la reunión cuando un Skype para usuarios de negocios o Teams de Microsoft ya no ha iniciado la conferencia. Si todo el mundo está marcando a la reunión, el PIN es necesario para el organizador de la reunión iniciar la reunión.
    
- Configuración de la seguridad de NIP se aplica a todos los números de teléfono están asociados con un puente de Microsoft. Se aplicará a todas las reuniones que utilizan los números de teléfono asociados con un puente determinado. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar esta tarea, puede utilizar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Para establecer el número de dígitos en el PIN 8:`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no realizar. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar a utilizar Windows PowerShell, consulte estos temas:
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo. Obtenga información acerca de estas ventajas en los siguientes temas: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>Vea también

[Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](set-up-audio-conferencing.md)

