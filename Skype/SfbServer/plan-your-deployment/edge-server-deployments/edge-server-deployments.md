---
title: Plan para las implementaciones de servidor perimetral de Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumen: Planear su Skype para el entorno empresarial servidor perimetral. En este tema se presenta a los conceptos de borde y le permite organizarse con nuestros temas más detallados.'
ms.openlocfilehash: e2154abd7e263b92011ca198ddaa1b90f8bd38c7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207142"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Plan para las implementaciones de servidor perimetral de Skype para Business Server
 
**Resumen:** Plan para su Skype para el entorno empresarial servidor perimetral. En este tema se presenta a los conceptos de borde y le permite organizarse con nuestros temas más detallados.
  
Cuando haya un Skype para el entorno de servidor empresarial que funciona bien internamente, podría ser el siguiente paso para presentan un servidor perimetral o un grupo de servidores perimetrales para el entorno. Esta función sería vital si desea que los servicios proporcionados por Skype para Business Server se pueden utilizar aquellas personas que están fuera de la red interna. Estos pueden incluir potencialmente:
  
- Usuarios remotos: empleados que están fuera del sitio, ya sea de forma temporal o continua.
    
- Los usuarios federados: Los empleados las organizaciones del socio.
    
- Usuarios móviles.
    
- Clientes potenciales, asociados e incluso usuarios anónimos que desea invitar a reuniones y presentaciones.
    
Acceso de usuarios externos, que es lo que proporcionan los servidores perimetrales, permitir que todos los que esto ocurra. Los usuarios internos podrán disfrutar de los siguientes servicios hospedados por su Skype para la implementación de Business Server:
  
- Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea. Pueden obtener información de presencia de otros usuarios (que también obtienen su información de presencia). No podrá realizar conferencias con varios participantes si está usando un proveedor de mensajería instantánea público, que es la comunicación de manera estricta de punto a punto. Pero se admiten los protocolos SIP y XMPP.
    
- Audio y vídeo (A / V) conferencia: los usuarios externos autorizados pueden participar en su Skype para las conferencias de audio y vídeos de Business Server.
    
- Conferencias Web: los usuarios externos autorizados pueden participar en su Skype para conferencias de empresa. También puede habilitar la participación de los usuarios remotos, usuarios federados y usuarios anónimos si así lo desea. Los usuarios de mensajería instantánea pública no pueden participar en conferencias. También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorio, e incluso actuar como organizadores o moderadores de reuniones.
    
Se admite el acceso a dispositivos móviles, como Enterprise Voice. Puede invitar a usuarios externos a esas reuniones que quiere que asistan, incluso a los usuarios anónimos, si desea concederles permisos.
  
Si esto le parece algo que necesita su organización, entonces planificar un entorno perimetral va a ser de gran ayuda al implementarlo. Para más información, hay los temas enumerados a continuación.

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019. Para obtener más información, vea [la federación XMPP migrar](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Temas de planeamiento:

Los artículos de planeamiento son:
  
- [Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015](system-requirements.md)
    
- [Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015](edge-environmental-requirements.md)
    
- [Escenarios del servidor perimetral en Skype Empresarial Server 2015](scenarios.md)
    

