---
title: Interacción entre Exchange y Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Conozca la funcionalidad que hay entre Microsoft Teams y las distintas configuraciones de Exchange, como crear equipos y unirse a ellos, crear canales y mucho más.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65bbcc3155147141b99f63be686a92b85f87c119
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Interacción entre Exchange y Microsoft Teams 
=========================================

Para disfrutar de la experiencia completa de Microsoft Teams, los usuarios debe habilitar Exchange Online, SharePoint Online y la creación de grupos de Office 365.

Los buzones de Exchange de los usuarios pueden hospedarse en línea o de manera local. Los usuarios hospedados en Exchange Online o Exchange Dedicated vNext pueden usar todas las características de Microsoft Teams. Pueden crear equipos y canales y unirse a ellos, crear y ver reuniones, utilizar las funcionalidades de chat y llamada, modificar imágenes de perfil de usuario, y agregar y configurar conectores, fichas y bots.

Los usuarios hospedados en Exchange Online Dedicated (versión heredada) o Exchange local deben sincronizarse en Azure Active Directory para Office 365. Pueden crear equipos y canales y unirse a ellos, agregar y configurar fichas y bots, y chatear y llamar. Sin embargo, no pueden modificar imágenes de perfil de usuario ni agregar o configurar conectores. Pueden recibir mensajes de conectores configurados por otros usuarios. En cuanto a la creación y visualización de reuniones, hay dos opciones: aunque es posible con Exchange 2016 actualización acumulativa 3 (CU3) y superiores, no lo es con versiones anteriores a Exchange 2016 CU3.

En la siguiente tabla se ofrece información para usuarios con Exchange Online hospedado en diversos entornos.

**Acciones compatibles:** 

| El buzón del usuario se hospeda en: | eDiscovery| Suspensión legal | Retención| Administración del equipo y canal |Crear y ver reuniones| Modificar la imagen de perfil de usuario | Historial de llamadas | Administrar contactos | Acceso a los contactos de Outlook | Correo de voz |Agregar y configurar conectores|Agregar y configurar fichas|Agregar y configurar bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|
|**Exchange Online Dedicated vNext**|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|
|**Exchange Online Dedicated – Versión heredada** (requiere sincronización con Azure AD)|Sí (lista de permitidos)|No|No|Sí|No|No|Sí|Sí|No|Sí (Exchange 2013 +)|No|Sí|Sí|
|**Exchange local** (requiere sincronización con Azure AD)|Sí (lista de permitidos)|No|No|Sí|Sí (Exchange 2016 CU3 +)|No|Sí|Sí|No|Sí (Exchange 2013 +)|No|Sí|Sí|
                                                            
*\*Exchange 2016 CU3 y las versiones posteriores son compatibles*

Información adicional:

-   Microsoft Teams no es compatible con SharePoint local.

-   Para poder compartir y almacenar archivos en las conversaciones del equipo se requiere SharePoint Online.

-   Para poder compartir y almacenar archivos en chats privados se requiere OneDrive para la Empresa.

-   Si los usuarios no tienen habilitadas ni asignadas las licencias de SharePoint Online, no tendrán almacenamiento de OneDrive para la Empresa en Office 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en chats si no disponen de almacenamiento de OneDrive para la Empresa en Office 365.

-   Es necesario habilitar a los usuarios para que puedan crear grupos de Office 365 y así poder crear equipos en Microsoft Teams.

-   En Microsoft Teams, las características de seguridad y cumplimiento (como la exhibición de documentos electrónicos, la búsqueda de contenido, el archivo y la retención legal) funcionan mejor en los entornos de Exchange Online y SharePoint Online. Para las conversaciones del canal, se crea un diario con los mensajes en el buzón del grupo en Exchange Online, y así están disponibles para la exhibición de documentos electrónicos. Si SharePoint Online y OneDrive para la Empresa (usando una cuenta profesional o educativa) están habilitados en toda la organización y para los usuarios, estas características de cumplimiento están disponibles también para todos los archivos de Teams.

> [!NOTE]
> Por el momento, si su organización tiene ciertas normativas por las que se tienen que poder detectar todas las discusiones de las reuniones, debe deshabilitar las reuniones privadas si el organizador tiene un buzón de correo local de Exchange.

> [!IMPORTANT]
  Usuarios que participan en las conversaciones que forman parte de la lista de Chat en Teams de Microsoft deben tener un buzón de Exchange Online (basada en nube) de administrador para buscar conversaciones por chat. Eso es porque las conversaciones que forman parte de la lista de charla se almacenan en los buzones de correo en la nube de los participantes de la charla. Si un participante del chat no tiene un buzón de Exchange Online, el administrador no podrá buscar o colocar una suspensión en las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con buzones locales podrían ser capaces de participar en las conversaciones que forman parte de la lista de Chat en Teams de Microsoft. Sin embargo, en este caso, el contenido de estas conversaciones no pueden buscar y no se puede colocar en suspensión, porque los usuarios no tienen buzones de correo en la nube. Para obtener más información acerca de búsquedas de contenido y Teams de Microsoft, vea [ejecutar una búsqueda de contenido en el centro de cumplimiento de normas y seguridad de Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

> [!TIP]
  Para obtener información acerca de cómo utilizar Azure Connect de AD para sincronizar con Active Directory de Azure, vea [*integración de las identidades locales con Azure Active Directory*](https://go.microsoft.com/fwlink/?linkid=854600).
