---
title: Ver una lista de usuarios habilitados para conferencias de audio en Skype empresarial online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. '
ms.openlocfilehash: ffc5649a4dc37428fb64915ce6a8b38d0869f388
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680427"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Ver una lista de usuarios habilitados para conferencias de audio en Skype empresarial online

> [!NOTE]
> Para obtener información sobre los usuarios habilitados en Microsoft Teams, vea [una lista de usuarios que están habilitados para conferencias de audio en Microsoft Teams](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

Una vez que haya habilitado a los usuarios de Skype empresarial de su organización para las conferencias de audio, puede ver la lista de los usuarios que se han habilitado. Al mirar la lista, también verá para cada usuario de la lista el tipo de proveedor de servicios de audioconferencia que están usando, el número de teléfono de acceso telefónico local predeterminado para el usuario y, si su organización no tiene habilitada la opción de identificación de conferencia dinámica, los identificadores de conferencia estáticos para las reuniones de audioconferencia que organizan.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Ver una lista de los usuarios

   
- En el navegación de la izquierda, vaya a**usuarios**de la **Conferencia** > de audio.

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Cuando ve la lista de usuarios que están habilitados, puede seleccionar un usuario de la lista y usar el panel de acciones para editar la configuración de la audioconferencia para ese usuario.
    
- Si selecciona un solo usuario configurado para usar Microsoft como el proveedor de servicios de audioconferencia, puede ver el número de teléfono predeterminado y si su organización está habilitada para los identificadores de conferencia dinámicos, y puede restablecer el identificador de conferencia para las reuniones que el usuarios organiza.
    
- Cuando selecciona un solo usuario que está configurado para usar un proveedor de servicios de audioconferencia de terceros, puede ver el nombre del proveedor de servicios de audioconferencia, el número de teléfono de pago y el número de teléfono gratuito (si están configurados).
    
- Puede usar las opciones de filtro para mostrar los usuarios que tienen:
    
  - **Audioconferencia activado**
    
  - **Audioconferencia deshabilitado**
    
  - **Proveedor de conferencias - Microsoft**
    
  - **Proveedor de conferencias - Otros**
    
- Puede usar el botón Buscar para buscar un usuario individual en la lista.
    
- Puede seleccionar más de un usuario y hacer lo siguiente:
    
  - Seleccionar un número predeterminado diferente para estos usuarios.
    
  - Desactive la Conferencia de audio para el usuario cambiando el proveedor a **ninguno**.
    
  - Cambie a Microsoft como el proveedor de servicios de audioconferencia si el usuario tiene asignada una licencia de **audioconferencia** .
    
  - Permitir o no permitir a los usuarios anónimos activar las reuniones telefónicas de los usuarios seleccionados.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
