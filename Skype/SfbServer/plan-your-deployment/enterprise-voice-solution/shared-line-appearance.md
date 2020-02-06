---
title: Plan para apariencia de línea compartida en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Lea este tema para obtener información sobre cómo planear la apariencia de líneas compartidas (SLA) en Skype empresarial Server 2015, actualización acumulativa de noviembre de 2015.
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802440"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Plan para apariencia de línea compartida en Skype Empresarial Server 2015
 
Lea este tema para obtener información sobre cómo planear la apariencia de líneas compartidas (SLA) en Skype empresarial Server 2015, actualización acumulativa de noviembre de 2015. 
  
La apariencia de las líneas compartidas es una característica de Skype empresarial para administrar varias llamadas en un número específico denominado número compartido. SLA puede configurar cualquier usuario de Skype empresarial habilitado para telefonía empresarial como un número compartido con varias líneas para responder a varias llamadas. En realidad, las llamadas no se reciben en el número compartido, sino que se desvían a usuarios que actúan como delegados para el número compartido. Cualquiera de estos delegados puede responder a la llamada mientras el resto de los delegados recibe una notificación en su teléfono sobre el usuario que respondió a la llamada y la línea que está ocupada como resultado. El número de líneas y los delegados se pueden configurar para un número compartido en SLA. Además, también se pueden configurar otras opciones avanzadas para un número compartido, como BusyOption (que se produce cuando todas las líneas están ocupadas) y MissedCallOption (si ninguno de los delegados responde a una llamada).
  
El SLA solo se admite en los siguientes dispositivos telefónicos (no es compatible con los clientes de Skype empresarial en equipos, teléfonos móviles u otros dispositivos): 
  
- Polycom VVX300 con actualización de firmware 5.4.1
    
- Polycom VVX400 con actualización de firmware 5.4.1
    
- Polycom VVX500 con actualización de firmware 5.4.1
    
- Polycom VVX600 con actualización de firmware 5.4.1
    
SLA es una nueva característica de Skype empresarial Server, actualización acumulativa de noviembre de 2015. 
  
Para obtener información sobre la implementación de SLA, vea [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Lista de características

Configurar un grupo de SLA permite lo siguiente:
  
- Todos los delegados del grupo pueden responder a llamadas entrantes al mismo número compartido. Las llamadas pueden estar basadas en RTC o en SIP.
    
- Los delegados pueden responder llamadas y ponerlas en espera.
    
- Los delegados pueden transferir llamadas a un número fuera del grupo de SLA.
    
- Los delegados pueden ver cuántas llamadas están actualmente en el número compartido, así como ver el estado de esas llamadas.
    
- Puede configurar un número máximo de llamadas simultáneas para el número compartido. Además, puede configurar cómo quiere administrar las llamadas adicionales cuando se alcanza el número máximo. Las llamadas que superen el límite se pueden rechazar con una señal de línea ocupada, desviar a un número alternativo o desviarlas al correo de voz.
    
- Puede configurar cómo quiere administrar las llamadas perdidas (llamadas que no se responden después de un tiempo específico). Si habilita el correo de voz para la identidad de grupo, las llamadas perdidas se desvían automáticamente al correo de voz. Si no tiene habilitado el correo de voz para la identidad de grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de línea ocupada, se desvíen a un número alternativo o se desconecten.
    

