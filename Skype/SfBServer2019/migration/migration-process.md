---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: El procedimiento de migración compatibles y recomendados para Skype para Business Server 2019 es migración en paralelo. En este tema se describe por qué debería usar la migración en paralelo y también se incluye información acerca de las pruebas de coexistencia.
ms.openlocfilehash: e14226721cbc09bd1f0ac66b47dbd1710712eb17
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876295"
---
# <a name="migration-process"></a>Proceso de migración

El procedimiento de migración compatibles y recomendados para Skype para Business Server 2019 es migración en paralelo. En este tema se describe por qué debería usar la migración en paralelo y también se incluye información acerca de las pruebas de coexistencia.
  
## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migración, debe usar la ruta de acceso de migración en paralelo. En una migración en paralelo, implementar un nuevo servidor con Skype para Business Server 2019 junto con un servidor correspondiente que se está ejecutando una versión anterior y, a continuación, transferir las operaciones al nuevo servidor. Si es necesario revertir a la versión anterior, debe sólo transferir las operaciones a los servidores originales. Tenga en cuenta que en esta situación no funcionará cualquier nueva reuniones programadas con los clientes actualizados, y también sería necesario que los clientes se puede degradar.
  
## <a name="coexistence-testing"></a>Prueba de coexistencia

Después de haber implementado Skype para Business Server 2019 en paralelo con la versión anterior, la implementación representa una comprobación de estado de Skype para Business Server 2019 y la versión anterior de coexistencia. En este estado, es importante probar y asegúrese de que se inician los servicios, puede administrarse de cada sitio y los clientes pueden comunicarse con los usuarios actuales y heredados. Antes de la migración de todos los usuarios, es muy importante comprender el estado de cada implementación y asegúrese de que cada implementación es funcional y funcionan correctamente. Normalmente, la fase de pruebas de coexistencia existe a lo largo de las pruebas piloto de Skype para Business Server 2019. Los usuarios heredados se mueven a Skype para Business Server 2019 durante un período de tiempo para garantizar la compatibilidad de esa aplicación y las características y funciones están funcionando correctamente. Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Skype para Business Server 2019 y los grupos de servidores heredados y aplicaciones de la versión anterior se retiran.
  
