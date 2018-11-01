---
title: Comprobar la federación y el acceso remoto para usuarios externos
TOCTitle: Comprobar la federación y el acceso remoto para usuarios externos
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49889520
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar la federación y el acceso remoto para usuarios externos

 

_**Última modificación del tema:** 2012-09-18_

Después de trasladar la ruta de federación al Servidor perimetral de Lync Server 2013, es necesario realizar algunas pruebas funcionales para confirmar que la federación funciona según lo previsto. Las comprobaciones de acceso de usuarios externos deben abarcar todos los tipos de usuario externo que la organización admita, incluido todos o cualquiera de los indicados a continuación.

## Probar la conectividad de los usuarios externos y el acceso externo

  - Usuarios de al menos un dominio federado, un usuario interno de Lync Server 2013 y un usuario de Lync Server 2010. Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.

  - Usuarios de cada proveedor de servicios de mensajería instantánea públicos que la organización admita (y para los que se haya completado el aprovisionamiento) que se comuniquen con un usuario de Lync Server 2013 y un usuario de Lync Server 2010.

  - Compruebe que los usuarios anónimos se pueden unir a las conferencias.

  - Un usuario hospedado en Lync Server 2010 que usa el acceso de usuarios remotos (inicia sesión en Lync Server 2010 desde fuera de la intranet, pero sin una VPN) con un usuario de Lync Server 2013 y un usuario de Lync Server 2010. Pruebe las características de mensajería instantánea, presencia, A/V y uso compartido de escritorio.

  - Un usuario hospedado en Lync Server 2013 que usa el acceso de usuarios remotos (inicia sesión en Lync Server 2013 desde fuera de la intranet, pero sin una VPN) con un usuario de Lync Server 2013 y un usuario de Lync Server 2010. Pruebe las características de mensajería instantánea, presencia, A/V y uso compartido de escritorio.

