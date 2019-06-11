---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Proceso de migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-24_

El procedimiento de migración recomendado y admitido para Lync Server 2013 es el procedimiento de migración en paralelo. En este tema se describe por qué debería usar la migración en paralelo y también se incluye información sobre la coexistencia.

<div>

## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migraciones, debe usar la ruta de migración en paralelo. En una migración en paralelo, se implementa un nuevo servidor con Lync Server 2013 junto con un servidor correspondiente que ejecuta Office Communications Server 2007 R2 y, a continuación, se transfieren las operaciones al nuevo servidor. Si es necesario revertir a Office Communications Server 2007 R2, solo tiene que desplazar las operaciones a los servidores originales. Tenga en cuenta que, en este caso, las reuniones nuevas programadas con clientes actualizados no funcionarán y los clientes también necesitarán cambiar de versión.

</div>

<div>

## <a name="coexistence-testing"></a>Pruebas de coexistencia

Después de implementar Lync Server 2013 en paralelo con Office Communications Server 2007 R2, la topología representa un estado de prueba de coexistencia de Lync Server 2013 y Office Communications Server 2007 R2. En este estado, es importante probar y garantizar que se inician los servicios, que cada sitio se puede administrar y que los clientes pueden comunicarse con los usuarios actuales y heredados. Antes de la migración de todos los usuarios, es muy importante comprender el estado de cada implementación y asegurarse de que cada implementación es funcional y funciona correctamente. Por lo general, la fase de pruebas de coexistencia se produce durante las pruebas piloto de Lync Server 2013. Los usuarios heredados se mueven a Lync Server 2013 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionen correctamente. Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Lync Server 2013, y se retirarán las aplicaciones y los grupos heredados de Office Communications Server 2007 R2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

