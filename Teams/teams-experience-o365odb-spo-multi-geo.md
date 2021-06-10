---
title: Teams experiencia en un Microsoft 365 multi-geo-enabled
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
description: En este artículo, aprenderá a usar Teams en un Microsoft 365 habilitado para varias ubicaciones geográficas.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760543"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams experiencia en un Microsoft 365 de arrendamiento habilitado para varias ubicaciones geográficas

Microsoft Teams es el software de chat grupal, el centro para el trabajo en equipo en Microsoft 365 y Office 365. Funciona con tecnología del servicio Microsoft 365 Groups junto con SharePoint Online y OneDrive para la Empresa para su experiencia de archivos. En una tenencia de OneDrive para la Empresa/SharePoint Online Multi-Geo, en la que el espacio empresarial se extiende a muchas ubicaciones geográficas como Norteamérica, Europa y Australia, la experiencia de archivos subyacentes es multi-geo-aware, por lo que la experiencia Teams con la colaboración de archivos también es multi-geo-aware. Esta funcionalidad es una funcionalidad clave de vanguardia para Teams a los archivos de superficie hospedados en varios geos en su experiencia de archivos nativos. Esto también incluye OneNote y wiki.

Por ejemplo, en una tenencia de Contoso con Europa como satélite Geo y Norteamérica como geo central,  un usuario de satélite europeo verá sus archivos OneDrive en la pestaña Archivos en el panel izquierdo, aunque los archivos se hospedan en la ubicación de datos de Europa y Estados Unidos es la ubicación central del inquilino. Además, el usuario puede obtener acceso a los archivos usados más recientemente en la **hoja Vista** reciente. Los archivos recientes pueden incluir archivos compartidos de usuarios en otras ubicaciones geográficas. 

Un determinado sitio de SharePoint equipo también es multiges geoeconsciente. Es decir, si un usuario de satélite europeo está creando un equipo, el sitio SharePoint se creará en la ubicación de Europa. Los archivos asociados a ese equipo se conservarán en reposo en esa ubicación. Cualquier experiencia posterior, como cargar un archivo nuevo o editarlo, se almacenará en esa ubicación europea, manteniendo la promesa de residencia de datos para esos archivos.

Dado que una tenencia Multi-Geo es un único inquilino global, durante @ menciones los usuarios de satélite podrán ver a sus compañeros de todo el mundo, independientemente de dónde estén.

Las conversaciones en chats, mensajes de canales y chats de mensajería instantánea de reunión dentro de la experiencia de Teams no son multigestivas y se mantienen solo dentro de la ubicación central del inquilino. Normalmente, las conversaciones de chat no se aplican a las necesidades de residencia de datos. Para obtener más información, vea [Ubicación de datos en Microsoft Teams](location-of-data-in-teams.md).

La compatibilidad multiges geográfica para Teams está en el [mapa Microsoft 365 ruta.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)

Para obtener más información sobre Multi-Geo, consulte la página de capacidades [multi geo de Microsoft](https://aka.ms/multi-geo).
