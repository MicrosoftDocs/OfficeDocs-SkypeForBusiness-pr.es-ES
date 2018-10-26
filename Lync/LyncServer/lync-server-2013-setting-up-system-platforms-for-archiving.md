---
title: Configurar plataformas del sistema para archivado
TOCTitle: Configurar plataformas del sistema para archivado
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48274795
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar plataformas del sistema para archivado

 

_**Última modificación del tema:** 2012-10-09_

Antes de iniciar la implementación de archivado, debe instalar el sistema operativo requerido y cualquier otro software necesario como requisito previo en el hardware que cumpla los requisitos del sistema:

  - Plataforma de **Lync Server 2013. Las implementaciones de**   Lync Server 2013 no tienen servidores de archivado. En su lugar, agentes de colección de datos unificada se ejecutan en servidores front-end y servidores de Standard Edition para capturar datos de archivado, de modo que ninguna plataforma independiente del sistema sea necesaria para hospedar el archivado.

  - **Plataforma de almacenamiento de datos**.   En Lync Server 2013, puede almacenar datos siguiendo una de estas opciones:
    
      - **Integración de Microsoft Exchange.**   Si desea almacenar datos de archivado de Lync Server 2013 mediante su implementación de Exchange 2013, en lugar de o además de configurar una base de datos independiente para el almacenamiento de datos de archivado, la implementación de Exchange debe ejecutar Exchange 2013. Para obtener más información sobre la configuración de plataformas del sistema para Exchange 2013, consulte la documentación del producto de Exchange.
    
      - **SQL Server.**   Si desea usar una base de datos de SQL Server independiente para el almacenamiento de datos de archivado, en lugar o además usar la integración de Microsoft Exchange, debe configurar la plataforma de sistema para la base de datos antes de la implementación de archivado. Los requisitos específicos de la plataforma del sistema dependen de si usa Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 para la base de datos de archivado. Para obtener más información sobre la configuración de las plataformas del sistema para estas bases de datos, consulte la documentación del producto de Microsoft SQL Server 2008 R2 y Microsoft SQL Server 2012.

  - **Plataforma de servidor de archivos**.   Lync Server 2013 almacena archivos de archivado de Lync Server en la misma ubicación que especifique para el almacenamiento de archivos al configurar los servidores front-end o los servidores de Standard Edition. No puede especificar una ubicación independiente para el almacenamiento de archivos de archivado, por lo que no es necesaria ninguna plataforma del sistema independiente para el almacenamiento de archivos de archivado. Si usa la integración de Microsoft Exchange, los archivos de Exchange 2013 para las comunicaciones de Lync archivadas se almacenan en servidores de Exchange 2013 para usuarios alojados en estos servidores de Exchange.

