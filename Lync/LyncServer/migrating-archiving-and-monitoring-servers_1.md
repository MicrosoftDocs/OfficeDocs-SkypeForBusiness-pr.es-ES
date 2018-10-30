---
title: Migrar los servidores de archivado y supervisión
TOCTitle: Migrar los servidores de archivado y supervisión
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49889370
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar los servidores de archivado y supervisión

 

_**Última modificación del tema:** 2012-10-02_

Si implementó el servidor de archivado y el servidor de supervisión en su Office Communications Server 2007 R2, podrá implementar estos servidores en su entorno de Lync Server 2013 después de migrar sus grupos de servidores front-end. No obstante, si las funciones de archivado y supervisión son esenciales para su organización, debe agregar el archivado y la supervisión a su grupo piloto antes de migrar para que dichas funciones estén disponibles durante el proceso de migración.

Si desea contar con la funcionalidad de archivado y de supervisión durante la fase de migración y coexistencia, tenga en cuenta lo siguiente:

  - Los datos de archivado y los datos de supervisión no se transfieren a la implementación de Lync Server 2013. Los datos de los que realice una copia de seguridad antes de retirar el entorno heredado serán su historial de actividades en Office Communications Server 2007 R2.

  - La versión Office Communications Server 2007 R2 del servidor de archivado y del servidor de supervisión solo puede asociarse con un grupo de servidores front-end Office Communications Server 2007 R2. En la versión Lync Server 2013, el archivado y la supervisión ya no son roles del servidor, sino servicio integrados en el grupo de servidores front-end Lync Server 2013.

  - Durante el tiempo en que coexisten su implementación heredada y su implementación de Lync Server 2013, la versión Office Communications Server 2007 R2 del servidor de archivado y del servidor de supervisión recopila datos de los usuarios hospedados en grupos de servidores de Office Communications Server 2007 R2. La versión Lync Server 2013 del servidor de archivado y del servidor de supervisión recopila datos de los usuarios hospedados en grupos de servidores de Lync Server 2013.
    

    > [!NOTE]
    > Durante la fase de migración, mientras sigue utilizando su servidor perimetral heredado con el nuevo grupo piloto Lync Server 2013, la versión Office Communications Server 2007 R2 del servidor de archivado continuará recopilando datos de los usuarios hospedados en grupos de servidores de Office Communications Server 2007 R2, y la versión Lync Server 2013 del servidor de archivado recopilará datos de los usuarios hospedados en grupos de servidores de Lync Server 2013.



  - Si usa una solución de archivado y de supervisión de un tercero junto con el servidor de archivado y el servidor de supervisión, consulte a su proveedor para saber el momento y la forma de integrar la solución del tercero con Lync Server 2013.

