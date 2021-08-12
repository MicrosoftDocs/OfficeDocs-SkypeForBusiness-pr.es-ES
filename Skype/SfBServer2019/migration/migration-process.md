---
title: Proceso de migración
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
description: El procedimiento de migración recomendado y admitido para Skype Empresarial Server 2019 es la migración en paralelo. Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.
ms.openlocfilehash: e1d89dc2081918d87f73cd3c6908fff0c388e6700d00af6dcd72161a2ccc9ece
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303414"
---
# <a name="migration-process"></a>Proceso de migración

El procedimiento de migración recomendado y admitido para Skype Empresarial Server 2019 es la migración en paralelo. Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.
  
## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migraciones se debe usar la vía de la migración en paralelo. En una migración en paralelo, se implementa un nuevo servidor con Skype Empresarial Server 2019 junto con un servidor correspondiente que ejecuta una versión anterior y, a continuación, se transfieren operaciones al nuevo servidor. Si es necesario revertir a la versión anterior, solo tiene que volver a cambiar las operaciones a los servidores originales. No olvide que, en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará, y los clientes también deberán cambiarse a la versión anterior.
  
## <a name="coexistence-testing"></a>Prueba de coexistencia

Después de implementar Skype Empresarial Server 2019 en paralelo con la versión anterior, la implementación representa un estado de prueba de coexistencia de Skype Empresarial Server 2019 y la versión anterior. Durante este estado, es importante comprobar y confirmar que los servicios se han iniciado, que todos los sitios se pueden administrar y que los clientes se pueden comunicar con los usuarios tanto actuales como heredados. Antes de la migración de todos los usuarios, es fundamental conocer el estado de cada implementación y asegurarse de que cada una de ellas funciona como debe. Normalmente, la fase de prueba de coexistencia existe durante las pruebas piloto de Skype Empresarial Server 2019. Los usuarios heredados se mueven a Skype Empresarial Server 2019 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionan correctamente. Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Skype Empresarial Server 2019 y se retiran los grupos de servidores heredados y las aplicaciones de la versión anterior.
  
