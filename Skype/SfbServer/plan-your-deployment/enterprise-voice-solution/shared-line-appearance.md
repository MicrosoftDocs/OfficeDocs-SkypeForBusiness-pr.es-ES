---
title: Planear la apariencia de línea compartida en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Lea este tema para obtener información sobre cómo planear la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015.
ms.openlocfilehash: cabd5a9f6780371a8345bd95c5686829e74ad3c18e875ec85decf6ab0ca2f789
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289728"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planear la apariencia de línea compartida en Skype Empresarial Server 2015
 
Lea este tema para obtener información sobre cómo planear la apariencia de línea compartida (SLA) en Skype Empresarial Server 2015, actualización acumulativa de noviembre de 2015. 
  
La apariencia de línea compartida es una característica Skype Empresarial para controlar varias llamadas en un número específico denominado número compartido. SLA puede configurar cualquier voz de empresa habilitada Skype Empresarial usuario como un número compartido con varias líneas para responder a varias llamadas. En realidad, las llamadas no se reciben en el número compartido, sino que se reenvían a los usuarios que actúan como delegados del número compartido. Cualquiera de los delegados puede recoger la llamada mientras el resto de los delegados recibe una notificación en su teléfono sobre quién ha recogido la llamada y qué línea se ha ocupado como resultado. Tanto el número de líneas como los delegados se pueden configurar para un número compartido en SLA. Además, las opciones avanzadas, como BusyOption (lo que sucede en una situación en la que todas las líneas están ocupadas) y MissedCallOption (el caso en el que ninguno de los delegados recoge una llamada), también se pueden configurar para un número compartido.
  
SLA solo se admite en los siguientes dispositivos telefónicos (no se admite para Skype Empresarial en equipos, teléfonos móviles u otros dispositivos): 
  
- Polycom VVX300 con actualización de firmware 5.4.1
    
- Polycom VVX400 con actualización de firmware 5.4.1
    
- Polycom VVX500 con actualización de firmware 5.4.1
    
- Polycom VVX600 con actualización de firmware 5.4.1
    
SLA es una nueva característica de Skype Empresarial Server, actualización acumulativa de noviembre de 2015. 
  
Para obtener información sobre la implementación de SLA, vea [Deploy Shared Line Appearance in Skype Empresarial Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Lista de características

La configuración de un grupo de SLA permite lo siguiente:
  
- Todos los delegados del grupo pueden responder llamadas entrantes al mismo número compartido. Las llamadas pueden estar basadas en RTC o en SIP.
    
- Los delegados pueden retener y recoger llamadas.
    
- Los delegados pueden transferir llamadas a un número fuera del grupo sla.
    
- Los delegados pueden ver cuántas llamadas se encuentran actualmente en el número compartido y ver el estado de cada una de esas llamadas.
    
- Puede configurar un número máximo de llamadas simultáneas para el número compartido. También puede establecer cómo desea que se controle el número de llamadas adicionales después de alcanzar este máximo. El exceso de llamadas puede rechazarse con una señal de disponibilidad, reenviarse a un número alternativo o reenviarse al correo de voz.
    
- Puede configurar cómo desea que se controle las llamadas perdidas (llamadas no recogidas después de un tiempo determinado). Si habilita el correo de voz para la identidad del grupo, las llamadas perdidas irán automáticamente al correo de voz. Si no tiene habilitado el correo de voz para la identidad del grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de disponibilidad, se reenvían a un número alternativo o se desconectaran.
    

