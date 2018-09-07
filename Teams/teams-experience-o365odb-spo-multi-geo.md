---
title: Experimentan de los equipos en un arrendamiento de Multi-ubican-enabled OneDrive de Office 365 y SharePoint Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: Obtenga información acerca del uso de los equipos en un arrendamiento de Multi-ubican-enabled OneDrive de Office 365 y SharePoint Online.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 343b15cd29f3ac40002bf7fe2851faea93f36288
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860750"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Experimentan de los equipos en un arrendamiento de Multi-ubican-enabled OneDrive de Office 365 y SharePoint Online
===========================================

Microsoft Teams es el software de chat de grupo, el concentrador de trabajo en equipo en Office 365. Funciona con el servicio de Office 365 grupos junto con SharePoint Online y OneDrive para la empresa para su experiencia de archivos. En un OneDrive for Business/SharePoint Online Multi-ubican arrendamiento, en el que se extiende el inquilino a muchas ubicaciones geográficas como North America, Europe y Australia, la experiencia de archivos subyacente es Multi-ubican tener en cuenta, por lo que los equipos de la experimentan con archivo la colaboración también es Multi-ubican tener en cuenta. Se trata de una capacidad clave de punta para los equipos para exponer archivos hospeda a lo largo de varias zonas en su experiencia de archivos nativos.

Por ejemplo, en un arrendamiento de Contoso con Europa como un satélite Geo y North America como el ubican central, un usuario de satélite Europeo verán su archivos de OneDrive en la ficha archivos en el panel izquierdo, aunque los archivos se hospedan en la ubicación de datos de Europa y el Stat United es es la ubicación central del inquilino. Además, el usuario puede tener acceso a los archivos utilizados más recientemente en el servidor blade de vista recientes. Archivos recientes pueden incluir los archivos que se comparten con el usuario de los usuarios en otras zonas y es posible que se han usado en otras ubicaciones ubican que se ha ampliado el inquilino a. 

Sitio de grupo de un equipo determinado también es Multi-ubican tener en cuenta. Es decir, si un usuario de satélite europeo es crear un equipo, se creará el sitio de grupos correspondiente en la ubicación de Europa y los archivos asociados con la que el grupo del equipo se mantendrá en reposo en dicha ubicación. Cualquier experiencias posteriores, como cargar un archivo nuevo o editar el archivo, se destinarán a esa ubicación Europea, mantener la promesa de residencia datos para esos archivos. Esto se todos hace posible subyacente Foundation Office 365 grupos convertirse en Multi-ubican tener en cuenta.

Dado que un arrendamiento Multi-ubican es un único inquilino global, durante @ menciones satélite los usuarios podrán ver sus compañeros desde en todo el mundo, independientemente del lugar donde residen. 

Observe que no están Multi-ubican tener en cuenta las conversaciones en chats y notas de mensajería instantánea dentro de la experiencia de los equipos de la reunión y que todos estén mantiene sólo dentro de la ubicación central del inquilino. Normalmente, las conversaciones de chat no se aplican a las necesidades de residencia de datos.

Para obtener más información acerca de Office 365 Multi-ubican, consulte la [página de las capacidades de Microsoft Multi-ubican](https://aka.ms/multi-geo).