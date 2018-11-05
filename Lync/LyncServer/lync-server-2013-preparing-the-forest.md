---
title: 'Lync Server 2013: Preparación del bosque'
TOCTitle: Preparación del bosque
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48275041
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparación del bosque para Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

La preparación del bosque crea la configuración global y los objetos de Active Directory, así como los grupos universales de Active Directory que usará Lync Server 2013, además concede permisos de acceso adecuados en los objetos de Active Directory. Para ver una descripción de los grupos universales y de la configuración global y los objetos creados por la preparación del bosque, consulte [Cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

La preparación del bosque también crea objetos que contienen conjuntos de propiedades y especificadores de presentación que usa Lync Server 2013, y los almacena en el contenedor de configuración.

> [!IMPORTANT]  
> Asegúrese de que los cambios efectuados durante la preparación del esquema se han replicado en todos los controladores de dominio antes de realizar el procedimiento de preparación del bosque. Si la replicación no se ha completado, se produce un error.



Si realiza una nueva implementación de Lync Server, debe almacenar la configuración global en el contenedor de configuración. Si actualiza desde una versión anterior y todavía almacena la configuración global en el contenedor del sistema, puede seguir usando el contenedor del sistema.

Debe ser miembro del grupo Administradores de empresas o Admins. del dominio para que el dominio raíz del bosque realice este procedimiento.

## En esta sección

  - [Ejecutar la preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Usar cmdlets para invertir la preparación del bosque para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

