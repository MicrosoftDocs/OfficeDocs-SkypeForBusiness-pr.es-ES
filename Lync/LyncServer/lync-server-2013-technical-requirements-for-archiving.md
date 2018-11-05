---
title: 'Lync Server 2013: Requisitos técnicos para archivado'
TOCTitle: Requisitos técnicos para archivado
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48275943
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para archivado en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Los requisitos técnicos de Lync Server 2013 incluyen lo siguiente:

  - Requisitos de infraestructura.

  - Software como requisito previo que debe estar instalado para el archivado.

  - Requisitos de almacenamiento de datos para el archivado.

  - Requisitos y consideraciones de escalado para su implementación de archivado.

  - Requisitos y consideraciones de rendimiento para sus bases de datos de archivado.


> [!NOTE]
> La información de escalado y rendimiento no está disponible en esta versión de Lync Server 2013.



## Requisitos de infraestructura

Los requisitos de infraestructura de archivado de Lync Server 2013 son los mismos que para la implementación de Lync Server 2013. Para obtener más información, vea [Determinar los requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación de planificación

## Requisitos previos de archivado

Lync Server 2013 simplifica los requisitos previos para el archivado debido a lo siguiente:

  - El servidor de archivado ya no es un rol de servidor. En su lugar, los agentes de la colección de datos unificada se ejecutan en los servidores front-end en un grupo de servidores y en servidores Standard Edition para capturar datos de archivado, por lo que no debe configurar plataformas de sistema independientes para el archivado.

  - El archivado usa el almacenamiento de archivos de Lync Server 2013 para almacenar temporalmente los archivos de contenido de las reuniones, por lo que no debe configurar un almacén de archivos independiente para el archivado.

  - En Lync Server 2013, no es necesario Message Queue Server.

## Requisitos de almacenamiento de datos para el archivado

De manera adicional, debe configurar la infraestructura de almacenamiento de archivado. Esto incluye uno o ambos de estos procedimientos:

  - Almacenamiento de **Microsoft Exchange**. Los archivos de contenido de las reuniones, como las presentaciones de PowerPoint, se archivan como datos adjuntos. Si desea usar la integración de Microsoft Exchange para que los datos de archivado de Lync se almacenen con los datos de cumplimiento de Exchange, debe usar Exchange 2013 para la implementación de Exchange y comprobar que el tamaño de almacenamiento máximo permite almacenar los archivos de contenido de las reuniones. Si implementa el archivado mediante la opción de integración de Microsoft Exchange, los datos de archivado de Lync se almacenan con los datos de cumplimiento de Exchange 2013 solo para los usuarios que están hospedados en sus servidores de Exchange 2013. Debe implementar Exchange 2013 antes de implementar y habilitar el archivado mediante la opción de integración de Microsoft Exchange. Si decide usar el almacenamiento de Exchange 2013, no tiene que implementar bases de datos de SQL Server independientes para el archivado, a menos que tenga usuarios de Lync que no estén hospedados en sus servidores de Exchange 2013.

  - Almacenamiento de bases de datos de **SQL Server para el archivado**. Para admitir usuarios que no estén hospedados en servidores de Exchange 2013, o si no desea usar la opción de integración de Microsoft Exchange, debe implementar el almacenamiento de archivado mediante una base de datos de SQL Server. Lync Server 2013 admite las versiones de 64 bits de SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    

    > [!NOTE]
    > Microsoft SQL Server 2008 R2&nbsp;Express y Microsoft SQL Server 2012&nbsp;Express no son compatibles con el archivado. Las versiones de 32&nbsp;bits de SQL Server no son compatibles. Para conocer los requisitos y las restricciones adicionales de SQL&nbsp;Server, consulte <A href="lync-server-2013-database-software-support.md">Compatibilidad con software de base de datos en Lync Server 2013</A> en la documentación sobre planeación o en la documentación sobre compatibilidad.

    
    Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación. Para más información sobre SQL Server, consulte el SQL Server TechCenter en [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0xc0a).

