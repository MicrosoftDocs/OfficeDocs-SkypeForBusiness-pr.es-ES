---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo. En este tema se describe por qué debería usar la migración en paralelo y también se incluye información sobre las pruebas de coexistencia.
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237782"
---
# <a name="migration-process"></a>Proceso de migración

El procedimiento de migración recomendado y admitido para Skype empresarial Server 2019 es la migración en paralelo. En este tema se describe por qué debería usar la migración en paralelo y también se incluye información sobre las pruebas de coexistencia.
  
## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migraciones, debe usar la ruta de migración en paralelo. En una migración en paralelo, se implementa un nuevo servidor con Skype empresarial Server 2019 junto con un servidor correspondiente que ejecuta una versión anterior y, a continuación, se transfieren las operaciones al nuevo servidor. Si es necesario revertir a la versión anterior, solo tiene que desplazar las operaciones de vuelta a los servidores originales. Tenga en cuenta que, en este caso, las reuniones nuevas programadas con clientes actualizados no funcionarán y los clientes también necesitarán cambiar de versión.
  
## <a name="coexistence-testing"></a>Pruebas de coexistencia

Una vez que haya implementado Skype empresarial Server 2019 en paralelo con la versión anterior, la implementación representa un estado de prueba de coexistencia de Skype empresarial Server 2019 y la versión anterior. Mientras se encuentre en este estado, es importante probar y asegurarse de que se inician los servicios, que cada sitio se puede administrar y que los clientes pueden comunicarse con los usuarios actuales y heredados. Antes de la migración de todos los usuarios, es muy importante comprender el estado de cada implementación y asegurarse de que cada implementación es funcional y funciona correctamente. Por lo general, la fase de pruebas de coexistencia se produce durante las pruebas piloto de Skype empresarial Server 2019. Los usuarios heredados se mueven a Skype empresarial Server 2019 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionen correctamente. Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Skype empresarial Server 2019, y se retirarán las aplicaciones y los grupos heredados de la versión anterior.
  
