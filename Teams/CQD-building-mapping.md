---
title: Crear un mapa de creación para el panel de calidad de llamadas (CQD)
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
description: Aprenda a crear un mapa de edificio que pueda usar para cargar inquilinos y datos de compilación en el panel de calidad de llamadas (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584039"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Crear un mapa de creación para el panel de calidad de llamadas (CQD)

En una implementación de Microsoft Teams o de Skype empresarial online, todos los clientes son externos. Como resultado, de forma predeterminada, todos los clientes se notifican como externos en el panel de calidad de llamadas (CQD), independientemente de si el cliente está conectado a una red corporativa interna.

Cuando trabaja con el CQD, necesita conocer la ubicación de un extremo y si está conectado a una red que puede administrar o a una red que no puede administrar; se supone que solo puede mejorar las redes que puede administrar. Al cargar la subred y la información de creación en el CQD, habilitará el CQD para determinar si el punto de conexión se ha conectado a una red interna (administrada) o a una red externa (no administrada). Por eso es importante crear un mapa de creación para la organización y [cargarlo en el CQD](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Creación de herramientas de asignación

Hay muchas maneras de asignar las subredes de su organización. Si necesita ayuda, puede usar el módulo de PowerShell CQDTools que se describe en esta [entrada de blog](https://aka.ms/cqdtools). Estas herramientas se basan en PowerShell y usan sitios y servicios de Active Directory (AD) y servicios DHCP de Microsoft para ayudarle a rellenar previamente el archivo de compilación. Estas herramientas le ayudarán a realizar las siguientes tareas:

1. Consultar sitios y servicios de AD y crear un archivo de compilación basado en la información contenida en él.
1. Consulte un servidor o servidores DHCP de Microsoft para extraer la información de subred y crear automáticamente un archivo de creación.
1. Validar un archivo de compilación existente, comprobando si existen duplicados y superposiciones.
1. Busque subredes sin asignar en el CQD.

## <a name="related-topics"></a>Temas relacionados

[Cargar inquilino y datos de compilación en el CQD](CQD-upload-tenant-building-data.md)