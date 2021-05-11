---
title: Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: Obtenga información sobre el identificador de línea de llamadas y el nombre de la parte de llamadas.
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308319"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama

CallerID consta de dos partes de información orientadas al usuario:

- Un número de teléfono (normalmente conocido como CLID o id. de línea de llamada).

- Nombre del usuario que llama (normalmente denominado CNAM). 

Cuando se realiza una llamada, el CLID (número de teléfono) se enruta al operador del destino (también conocido como el operador de finalización). La información de CNAM para la llamada puede o no enrutada con la llamada, ya que esta información depende de cómo el país haya implementado CNAM (si es que lo hace). La confiabilidad de la entrega CNAM con la llamada varía según el país y los transportistas que se encargan de la llamada, ya sea como intermediario o como transportista de finalización. 

Clid & transmisión CNAM es la responsabilidad del operador de terminación. El operador de terminación debe admitir & funcionalidad CNAM, así como proporcionar registros actualizados para ambos valores. Microsoft proporciona de forma fiable valores CLID al originar llamadas, pero es posible que esos valores no se conservarán intactos una vez que pasen por un operador intermedio o el operador de terminación. Si el operador intermedio o de terminación cambia, omite o trunca el valor CLID, Microsoft tiene poco o ningún recurso para corregir estos problemas en la red telefónica pública.

Las incoherencias en CNAM pueden deberse a que los operadores intermedios o finales retrasan la actualización de la información de CNAM en bases de datos autoritarios, como en el caso de Estados Unidos. En los países donde no hay bases de datos autoritarias para CNAM, las prácticas de operadores individuales también pueden causar problemas con la información de CNAM que llega intacta con la llamada. Actualmente, Microsoft no admite la información CNAM de origen en países distintos de Estados Unidos.

## <a name="related-topics"></a>Temas relacionados


