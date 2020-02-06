---
title: Migrar múltiples sitios y grupos de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype empresarial Server 2019 admite implementaciones de varios sitios y de varios grupos. El proceso de migración de varios grupos a Skype empresarial Server 2019 requiere las siguientes consideraciones:'
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813448"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrar múltiples sitios y grupos de servidores

Skype empresarial Server 2019 admite implementaciones de varios sitios y de varios grupos. El proceso de migración de varios grupos a Skype empresarial Server 2019 requiere las siguientes consideraciones: 
  
1. Después de implementar un grupo piloto de Skype empresarial Server 2019, debe definir un subconjunto de usuarios piloto que se moverá al grupo de Skype empresarial Server 2019 y una metodología para validar la funcionalidad de los usuarios. Por ejemplo, después de mover un usuario a la agrupación piloto, compruebe que la Directiva de conferencia del usuario se ha movido a Skype empresarial Server 2019. 
    
2. Después de implementar un servidor perimetral en la agrupación piloto, debe validar que los usuarios externos puedan comunicarse con el grupo de servidores de Skype empresarial 2019.

3. Las funcionalidades chat persistente, reflejo SQL y XMPP han quedado obsoletas en Skype empresarial Server 2019 y ya no están disponibles como características de Skype empresarial Server 2019, pero se pueden continuar en un entorno de coexistencia si se han implementado previamente en un entorno heredado. Si desea seguir usando estas características, debe planear la continuación de un entorno de coexistencia en el que determinados usuarios permanecerán en agrupaciones heredadas.
    
4. Después de realizar la transición de los servidores perimetrales de las rutas federadas a los servidores perimetrales de Skype empresarial Server 2019, debe validar que los usuarios federados puedan comunicarse con el grupo de servidores de Skype empresarial 2019.
    
5. Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo heredado esté vacío.
    
6. Después de verificar que el grupo heredado está vacío, puede desactivar el grupo. 
    
    Para obtener más información sobre cómo desactivar el grupo de servidores y los servidores heredados, consulte [Phase 8: retiro pools heredados](phase-8-decommission-legacy-pools.md).
    

