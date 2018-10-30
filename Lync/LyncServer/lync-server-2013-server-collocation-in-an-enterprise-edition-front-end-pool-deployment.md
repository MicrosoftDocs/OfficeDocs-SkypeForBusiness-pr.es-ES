---
title: "Colocar servidor en implementación de grupo servidores front-end Enterprise Edition"
TOCTitle: Colocación de un servidor en una implementación de grupo de servidores front-end Enterprise Edition
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48274289
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Colocación de un servidor en una implementación de grupo de servidores front-end Enterprise Edition en Lync Server 2013

 

_**Última modificación del tema:** 2013-11-11_

En esta sección se describen los roles de servidor, las bases de datos y los recursos compartidos de archivos que puede colocar en una implementación de un grupo de servidores front-end de Lync Server 2013.

## Roles de servidor

En Lync Server 2013, el servicio de conferencia A/V, el servicio de mediación, la supervisión y el archivado se recopilan en el servidor front-end, aunque es necesaria una configuración adicional para habilitarlos. Si no desea recopilar el servidor de mediación con el servidor front-end, puede implementarlo como un servidor de mediación independiente en un equipo individual.

Puede recopilar un servidor de aplicaciones de confianza con el servidor front-end.

Cada uno de los siguientes roles debe implementarse en un equipo separado:

  - Director

  - Servidor perimetral

  - Servidor de mediación (si no se combina con el servidor front-end)

  - Servidor Office Web Apps

No puede combinar un rol de servidor de Chat persistente con el servidor front-end.

## Bases de datos

Puede combinar cada una de las siguientes bases de datos en el mismo servidor de base de datos:

  - Base de datos back-end

  - Base de datos de supervisión

  - Base de datos de archivado

  - Base de datos de Chat persistente

  - Base de datos de cumplimiento de Chat persistente

Puede combinar cualquiera de estas bases de datos, o todas ellas, en una sola instancia de SQL Server; o bien, puede usar una instancia de SQL Server separada para cada una, con las siguientes limitaciones:

  - Cada instancia de SQL Server puede contener solo una única base de datos back-end, una sola base de datos de supervisión, una sola base de datos de archivado, una sola base de datos de Chat persistente y una sola base de datos de cumplimiento de Chat persistente.

  - El servidor de base de datos no puede admitir más de un grupo de servidores front-end, una implementación de archivado y una implementación de supervisión, pero puede admitir uno de cada uno, independientemente de que las bases de datos usen la misma instancia de SQL Server o instancias de SQL Server separadas.

Puede combinar un recurso compartido de archivos con las bases de datos, como se describe más adelante en esta sección.


> [!NOTE]
> En Lync Server 2013, tiene la opción de integrar el almacenamiento de archivado con el almacenamiento de Exchange 2013 para algunos o para todos los usuarios de su implementación. No puede implementar ningún componente o servidor que ejecute Lync Server en los mismos servidores que el almacenamiento de Exchange.



> [!IMPORTANT]  
> Aunque se admite la combinación de las bases de datos, el tamaño de estas puede crecer rápidamente. Por ejemplo, si considera la combinación de la base de datos de archivado con otras bases de datos, tenga en cuenta que si va a archivar los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de archivado puede aumentar considerablemente. Por este motivo, no se recomienda la combinación de varias bases de datos, especialmente la base de datos de archivado, la base de datos de Chat persistente y la base de datos de cumplimiento de Chat persistente con la base de datos back-end.



## Recurso compartido de archivos

El recurso compartido de archivos puede estar en un servidor separado o puede combinarse en el mismo servidor que el de cualquier o todos los siguientes elementos:

  - Servidor de base de datos, incluido el servidor back-end de un grupo de servidores front-end de Enterprise Edition

  - Base de datos de archivado

  - Base de datos de supervisión

  - Base de datos de Chat persistente

  - Base de datos de cumplimiento de Chat persistente

Se puede usar un solo recurso compartido de archivos para varios grupos de servidores front-end y servidores Standard Edition (todo en el mismo sitio).


> [!NOTE]
> En Lync Server 2013, la supervisión y el archivado usan el recurso compartido de archivos de Lync Server como el servidor front-end.



## Otros componentes

No puede combinar un servidor proxy inverso, que no es un componente de Lync Server 2013 pero es un necesario en la implementación si desea proporcionar compatibilidad para compartir contenido web para los usuarios federados con cualquier rol de servidor Lync Server 2013. Sin embargo, puede implementar la compatibilidad de servidor proxy inverso para una implementación de Lync Server 2013 mediante la configuración de la compatibilidad en un servidor proxy inverso existente de su organización que se use para otras aplicaciones.

No puede combinar ningún componente de Mensajería unificada de Exchange (UM) ni de SharePoint con ningún rol de SharePoint Server.

