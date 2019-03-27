---
title: Migrar múltiples sitios y grupos de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server 2019 es compatible con las implementaciones de varios sitios y grupo de varios servidores. El proceso de migración de varios grupos de servidores a Skype para Business Server 2019 requiere las siguientes consideraciones:'
ms.openlocfilehash: 5e369adb51bf95f4e3c3d12688d1e39611aa5692
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888664"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar múltiples sitios y grupos de servidores

Skype para Business Server 2019 es compatible con las implementaciones de varios sitios y grupo de varios servidores. El proceso de migración de varios grupos de servidores a Skype para Business Server 2019 requiere las siguientes consideraciones: 
  
1. Después de implementar un Skype para Business Server 2019 el grupo piloto, debe definir un subconjunto de usuarios pilotos que se moverán a la Skype una metodología para validar la funcionalidad de los usuarios y de grupo de servidores de Business Server 2019. Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la directiva del usuario conferencia ha movido a Skype para Business Server 2019. 
    
2. Después de implementar un servidor perimetral en el grupo piloto, debe comprobar que los usuarios externos pueden comunicarse con el Skype para el grupo de servidores de Business Server 2019.

3. Chat en grupo, la creación de reflejos de SQL y la funcionalidad XMPP están en desuso en Skype para Business Server 2019 y ya no están disponibles como Skype para las características de Business Server 2019, pero puede continuar en un entorno de coexistencia si anteriormente se implementan en un entorno heredado. Si desea seguir utilizando estas características, debe planear continuar con un entorno de coexistencia, donde permanecerá determinados usuarios en grupos de servidores heredados.
    
4. Después de trasladar los servidores perimetrales de las rutas federadas para el piloto Skype para los servidores perimetrales de Business Server 2019, debe comprobar que los usuarios federados pueden comunicarse con el Skype para el grupo de servidores de Business Server 2019.
    
5. Después de mover todos los usuarios y objetos de contacto que no sean usuarios, deberá validar que el grupo heredado está vacío.
    
6. Después de comprobar que el grupo heredado está vacío, a continuación, puede desactivar el grupo de servidores. 
    
    Para obtener información detallada acerca de cómo desactivar los servidores y el grupo de servidores heredado, vea [fase 8: retirar grupos heredados](phase-8-decommission-legacy-pools.md).
    

