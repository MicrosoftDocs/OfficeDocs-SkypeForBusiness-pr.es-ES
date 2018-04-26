---
title: Más información sobre identificador de línea llama y llamar a nombre de entidad
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Obtenga información acerca de por qué necesita agregar a una persona autorizada que puede realizar cambios en la cuenta cuando se utiliza el Asistente para nuevo pedido de puerto número Local.
ms.openlocfilehash: 1174ba5837bb91c3251232ab48fa63c343425ac1
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Más información sobre identificador de línea llama y llamar a nombre de entidad

CallerID, como normalmente se conoce, consta realmente de dos partes identificables de cara al usuario de información:
    - Un número de teléfono (normalmente conocido como CLID o llamar a la línea Id.) 
    - Nombre del fabricante (normalmente denominado CNAM) que puede tener hasta 15 caracteres de longitud que llama. 

Cuando se realiza una llamada, el CLID (número de teléfono) se enruta al portador del destino (también conocido como el portador de terminación). La información de CNAM de la llamada puede o no se pueden enrutar a la llamada como esto depende de cómo el país ha implementado CNAM (si). La confiabilidad de entrega CNAM con la llamada varía dependiendo del país y los transportistas que controlan la llamada como un intermediario o una compañía de terminación. 

Transmisión CLID & CNAM es responsabilidad terminación del portador de la medida en que el transportista terminación debe admitir funcionalidad CLID & CNAM así como proporcionar registros actualizados para ambos valores. Microsoft proporciona confiablemente valores CLID cuando origina llamadas, pero dichos valores no se mantiene intactos cuando pasan a través de un intermediario portador o la portadora de terminación. Por desgracia, en caso de que el valor CLID se cambia, se omite o truncado por el transportista intermediario o terminación, Microsoft no tiene poco a ningún recurso en la corrección de este tipo de problemas en la red telefónica pública.

Incoherencias en el CNAM pueden deberse a retrasos en la terminación o intermedios portadores actualizar info CNAM en bases de datos autorizados como en el caso de los Estados Unidos. En los países donde no existe ninguna base de datos autorizado para CNAM, prácticas de portadora individuales también pueden causar problemas con información CNAM que lleguen intactos a la llamada. Microsoft actualmente no admite información de origen CNAM en países distintos de EE."

## <a name="related-topics"></a>See also


