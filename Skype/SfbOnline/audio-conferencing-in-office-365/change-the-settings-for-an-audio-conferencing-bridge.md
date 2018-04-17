---
title: Cambiar la configuración de un puente de conferencia de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/03/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: 'Obtenga los pasos que necesarios para cambiar la configuración de un puente de conferencia que se utiliza para solicitar a los llamadores y recopilar nombres y clavijas para los organizadores de la reunión cuando no utilizan Skype para aplicaciones empresariales o Teams de Microsoft. '
ms.openlocfilehash: 727392bc81bce2fb3cfd84029e6a275e1eed3e24
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Cambiar la configuración de un puente de conferencia de Audio

Cuando configura la audioconferencia en Office 365, recibirá los números de teléfono para los usuarios de lo que se denomina un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Estos números de teléfono se utilizan cuando los llamadores llama a una reunión. El número de teléfono se incluye en la parte inferior de la Skype para invitar a la reunión de negocios o Teams de Microsoft.
  
El puente de conferencia contesta una llamada y solicita al llamador con indicaciones de voz utilizando un auto reunión operador y a continuación, dependiendo de la configuración, puede reproducir las notificaciones, pregunte a los llamadores para registrar su nombre y controlar la configuración de pines. Pines se otorgan a los organizadores de reuniones para permitirles iniciar una reunión cuando están no esté utilizando un Skype para la aplicación de negocios o Teams de Microsoft.

  > [!IMPORTANT]
  > Un PIN sólo es necesario para el organizador de la reunión cuando un Skype para usuario de la aplicación empresarial o Teams de Microsoft ya no ha iniciado la conferencia. Si todo el mundo está marcando a la reunión, el PIN es necesario para el organizador de la reunión iniciar la reunión. 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a>Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios

1. En la exploración de la izquierda, vaya a **reuniones** > **puentes de conferencia**. 

2. En la parte superior de la página **puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , seleccione: 
  - **Entrada de reunión y salir de las notificaciones** Si desactiva esta opción, los usuarios que ya han participado en la reunión no se le notificará cuando alguien entra o sale de la reunión.
    
    Al activar **las notificaciones de entrada y salida de la reunión**, puede seleccionar estas opciones:
    
  - **Los nombres o números de teléfono** Cuando los usuarios de acceso telefónico a una reunión, su número de teléfono se reproducirá cuando se unan a ella.
    
  - **Tonos** Cuando los usuarios de acceso telefónico a una reunión, un tono de sonido se reproducirá cuando se unan a ella.
      
  - **Llamadores ASK para registrar su nombre antes de unirse a la reunión** Si desactiva esta opción, los llamadores no pedirá que registre su nombre antes de que se unen a una reunión.

4. Para establecer la longitud del perno para las reuniones, seleccione el número de dígitos que desee para el PIN en la lista de **longitud PIN** .

5. Para especificar si desea enviar correo electrónico a los usuarios, activar o desactivar **automáticamente enviar correos electrónicos a los usuarios si cambia su configuración de conferencia de audio**.
    Para obtener más información, consulte [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md) .
 
6. Haga clic en **Aplicar**. 

## <a name="using-skype-for-business-admin-center"></a>Usar Skype para el centro de administración de negocios

 **Configurar la experiencia de reunión cuando los llamadores unirse a una reunión**
    
1. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
2. En la página **configuración de puente de Microsoft** , en la **experiencia de unión de la reunión**, seleccione:
    
  - **Habilitar la entrada de la reunión y salir de notificaciones para activarse** Esto está seleccionada por defecto. Si desactiva la casilla de verificación, los usuarios que ya han participado en la reunión no se le notificará cuando alguien entra o sale de la reunión.
    
    Cuando selecciona **Habilitar la entrada de la reunión y salir notificaciones para ser activado**, puede seleccionar estas opciones en la lista **tipo de entrada o salida de anuncio** :
    
  - **Los nombres o números de teléfono** Cuando los usuarios de acceso telefónico a una reunión, su número de teléfono se reproducirá cuando se unan a ella.
    
  - **Tonos** Cuando los usuarios de acceso telefónico a una reunión, un tono de sonido se reproducirá cuando se unan a ella.
  
  - **Llamadores ASK para registrar su nombre antes de unirse a la reunión** Esto está seleccionada por defecto. Si desactiva la casilla de verificación, los llamadores no pedirá que registre su nombre antes de que se unen a una reunión.
    
3. Después de realizar los cambios, haga clic en **Guardar**.
    
Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.
  
1. Configurar la longitud del PIN de las reuniones
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. En la página de **configuración de puente de Microsoft** en **seguridad**, especifique el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.
    
    > [!IMPORTANT]
    > The PIN must be between 4 and 12 digits. 
  
**Seleccione si desea enviar correo electrónico a los usuarios**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. En la página **configuración de puente de Microsoft** , seleccione o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su información de acceso telefónico**y, a continuación, haga clic en **Guardar**.
    
    Para obtener más información, consulte [mensajes de correo electrónico se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede utilizar el cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Configurar Audioconferencia](set-up-audio-conferencing.md)
