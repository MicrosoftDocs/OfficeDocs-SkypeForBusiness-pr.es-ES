---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ea0dd9dee35693fadedd13f6026ebb0d9f211d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Proceso de migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

El procedimiento de migración recomendado y admitido para Lync Server 2013 es el procedimiento de migración en paralelo. En este tema se describe por qué debe usar la migración en paralelo y también se incluye información sobre la coexistencia.

<div>

## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migraciones se debe usar la vía de la migración en paralelo. En una migración en paralelo, se implementa un nuevo servidor con Lync Server 2013 junto con un servidor correspondiente que ejecuta Office Communications Server 2007 R2 y, a continuación, se transfieren las operaciones al nuevo servidor. Si es necesario revertir a Office Communications Server 2007 R2, solo tiene que desplazar las operaciones de vuelta a los servidores originales. No olvide que, en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará, y los clientes también deberán cambiarse a la versión anterior.

</div>

<div>

## <a name="coexistence-testing"></a>Prueba de coexistencia

Después de implementar Lync Server 2013 en paralelo con Office Communications Server 2007 R2, la topología representa un estado de prueba de coexistencia de Lync Server 2013 y Office Communications Server 2007 R2. En este estado, es importante probar y garantizar que los servicios se inicien, que se puedan administrar todos los sitios y que los clientes puedan comunicarse con los usuarios actuales y heredados. Antes de la migración de todos los usuarios, es fundamental conocer el estado de cada implementación y asegurarse de que cada una de ellas funciona como debe. Normalmente, la fase de pruebas de coexistencia existe en las pruebas piloto de Lync Server 2013. Los usuarios heredados se mueven a Lync Server 2013 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionan correctamente. Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Lync Server 2013 y se retiran las aplicaciones y los grupos de servidores heredados de Office Communications Server 2007 R2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

