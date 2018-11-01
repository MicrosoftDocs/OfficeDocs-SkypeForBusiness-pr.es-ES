---
title: Migrar la federación XMPP
TOCTitle: Migrar la federación XMPP
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49889229
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar la federación XMPP

 

_**Última modificación del tema:** 2012-10-16_

Las versiones anteriores de Office Communications Server proporcionaban una puerta de enlace de Protocolo extensible de mensajería y presencia (XMPP) que podría implementarse como un rol del servidor independiente para permitir la federación con implementaciones de XMPP. En Lync Server 2013, la funcionalidad de XMPP se puede implementar como una característica. La funcionalidad de XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral de Lync Server 2013 y como la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.

Desde la perspectiva de la migración, una cuenta de usuario de Office Communications Server 2007 R2 puede transferirse a un grupo de Lync Server 2013 y continuar usando la puerta de enlace XMPP de Office Communications Server 2007 R2. Esto solo es posible cuando el socio federado de XMPP no se configuró en Lync Server 2013.

En resumen, si Office Communications Server se ha implementado con la puerta de enlace XMPP de Office Communications Server 2007 R2 y la federación de XMPP se ha habilitado para los usuarios de Office Communications Server 2007 R2 heredados, para migrar la federación de XMPP a Lync Server 2013:

1.  Implemente un grupo de Lync Server 2013.

2.  Implemente un servidor perimetral de Lync Server 2013.

3.  Mueva a todos los usuarios al grupo de Lync Server 2013.

4.  Cree certificados y directivas de acceso de XMPP para el servidor perimetral.

5.  Habilite la federación de XMPP en Lync Server 2013. 

6.  Actualice las entradas DNS para que apunten a la puerta de enlace XMPP de Lync Server 2013.

