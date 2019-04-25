---
title: Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Obtenga información sobre por qué necesita agregar a una persona autorizada que puede realizar cambios en la cuenta cuando se usa el Asistente para nuevo pedido de puerto número Local.
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229871"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama

CallerID, tal y como normalmente se conoce, realmente consta de dos partes de identificación de cara al usuario de la información:
    - Un número de teléfono (normalmente conocido como CLID o llamada de línea Id.) 
    - Llamar al nombre del usuario (que normalmente se denomina CNAM) que puede tener hasta 15 caracteres de longitud. 

Cuando se realiza una llamada, el CLID (número de teléfono) se redirige al operador de destino (también conocido como el operador de terminación). La información de CNAM de la llamada puede o no se pueden enrutar con la llamada como esto depende de cómo ha implementado el país CNAM (si en absoluto). La confiabilidad de entrega CNAM con la llamada varía según el país y operadores que controlan la llamada ya sea como intermediario o un operador de terminación. 

Transmisión de CLID & CNAM es responsabilidad de la compañía de terminación medida en que el operador de terminación debe admitir CLID & CNAM funcionalidad, así como proporcionar registros actualizados para los dos valores. Microsoft proporciona confiable valores CLID cuando se originan las llamadas, pero esos valores no se mantiene intactas una vez que se pasan a través de un intermediario portadora o el operador de terminación. Desafortunadamente, en caso de que el valor CLID se ha cambiado, se omite o truncado por el operador de intermediario o terminación, Microsoft no tiene poca o ninguna recurrir en la corrección de este tipo de problemas en la red telefónica.

Incoherencias en CNAM pueden deberse a los retrasos en el nivel intermedios o terminación operadores actualizar info CNAM en bases de datos relevantes como en el caso de los Estados Unidos. En los países donde no hay ninguna base de datos relevante para CNAM, prácticas de portadora individuales también pueden causar problemas con información CNAM que llega permanecen con la llamada. Microsoft actualmente no admite original información CNAM en países distintos de los Estados Unidos."

## <a name="related-topics"></a>Temas relacionados


