---
title: Planeación de implementaciones de servidores perimetrales en Skype Empresarial Server
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
description: 'Resumen: planee su entorno perimetral de Skype Empresarial Server. Este tema le presenta los conceptos de Edge y le permite organizarse con nuestros temas más exhaustivos.'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813810"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planeación de implementaciones de servidores perimetrales en Skype Empresarial Server
 
**Resumen:** Planee su entorno perimetral de Skype Empresarial Server. Este tema le presenta los conceptos de Edge y le permite organizarse con nuestros temas más exhaustivos.
  
Cuando tiene un entorno de Skype Empresarial Server que funciona bien internamente, es posible que el siguiente paso sea introducir un servidor perimetral o un grupo de servidores perimetrales en el entorno. Este rol sería fundamental si quiere que los servicios proporcionados por Skype Empresarial Server sean usados por personas que están fuera de la red interna. Estos pueden incluir posiblemente:
  
- Usuarios remotos: empleados que están fuera del sitio, ya sea temporalmente o de forma continua.
    
- Usuarios federados: los empleados de las organizaciones asociadas.
    
- Usuarios móviles.
    
- Posibles clientes, partners e incluso usuarios anónimos a los que quiera invitar a reuniones y presentaciones.
    
El acceso de usuarios externos, que es lo que proporcionan los servidores perimetrales, permite que todo esto suceda. Los usuarios internos podrán disfrutar de los siguientes servicios hospedados en la implementación de Skype Empresarial Server:
  
- Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden unirse a conversaciones y conferencias de mensajería instantánea. Pueden obtener información de presencia para otros usuarios (que también obtienen su información de presencia). No podrá realizar conferencias entre varias entidades si usa un proveedor de mensajería instantánea pública, que es estrictamente comunicación punto a punto. Pero se admiten los protocolos SIP y XMPP.
    
- Conferencia de audio y vídeo (A/V): los usuarios externos autorizados pueden participar en las conferencias de audio y vídeo de Skype Empresarial Server.
    
- Conferencia web: los usuarios externos autorizados pueden participar en las conferencias de Skype Empresarial. También puede habilitar la participación de usuarios remotos, usuarios federados y usuarios anónimos si lo desea. Los usuarios de mensajería instantánea pública no pueden participar en conferencias. También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorios, e incluso actuar como organizadores o presentadores de reuniones.
    
Se admite el acceso a dispositivos móviles, como Telefonía IP empresarial. Puede invitar a usuarios externos a esas reuniones a las que desea que asistan, incluso a los usuarios anónimos, si desea concederles permisos.
  
Si esto parece algo que necesita su organización, la planeación de un entorno perimetral le será de gran ayuda para implementarlo. Para obtener más información, tenemos los temas que se enumeran a continuación.

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019. Consulte [Migración de la federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información. 
  
## <a name="planning-topics"></a>Temas de planeación:

Los artículos de planeación son:
  
- [Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015](system-requirements.md)
    
- [Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015](edge-environmental-requirements.md)
    
- [Escenarios de servidor perimetral en Skype Empresarial Server 2015](scenarios.md)
    

