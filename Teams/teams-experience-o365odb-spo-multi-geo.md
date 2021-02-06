---
title: Experiencia de Teams en un entorno multigeómico de Microsoft 365
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
description: En este artículo, aprenderá a usar Teams en un entorno multigeómico de Microsoft 365.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122250"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Experiencia de Teams en un entorno multigeómico de Microsoft 365

Microsoft Teams es un software de chat grupal, el centro para el trabajo en equipo en Microsoft 365 y Office 365. Se usa con tecnología del servicio Microsoft 365 Groups junto con SharePoint Online y OneDrive para la Empresa para mejorar su experiencia con los archivos. En un entorno multige geográfico de OneDrive para la Empresa/SharePoint Online, en el que el espacio empresarial se extiende a muchas ubicaciones geográficas como Norteamérica, Europa y Australia, la experiencia de archivos subyacentes es multigeado, por lo que la experiencia de Teams con la colaboración de archivos también es multigeado. Esta funcionalidad es una funcionalidad principal de Teams para surface los archivos hospedados en varias ubicaciones geográficas en su experiencia de archivos nativos. Esto también incluye archivos de OneNote y wiki.

Por ejemplo, en un entorno de Contoso con Europa como satélite Geo y Norteamérica como geo central, un usuario satélite europeo verá sus archivos de OneDrive en la pestaña Archivos en el panel izquierdo, aunque los archivos se hospedan en la ubicación de datos de Europa y Estados Unidos es la ubicación central del inquilino.  Además, el usuario puede acceder a los archivos usados recientemente en la **hoja vista** Recientes. Los archivos recientes pueden incluir archivos compartidos por usuarios de otras ubicaciones geográficas. 

Un sitio de SharePoint de un equipo determinado también es multigeómico. Es decir, si un usuario satélite europeo está creando un Equipo, el sitio de SharePoint correspondiente se creará en la ubicación de Europa. Los archivos asociados a ese Equipo se mantendrán en reposo en esa ubicación. Las experiencias subsiguientes, como cargar un nuevo archivo o editar el archivo, se almacenarán en esa ubicación europea, manteniendo la promesa de residencia de datos para esos archivos.

Dado que un inquilino multigemico es un único inquilino global, los usuarios de satélites podrán ver a sus compañeros de todo el mundo, independientemente de dónde estén.

Las conversaciones en chats, mensajes de canales y notas de mensajería instantánea de reuniones o chats dentro de la experiencia de Teams no son multiempresa y se mantienen solo dentro de la ubicación central del inquilino. Normalmente, las conversaciones de chat no se aplican a las necesidades de residencia de datos. Para obtener más información, [vea Ubicación de los datos en Microsoft Teams.](location-of-data-in-teams.md)

Para obtener más información sobre multige geo, consulta la página de [capacidades multige geo.](https://aka.ms/multi-geo)
