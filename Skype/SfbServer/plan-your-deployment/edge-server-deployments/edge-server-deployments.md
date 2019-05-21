---
title: Plan para implementaciones de servidores perimetrales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumen: Planee su entorno de Skype empresarial Server Edge. En este tema te presentamos los conceptos básicos y te permite organizarte con nuestros temas más detallados.'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277163"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Plan para implementaciones de servidores perimetrales en Skype empresarial Server
 
**Resumen:** Planear el entorno de Skype empresarial Server Edge. En este tema te presentamos los conceptos básicos y te permite organizarte con nuestros temas más detallados.
  
Cuando tiene un entorno de Skype empresarial Server que funciona bien internamente, el siguiente paso para usted puede ser introducir un servidor perimetral o un grupo de servidores perimetrales en el entorno. Este rol sería vital si desea que los servicios proporcionados por Skype empresarial Server los usen personas que estén fuera de su red interna. Estos pueden incluir potencialmente:
  
- Usuarios remotos: empleados que están fuera del sitio, ya sea de forma temporal o continua.
    
- Usuarios federados: los empleados de su compañero.
    
- Usuarios móviles.
    
- Clientes potenciales, asociados e incluso usuarios anónimos que desea invitar a reuniones y presentaciones.
    
Acceso externo de usuario, que es lo que proporcionan los servidores perimetrales, permita que esto suceda. Los usuarios internos podrán disfrutar de los siguientes servicios que se hospedan en la implementación de Skype empresarial Server:
  
- Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea. Pueden obtener información de presencia de otros usuarios (que también obtienen su información de presencia). No podrá realizar conferencias de varias partes si está usando un proveedor de mensajería instantánea pública, que es estrictamente una comunicación par a par. Pero se admiten los protocolos SIP y XMPP.
    
- Conferencias de audio y vídeo (A/V): los usuarios externos autorizados pueden participar en sus conferencias de audio y vídeo de Skype empresarial Server.
    
- Conferencias web: los usuarios externos autorizados pueden participar en sus conferencias de Skype empresarial. También puede habilitar la participación para usuarios remotos, usuarios federados y usuarios anónimos si lo desea. Los usuarios de la mensajería instantánea pública no pueden participar en conferencias. También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorio, e incluso actuar como organizadores o moderadores de reuniones.
    
El acceso a dispositivos móviles es compatible, como la telefonía IP empresarial. Puede invitar a usuarios externos a esas reuniones que quiere que asistan, incluso a los usuarios anónimos, si desea concederles permisos.
  
Si esto le parece algo que necesita su organización, entonces planificar un entorno perimetral va a ser de gran ayuda al implementarlo. Para más información, hay los temas enumerados a continuación.

> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Para obtener más información, consulte migrar la [Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Temas de planeamiento:

Los artículos de planeamiento son:
  
- [Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015](system-requirements.md)
    
- [Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015](edge-environmental-requirements.md)
    
- [Escenarios del servidor perimetral en Skype Empresarial Server 2015](scenarios.md)
    

