---
title: Crear una asignación de creación para el panel de calidad de llamadas (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Obtenga información sobre cómo crear un mapa de creación que puede usar para cargar inquilinos y generar datos en el Panel de calidad de llamadas .
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789825"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Crear una asignación de creación para el panel de calidad de llamadas (CQD)

En una implementación de Microsoft Teams o Skype Empresarial Online, todos los clientes son externos. Como resultado, de forma predeterminada, todos los clientes se notifican como externos en el Panel de calidad de llamadas (CQD), independientemente de si el cliente está conectado en una red corporativa interna.

Cuando trabaja con el CQD, necesita saber la ubicación de un punto de conexión y si estaba conectado a una red que puede administrar o una red que no puede administrar, suponiendo que solo puede mejorar las redes que puede administrar. Al cargar la subred y generar información en el CQD, habilita al CQD para determinar si el punto de conexión estaba conectado a una red interna (administrada) o a una red externa (no administrada). Por eso es importante crear un mapa de creación para su organización y [cargarlo en el CQD](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Crear herramientas de asignación

Hay muchas maneras de asignar las subredes de su organización. Si necesita ayuda, puede usar el módulo de PowerShell CQDTools que se describe en esta [entrada de blog](https://aka.ms/cqdtools). Estas herramientas se basan en PowerShell y usan servicios y sitios de Active Directory (AD) y servicios DHCP de Microsoft para ayudar a rellenar previamente el archivo de compilación. Estas herramientas le ayudarán con las siguientes tareas:

1. Consulte servicios y sitios de AD y cree un archivo de compilación basado en la información contenida en.
1. Consulte un servidor DHCP de Microsoft o servidores para extraer información de subred y crear automáticamente un archivo de compilación.
1. Valide un archivo de compilación existente, comprobando si hay duplicados y solapamientos.
1. Busque subredes no asignadas en el CQD.

## <a name="related-topics"></a>Temas relacionados

[Cargar datos de inquilinos y compilación en el CQD](CQD-upload-tenant-building-data.md)