---
title: 'Lync Server 2013: Comprobar el diseño de la topología'
TOCTitle: Comprobar el diseño de la topología
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48276568
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar el diseño de la topología en Lync Server 2013

 

_**Última modificación del tema:** 2012-01-02_

Generador de topologías comprueba automáticamente la topología. Cualquier error de topología se identifica como un error de validación y se indica con el icono de error de validación junto al rol del servidor. Es importante comprobar también que la topología representa correctamente la topología de su implementación. Antes de publicarla, debe seleccionar también el grupo que hospedará el almacén de administración central.

## Para comprobar la topología antes de su publicación

1.  Compruebe que todas las URL sencillas están configuradas correctamente.

2.  Confirme que el servidor basado en SQL Server está conectado y disponible para el equipo en el que se ha instalado Generador de topologías, e incluye todas las reglas de puerta de enlace necesarias.

3.  Confirme que el recurso compartido de archivos esté disponible y que los permisos correctos estén definidos.

4.  Confirme que se han definido en la topología los roles de servidor correctos que cumplen los requisitos de la implementación.

5.  Verifique que los servidores existen en Servicios de dominio de Active Directory. Esto se producirá automáticamente si ha incorporado los servidores al dominio.

Una vez que haya verificado la topología y comprobado que no existen errores de validación, estará listo para publicar la topología. Si hay errores de validación, deberá corregirlos para poder publicar la topología. Para más información, consulte [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).

