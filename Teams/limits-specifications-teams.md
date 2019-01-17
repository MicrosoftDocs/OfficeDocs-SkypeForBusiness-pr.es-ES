---
title: Límites y especificaciones para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: karuanag
description: Obtenga información sobre los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa699ebabd57299ef2ced07c2c6d0fc551ac6b17
ms.sourcegitcommit: 0fcca2d8303da82cc00a504f4183bee50ab23eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328258"
---
<a name="limits-and-specifications-for-microsoft-teams"></a>Límites y especificaciones para Microsoft Teams
=============================================

En este artículo se describe algunos de los límites, especificaciones y otros requisitos que se aplican a Microsoft Teams. 

<a name="teams-and-channels"></a>Equipos y canales 
------------------

|Característica    | Límite máximo |
|-----------|---------------|
|Número de equipos, que puede crear un usuario | Sujeto a un limit&sup1 250 objeto;         |
|Número de miembros de un equipo | 2.500       |
|Número de miembros de un [equipo de toda la organización](create-an-org-wide-team.md) | 2.500       |
|Número de equipos, que puede crear un administrador global        |  500.000   |
|Número de equipos que puede tener un inquilino de Office 365    | 500.000     |
|Número de canales por equipo    | 200 (incluye canales eliminados)         |

&sup1; Los recuentos de cualquier objeto de directorio en Azure Active Directory para este límite.

<a name="meetings-and-calls"></a>Las reuniones y llamadas 
------------------

|Característica     | Límite máximo |
|------------|---------------|
|Número de personas en una reunión  | 250    |
|Número de personas en un chat privado  | 50    |

<a name="storage"></a>Almacenamiento de información
-------

Cada equipo de Microsoft Teams tiene un sitio de grupo en SharePoint Online y cada canal de un equipo tiene una carpeta dentro de la biblioteca de documentos del sitio de grupo predeterminado. Los archivos compartidos en un chat se agregan automáticamente a la biblioteca de documentos y los permisos y opciones de seguridad configurados en SharePonit se reflejan automáticamente en Microsoft Teams.

Si no tiene habilitado en el inquilino de SharePoint Online, los usuarios de Microsoft Teams siempre no pueden compartir archivos en los equipos. Los usuarios de chat privado también no pueden compartir archivos porque es necesario para que la funcionalidad OneDrive para la empresa (que está asociado a la licencia de SharePoint).

Al almacenar archivos en la biblioteca de documentos de SharePoint Online y OneDrive para la Empresa, se siguen todas las reglas de cumplimiento configuradas en el nivel de inquilino. (Para obtener más información, vea [cómo SharePoint Online y OneDrive para la empresa interactúan con los equipos de Microsoft](sharepoint-onedrive-interact.md)).

Dado que los equipos se ejecuta en un back-end de SharePoint Online para uso compartido de archivos, SharePoint limitaciones se aplican a la sección de los archivos dentro de un equipo. Estos son los límites de almacenamiento de información aplicable para SharePoint Online.

|Característica                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Almacenamiento de información                 |1 TB por organización más de 10 GB por cada licencia adquirida  |1 TB por organización más de 10 GB por cada licencia adquirida  |1 TB por organización más de 10 GB por cada licencia adquirida   |1 TB por organización más de 10 GB por cada licencia adquirida |1 TB por organización más de 10 GB por cada licencia adquirida  |1 TB por organización           |
|Almacenamiento de información para los archivos de los equipos |Hasta 25 TB por colección de sitios o de grupo |Hasta 25 TB por colección de sitios o de grupo |Hasta 25 TB por colección de sitios o de grupo |Hasta 25 TB por colección de sitios o de grupo |Hasta 25 TB por colección de sitios o de grupo |Hasta 25 TB por colección de sitios o de grupo |
|Límite de carga de archivo       |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

Cada ficha archivos en los equipos se ejecuta en un back-end de SharePoint Online, por lo que los límites de almacenamiento de información anteriores se aplican a cada canal dentro de un equipo.

Para obtener más información, vea [los límites de SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

<a name="messaging"></a>Mensajes
---------

Los usuarios que participan en las conversaciones que forman parte de la lista de Chat en Microsoft Teams deben tener un buzón de Exchange Online (basada en la nube) para un administrador buscar las conversaciones de chat. Eso es porque las conversaciones que forman parte de la lista de Chat se almacenan en los buzones de correo basados en la nube de los participantes de chat. Si un participante de chat no tiene un buzón de Exchange Online, el administrador no podrá buscar o colocar una suspensión en las conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con buzones locales es posible que puedan participar en las conversaciones que forman parte de la lista de Chat en Microsoft Teams. Sin embargo, en este caso, el contenido de estas conversaciones no es que admite búsquedo y no se puede colocar en espera, debido a que los usuarios no dispongan de buzones de correo basados en la nube. (Para obtener más información, vea [cómo Exchange y los equipos de Microsoft interactuar](exchange-teams-interact.md)).

Función de chat de Microsoft Teams funciona en un back-end de Microsoft Exchange, para que pueda aplicar los límites a la función de chat dentro de Microsoft Teams de mensajería de Exchange. Si desean que los usuarios enviar un correo electrónico a un canal en los equipos, utilizan la dirección de correo electrónico de canal. Una vez que un correo electrónico forma parte de un canal, cualquier persona puede responder a ella para iniciar una conversación. Éstos son algunos de los límites aplicables para el envío de correo electrónico a un canal. 

|Característica  |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|---------|---------|---------|---------|---------|
|Límite de tamaño de mensaje&dagger;  |25 KB   |25 KB   |25 KB   |25 KB   |
|Límite de datos adjuntos del archivo&Dagger;  |20     |20     |20     |20    |
|Límite de imágenes en línea&Dagger; |50   |50   |50   |50   |

&dagger;Si el mensaje supera este límite, se genera una vista previa del mensaje y se pregunta al usuario a la vista y descarga el correo electrónico original desde el vínculo proporcionado.

&Dagger;Si el número de datos adjuntos o imágenes excede este límite, no se procesará el mensaje y se enviará un correo electrónico NDR al remitente donde se notifica el error.

Para obtener más información, vea [los límites de Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

<a name="browsers"></a>Exploradores de  
--------

[!INCLUDE [browser-support](includes/browser-support.md)]

<a name="operating-systems"></a>Sistemas operativos
-----------------

Para obtener información acerca de los requisitos de sistema operativo, vea [obtener los clientes de equipos de Microsoft](get-clients.md).


