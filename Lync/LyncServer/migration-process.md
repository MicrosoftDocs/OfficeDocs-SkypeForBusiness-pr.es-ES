---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a955133dcadfc1966225b643467e5640c81d128
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Proceso de migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

El procedimiento de migración recomendado y admitido para Lync Server 2013 es la migración en paralelo. Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.

<div>

## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migraciones se debe usar la vía de la migración en paralelo. En una migración en paralelo, se implementa un nuevo servidor con Lync Server 2013 junto con un servidor correspondiente que ejecuta Lync Server 2010 y, a continuación, se transfieren las operaciones al nuevo servidor. Si es necesario revertir a Lync Server 2010, solo tiene que desplazar las operaciones de vuelta a los servidores originales. No olvide que, en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará, y los clientes también deberán cambiarse a la versión anterior.

</div>

<div>

## <a name="coexistence-testing"></a>Prueba de coexistencia

Después de implementar Lync Server 2013 en paralelo con Lync Server 2010, la implementación representa un estado de prueba de coexistencia de Lync Server 2013 y Lync Server 2010. Durante este estado, es importante comprobar y confirmar que los servicios se han iniciado, que todos los sitios se pueden administrar y que los clientes se pueden comunicar con los usuarios tanto actuales como heredados. Antes de la migración de todos los usuarios, es fundamental conocer el estado de cada implementación y asegurarse de que cada una de ellas funciona como debe. Normalmente, la fase de pruebas de coexistencia existe en las pruebas piloto de Lync Server 2013. Los usuarios heredados se mueven a Lync Server 2013 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionan correctamente. Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Lync Server 2013 y se retiran las aplicaciones y los grupos de servidores heredados de Lync Server 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

