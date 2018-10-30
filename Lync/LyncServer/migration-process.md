---
title: Proceso de migración
TOCTitle: Proceso de migración
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48274507
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proceso de migración

 

_**Última modificación del tema:** 2012-09-17_

El procedimiento de migración admitido y recomendado para Lync Server 2013 es el procedimiento de migración en paralelo. Este tema describe porqué debería utilizar la migración en paralelo y también incluye información acerca de la prueba de coexistencia.

## Migración en paralelo

En casi todas las migraciones se debe usar la vía de la migración en paralelo. En una migración de este tipo, se implementa un nuevo servidor con Lync Server 2013 junto con el servidor correspondiente que ejecuta Lync Server 2010 y, tras ello, las operaciones se transfieren al nuevo servidor. En caso de que se deba revertir a Lync Server 2010, solo tendrá que trasladar las operaciones de nuevo a los servidores originales. No olvide que, en esta situación, cualquier reunión que haya programada con clientes actualizados no funcionará, y los clientes también deberán cambiarse a la versión anterior.

## Prueba de coexistencia

Tras implementar Lync Server 2013 en paralelo con Lync Server 2010, la implementación representa un estado de prueba de coexistencia de Lync Server 2013 y Lync Server 2010. Durante este estado, es importante comprobar y confirmar que los servicios se han iniciado, que todos los sitios se pueden administrar y que los clientes se pueden comunicar con los usuarios tanto actuales como heredados. Antes de la migración de todos los usuarios, es fundamental conocer el estado de cada implementación y asegurarse de que cada una de ellas funciona como debe. Por lo general, la fase de prueba de coexistencia existe durante toda la prueba piloto de Lync Server 2013. Los usuarios heredados se mueven a Lync Server 2013 por un tiempo determinado para garantizar que la compatibilidad de las aplicaciones y las características funcionen correctamente. Tras la prueba piloto, se migran los usuarios y las aplicaciones a la versión de producción de Lync Server 2013, y se retiran las aplicaciones y los grupos de servidores heredados de Lync Server 2010.

