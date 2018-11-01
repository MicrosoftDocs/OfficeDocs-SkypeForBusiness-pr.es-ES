---
title: 'Lync Server 2013: Definición de los requisitos para la telefonía IP empresarial'
TOCTitle: Definición de los requisitos de la organización para la telefonía IP empresarial
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48274865
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definición de los requisitos para la telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2012-08-07_

Este tema proporciona información general sobre las consideraciones que hay que tener en cuenta sobre las regiones, los sitios y los vínculos entre sitios de la topología y lo importante que son cuando se implementa Telefonía IP empresarial. Para obtener más información que le ayude a plantearse estas decisiones, vea “ [Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)” en la documentación sobre planificación.

## Sitios y regiones

En primer lugar, identifique los sitios de la topología en los que implementará Telefonía IP empresarial y las regiones de red a los que dichos sitios pertenecen. En concreto, tenga en cuenta la forma en que proporcionará conectividad de red telefónica conmutada (RTC) a cada sitio. Por motivos logísticos y de manejabilidad, las regiones a las que dichos sitios pertenecen pueden constituir un factor decisivo. Decida dónde se implementarán localmente las puertas de enlace, dónde se implementaran las Aplicaciones de sucursal con funciones de supervivencia (SBA) y dónde se pueden configurar conexiones basadas en troncos SIP (localmente o en el sitio central) para un proveedor de servicios de telefonía.

## Vínculos de red entre sitios

También debe tener en cuenta el uso de ancho de banda que espera en los vínculos de red entre el sitio central y sus sitios de sucursal. Si ha implementado, o piensa hacerlo, vínculos WAN resistentes entre los sitios, se recomienda implementar una puerta de enlace en cada Sitio de sucursal para proporcionar finalización de llamada directa a la extensión (DID) a los usuarios de dichos sitios. Si tiene vínculos WAN resistentes, pero es probable que el ancho de banda de un vínculo WAN se vea restringido, configure el control de admisión de llamadas para dicho vínculo. Si no tiene vínculos WAN resistentes, hospede menos de 1.000 usuarios en la Sitio de sucursal. Si no dispone de administradores locales que hayan recibido cursos de Lync Server, se recomienda implementar una Aplicación de sucursal con funciones de supervivencia en la Sitio de sucursal. Si hospeda entre 1.000 y 5.000 usuarios en la Sitio de sucursal, carece de una conexión WAN resistente y dispone de administradores que hayan recibido cursos de Lync Server, se recomienda implementar un Servidor de sucursal con funciones de supervivencia con una puerta de enlace pequeña en la Sitio de sucursal. Considere también la posibilidad de habilitar el desvío de medios en vínculos restringidos si tiene una puerta de enlace del mismo nivel que admita desvío de medios.

## Vea también

#### Conceptos

[Configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

