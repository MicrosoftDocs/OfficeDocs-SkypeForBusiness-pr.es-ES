---
title: Comprobar coexistencia de grupo de servidores piloto con grupo de servidores heredado
TOCTitle: Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48277279
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado

 

_**Última modificación del tema:** 2012-09-29_

Después de implementar el grupo piloto, compruebe la coexistencia de los dos grupos de servidores con las herramientas administrativas para ver la información del grupo. Para los grupos de Lync Server 2013 y los grupos heredados, debe usar las herramientas del Panel de control de Lync Server 2013 y del Generador de topologías.

## Compruebe que se hayan iniciado los servicios de Lync Server 2013

1.  En el servidor front-end de Lync Server 2013, desplácese hasta Herramientas administrativas\\Applet Servicios.

2.  Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:

**Servicios de Lync Server 2013**

![Lista de servicios de Lync Server iniciados](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Lista de servicios de Lync Server iniciados")

## Abra el Panel de control de Lync Server 2013

Desde el servidor front-end en la implementación de Lync Server 2013, abra el Panel de control de Lync Server 2013 y seleccione el grupo Lync Server 2010. Repita el procedimiento para abrir el grupo Lync Server 2013.

**Abra el panel de control de Lync Server 2013.**

![Cuadro de diálogo Seleccionar dirección URL](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Cuadro de diálogo Seleccionar dirección URL")

> [!IMPORTANT]  
> En Lync Server 2013, debe actualizar Silverlight a la versión 5 de Silverlight antes de usar el Panel de control de Lync Server.



Esta topología incluye los roles del servidor Lync Server 2010 y Lync Server 2013.

**Página Topología del panel de control de Lync Server 2013**

![Panel de control de Lync Server - página Topología](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Panel de control de Lync Server - página Topología")

## No intente abrir la topología en el Generador de topologías de Lync Server 2010

Si intenta abrir la topología desde el Generador de topologías de Lync Server 2010, aparecerá el error indicado abajo. La topología solo se puede visualizar en el Generador de topologías de Lync Server 2013. Se debe usar el Generador de topologías de Lync Server 2013 para crear grupos para los servidores Lync Server 2013 y Lync Server 2010.

**Mensaje de error del Generador de topologías de Lync Server 2010**

![Error en Complemento MMC del Generador de topologías de Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Error en Complemento MMC del Generador de topologías de Lync Server")

