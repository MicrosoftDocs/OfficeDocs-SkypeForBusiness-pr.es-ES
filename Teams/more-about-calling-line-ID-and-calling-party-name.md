---
title: Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Obtenga información sobre por qué necesita agregar a una persona autorizada que pueda realizar cambios en la cuenta al usar el Asistente para nueva portabilidad de número local.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255403"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama

El identificador de llamada, como se suele denominar, se compone realmente de dos partes de información identificables hacia el usuario:
    - Un número de teléfono (generalmente denominado ID de línea de llamada o CLID) 
    - Nombre del usuario que llama (generalmente conocido como CNAM), que puede tener hasta 15 caracteres de longitud. 

Cuando se realiza una llamada, el CLID (número de teléfono) se enruta al operador de destino (también conocido como el operador de terminación). La información CNAM de la llamada se puede o no enrutar con la llamada, ya que esto depende de cómo el país haya implementado el CNAM (si es necesario). La confiabilidad de la entrega CNAM con la llamada varía según el país y los operadores que se encargan de la llamada, ya sea como transportista intermedio o de terminación. 

Clid & transmisión CNAM es la responsabilidad del operador de terminación en la medida en que el operador de terminación debe admitir la funcionalidad CNAM de CLID & y proporcionar registros actualizados para ambos valores. Microsoft proporciona valores CLID de forma fiable al crear llamadas, pero es posible que estos valores no se mantengan intactos cuando pasen por un operador intermedio o el operador de terminación. Desafortunadamente, en el caso de que el valor de CLID cambie, se oja o truncará por el operador intermedio o de terminación, Microsoft tendrá poco o ningún recurso para corregir estos problemas en la red telefónica pública.

Las incoherencias en CNAM pueden deberse a retrasos en los operadores intermedios o de terminación que actualizan información CNAM en bases de datos relevantes como en el caso de Estados Unidos. En los países donde no hay ninguna base de datos relevante para CNAM, las prácticas de operadores individuales también pueden causar problemas con la información CNAM que llega intacta con la llamada. Actualmente, Microsoft no admite información CNAM originada en países que no son Estados Unidos".

## <a name="related-topics"></a>Temas relacionados


