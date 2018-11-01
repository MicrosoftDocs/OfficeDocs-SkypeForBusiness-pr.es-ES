---
title: "Lync Server 2013 : Vérif. de la connectivité pour les utilisateurs externes"
TOCTitle: Comprobar la conectividad de usuarios externos
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48275388
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar la conectividad de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

La validación de conectividad para usuarios externos exige garantizar la conectividad de los usuarios con el servidor y el puerto para el servicio perimetral de acceso.

El sitio del Analizador de conectividad remota ( <https://www.testocsconnectivity.com/> ) es un recurso valioso para confirmar la configuración y la capacidad de conectarse, enviar y recibir los mensajes correctos en escenarios de acceso de usuarios externos. El soporte técnico de Microsoft se encarga de administrar y mantener este sitio. Para acceder al Analizador de conectividad remota, abra el sitio web en un explorador y siga las instrucciones para seleccionar el escenario.

## Probar la conectividad de los usuarios externos y el acceso externo

Las pruebas de acceso de usuarios externos deberán incluir cada tipo de usuario externo que admita su organización, incluidos todos los siguientes:

  - Usuarios de al menos un dominio federado y uso compartido de mensajería instantánea de prueba, presencia, A/V y escritorio.

  - Usuarios de cada proveedor de servicios de mensajería instantánea públicos que admita su organización (y para los que se haya completado el aprovisionamiento).

  - Usuarios anónimos.

  - Usuarios de la organización que inicien la sesión de forma remota en Lync, pero que no usen una VPN.

Estas pruebas determinan si el servidor perimetral:

  - Escucha en los puertos necesarios a través de un cliente de telnet de fuera de la red.
    
      - Ejemplo: telnet ae.contoso.com 443
    
      - Realice las pruebas anteriores en los puertos que esté usando en el servidor perimetral o en el grupo de servidores perimetrales según la implementación.

  - Logre una resolución de DNS externa precisa.
    
      - Desde fuera de la red, realice un ping de red de los FQDN externos de su servidor perimetral o grupo de servidores perimetrales. Incluso aunque el ping dé un error, verá las direcciones IP que podrá comparar con las que ha asignado.

