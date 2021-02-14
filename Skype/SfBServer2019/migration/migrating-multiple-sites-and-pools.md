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
description: 'Skype Empresarial Server 2019 admite implementaciones de varios sitios y de varios servidores. El proceso de migración de varios grupos a Skype Empresarial Server 2019 requiere las siguientes consideraciones:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752662"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar múltiples sitios y grupos de servidores

Skype Empresarial Server 2019 admite implementaciones de varios sitios y de varios servidores. El proceso de migración de varios grupos a Skype Empresarial Server 2019 requiere las siguientes consideraciones: 
  
1. Después de implementar un grupo piloto de Skype Empresarial Server 2019, debe definir un subconjunto de usuarios piloto que se trasladarán al grupo de Skype Empresarial Server 2019 y una metodología para validar la funcionalidad de los usuarios. Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la directiva de conferencia del usuario se ha movido a Skype Empresarial Server 2019. 
    
2. Después de implementar un servidor perimetral en el grupo piloto, debe validar que los usuarios externos puedan comunicarse con el grupo de Skype Empresarial Server 2019.

3. Las funciones de chat persistente, creación de reflejo de SQL y XMPP están en desuso en Skype Empresarial Server 2019 y ya no están disponibles como características de Skype Empresarial Server 2019, pero pueden continuar en un entorno de coexistencia si se implementaron anteriormente en un entorno heredado. Si desea seguir usando estas características, debe planear continuar con un entorno de coexistencia en el que determinados usuarios permanecerán en grupos heredados.
    
4. Después de realizar la transición de los servidores perimetrales de las rutas federadas a los servidores perimetrales piloto de Skype Empresarial Server 2019, debe validar que los usuarios federados puedan comunicarse con el grupo de Skype Empresarial Server 2019.
    
5. Después de mover todos los usuarios y objetos de contacto que no son de usuario, debe validar que el grupo heredado está vacío.
    
6. Después de comprobar que el grupo heredado está vacío, puede desactivarlo. 
    
    Para obtener más información acerca de cómo desactivar el grupo heredado y los servidores, consulte [Fase 8: Retirar grupos heredados.](phase-8-decommission-legacy-pools.md)
    

