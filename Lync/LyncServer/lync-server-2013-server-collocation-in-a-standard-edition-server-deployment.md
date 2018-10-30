---
title: "Colocación de un servidor en una implementación de servidores de Standard Edition"
TOCTitle: Colocación de un servidor en una implementación de servidores de Standard Edition
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48274330
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Colocación de un servidor en una implementación de servidores de Standard Edition en Lync Server 2013

 

_**Última modificación del tema:** 2013-01-20_

En este tema se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que se pueden combinar en una implementación de servidor Lync Server 2013 Standard Edition.

## Roles de servidor

En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado se recopilan en el servidor Standard Edition, aunque es necesaria una configuración adicional para habilitarlos. Puede implementar el servicio de mediación en servidores distintos.

Puede recopilar un servidor de aplicaciones de confianza con el servidor Standard Edition.

Cada uno de los siguientes roles debe implementarse en un equipo separado:

  - Director

  - Servidor perimetral

  - Servidor de mediación (si no se combina con el servidor de Standard Edition)

  - Servidor Office Web Apps

## Bases de datos

De manera predeterminada, la base de datos back-end de SQL Server Express se combina con el servidor Standard Edition. No se puede mover a otro equipo diferente. Con una excepción, no se puede combinar con otras bases de datos en el servidor Standard Edition. Si elige implementar Servidor de chat persistente en un servidor Standard Edition, puede colocar la base de datos de chat persistente y la base de datos de conformidad de chat persistente en el mismo servidor Standard Edition.

Se puede combinar cada una de las siguientes bases de datos en un único servidor de base de datos:

  - Base de datos de supervisión

  - Base de datos de archivado

  - Una base de datos back-end para un grupo de servidores front-end de Enterprise Edition

Se puede combinar cualquiera de estas bases de datos, o todas ellas, en una única instancia de SQL o usar una instancia de SQL diferente para cada una, con las siguientes restricciones:

  - Cada instancia de SQL puede contener únicamente una base de datos back-end (para un grupo de servidores front-end de Enterprise Edition), una sola base de datos de supervisión, una sola base de datos de archivado, una sola base de datos de chat persistente o una sola base de datos de cumplimiento de chat persistente.

  - El servidor de base de datos no admite más de un grupo de servidores front-end Enterprise Edition, un servidor de archivado, un servidor de supervisión, una sola base de datos de Chat persistente y una sola base de datos de Chat persistente, pero admite uno de cada, independientemente de si las bases de datos usan la misma instancia de SQL Server o instancias diferentes de SQL Server.

Puede combinar un recurso compartido de archivos con las bases de datos, como se describe más adelante en esta sección.


> [!NOTE]
> En Lync Server 2013, tiene la opción de integrar el almacenamiento de supervisión y archivado con el almacenamiento de Exchange 2013 para algunos o para todos los usuarios de su implementación. No puede implementar ningún componente o servidor que ejecute Lync Server en los mismos servidores que el almacenamiento de Exchange.



> [!IMPORTANT]  
> Aunque se admite la combinación de las bases de datos, el tamaño de estas puede crecer rápidamente. Por ejemplo, si considera la combinación de la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede aumentar considerablemente. Por este motivo, no se recomienda la combinación de varias bases de datos, especialmente la base de datos de archivado, la base de datos de Chat persistente y la base de datos de cumplimiento de Chat persistente con la base de datos back-end.



## Recursos compartidos de archivos

El recurso compartido de archivos puede estar en un servidor separado o puede combinarse en el mismo servidor que el de cualquier o todos los siguientes elementos:

  - Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front-end de Enterprise Edition

  - Base de datos de archivado

  - Base de datos de supervisión

  - Base de datos de Chat persistente

  - Base de datos de cumplimiento de Chat persistente

Se puede usar un solo recurso compartido de archivos para varios grupos de servidores front-end y servidores Standard Edition (todo en el mismo sitio).


> [!NOTE]
> En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como servidor de Standard Edition.



## Otros componentes

No puede combinar un servidor proxy inverso, que no es un componente de Lync Server 2013 pero es un necesario en la implementación si desea proporcionar compatibilidad para compartir contenido web para los usuarios federados con cualquier rol de servidor Lync Server 2013. Sin embargo, puede implementar la compatibilidad de servidor proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente de su organización que se use para otras aplicaciones.

No puede combinar ningún componente de Mensajería unificada de Exchange ni de SharePoint con ningún rol de Lync Server 2013.

