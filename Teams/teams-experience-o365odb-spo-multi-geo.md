---
title: Experiencia de Teams en un entorno multilingüe habilitado de Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
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
description: En este artículo, obtendrá información sobre el uso de Teams en un entorno multilingüe habilitado de Microsoft 365.
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757755"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Experiencia de Teams en un inquilino multilingüe habilitado en Microsoft 365

Microsoft Teams es un software de chats grupales, el hub para el trabajo en equipo de Microsoft 365. Es alimentado por el servicio Microsoft 365 Groups, junto con SharePoint y OneDrive para la experiencia de los archivos. En una organización multigeográfica en la que el inquilino se extiende a muchas ubicaciones geográficas, como América del norte, Europa y Australia, la experiencia de archivos subyacentes es la que tiene conciencia múltiple, por lo que la experiencia de los equipos con la colaboración de archivos también está preparada para varios países. Esto permite a los equipos exponer archivos alojados en varias ubicaciones geográficas en la experiencia de los archivos nativos.

Por ejemplo, en una empresa de Contoso con Europa como una geo de satélite y Norteamérica como la geo central, un usuario de satélite europeo verá sus archivos de OneDrive en la pestaña archivos en el panel izquierdo, aunque los archivos se hospeden en la ubicación de datos de Europa y los Estados Unidos sean la ubicación central del inquilino. Además, el usuario puede acceder a los archivos usados recientemente en el blade de la vista recientes. Los archivos recientes pueden incluir archivos compartidos de usuarios en otras ubicaciones geográficas. 

Un sitio de SharePoint de un equipo determinado también es compatible con multigeografía. Es decir, si un usuario satélite europeo está creando un equipo, el sitio de SharePoint correspondiente se creará en la ubicación Europa y los archivos asociados con ese equipo se mantendrán en esa ubicación. Cualquier experiencia posterior, como cargar un archivo nuevo o editar el archivo, se almacenará en esa ubicación Europea, manteniendo la promesa de la residencia de datos para esos archivos.

Tenga en cuenta que las conversaciones en los chats y en las notas de mensajería instantánea de reuniones dentro de la experiencia de Teams no son muy importantes y se guardan solo dentro de la ubicación central de la organización.

Para obtener más información sobre multi-Geo, vea [funciones multigeo de Microsoft](https://aka.ms/multi-geo).
