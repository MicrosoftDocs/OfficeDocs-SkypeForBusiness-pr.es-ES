---
title: Migrar la federación XMPP
TOCTitle: Migrar la federación XMPP
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49889566
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar la federación XMPP

 

_**Última modificación del tema:** 2012-10-19_

Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP), que podía implementarse como un rol de servidor independiente para permitir la federación con las implementaciones de XMPP. En Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica. La funcionalidad de XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral de Lync Server 2013, y la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.

Desde el punto de vista de la migración, una cuenta de usuario de Lync Server puede moverse a un grupo de Lync Server 2013 y seguir usando la puerta de enlace XMPP heredada. Esto solo es posible cuando el socio federado de XMPP no está configurado en Lync Server 2013.

En resumen, si Lync Server 2010 se ha implementado con la puerta de enlace XMPP de Office Communications Server 2007 R2 y la federación de XMPP se ha habilitado para los usuarios de Lync Server 2010 heredados, para migrar la federación de XMPP a Lync Server 2013:

1.  Implemente un grupo de Lync Server 2013.

2.  Implemente un servidor perimetral de Lync Server 2013.

3.  Mueva todos los usuarios al grupo de Lync Server 2013.

4.  Cree certificados y directivas de acceso de XMPP para el servidor perimetral.

5.  Habilite la federación de XMPP en Lync Server 2013. 

6.  Actualice las entradas DNS para que apunten a la puerta de enlace XMPP de Lync Server 2013.

