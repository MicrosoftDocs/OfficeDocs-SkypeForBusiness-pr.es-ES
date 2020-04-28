---
title: Experiencia de Teams en un inquilino multigeo de Microsoft 365 u Office 365 OneDrive y SharePoint Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: En este artículo, obtendrá información sobre cómo usar Teams en un inquilino multigeografía de Microsoft 365 u Office 365 y SharePoint Online.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e754177de6f08476c9160254f2334f6f3ac18d3
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903145"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Experiencia de Teams en un inquilino multigeo de Microsoft 365 u Office 365 OneDrive y SharePoint Online
===========================================

Microsoft Teams es un software de chats grupales, el hub para el trabajo en equipo de Office 365. Está alimentado por el servicio de grupos de Microsoft 365, junto con SharePoint Online y OneDrive para la empresa para la experiencia de los archivos. En un inquilino multifunción de OneDrive para la empresa o SharePoint Online, en el que el inquilino se extiende a muchas ubicaciones geográficas, como Norteamérica, Europa y Australia, la experiencia de archivos subyacentes es la de multigeo, por lo que la experiencia de los equipos con la colaboración de archivos también está preparada para varios países. Esta es una función líder de vanguardia para que los equipos se encaran de archivos alojados en varios GEOS en la experiencia de los archivos nativos.

Por ejemplo, en una empresa de Contoso con Europa como una geo de satélite y Norteamérica como la geo central, un usuario de satélite europeo verá sus archivos de OneDrive en la pestaña archivos en el panel izquierdo, aunque los archivos se hospeden en la ubicación de datos de Europa y los Estados Unidos sean la ubicación central del inquilino. Además, el usuario puede acceder a los archivos usados recientemente en el blade de la vista recientes. Los archivos recientes pueden incluir archivos compartidos con el usuario de los usuarios en otros GEOS y podrían ser maestros en otras ubicaciones geográficas a las que se extiende el inquilino. 

Un sitio de grupo de un equipo determinado también es compatible con multigeografía. Es decir, si un usuario satélite europeo está creando un equipo, el sitio de grupos correspondiente se creará en la ubicación de Europa y los archivos asociados a ese grupo de equipo se mantendrán en la ubicación. Cualquier experiencia posterior, como cargar un archivo nuevo o editar el archivo, se dirigirá a esa ubicación Europea, manteniendo la promesa de residencia de datos para esos archivos. Esto es posible gracias a la base subyacente Microsoft 365 grupos que se están reconocendo con multigeografía.

Debido a que un inquilino multilingüe es un único inquilino global, durante las @ menciones, los usuarios satélite podrán ver a sus colegas de todo el mundo, sin importar dónde residan. 

Tenga en cuenta que las conversaciones en conversaciones y notas de mensajería instantánea de reuniones dentro de la experiencia de Teams no son muy importantes y se guardan solo dentro de la ubicación central del inquilino. Por lo general, las conversaciones de chat no se aplican a las necesidades de residencia de datos.

Para obtener más información sobre Office 365 multi-Geo, consulte la [Página de funciones multigeo de Microsoft](https://aka.ms/multi-geo).