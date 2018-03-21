---
title: "Ver una lista de usuarios que están habilitados para conferencias de Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. '
ms.openlocfilehash: aedba84f7cda1307dd5fe84d368515220ecb3613
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing"></a>Ver una lista de usuarios que están habilitados para conferencias de Audio

Después de haber habilitado Skype para usuarios de negocios o Teams de Microsoft en su organización para conferencias de Audio, puede ver la lista de aquellos usuarios que se han habilitado. Al mirar la lista, verá también para cada usuario en la lista el tipo de proveedor de conferencia de audio que utiliza, el número de teléfono marcado predeterminado para el usuario, y si la organización no está habilitada para identificadores de conferencia dinámico, la conferencia estática IDs para las reuniones de conferencia de audio que se organizan.
  
## <a name="viewing-a-list-of-users"></a>Ver una lista de los usuarios

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**.
    
## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Al ver la lista de usuarios que están habilitados, puede seleccionar un usuario de la lista y utilice el panel de acción para modificar la configuración de conferencia de audio para ese usuario.
    
- Cuando selecciona un usuario que está configurado para utilizar Microsoft como proveedor de conferencia de audio, puede ver el número de teléfono predeterminado y si su organización está habilitada para identificadores de conferencia dinámico y puede restablecer el Id. de conferencia para las reuniones que la Organiza el usuario.
    
- Al seleccionar un usuario, que está configurado para utilizar un proveedor de conferencia de audio de terceros, puede ver el nombre del proveedor de conferencia de audio, el número de teléfono de pago y el número de teléfono gratuito (si se configuran).
    
- Puede usar las opciones de filtro para mostrar los usuarios que tienen:
    
  - **Conferencias de audio en**
    
  - **Conferencias de audio apagado**
    
  - **Proveedor de conferencias - Microsoft**
    
  - **Proveedor de conferencias - Otros**
    
- Puede usar el botón Buscar para buscar un usuario individual en la lista.
    
- Puede seleccionar más de un usuario y hacer lo siguiente:
    
  - Seleccionar un número predeterminado diferente para estos usuarios.
    
  - Desactivar las conferencias de audio para el usuario, cambiando el proveedor a **Ninguno**.
    
  - Cambie a Microsoft como proveedor de conferencia de audio si al usuario se le ha asignado una licencia de **Conferencia de Audio** .
    
  - Permitir o no permitir a los usuarios anónimos activar las reuniones telefónicas de los usuarios seleccionados.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Conferencias de acceso telefónico en Office 365](set-up-audio-conferencing.md)
