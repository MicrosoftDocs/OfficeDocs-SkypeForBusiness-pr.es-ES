---
title: Ver una lista de usuarios que están habilitados para conferencias de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. '
ms.openlocfilehash: d7a5c272968def249df22af25fd36d257f8c74a0
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703468"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing"></a>Ver una lista de usuarios que están habilitados para conferencias de Audio

Después de haber habilitado Skype para los usuarios empresariales o Teams de Microsoft en su organización para conferencias de Audio, puede ver la lista de los usuarios que han sido habilitados. Cuando examine la lista, también verá para cada usuario en la lista el tipo de proveedor de conferencias de audio que están usando, el número de teléfono de acceso telefónico predeterminada para el usuario, y si su organización no está habilitada para los identificadores de conferencia dinámico, la conferencia estática identificadores para las reuniones de conferencia de audio que organizan.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Ver una lista de los usuarios

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

- En el panel de navegación izquierdo, haga clic en **usuarios**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
    
- En el panel de navegación izquierdo, vaya a la **conferencia de Audio** > **a los usuarios**.

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Al ver la lista de usuarios que están habilitadas, puede seleccionar un usuario de la lista y usar el panel de acciones para modificar la configuración de conferencia de audio para que el usuario.
    
- Cuando se selecciona un único usuario que está configurado para usar Microsoft como proveedor de conferencias de audio, puede ver el número de teléfono predeterminado y si la organización está habilitada para los identificadores de conferencia dinámico y puede restablecer el identificador de conferencia para las reuniones que el Organiza el usuario.
    
- Cuando se selecciona un único usuario al que está configurado para usar un proveedor de conferencia de audio de terceros, puede ver el nombre del proveedor de conferencias de audio, el número de teléfono de pago y el número de teléfono gratuito (si se configuran).
    
- Puede usar las opciones de filtro para mostrar los usuarios que tienen:
    
  - **Conferencias de audio en**
    
  - **Conferencias de audio desactivado**
    
  - **Proveedor de conferencias - Microsoft**
    
  - **Proveedor de conferencias - Otros**
    
- Puede usar el botón Buscar para buscar un usuario individual en la lista.
    
- Puede seleccionar más de un usuario y hacer lo siguiente:
    
  - Seleccionar un número predeterminado diferente para estos usuarios.
    
  - Desactivar conferencias de audio para el usuario cambiando el proveedor en **Ninguno**.
    
  - Cambie a Microsoft como proveedor de conferencias de audio si el usuario se ha asignado una licencia de **Conferencias de Audio** .
    
  - Permitir o no permitir a los usuarios anónimos activar las reuniones telefónicas de los usuarios seleccionados.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
