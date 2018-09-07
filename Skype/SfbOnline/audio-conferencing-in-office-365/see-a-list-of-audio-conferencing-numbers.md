---
title: Ver una lista de números de Audioconferencia de Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo buscar los números de conferencia de acceso telefónico desde dentro de Skype for Business Online '
ms.openlocfilehash: 118b929f16f0c6edf5c512ddc9b94529a34a8860
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861153"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Ver una lista de números de Audioconferencia de Skype for Business Online

> [!NOTE]
> Para obtener información acerca de los números de Audioconferencia en Microsoft Teams, consulte [Ver una lista de números de Audioconferencia en Microsof Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Cuando establece una Audioconferencia para usuarios de Skype for Business, puede ver los números de teléfono que están a su disposición para audioconferencias. La lista incluirá todos los números de teléfono para audioconferencias que estén disponibles para su organización.
  
 **¿Busca los precios?** Consulte [Precios de Audioconferencia](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia.** Para averiguar si hay números de teléfono de acceso telefónico disponibles en su área o país/región, vaya a **Centro de administración de Skype for Business** > **Voz** > **Números de teléfono**, haga clic en **Agregar** y, a continuación, en **Nuevos números de servicio**. Use las listas de **País o región**, **Estado o región** y **Ciudad** para filtrar la búsqueda. Si busca números de servicio gratuitos, seleccione **Número gratuito** en la lista **Estado o región**.
  
Si solo hay un número de teléfono disponible en su organización, todos los usuarios lo usarán como número predeterminado. Cuando varios números de teléfono están disponibles, puede seleccionar el número de teléfono predeterminado para cada usuario. El número predeterminado se incluirá en las invitaciones a las reuniones de Skype for Business.
  
Puede consultar [Establecer los números de teléfono que se incluyen en invitaciones](set-the-phone-numbers-included-on-invites.md) para cambiar el número de teléfono de marcado para un único usuario.
  
> [!NOTE]
> Los números de marcado domésticos están dedicados a su organización y son los únicos que pueden configurarse como el número de teléfono predeterminado. Sin embargo, los números de marcado internacionales pueden compartirse en varias organizaciones. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Para ver los números de teléfono de audioconferencia

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Puente de Microsoft**, y luego:
    
  - Puede ver los números de teléfono que están disponibles para las audioconferencias.
    
  - También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las audioconferencias.
    
> [!NOTE]
> Puede ir a **Audioconferencia** > **Usuarios** y seleccionar las propiedades del usuario para cambiar el número predeterminado seleccionando un nuevo número de la lista de los números disponibles en su organización. Vea [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
