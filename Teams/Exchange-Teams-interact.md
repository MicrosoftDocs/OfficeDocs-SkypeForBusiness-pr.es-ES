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
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9aeeab6f84b222500829282d29ac06ec73d42ecc
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373339"
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

| El buzón del usuario se hospeda en: | eDiscovery| Suspensión legal | Retención| Equipo y canal mgmt |Crear y ver reuniones| Modificar la imagen de perfil de usuario | Historial de llamadas | Administrar contactos | Obtener acceso a los contactos de Outlook | Correo de voz |Agregar y configurar conectores|Agregar y configurar fichas|Agregar y configurar bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sí<sup>2</sup>|Sí<sup>2</sup>|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|
|**Exchange Online Dedicated vNext**|Sí<sup>2</sup>|Sí<sup>2</sup>|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|
|**Exchange Online Dedicated – Versión heredada** (requiere sincronización con Azure AD)|Sí ([lista de permitidos](https://support.office.com/en-us/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c?ui=en-US&rs=en-US&ad=US))<sup>2</sup>|Sí,<sup>2, 3</sup>|No|Sí|No|No|Sí|Sí|No|No|No|Sí|Sí|
|**Exchange local** (requiere sincronización con Azure AD)|Sí ([lista de permitidos](https://support.office.com/en-us/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c?ui=en-US&rs=en-US&ad=US))<sup>2</sup>|Sí,<sup>2, 3</sup>|No|Sí|Sí (Exchange 2016 CU3 +)|No|Sí|Sí|No|No|No|No|Sí|
                                                            
<sup>1</sup> CU3 de 2016 admite exchange y por encima de  
<sup>2</sup> de exhibición de documentos electrónicos y retención Legal para el cumplimiento de mensajes del canal es compatible con todas las opciones de hospedaje.  
<sup>3</sup> mensajes de chat privado de los equipos aún de no admiten la suspensión Legal para esta opción de hospedaje.

Información adicional:

-   Microsoft Teams no es compatible con SharePoint local.

-   Para poder compartir y almacenar archivos en las conversaciones del equipo se requiere SharePoint Online.

-   Para poder compartir y almacenar archivos en chats privados se requiere OneDrive para la Empresa.

-   Si los usuarios no tienen habilitadas ni asignadas las licencias de SharePoint Online, no tendrán almacenamiento de OneDrive para la Empresa en Office 365. El uso compartido de archivos seguirá funcionando en canales, pero los usuarios no podrán compartir archivos en chats si no disponen de almacenamiento de OneDrive para la Empresa en Office 365.

-   Es necesario habilitar a los usuarios para que puedan crear grupos de Office 365 y así poder crear equipos en Microsoft Teams.

-   En Microsoft Teams, las características de seguridad y cumplimiento (como la exhibición de documentos electrónicos, la búsqueda de contenido, el archivo y la retención legal) funcionan mejor en los entornos de Exchange Online y SharePoint Online. Para las conversaciones del canal, se crea un diario con los mensajes en el buzón del grupo en Exchange Online, y así están disponibles para la exhibición de documentos electrónicos. Si SharePoint Online y OneDrive para la Empresa (usando una cuenta profesional o educativa) están habilitados en toda la organización y para los usuarios, estas características de cumplimiento están disponibles también para todos los archivos de Teams.

-   Para Exchange local (implementación híbrida), debe configurar OAuth tal como se describe en [Configurar OAuth autenticación entre organizaciones de Exchange y Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx). 

> [!NOTE]
> Por el momento, si su organización tiene ciertas normativas por las que se tienen que poder detectar todas las discusiones de las reuniones, debe deshabilitar las reuniones privadas si el organizador tiene un buzón de correo local de Exchange.
> 
> [!IMPORTANT]
>   Los usuarios que participan en las conversaciones que forman parte de la lista de Chat en Microsoft Teams deben tener un buzón de Exchange Online (basada en la nube) para un administrador buscar las conversaciones de chat. Eso es porque las conversaciones que forman parte de la lista de Chat se almacenan en los buzones de correo basados en la nube de los participantes de chat. Si un participante de chat no tiene un buzón de Exchange Online, el administrador no podrá buscar o colocar una suspensión en las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con buzones locales es posible que puedan participar en las conversaciones que forman parte de la lista de Chat en Microsoft Teams. Sin embargo, en este caso, el contenido de estas conversaciones no es que admite búsquedo y no se puede colocar en espera, debido a que los usuarios no dispongan de buzones de correo basados en la nube. Para obtener más información acerca de las búsquedas de contenido y Microsoft Teams, vea [ejecutar una búsqueda de contenido en el centro de cumplimiento y seguridad de Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).
> 
> [!TIP]
>   Para obtener información acerca de cómo usar Azure Connect de AD para sincronizar con Azure Active Directory, vea [*integración de sus identidades local con Azure Active Directory*](https://go.microsoft.com/fwlink/?linkid=854600).
