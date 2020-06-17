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
description: El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo. Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752642"
---
# <a name="migration-process"></a>Proceso de migración

El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo. Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.
  
## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migraciones se debe usar la vía de la migración en paralelo. En una migración en paralelo, se implementa un nuevo servidor con Skype empresarial Server 2019 junto con un servidor correspondiente que ejecuta una versión anterior y, a continuación, se transfieren las operaciones al nuevo servidor. Si es necesario revertir a la versión anterior, solo tiene que desplazar las operaciones de vuelta a los servidores originales. No olvide que, en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará, y los clientes también deberán cambiarse a la versión anterior.
  
## <a name="coexistence-testing"></a>Prueba de coexistencia

Una vez que haya implementado Skype empresarial Server 2019 en paralelo con la versión anterior, la implementación representa un estado de prueba de coexistencia de Skype empresarial Server 2019 y la versión anterior. Durante este estado, es importante comprobar y confirmar que los servicios se han iniciado, que todos los sitios se pueden administrar y que los clientes se pueden comunicar con los usuarios tanto actuales como heredados. Antes de la migración de todos los usuarios, es fundamental conocer el estado de cada implementación y asegurarse de que cada una de ellas funciona como debe. Normalmente, la fase de pruebas de coexistencia existe en las pruebas piloto de Skype empresarial Server 2019. Los usuarios heredados se mueven a Skype empresarial Server 2019 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionan correctamente. Después de realizar las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Skype empresarial Server 2019 y se retiran las aplicaciones y los grupos de servidores heredados de la versión anterior.
  
