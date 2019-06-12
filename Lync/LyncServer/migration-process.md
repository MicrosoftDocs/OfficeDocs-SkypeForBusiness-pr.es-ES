---
title: Proceso de migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Proceso de migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

El procedimiento de migración recomendado y admitido para Lync Server 2013 es la migración en paralelo. En este tema se describe por qué debería usar la migración en paralelo y también se incluye información sobre las pruebas de coexistencia.

<div>

## <a name="side-by-side-migration"></a>Migración en paralelo

En casi todas las migraciones, debe usar la ruta de migración en paralelo. En una migración en paralelo, se implementa un nuevo servidor con Lync Server 2013 junto a un servidor correspondiente que ejecuta Lync Server 2010 y, después, se transfieren las operaciones al nuevo servidor. Si es necesario revertir a Lync Server 2010, solo tiene que desplazar las operaciones de vuelta a los servidores originales. Tenga en cuenta que, en este caso, las reuniones nuevas programadas con clientes actualizados no funcionarán y los clientes también necesitarán cambiar de versión.

</div>

<div>

## <a name="coexistence-testing"></a>Pruebas de coexistencia

Después de implementar Lync Server 2013 en paralelo con Lync Server 2010, la implementación representa un estado de prueba de coexistencia de Lync Server 2013 y Lync Server 2010. Mientras se encuentre en este estado, es importante probar y asegurarse de que se inician los servicios, que cada sitio se puede administrar y que los clientes pueden comunicarse con los usuarios actuales y heredados. Antes de la migración de todos los usuarios, es muy importante comprender el estado de cada implementación y asegurarse de que cada implementación es funcional y funciona correctamente. Por lo general, la fase de pruebas de coexistencia se produce durante las pruebas piloto de Lync Server 2013. Los usuarios heredados se mueven a Lync Server 2013 durante un período de tiempo para garantizar que la compatibilidad de aplicaciones y las características y funciones funcionen correctamente. Después de las pruebas piloto, los usuarios y las aplicaciones se mueven a la versión de producción de Lync Server 2013, y se retirarán las aplicaciones y los grupos heredados de Lync Server 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

