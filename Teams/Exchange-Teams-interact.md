---
title: Interacción entre Exchange y Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Conozca la funcionalidad que hay entre Microsoft Teams y las distintas configuraciones de Exchange, como crear equipos y unirse a ellos, crear canales y mucho más.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0f3e24d38e877d923e52de3f1c7116853737dc7
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393351"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interacción entre Exchange y Microsoft Teams

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (AAD), grupos de Office 365, Exchange, SharePoint y OneDrive para la empresa: [bases de Microsoft Teams](https://aka.ms/teams-foundations)

Para disfrutar de la experiencia completa de Teams, los usuarios debe habilitarse en Exchange Online, SharePoint Online y la creación de grupos de Office 365.

Los buzones de Exchange de los usuarios se pueden hospedar en línea o local. Sin embargo, algunas características requieren que haya una implementación híbrida en su lugar con su inquilino de Office 365.

Los usuarios alojados en Exchange online o Exchange Dedicated vNext pueden usar todas las características de Teams. Pueden crear y unirse a equipos y canales, crear y ver reuniones, llamar y conversar, modificar imágenes de Perfil de usuario y agregar y configurar conectores, fichas y bots.

Los usuarios alojados en Exchange Online Dedicated (Legacy) deben sincronizarse con Azure Active Directory en Office 365. Pueden crear y unirse a equipos y canales, agregar y configurar pestañas y bots, y usar las características de chat y llamada. Sin embargo, no pueden modificar las imágenes de perfil, administrar reuniones, obtener acceso a los contactos de Outlook ni administrar conectores.

Los usuarios con buzones locales se deben sincronizar con Azure Active Directory. Pueden usar todas las características del escenario anterior, pero además también pueden cambiar la imagen del perfil de usuario y administrar las reuniones, lo que proporciona a Exchange Server 2016 (la actualización acumulativa 3), o una versión posterior, se ejecute de forma local.

La siguiente tabla proporciona una referencia rápida y útil sobre la disponibilidad de las características basadas en el entorno de Exchange.


**Acciones compatibles:**

| El buzón del usuario se hospeda en: | eDiscovery| Retención&nbsp;legal | Policy| Administración de equipos y canales |Crear y ver reuniones| Modificar la imagen de perfil de usuario | Historial de llamadas | Administrar contactos | Obtener acceso a contactos de Outlook | Correo de voz |Agregar y configurar conectores|Agregar y configurar fichas|Agregar y configurar bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sí <sup>2</sup>|Sí <sup>2</sup>|Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí|
|**Exchange Online Dedicated vNext**|Sí <sup>2</sup>|Sí <sup>2</sup>|Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí |Sí|
|**Exchange Online Dedicated – Versión heredada** (requiere sincronización con Azure AD)|Sí <sup>2</sup>|Sí <sup>, 2, 3</sup>|Sí <sup>4|Sí|No|No|Sí|Sí|No|Sí <sup>5|Sí <sup>6|Sí |Sí|
|**Exchange local** (Requiere sincronización con Azure AD)|Sí <sup>2</sup>| Sí <sup>, 2, 3</sup> |Sí <sup>4|Sí|Sí (Exchange 2016 CU3 +)|Sí (Exchange 2016 CU3 +)|Sí |Sí|No|Sí <sup>5|Sí <sup>6|Sí |Sí|

<sup>1</sup> se admite la versión Exchange 2016 CU3 y versiones posteriores.  

<sup>2</sup> las opciones de hospedaje admiten EDiscovery y retención legal para el cumplimiento de los mensajes de canal.

los mensajes de chat privado de <sup>3</sup> equipos aún no son compatibles con la retención legal de esta opción de hospedaje.

<sup>4</sup> la retención usará un buzón de sombra para que el usuario en línea almacene los mensajes. [Microsoft Teams es compatible con eDiscovery para usuarios de equipos en un entorno híbrido de Exchange](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> los usuarios de equipos con buzón de Exchange local pueden usar el correo de voz con Teams y recibir mensajes de voz en Outlook, pero los mensajes de voz no estarán disponibles para su visualización o reproducción en el cliente de Teams.

<sup>6</sup> si uno de los propietarios de un equipo puede Agregar conectores, todos los demás miembros de ese equipo podrán hacerlo, incluso si sus buzones están alojados en local.


Información adicional:

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisitos para sacar el máximo provecho de Microsoft Teams

Microsoft Teams funciona con varios servicios de Office 365 para ofrecer a los usuarios una experiencia enriquecida. Para admitir esta experiencia, debe habilitar ciertas características o servicios y asignar licencias.

- Para poder compartir y almacenar archivos en las conversaciones del equipo se requiere SharePoint Online. Microsoft Teams no es compatible con SharePoint local.

- Los usuarios deben tener asignada una licencia de SharePoint Online si desean compartir archivos en chats. Si los usuarios no tienen asignada ni habilitada licencias de SharePoint Online, no tienen almacenamiento de OneDrive para la empresa en Office 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en chats sin el almacenamiento de OneDrive para la empresa en Office 365.

- Es necesario habilitar a los usuarios para que puedan crear grupos de Office 365 y así poder crear equipos en Microsoft Teams.

- Para permitir que Microsoft Teams funcione con Exchange local, debe configurar el nuevo protocolo de autenticación de OAuth de Exchange como se describe en [configurar la autenticación de OAuth entre Exchange y las organizaciones de Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

> [!NOTE]
>Para la integración de Exchange local y de Teams, es necesario asignar la licencia necesaria para el usuario sincronizado de AAD.

## <a name="additional-considerations"></a>Consideraciones adicionales

A continuación se muestran algunas cosas que debe tener en cuenta al implementar Microsoft Teams en su organización.

- En Microsoft Teams, las características de seguridad y cumplimiento (como la exhibición de documentos electrónicos, la búsqueda de contenido, el archivo y la retención legal) funcionan mejor en los entornos de Exchange Online y SharePoint Online. Para las conversaciones del canal, se crea un diario con los mensajes en el buzón del grupo en Exchange Online, y así están disponibles para la exhibición de documentos electrónicos. Si SharePoint Online y OneDrive para la Empresa (usando una cuenta profesional o educativa) están habilitados en toda la organización y para los usuarios, estas características de cumplimiento están disponibles también para todos los archivos de Teams.

- Controlar y proteger la configuración de directivas de cumplimiento en Teams y Exchange mediante el acceso condicional. Para obtener más información, vea [¿Cómo funcionan las directivas de acceso condicional para Teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Si su organización tiene requisitos de cumplimiento para garantizar que todas las discusiones de reuniones se descubran, debe deshabilitar las reuniones privadas si el organizador tiene un buzón local de Exchange.

- En una implementación híbrida de Exchange, el contenido de los mensajes instantáneos se pueden buscar independientemente de si los participantes del chat tienen un buzón basado en la nube o un buzón local. Para obtener más información, lea [búsqueda de buzones de correo basados en la nube para usuarios locales en Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para obtener información sobre la búsqueda de contenido en Teams, lea [búsqueda de contenido en el centro de cumplimiento de & de seguridad de Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Para obtener más información sobre cómo usar Azure AD Connect para sincronizar con Azure Active Directory, consulte [integrar las identidades locales con Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
