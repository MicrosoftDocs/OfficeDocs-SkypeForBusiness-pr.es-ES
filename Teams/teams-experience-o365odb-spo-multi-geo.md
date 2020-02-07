---
title: Experiencia de Teams en un espacio empresarial de OneDrive y SharePoint Online Multi-Geo en Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Obtenga más información sobre el uso de Teams en un espacio empresarial de Office 365 OneDrive y SharePoint Online con varias geografía habilitadas.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: de798e3e76b4c826cf5b235b61b3fe88e94ea1c7
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837700"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Experiencia de Teams en un espacio empresarial de OneDrive y SharePoint Online Multi-Geo en Office 365
===========================================

Microsoft Teams es un software de chats grupales, el hub para el trabajo en equipo de Office 365. Está alimentado por el servicio de grupos de Office 365, junto con SharePoint Online y OneDrive para la empresa para la experiencia de los archivos. En un inquilino multifunción de OneDrive para la empresa o SharePoint Online, en el que el inquilino se extiende a muchas ubicaciones geográficas, como Norteamérica, Europa y Australia, la experiencia de archivos subyacentes es la de multigeo, por lo que la experiencia de los equipos con la colaboración de archivos también está preparada para varios países. Esta es una función líder de vanguardia para que los equipos se encaran de archivos alojados en varios GEOS en la experiencia de los archivos nativos.

Por ejemplo, en una empresa de Contoso con Europa como una geo de satélite y América del norte como la geo central, un usuario de satélite europeo verá sus archivos de OneDrive en la pestaña archivos en el panel izquierdo, aunque los archivos se hospeden en la ubicación de datos de Europa y en el STAT estadounidense es la ubicación central del inquilino. Además, el usuario puede acceder a los archivos usados recientemente en el blade de la vista recientes. Los archivos recientes pueden incluir archivos compartidos con el usuario de los usuarios en otros GEOS y podrían ser maestros en otras ubicaciones geográficas a las que se extiende el inquilino. 

Un sitio de grupo de un equipo determinado también es compatible con multigeografía. Es decir, si un usuario satélite europeo está creando un equipo, el sitio de grupos correspondiente se creará en la ubicación de Europa y los archivos asociados a ese grupo de equipo se mantendrán en la ubicación. Cualquier experiencia posterior, como cargar un archivo nuevo o editar el archivo, se dirigirá a esa ubicación Europea, manteniendo la promesa de residencia de datos para esos archivos. Esto es posible gracias a la base subyacente de los grupos de Office 365 que se conviertan en multiestado.

Debido a que un inquilino multilingüe es un único inquilino global, durante las @ menciones, los usuarios satélite podrán ver a sus colegas de todo el mundo, sin importar dónde residan. 

Tenga en cuenta que las conversaciones en conversaciones y notas de mensajería instantánea de reuniones dentro de la experiencia de Teams no son muy importantes y se guardan solo dentro de la ubicación central del inquilino. Por lo general, las conversaciones de chat no se aplican a las necesidades de residencia de datos.

Para obtener más información sobre Office 365 multi-Geo, consulte la [Página de funciones multigeo de Microsoft](https://aka.ms/multi-geo).