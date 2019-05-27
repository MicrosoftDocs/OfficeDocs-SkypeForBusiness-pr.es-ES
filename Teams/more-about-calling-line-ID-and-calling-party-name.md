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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Obtenga información sobre por qué necesita agregar una persona autorizada que pueda realizar cambios en la cuenta cuando use el Asistente para la solicitud de portabilidad de nuevo número local.
ms.openlocfilehash: e77176b978cb33df2bc4efebae11fb218c3932a5
ms.sourcegitcommit: 4bb900228cc55e0cbbce8c5b74b7de8df5a2288f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "34415757"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama

CallerID, como se hace normalmente, consta de dos partes de información identificables por el usuario:
    - Un número de teléfono (generalmente denominado CLID o identificador de línea de llamada) 
    - Nombre de la persona que llama (normalmente se denomina CNAM), que puede tener hasta 15 caracteres de longitud. 

Cuando se realiza una llamada, la CLID (número de teléfono) se enruta al operador de telefonía del destinatario (también conocido como portador final). La información de CNAM de la llamada puede enrutarse con la llamada, ya que depende de la forma en que el país haya implementado CNAM (si es que es necesario). La fiabilidad de la entrega de CNAM con la llamada varía según el país y los operadores que administran la llamada, ya sea como un intermediario o un portador de terminación. 

La transmisión de CLID & CNAM es responsabilidad del transportista de terminación en la medida en que el portador de terminación debe ser compatible con la funcionalidad CNAM de CLID & y también puede proporcionar registros actualizados para ambos valores. Microsoft proporciona de manera confiable valores de CLID durante las llamadas de origen, pero es posible que esos valores no se mantengan intactos una vez que pasen por un operador intermediario o el portador de terminación. Lamentablemente, en el caso de que el valor de la CLID se cambie, se omita o se elimine o se trunque por parte del transportista o de la terminación, Microsoft tiene poco que recurrir al problema de la red telefónica pública.

Las incoherencias en CNAM pueden estar causadas por retrasos en las transportadoras intermedias o de terminación que actualizan CNAM información de las bases de datos autorizadas, como en el caso de los Estados Unidos. En los países en los que no hay una base de datos autoritaria para CNAM, las prácticas de los operadores individuales también pueden causar problemas con la información de CNAM que se encuentra intacto con la llamada. Actualmente, Microsoft no admite la información de CNAM de origen en países que no sean de Estados Unidos. "

## <a name="related-topics"></a>Temas relacionados


