---
title: Planear implementaciones de servidor perimetral en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumen: planee su entorno Skype Empresarial Server edge. Este tema le presenta los conceptos perimetrales y le permite organizarse con nuestros temas más profundos.'
ms.openlocfilehash: 5a0541eabdc0f3db9a8fb23eaa9d20b0792750263e8d576bcf11e6d96c0fd2d1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320053"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planear implementaciones de servidor perimetral en Skype Empresarial Server
 
**Resumen:** Planee el entorno Skype Empresarial Server edge. Este tema le presenta los conceptos perimetrales y le permite organizarse con nuestros temas más profundos.
  
Cuando tiene un entorno Skype Empresarial Server que funciona bien internamente, es posible que el siguiente paso sea introducir un servidor perimetral o un grupo de servidores perimetrales en el entorno. Este rol sería vital si desea que los servicios proporcionados por Skype Empresarial Server los usan personas que están fuera de la red interna. Estos pueden incluir posiblemente:
  
- Usuarios remotos: empleados que están fuera del sitio, ya sea temporalmente o de forma continua.
    
- Usuarios federados: los empleados de las organizaciones asociadas.
    
- Usuarios móviles.
    
- Clientes potenciales, partners e incluso usuarios anónimos que desea invitar a reuniones y presentaciones.
    
El acceso de usuarios externos, que es lo que proporcionan los servidores perimetrales, permiten que todo esto suceda. Los usuarios internos podrán disfrutar de los siguientes servicios hospedados por su Skype Empresarial Server implementación:
  
- Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden unirse a conversaciones y conferencias de mensajería instantánea. Pueden obtener información de presencia para otros usuarios (que también obtienen su información de presencia). No podrá realizar conferencias multipartid si usa un proveedor de mensajería instantánea pública, es decir, una comunicación estrictamente punto a punto. Pero se admiten los protocolos SIP y XMPP.
    
- Conferencias de audio y vídeo (A/V): los usuarios externos autorizados pueden participar en sus conferencias de audio y vídeo Skype Empresarial Server de audio y vídeo.
    
- Conferencia web: los usuarios externos autorizados pueden participar en sus Skype Empresarial conferencias. También puede habilitar la participación de usuarios remotos, usuarios federados y usuarios anónimos si lo desea. Los usuarios de mensajería instantánea pública no pueden participar en conferencias. También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorios, e incluso actuar como organizadores o presentadores de reuniones.
    
Se admite el acceso a dispositivos móviles, como Telefonía IP empresarial. Puede invitar a usuarios externos a aquellas reuniones a las que desee que asistan, incluso a usuarios anónimos, si desea concederles permisos.
  
If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. Para obtener más información, tenemos los temas que se enumeran a continuación.

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información. 
  
## <a name="planning-topics"></a>Temas de planeación:

Los artículos de planeación son:
  
- [Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015](system-requirements.md)
    
- [Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015](edge-environmental-requirements.md)
    
- [Escenarios de servidor perimetral en Skype Empresarial Server 2015](scenarios.md)
    

