---
title: Migrar servidores de archivado y supervisión
TOCTitle: Migrar servidores de archivado y supervisión
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48275714
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar servidores de archivado y supervisión

 

_**Última modificación del tema:** 2012-10-02_

Si implementó el servidor de archivado y el servidor de supervisión en su entorno de Lync Server 2010, podrá implementar estos servidores en su entorno de Lync Server 2013 después de migrar sus grupos de servidores front-end. No obstante, si las funciones de archivado y supervisión son esenciales para su organización, debería agregar el servidor de archivado y de supervisión a su grupo piloto de Lync Server 2013 antes de migrar para que dichas funciones estén disponibles durante el proceso de migración.

Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:

  - Los datos de archivado y los datos de supervisión no se transfieren a la implementación de Lync Server 2013. Los datos de los que realice una copia de seguridad antes de retirar el entorno heredado serán su historial de actividades en el entorno de Lync Server 2010.

  - La versión Lync Server 2010 del servidor de archivado y del servidor de supervisión solo puede asociarse con un grupo de servidores front-end Lync Server 2010. En la versión Lync Server 2013, el archivado y la supervisión ya no son roles del servidor, sino servicio integrados en el grupo de servidores front-end Lync Server 2013.

  - Durante el tiempo en que coexisten su implementación heredada y su implementación de Lync Server 2013, la versión Lync Server 2010 del servidor de archivado y del servidor de supervisión recopila datos para usuarios ubicados en grupos de servidores Lync Server 2010. En Lync Server 2013, el archivado y la supervisión recopilan datos para usuarios ubicados en grupos de servidores Lync Server 2013.
    

    > [!NOTE]
    > Durante la fase de migración, cuando continúe utilizando su servidor perimetral heredado con el nuevo grupo piloto Lync Server 2013, la versión Lync Server 2010 del servidor de archivado continuará recopilando datos para usuarios ubicados en grupos de servidores Lync Server 2010 y el archivado de Lync Server 2013 recopilará datos para usuarios ubicados en grupos de servidores Lync Server 2013.



  - Si usa una solución de archivado y de supervisión de un tercero junto con el archivado y la supervisión en Lync Server 2013, consulte a su proveedor sobre el momento y la forma de integrar la solución del tercero con Lync Server 2013.

