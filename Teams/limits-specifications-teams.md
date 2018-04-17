---
title: Límites y especificaciones de Teams de Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/09/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Obtenga información sobre los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff28cb59dabbf3d9d43dbde00cba73541280b39
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
<a name="limits-and-specifications-for-microsoft-teams"></a>Límites y especificaciones de Teams de Microsoft
=============================================

Este artículo describe algunos de los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams. 

<a name="teams-and-channels"></a>Equipos y canales 
------------------

|Característica    | Límite máximo |
|-----------|---------------|
|Número de equipos que un usuario puede crear | 250         |
|Número de miembros de un equipo | 2.500       |
|Número de equipos que puede crear un administrador global        | Ilimitado   |
|Número de equipos que puede tener un arrendatario de Office 365    | 500.000     |
|Número de canales por equipo    | 200         |

<a name="meetings-and-calls"></a>Conferencias y llamadas 
------------------

|Característica     | Límite máximo |
|------------|---------------|
|Número de personas en una reunión  | 80    |
|Número de personas en una charla privada  | 20    |

<a name="storage"></a>Almacenamiento de información
-------

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Si no tiene habilitado en su inquilino SharePoint Online, los usuarios de Microsoft Teams siempre no pueden compartir archivos en los equipos. Los usuarios de charla privada también no pueden compartir archivos porque se requiere dicha funcionalidad OneDrive para el negocio (que está vinculado a la licencia de SharePoint).

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. (Para obtener más información, consulte [cómo SharePoint Online y OneDrive para el negocio interactúan con equipos de Microsoft](sharepoint-onedrive-interact.md)).

Puesto que los equipos se ejecuta en un back-end de SharePoint Online para compartir archivos, SharePoint limitaciones a la sección de archivos dentro de un equipo. Aquí son los límites de almacenamiento de información aplicable para SharePoint Online.

|Característica                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Almacenamiento de información                 |1 TB por organización además de 0,5 GB por cada licencia adquirida  |1 TB por organización además de 0,5 GB por cada licencia adquirida  |1 TB por organización además de 0,5 GB por cada licencia adquirida   |1 TB por organización además de 0,5 GB por cada licencia adquirida |1 TB por organización además de 0,5 GB por cada licencia adquirida  |1 TB por organización           |
|Almacenamiento de información para archivos de equipos |Hasta 25 TB por colección de sitios o grupo |Hasta 25 TB por colección de sitios o grupo |Hasta 25 TB por colección de sitios o grupo |Hasta 25 TB por colección de sitios o grupo |Hasta 25 TB por colección de sitios o grupo |Hasta 25 TB por colección de sitios o grupo |
|Límite de carga de archivo       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Cada ficha de archivos en los equipos se ejecuta en un servidor de SharePoint Online, por lo que los límites de almacenamiento anteriores se aplican a cada canal dentro de un equipo.

Para obtener más información, consulte [límites de SharePoint Online](https://support.office.com/en-us/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

<a name="messaging"></a>Mensajes
---------

Usuarios que participan en las conversaciones que forman parte de la lista de Chat en Teams de Microsoft deben tener un buzón de Exchange Online (basada en nube) de administrador para buscar conversaciones por chat. Eso es porque las conversaciones que forman parte de la lista de charla se almacenan en los buzones de correo en la nube de los participantes de la charla. Si un participante del chat no tiene un buzón de Exchange Online, el administrador no podrá buscar o colocar una suspensión en las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con buzones locales podrían ser capaces de participar en las conversaciones que forman parte de la lista de Chat en Teams de Microsoft. Sin embargo, en este caso, el contenido de estas conversaciones no pueden buscar y no se puede colocar en suspensión, porque los usuarios no tienen buzones de correo en la nube. (Para obtener más información, consulte [cómo Exchange y equipos de Microsoft interactuar](exchange-teams-interact.md)).

Teams Microsoft chat funciona en un back-end de Microsoft Exchange, para que pueda aplicar lo límites a la función de charla dentro de Microsoft Teams de mensajería de Exchange. Si los usuarios desean enviar un correo electrónico a un canal en equipos, utilizan la dirección de correo electrónico del canal. Una vez que un correo electrónico forma parte de un canal, cualquier persona puede responder para iniciar una conversación. Presentamos algunos de los límites aplicables para enviar correo electrónico a un canal. 

|Característica  |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|---------|---------|---------|---------|---------|
|Límite de tamaño de mensaje&dagger;  |25 KB   |25 KB   |25 KB   |25 KB   |
|Límite de datos adjuntos de archivo&Dagger;  |20     |20     |20     |20    |
|Límite de imágenes en línea&Dagger; |50   |50   |50   |50   |

&dagger;Si el mensaje supera este límite, se genera una vista previa del mensaje y se pregunta al usuario para ver o descargar el correo electrónico original desde el enlace proporcionado.

&Dagger;Si el número de datos adjuntos o imágenes supera este límite, el mensaje no se procesarán y se enviará un correo electrónico NDR al remitente notificándoles acerca del error.

Para obtener más información, consulte [límites de Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

<a name="browsers"></a>Exploradores 
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>Sistemas operativos
-----------------

Para obtener información acerca de los requisitos de sistema operativo, consulte [obtener los clientes de equipos de Microsoft](get-clients.md).


