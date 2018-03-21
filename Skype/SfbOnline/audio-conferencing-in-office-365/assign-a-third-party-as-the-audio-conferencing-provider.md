---
title: Asignar a un tercero como el proveedor de conferencia de audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: 5ae513c754764933f08370139eeb557f0fb39211
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>Asignar a un tercero como el proveedor de conferencia de audio

Un proveedor de conferencia de audio proporciona el *puente de conferencia*. El puente de conferencia proporciona el número de teléfono de acceso telefónico, pasadores y conferencia identificadores para las reuniones que se crean. Sólo debe asignar a un proveedor de conferencia de audio para las personas que se van a programar o plomo Skype para reuniones de negocios o Teams de Microsoft.
  
> [!NOTE]
> Para Teams de Microsoft, un usuario no puede utilizar un proveedor de conferencia de audio de terceros, deben utilizar audioconferencia en Office 365, que establece el proveedor de conferencia de audio en Microsoft. 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>Pasos a realizar antes de que se puede asignar a un proveedor de conferencia de audio de terceros

1. Dependiendo del plan de Office 365, debe comprar licencias adicionales de **Conferencia de Audio** para las personas de la organización que se va a programar o plomo Skype para reuniones de negocios o Teams de Microsoft mediante conferencias de Audio. Para obtener más información, vea [Skype para negocios y equipos de Microsoft licencias adicionales](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Si ha adquirido licencias adicionales de **Conferencias de Audio** , asignarlos a las personas de la organización que se va a programar o llevar las reuniones que se utilizan en conferencias de Audio. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Si asigna una licencia de **Conferencias de Audio** a otra persona **después** que se les asigne a un proveedor de conferencia de audio de terceros, esa persona se establecerá automáticamente para utilizar en su lugar Microsoft como su proveedor de conferencia de audio! Si esto ocurre, debe quitar Microsoft como proveedor de conferencia de audio antes de poder asignar a un proveedor de conferencia de audio de terceros a ellos.
  
3. Encontrar un proveedor de conferencia de audio de terceros en [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Póngase en contacto con ellos y descubra cómo se configuran todos los aspectos con ellos.
    
    Se le ofrecerá lo siguiente:
    
  - **Números de acceso telefónico (de pago)** y números de teléfono gratuitos si están disponibles.
    
  - **Id. de conferencia** para cada persona que programe reuniones. Algunos ACP los llaman códigos de acceso a conferencias.
    
    > [!NOTE]
    > Si ha hecho la inicial configurada para un ACP de terceros pero ahora necesita realizar cambios, en la parte inferior de la página de **Puente de Microsoft** **haga clic aquí para configurar un proveedor de conferencia de audio de terceros**. 
  
    > [!NOTE]
    > Cuando habilita a una persona para conferencias de audio y asignarles a un proveedor de conferencia de audio de otros fabricantes, los números de audio y los identificadores de conferencia (contraseñas) se agregan automáticamente a cualquier **nuevo** Skype para reuniones de negocios en línea creados por ellos mismos.
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>Cómo asignar a un proveedor de conferencia de audio de terceros a un usuario

1. En el **Centro de administración de Skype Empresarial**, seleccione **Usuarios**. Seleccione el usuario de la lista y haga clic en **Editar** en el panel de acciones.
    
2. En la página de propiedades del usuario, haga clic en **conferencias de Audio** y escriba esta información:
    
  - **Nombre del proveedor** Seleccione el proveedor de la lista.
    
  - **Número de peaje predeterminado** Esto es necesario.
    
  - **Predeterminado el número de teléfono gratuito** Esto no es necesario.
    
  - **Id. de conferencia** Esto es proporcionada por su proveedor de conferencia de audio.
    
3. Haga clic en **Guardar**.
    
4. Envíe el NIP que recibió del proveedor de conferencia de audio de cada persona. El NIP se requiera para llamar en que el organizador de la conferencia o el líder.
    
    > [!NOTE]
    > Cuando se utiliza un proveedor de conferencia de audio de otros fabricantes, no hay una manera de ver o configurar el PIN en nombre de los organizadores de la reunión. 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a>Cómo asignar a un proveedor de conferencia de audio de terceros a varias personas al mismo tiempo

1. En el **Skype para el centro de administración de negocios**, elija **conferencias de Audio** > **puente de Microsoft**. En la parte inferior de la página, haga clic en el vínculo de **Si desea configurar un proveedor de conferencia de audio de terceros en su lugar, haga clic aquí**.
    
    > [!NOTE]
    > Si ha hecho la inicial configurada para un ACP de terceros pero ahora necesita realizar cambios, en la parte inferior de la página de **Puente de Microsoft** , **haga clic aquí para configurar un proveedor de conferencia de audio de terceros**. 
  
2. En la página **configurar un tercero proveedor de conferencia de audio** , en **Importar y exportar usuarios**, haga clic en **Asistente para exportar**y, a continuación, siga los pasos del **Asistente para exportar usuarios**. Cuando termine, tendrá un archivo que enumere las personas que desea configurar para conferencias de audio.
    
3. Enviar el archivo creado con el proveedor de conferencia de audio de terceros. Se agrega información de conferencia de audio para las personas incluidas en el archivo y, a continuación, devuelva el archivo.
    
4. Compruebe que el archivo devuelto contiene la información correcta. Hemos sabido de casos en los que no todas las personas que aparecían en el archivo obtuvieron la información correcta.
    
5. En la **página para configurar un proveedor de conferencias de audio de terceros**, en **Importar y exportar usuarios**, haga clic en **Asistente para importación** y, después, siga los pasos que se detallan en el **Asistente para la importación de usuarios**.
    
6. Envíe el NIP que recibió del proveedor de conferencia de audio de cada persona. Puede que se le requiera el PIN para actuar como organizador o coordinador de la llamada de conferencia.
    
    > [!NOTE]
    > Cuando se utiliza un proveedor de conferencia de audio de otros fabricantes, no hay una manera de ver o configurar el PIN en nombre de los organizadores de la reunión. 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>Cuándo utilizar un proveedor de conferencia de audio de terceros

Si estás en un país o región donde no está disponible en Office 365 conferencias de Audio, la calidad de servicio no es gran cosa debido a su ubicación o tiene un contrato existente con un proveedor de conferencia de audio de terceros, se recomienda utilizar un audio de otros fabricantes proveedor de conferencia. De lo contrario, se recomienda utilizar Microsoft como proveedor de conferencia de audio.
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>Automatizar la asignación del proveedor de audioconferencias de terceros mediante Windows PowerShell

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).
    
    > [!NOTE]
    > Para cambiar el proveedor de audio de Microsoft a un proveedor de conferencia de audio de terceros, debe quitar Microsoft como proveedor de conferencia de audio. Esto puede realizarse usando el cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ).
  
- Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## <a name="what-else-do-i-need-to-know"></a>¿Qué más debo saber?

Una persona de su organización sólo puede utilizar un proveedor de conferencia de audio. Para cambiar el proveedor de conferencia de audio de una persona a Microsoft, consulte [mover el proveedor de conferencia de audio de un usuario a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) o [Asignar Microsoft como proveedor de conferencia de audio](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## <a name="related-topics"></a>Temas relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

