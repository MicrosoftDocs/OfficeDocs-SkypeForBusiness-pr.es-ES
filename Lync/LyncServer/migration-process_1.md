---
title: Proceso de migración
TOCTitle: Proceso de migración
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48276402
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de migración

 

_**Última modificación del tema:** 2012-09-24_

El procedimiento de migración recomendado y admitido para Lync Server 2013 es el procedimiento de migración en paralelo. En este tema se describe porqué se debe usar la migración en paralelo y también incluye información acerca de la coexistencia.

## Migración en paralelo

En casi todas las migraciones, se debe usar la vía de la migración en paralelo. En una migración de este tipo, se implementa un nuevo servidor con Lync Server 2013 junto con el servidor correspondiente que ejecuta Office Communications Server 2007 R2 y, a continuación, las operaciones se transfieren al nuevo servidor. En caso de que se deba revertir a Office Communications Server 2007 R2, solo tendrá que trasladar las operaciones a los servidores originales. No olvide, que en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará y los clientes también deberán cambiarse a la versión anterior.

## Prueba de coexistencia

Después de haber implementado Lync Server 2013 en paralelo con Office Communications Server 2007 R2, la topología representa el estado de la prueba de coexistencia entre Lync Server 2013 y Office Communications Server 2007 R2. Mientras está en este estado, es importante que pruebe ambas implementaciones y que se asegure de que los servicios se inician; se puede administrar cada sitio y los clientes pueden comunicarse con usuarios heredados y actuales. Antes de migrar a todos los usuarios, es muy importante que comprenda el estado de cada implementación y garantizar que cada implementación funciona correctamente. Esta fase de prueba de coexistencia suele extenderse durante las pruebas piloto de Lync Server 2013. Los usuarios heredados se mueven a Lync Server 2013 durante cierto tiempo para garantizar que las características, funciones y compatibilidad de las aplicaciones funcionan adecuadamente. Una vez finalizadas las pruebas piloto, los usuarios y aplicaciones se mueven a la versión de producción de Lync Server 2013 y se retiran los grupos y las aplicaciones heredados de Office Communications Server 2007 R2.

