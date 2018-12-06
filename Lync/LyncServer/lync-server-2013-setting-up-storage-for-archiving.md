---
title: Configurar almacenamiento para el archivado
TOCTitle: Configurar almacenamiento para el archivado
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48277197
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar almacenamiento para el archivado

 

_**Última modificación del tema:** 2016-12-08_

El almacenamiento de archivado para Lync Server 2013 incluye lo siguiente:

  - **Almacenamiento de datos.** El almacenamiento de datos es necesario para almacenar el contenido de mensajería instantánea.

  - **Almacenamiento de archivos.** El almacenamiento de archivos es necesario para almacenar el almacenamiento de archivos y el almacenamiento de datos de contenido (reunión) de conferencias.

## Configuración de almacenamiento de datos

Los requisitos para la configuración de almacenamiento de datos para el archivado en Lync Server 2013 dependen de cómo desea almacenar los datos de archivado:

  - Integre el archivado de Lync Server 2013 con la implementación de Exchange para almacenar datos de archivado mediante el almacenamiento de Exchange.

  - Instale servidores de bases de datos de SQL Server independientes para almacenar datos de archivado.

## Configuración de almacenamiento de Exchange para datos de archivado

La configuración de Exchange para el almacenamiento de datos de archivado requiere que la implementación de Exchange esté ejecutando Exchange 2013. Además, los buzones de correo de los usuarios deben estar hospedados en el servidor de Exchange 2013 y deben estar situados en Conservación local. Para más información sobre la configuración de Exchange 2013, consulte la documentación del producto de Exchange.

## Configuración de servidores de bases de datos de SQL Server para el almacenamiento de datos de archivado

El archivado en Lync Server 2013 requiere el software de base de datos de SQL Server para almacenar los datos archivados, a menos que integre la implementación con Exchange.

Para las bases de datos de archivado de SQL Server, debe instalar SQL Server en el equipo que hospedará la base de datos de archivado. Puede usar la misma instancia de SQL que usa para la base de datos de back-end de un grupo de servidores front-end. Para un mejor rendimiento, debe implementar la base de datos de archivado en un equipo que sea independiente del Almacén de administración central. Para obtener información sobre la combinación de componentes de Lync Server 2013, consulte [Instalación de servidores compatibles en Lync Server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.

Cada servidor de base de datos debe estar ejecutando una versión compatible de SQL Server. Para más información sobre las versiones compatibles, consulte [Requisitos técnicos para archivado en Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) en la documentación sobre planificación.

Debe configurar las plataformas de SQL Server antes de implementar y habilitar el archivado. Si la cuenta que se usará para publicar la topología tiene los derechos y permisos de administrador apropiados, puede crear la base de datos de archivado (LcsLog) al publicar la topología. También puede crear la base de datos más adelante, incluida como parte del procedimiento de instalación. Para más información sobre SQL Server, consulte el SQL Server TechCenter en [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0xc0a).


> [!NOTE]
> Asegúrese de que el tipo de inicio del servicio de agente SQL Server sea Automático y de que el servicio de agente SQL Server se esté ejecutando para la instancia de SQL que hospeda la base de datos de Archivado, de manera que la tarea de mantenimiento predeterminada de SQL Server para el archivado pueda ejecutarse como se programó, bajo el control del servicio de agente SQL Server.



## Configuración de almacenamiento de archivos

El archivado usa el recurso compartido de archivos de Lync Server 2013 que especificó al configurar el grupo de servidores front-end o el servidor Standard Edition. No se puede cambiar el recurso compartido de archivos usado para el archivado. Para más información sobre los sistemas de almacenamiento de archivos compatibles, consulte [Compatibilidad con el almacenamiento de archivos en Lync Server 2013](lync-server-2013-file-storage-support.md) en la documentación sobre compatibilidad.

