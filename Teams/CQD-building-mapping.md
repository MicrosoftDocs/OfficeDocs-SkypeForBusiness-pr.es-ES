---
title: Crear un mapa de creación para el panel de calidad de llamadas
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Obtenga información sobre cómo crear un mapa de creación que puede usar para cargar el inquilino y generar datos en el panel de calidad de llamadas (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584039"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Crear un mapa de creación para el panel de calidad de llamadas

En una implementación de Microsoft Teams o Skype Empresarial Online, todos los clientes son externos. Como resultado, de forma predeterminada, todos los clientes se notifican como externos en el Panel de calidad de llamadas (CQD), independientemente de si el cliente está conectado a una red corporativa interna.

Al trabajar con el CQD, necesita saber la ubicación de un punto de conexión y si se conectó a una red que puede administrar o una red que no puede administrar, el supuesto de que solo puede mejorar las redes que puede administrar. Al cargar la subred y la información de edificio en el CQD, habilita el CQD para determinar si el punto de conexión se conectó a una red interna (administrada) o a una red externa (no administrada). Por eso es importante crear un mapa de creación para su organización y [cargarlo en el CQD.](CQD-upload-tenant-building-data.md)

## <a name="building-mapping-tools"></a>Creación de herramientas de asignación

Hay muchas formas de asignar las subredes de su organización. Si necesita ayuda, puede usar el módulo de PowerShell CQDTools que se describe en esta [entrada de blog.](https://aka.ms/cqdtools) Estas herramientas se basan en PowerShell y usan servicios y sitios de Active Directory (AD) y servicios MICROSOFT AND para ayudar a rellenar previamente el archivo de creación. Estas herramientas le ayudarán con las siguientes tareas:

1. Consulte sitios y servicios de AD y cree un archivo de creación basado en la información que contenga.
1. Consulte los servidores o servidores MICROSOFT LAB para extraer la información de subred y crear automáticamente un archivo de creación.
1. Valide un archivo de creación existente, comprobando duplicados y superposiciones.
1. Busque subredes no asociadas en el CQD.

## <a name="related-topics"></a>Temas relacionados

[Cargar datos de inquilino y de edificio en el CQD](CQD-upload-tenant-building-data.md)