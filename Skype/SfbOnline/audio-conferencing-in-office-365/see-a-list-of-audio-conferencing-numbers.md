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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo buscar los números de conferencia de acceso telefónico local desde Skype Empresarial Online. '
ms.openlocfilehash: f7343010cfdc34325d2f164b5560c542af0551ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114156"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Ver una lista de números de Audioconferencia de Skype for Business Online

> [!NOTE]
> Para obtener información acerca de los números de Audioconferencia en Microsoft Teams, consulte [Ver una lista de números de Audioconferencia en Microsof Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Cuando establece una Audioconferencia para usuarios de Skype for Business, puede ver los números de teléfono que están a su disposición para audioconferencias. Esta lista tendrá todos los números de teléfono de audioconferencia que están disponibles para su organización.
  
 **¿Busca los precios?** Vea [Precios para audioconferencias.](https://products.office.com/skype-for-business/audio-conferencing#Requirements)
  
> [!IMPORTANT]
> **No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia.** Si quiere ver si hay números de teléfono de acceso telefónico telefónico disponible en su área o país o región, vaya al Centro de administración de **Skype** Empresarial Números de teléfono de voz, haga clic en Agregar y, a continuación, haga clic en Nuevos números de  >    >   **servicio.**  Use las listas de **País o región**, **Estado o región** y **Ciudad** para filtrar la búsqueda. Además, si busca números de servicio gratuitos, **seleccione** Gratuito en la lista Estado **o Región.**
  
Si solo hay un número de teléfono disponible en su organización, todos los usuarios lo usarán como número predeterminado. Cuando varios números de teléfono están disponibles, puede seleccionar el número de teléfono predeterminado para cada usuario. Este número predeterminado se incluirá en las invitaciones a reuniones de Skype Empresarial.
  
Puede ver [Establecer los números de teléfono incluidos en las invitaciones](set-the-phone-numbers-included-on-invites.md) para cambiar el número de teléfono de acceso telefónico de un solo usuario.
  
> [!NOTE]
> Los números de marcado domésticos están dedicados a su organización y son los únicos que pueden configurarse como el número de teléfono predeterminado. Sin embargo, los números de marcado internacionales pueden compartirse en varias organizaciones. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Para ver los números de teléfono de las audioconferencias

1. Inicie sesión con su cuenta de trabajo o escuela.
    
2. Vaya al Centro de administración > **Skype Empresarial.**
    
3. En el **Centro de administración de Skype Empresarial,** en el panel de navegación izquierdo, vaya a Puente de Microsoft de **audioconferencia**  >  y, a continuación, haga lo siguiente:
    
   - Puede ver los números de teléfono que están disponibles para las audioconferencias.
    
   - También puede ver la ubicación y los idiomas principal y secundario que usará el operador automático de audioconferencia.
    
> [!NOTE]
> Puede ir a Usuarios de **audioconferencia** y seleccionar las propiedades del usuario para cambiar el número predeterminado eligiendo un nuevo número de la lista de números disponibles en  >   su organización. Vea [Establecer los números de teléfono incluidos en las invitaciones.](set-the-phone-numbers-included-on-invites.md) 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Get-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber).
    
- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Por qué necesita usar Microsoft 365 u Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del Centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
