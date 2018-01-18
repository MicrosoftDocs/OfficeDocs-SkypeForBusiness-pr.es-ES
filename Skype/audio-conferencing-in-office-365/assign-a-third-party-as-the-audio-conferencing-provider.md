---
title: Asignar a un tercero como el proveedor de conferencia de audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Aprenda a configurar un tercero como proveedor de conferencia de acceso telefónico con Skype para el negocio. "
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>Asignar a un tercero como el proveedor de conferencia de audio

Un proveedor de conferencia de audio proporciona el *puente de conferencia*. El puente de conferencia proporciona el número de teléfono de acceso telefónico, pasadores y conferencia identificadores para las reuniones que se crean. Sólo debe asignar a un proveedor de conferencia de audio para las personas que se van a programar o plomo Skype para reuniones de negocios o Teams de Microsoft.
  
> [!NOTE]
> Para Teams de Microsoft, un usuario no puede utilizar un proveedor de conferencia de audio de terceros, deben utilizar audioconferencia en Office 365, que establece el proveedor de conferencia de audio en Microsoft. 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>Pasos a realizar antes de que se puede asignar a un proveedor de conferencia de audio de terceros

1. Dependiendo del plan de Office 365, debe comprar licencias adicionales de **Conferencia de Audio** para las personas de la organización que se va a programar o plomo Skype para reuniones de negocios o Teams de Microsoft mediante conferencias de Audio. Para obtener más información, vea [Skype para negocios y equipos de Microsoft licencias adicionales](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Si ha adquirido licencias adicionales de **Conferencias de Audio** , asignarlos a las personas de la organización que se va a programar o llevar las reuniones que se utilizan en conferencias de Audio. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Si asigna una licencia de **Conferencias de Audio** a otra persona **después** que se les asigne a un proveedor de conferencia de audio de terceros, esa persona se establecerá automáticamente para utilizar en su lugar Microsoft como su proveedor de conferencia de audio! Si esto ocurre, debe quitar Microsoft como proveedor de conferencia de audio antes de poder asignar a un proveedor de conferencia de audio de terceros a ellos.
  
3. Encontrar un proveedor de conferencia de audio de terceros en [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Póngase en contacto con ellos y descubra cómo conseguir cosas con ellos.
    
    Le proporcionará:
    
  - **Números de acceso telefónico (de pago)** y números de teléfono gratuitos si están disponibles.
    
  - **Conferencia de identificadores** que se utilizan para cada persona que programa reuniones. Algunos ACP llame a estos códigos de acceso de la conferencia.
    
    > [!NOTE]
    > Si ha hecho la inicial configurada para un ACP de terceros pero ahora necesita realizar cambios, en la parte inferior de la página de **Puente de Microsoft** **haga clic aquí para configurar un proveedor de conferencia de audio de terceros**. 
  
    > [!NOTE]
    > Cuando habilita a una persona para conferencias de audio y asignarles a un proveedor de conferencia de audio de otros fabricantes, los números de audio y los identificadores de conferencia (contraseñas) se agregan automáticamente a cualquier **nuevo** Skype para reuniones de negocios en línea creados por ellos mismos.
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>Cómo asignar a un proveedor de conferencia de audio de terceros a un usuario

1. En el **Skype para el centro de administración de negocios**, elegir **los usuarios**. Seleccione el usuario de la lista y haga clic en **Editar** en el panel de acción.
    
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
    
4. Compruebe que el archivo devuelto contiene la información correcta. Hemos oído de instancias donde no todos los usuarios enumerados en el archivo tiene la información correcta.
    
5. En **Configurar una página de proveedor de conferencia de audio de terceros**, en **los usuarios importar y exportar**, haga clic en **Asistente para importar**y, a continuación, siga los pasos del **Asistente para importar usuarios**
    
6. Envíe el NIP que recibió del proveedor de conferencia de audio de cada persona. El NIP se requiera para llamar en que el organizador de la conferencia o el líder.
    
    > [!NOTE]
    > Cuando se utiliza un proveedor de conferencia de audio de otros fabricantes, no hay una manera de ver o configurar el PIN en nombre de los organizadores de la reunión. 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>Cuándo utilizar un proveedor de conferencia de audio de terceros

Si estás en un país o región donde no está disponible en Office 365 conferencias de Audio, la calidad de servicio no es gran cosa debido a su ubicación o tiene un contrato existente con un proveedor de conferencia de audio de terceros, se recomienda utilizar un audio de otros fabricantes proveedor de conferencia. De lo contrario, se recomienda utilizar Microsoft como proveedor de conferencia de audio.
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>Automatizar la asignación de proveedor de conferencia de audio de terceros mediante Windows PowerShell

- Para ahorrar tiempo o automatizar esta tarea, puede utilizar el cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) .
    
    > [!NOTE]
    > Para cambiar el proveedor de audio de Microsoft a un proveedor de conferencia de audio de terceros, debe quitar Microsoft como proveedor de conferencia de audio. Para ello, use el cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .
  
- Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## <a name="what-else-do-i-need-to-know"></a>Más información de utilidad

Una persona de su organización sólo puede utilizar un proveedor de conferencia de audio. Para cambiar el proveedor de conferencia de audio de una persona a Microsoft, consulte [mover el proveedor de conferencia de audio de un usuario a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) o [Asignar Microsoft como proveedor de conferencia de audio](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## <a name="related-topics"></a>Temas relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing.md)
  
[Configurar Skype Empresarial Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

