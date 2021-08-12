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
description: Obtenga información sobre cómo crear un mapa de creación que puede usar para cargar datos de inquilino y creación en el Panel de calidad de llamadas (CQD).
ms.openlocfilehash: fbe033511ad0c717dd79bb5d0bb5b480037175abaa9ce7e5dd40aee334094fff
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314296"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Crear un mapa de creación para el panel de calidad de llamadas (CQD)

En una Microsoft Teams o Skype Empresarial online, todos los clientes son externos. Como resultado, de forma predeterminada, todos los clientes se notifican como externos en el Panel de calidad de llamadas (CQD), independientemente de si el cliente está conectado en una red corporativa interna.

Cuando trabaja con CQD, necesita conocer la ubicación de un punto de conexión y si estaba conectado a una red que puede administrar o una red que no puede administrar, lo que supone que solo puede mejorar las redes que puede administrar. Al cargar la subred y generar información en CQD, habilita CQD para determinar si el punto de conexión estaba conectado a una red interna (administrada) o a una red externa (no administrada). Por eso es importante crear un mapa de creación para su organización y [cargarlo en CQD.](CQD-upload-tenant-building-data.md)

## <a name="building-mapping-tools"></a>Crear herramientas de asignación

Hay muchas maneras de asignar subredes de su organización. Si necesita ayuda, puede usar el módulo de PowerShell CQDTools descrito en esta [entrada de blog.](https://aka.ms/cqdtools) Estas herramientas se basan en PowerShell y usan sitios y servicios de Active Directory (AD) y servicios DE MICROSOFT DHCP para ayudar a rellenar previamente el archivo de creación. Estas herramientas le ayudarán con las siguientes tareas:

1. Consulte sitios y servicios de AD y cree un archivo de creación basado en la información que contiene.
1. Consulte un servidor o servidores DHCP de Microsoft para extraer información de subred y crear automáticamente un archivo de creación.
1. Valide un archivo de creación existente, buscando duplicados y superpuestos.
1. Busque subredes no recortadas en CQD.

## <a name="related-topics"></a>Temas relacionados

[Upload inquilino y generar datos en CQD](CQD-upload-tenant-building-data.md)