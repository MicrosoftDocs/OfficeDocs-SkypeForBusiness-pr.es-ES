---
title: Migrar múltiples sitios y grupos de servidores
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype empresarial Server 2019 admite implementaciones de varios sitios y de varios grupos. El proceso de migración de varios grupos a Skype empresarial Server 2019 requiere las siguientes consideraciones:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752662"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar múltiples sitios y grupos de servidores

Skype empresarial Server 2019 admite implementaciones de varios sitios y de varios grupos. El proceso de migración de varios grupos a Skype empresarial Server 2019 requiere las siguientes consideraciones: 
  
1. Después de implementar un grupo piloto de Skype empresarial Server 2019, debe definir un subconjunto de usuarios piloto que se trasladarán al grupo de servidores de Skype empresarial 2019 y una metodología para validar la funcionalidad de los usuarios. Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la Directiva de conferencia del usuario se ha trasladado a Skype empresarial Server 2019. 
    
2. Después de implementar un servidor perimetral en el grupo piloto, debe validar que los usuarios externos pueden comunicarse con el grupo de servidores de Skype empresarial Server 2019.

3. La funcionalidad del chat persistente, la creación de reflejo de SQL y XMPP están en desuso en Skype empresarial Server 2019 y ya no están disponibles como características de Skype empresarial Server 2019, pero pueden continuarse en un entorno de coexistencia si se han implementado anteriormente en un entorno heredado. Si desea seguir usando estas características, debe tener previsto continuar con un entorno de coexistencia en el que determinados usuarios permanecerán en los grupos de servidores heredados.
    
4. Después de realizar la transición de los servidores perimetrales de las rutas federadas a los servidores perimetrales piloto de Skype empresarial Server 2019, debe validar que los usuarios federados puedan comunicarse con el grupo de servidores de Skype empresarial 2019.
    
5. Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo de servidores heredado esté vacío.
    
6. Después de comprobar que el grupo heredado está vacío, puede desactivar el grupo de servidores. 
    
    Para obtener más información sobre cómo desactivar los servidores y el grupo de servidores heredados, vea [Phase 8: decommission Legacy pools](phase-8-decommission-legacy-pools.md).
    

