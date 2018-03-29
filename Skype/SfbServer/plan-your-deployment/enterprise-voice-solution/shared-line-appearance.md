---
title: Plan para apariencia de línea compartida en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Lea este tema para aprender a planear para apariencia de línea compartida (SLA) en Skype para Business Server 2015, noviembre de 2015 actualización acumulativa.
ms.openlocfilehash: bed7eaf520cb8fd9bfc9c7a9a27093d55647b510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Plan para apariencia de línea compartida en Skype Empresarial Server 2015
 
Lea este tema para aprender a planear para apariencia de línea compartida (SLA) en Skype para Business Server 2015, noviembre de 2015 actualización acumulativa. 
  
Apariencia de línea compartida es una característica de Skype para empresas para controlar varias llamadas en un número específico, denominado número de compartidos. SLA puede configurar cualquier empresa voz habilitado Skype para usuarios de empresa como un número compartido con varias líneas para responder a varias llamadas. En realidad, las llamadas no se reciben en el número compartido, sino que se desvían a usuarios que actúan como delegados para el número compartido. Cualquiera de estos delegados puede responder a la llamada mientras el resto de los delegados recibe una notificación en su teléfono sobre el usuario que respondió a la llamada y la línea que está ocupada como resultado. El número de líneas y los delegados se pueden configurar para un número compartido en SLA. Además, también se pueden configurar otras opciones avanzadas para un número compartido, como BusyOption (que se produce cuando todas las líneas están ocupadas) y MissedCallOption (si ninguno de los delegados responde a una llamada).
  
SLA es compatible sólo con los siguientes dispositivos de teléfono (no se admite para Skype para clientes empresariales en equipos, teléfonos móviles u otros dispositivos): 
  
- Polycom VVX300 con actualización de firmware 5.4.1
    
- Polycom VVX400 con actualización de firmware 5.4.1
    
- Polycom VVX500 con actualización de firmware 5.4.1
    
- Polycom VVX600 con actualización de firmware 5.4.1
    
SLA es una nueva característica de Skype para Business Server, noviembre de 2015 actualización acumulativa. 
  
Para obtener información acerca de la implementación de SLA, vea [Implementar el aspecto de línea compartida en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Lista de características

Configurar un grupo de SLA permite lo siguiente:
  
- Todos los delegados del grupo pueden responder a llamadas entrantes al mismo número compartido. Las llamadas pueden estar basadas en RTC o en SIP.
    
- Los delegados pueden responder llamadas y ponerlas en espera.
    
- Los delegados pueden transferir llamadas a un número fuera del grupo de SLA.
    
- Los delegados pueden ver cuántas llamadas están actualmente en el número compartido, así como ver el estado de esas llamadas.
    
- Puede configurar un número máximo de llamadas simultáneas para el número compartido. Además, puede configurar cómo quiere administrar las llamadas adicionales cuando se alcanza el número máximo. Las llamadas que superen el límite se pueden rechazar con una señal de línea ocupada, desviar a un número alternativo o desviarlas al correo de voz.
    
- Puede configurar cómo quiere administrar las llamadas perdidas (llamadas que no se responden después de un tiempo específico). Si habilita el correo de voz para la identidad de grupo, las llamadas perdidas se desvían automáticamente al correo de voz. Si no tiene habilitado el correo de voz para la identidad de grupo (número compartido), puede elegir que las llamadas perdidas se rechacen con una señal de línea ocupada, se desvíen a un número alternativo o se desconecten.
    

