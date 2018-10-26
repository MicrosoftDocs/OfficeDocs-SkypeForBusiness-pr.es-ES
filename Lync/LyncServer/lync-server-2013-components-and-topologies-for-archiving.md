---
title: 'Lync Server 2013: Componentes y topologías para archivado'
TOCTitle: Componentes y topologías para archivado
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48275335
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes y topologías para archivado en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-09_

Si desea archivar contenido de mensajería instantánea y conferencias de Lync Server 2013, puede implementar el archivado en Lync Server.

## Componentes de archivado

La característica Archivado incluye los siguientes componentes:

  - **Agentes de archivado**   Los agentes de archivado (también llamados agentes de colección de datos unificada) se instalan y activan automáticamente en cada grupo de servidores front-end y en el servidor Standard Edition. Aunque los agentes de archivado se activan automáticamente, no se capturan realmente mensajes hasta que se habilite y configure correctamente el archivado.

  - **Almacenamiento de datos de archivado**. El almacenamiento de datos para Lync Server 2013 puede ser cualquiera de los siguientes:
    
      - Almacenamiento de Exchange 2013Si habilita la opción de integración de Microsoft Exchange, los buzones de los usuarios alojados en el servidor de Exchange 2013 usan el almacenamiento de Exchange 2013 para datos archivados, pero solo si los buzones se han colocado en Conservación local.
    
      - Almacenamiento de SQL Server. Si tiene usuarios en la implementación que están alojados en Lync Server 2013, puede configurar las bases de datos de archivado para que se ejecuten en una versión compatible de SQL Server con el fin de habilitar el archivado en esos usuarios.

El archivado también requiere almacenamiento de archivos, pero el archivado usa el mismo almacenamiento de archivos que los servidores front-end o que el servidor Standard Edition.

Para obtener una lista de requisitos de hardware y software para archivado, vea [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) y [Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación sobre compatibilidad.

## Topologías admitidas

Implemente el archivado en cada grupo que tenga usuarios que requieran compatibilidad de archivado. El archivado se ejecuta en Servidores front-end en grupos de Enterprise Edition y en Servidores Standard Edition. El almacenamiento de datos de archivado puede ser el siguiente:

  - Integrado con el almacenamiento de Exchange 2013

  - Implementado mediante bases de datos de SQL Server independientes

Si la implementación de Exchange 2013 no incluye a todos los usuarios de su implementación de Lync Server, debe usar la integración de Microsoft Exchange para los usuarios que usan buzones de alojados en servidores de Exchange 2013, y debe implementar bases de datos de SQL Server independientes para el resto de usuarios de Lync para el archivado.

## Combinación admitida

Lync Server 2013 admite una variedad de escenarios de combinación, lo que permite flexibilidad para ahorrar costos de hardware mediante la ejecución de varios componentes en un servidor (si dispone de una organización pequeña) o para ejecutar componentes individuales en diferentes servidores (si dispone de una organización más grande con necesidades de escalabilidad y rendimiento). Los factores de escalabilidad se deben tener en cuenta antes de decidir si se van a combinar componentes..

El archivado se implementa en los Servidores front-end de un grupo o en Servidores Standard Edition. Para más información sobre los componentes que se pueden combinar allí, vea [Instalación de servidores compatibles en Lync Server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de compatibilidad.

Si usa bases de datos de SQL Server independientes para el archivado, en lugar de o además de la integración del almacenamiento con el almacenamiento de Exchange 2013, puede combinar la base de datos de archivado con cualquiera de los siguientes elementos:

  - Base de datos de supervisión

  - Base de datos back-end de un grupo de servidores front-end de Enterprise Edition


> [!NOTE]
> El servidor que hospeda la base de datos de archivado puede hospedar otras bases de datos. Sin embargo, si piensa combinar la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede crecer mucho. Por este motivo, no se recomienda la combinación de la base de datos de archivado con la base de datos back-end.



Si combina la base de datos de archivado con la base de datos de supervisión, la base de datos back-end, o con ambas, puede usar una sola instancia de SQL para cualquiera de las bases de datos o pude usar una instancia SQL independiente para cada base de datos, con la siguiente limitación:

  - Cada instancia de SQL puede contener únicamente una sola base de datos back-end, una sola base de datos de supervisión y una sola base de datos de archivado.

Para más información sobre la combinación de todos los roles de servidor y de las bases de datos, vea [Instalación de servidores compatibles en Lync Server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de compatibilidad.

