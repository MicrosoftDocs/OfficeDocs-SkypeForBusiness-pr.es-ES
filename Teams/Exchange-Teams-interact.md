---
title: Interacción entre Exchange y Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Conozca la funcionalidad que hay entre Microsoft Teams y las distintas configuraciones de Exchange, como crear equipos y unirse a ellos, crear canales y mucho más.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c251255807e1c673c672db20a85b7f56c4a64d6
ms.sourcegitcommit: 47b29c15ca3cf1676168608537613f3b841dbfcb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "29992820"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Interacción entre Exchange y Microsoft Teams 
=========================================

> [!Tip]
> Vea la sesión siguiente para obtener información sobre cómo los equipos interactúa con Azure Active Directory (AAD), grupos de Office 365, Exchange, SharePoint y OneDrive para la empresa: [Fundamentos de los equipos de Microsoft](https://aka.ms/teams-foundations)

Para disfrutar de la experiencia completa de Microsoft Teams, los usuarios debe habilitar Exchange Online, SharePoint Online y la creación de grupos de Office 365.

Los buzones de Exchange de los usuarios pueden hospedarse en línea o de manera local. Los usuarios hospedados en Exchange Online o Exchange Dedicated vNext pueden usar todas las características de Microsoft Teams. Pueden crear equipos y canales y unirse a ellos, crear y ver reuniones, utilizar las funcionalidades de chat y llamada, modificar imágenes de perfil de usuario, y agregar y configurar conectores, fichas y bots.

Los usuarios hospedados en Exchange Online Dedicated (versión heredada) o Exchange local deben sincronizarse en Azure Active Directory para Office 365. Pueden crear equipos y canales y unirse a ellos, agregar y configurar fichas y bots, y chatear y llamar. Sin embargo, no pueden modificar imágenes de perfil de usuario ni agregar o configurar conectores. Pueden recibir mensajes de conectores configurados por otros usuarios. En cuanto a la creación y visualización de reuniones, hay dos opciones: aunque es posible con Exchange 2016 actualización acumulativa 3 (CU3) y superiores, no lo es con versiones anteriores a Exchange 2016 CU3.

En la siguiente tabla se ofrece información para usuarios con Exchange Online hospedado en diversos entornos.

**Acciones compatibles:** 

| El buzón del usuario se hospeda en: | eDiscovery| Legal&nbsp;suspensión | Retención| Equipo y canal mgmt |Crear y ver reuniones| Modificar la imagen de perfil de usuario | Historial de llamadas | Administrar contactos | Obtener acceso a los contactos de Outlook | Correo de voz |Agregar y configurar conectores|Agregar y configurar fichas|Agregar y configurar bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sí <sup>2</sup>|Sí <sup>2</sup>|Sí |Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí |Sí|
|**Exchange Online Dedicated vNext**|Sí <sup>2</sup>|Sí <sup>2</sup>|Sí |Sí |Sí|Sí|Sí |Sí|Sí|Sí|Sí |Sí |Sí|
|**Exchange Online Dedicated – Versión heredada** (requiere sincronización con Azure AD)|Sí <sup>2</sup>|Sí <sup>2,3</sup>|Sí <sup>4|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|Sí|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|No|Sí|Sí|
|**Exchange local** (requiere sincronización con Azure AD)|Sí <sup>2</sup>| Sí <sup>2,3</sup> |Sí <sup>4|Sí|Sí (Exchange 2016 CU3 +)|No|Sí|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No <sup>5|No|No|Sí|

<sup>1</sup> CU3 de 2016 admite exchange y por encima de  
<sup>2</sup> de exhibición de documentos electrónicos y retención Legal para el cumplimiento de mensajes del canal es compatible con todas las opciones de hospedaje.  
<sup>3</sup> mensajes de chat privado de los equipos aún de no admiten la suspensión Legal para esta opción de hospedaje.

<sup>4</sup> retención va a usar un buzón de sombra para el usuario en línea para almacenar los mensajes. [Exhibición de documentos electrónicos es compatible con los equipos de Microsoft para el usuario de los equipos en un entorno de implementación híbrida de Exchange](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> usuarios de los equipos con locales buzón de Exchange puede usar el correo de voz con los equipos y recibir mensajes de correo de voz en Outlook, pero los mensajes de correo de voz no estarán disponibles para ver o reproducir el cliente de los equipos.

Información adicional:

-   Microsoft Teams no es compatible con SharePoint local.

-   Para poder compartir y almacenar archivos en las conversaciones del equipo se requiere SharePoint Online.

-   Para poder compartir y almacenar archivos en chats privados se requiere OneDrive para la Empresa.

-   Si los usuarios no tienen habilitadas ni asignadas las licencias de SharePoint Online, no tendrán almacenamiento de OneDrive para la Empresa en Office 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en chats si no disponen de almacenamiento de OneDrive para la Empresa en Office 365.

-   Es necesario habilitar a los usuarios para que puedan crear grupos de Office 365 y así poder crear equipos en Microsoft Teams.

-   En Microsoft Teams, las características de seguridad y cumplimiento (como la exhibición de documentos electrónicos, la búsqueda de contenido, el archivo y la retención legal) funcionan mejor en los entornos de Exchange Online y SharePoint Online. Para las conversaciones del canal, se crea un diario con los mensajes en el buzón del grupo en Exchange Online, y así están disponibles para la exhibición de documentos electrónicos. Si SharePoint Online y OneDrive para la Empresa (usando una cuenta profesional o educativa) están habilitados en toda la organización y para los usuarios, estas características de cumplimiento están disponibles también para todos los archivos de Teams.

-   Para Exchange local, debe para configurar OAuth tal como se describe en [Configurar OAuth autenticación entre organizaciones de Exchange y Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx). 

> [!NOTE]
> Por el momento, si su organización tiene ciertas normativas por las que se tienen que poder detectar todas las discusiones de las reuniones, debe deshabilitar las reuniones privadas si el organizador tiene un buzón de correo local de Exchange.
> 
> [!IMPORTANT]
> En una implementación híbrida de Exchange, contenido de mensajes de chat es que admite búsquedo independientemente de si los participantes de chat tienen un buzón de correo basados en la nube o un buzón de correo local. Para obtener más información, lea [los buzones basados en la nube de búsqueda para los usuarios de Office 365 local](https://docs.microsoft.com/en-us/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para obtener información acerca de cómo buscar contenido en los equipos, lea la [Búsqueda de contenido en el centro de cumplimiento de seguridad de Office 365 &](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).
> 
> [!TIP]
> Para obtener información acerca de cómo usar Azure Connect de AD para sincronizar con Azure Active Directory, vea [integración de sus identidades local con Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
