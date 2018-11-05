---
title: 'Lync Server 2013: Características de resistencia de sitios de sucursal'
TOCTitle: Características de resistencia de sitios de sucursal
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48275974
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Características de resistencia de sitios de sucursal en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-10_

Al proporcionar resistencia a las sucursales, si se produce un error en la conexión WAN de una sucursal a un sitio central o si no se puede alcanzar el sitio central, las siguientes características de voz deberían seguir disponibles:


  - Llamadas de red telefónica conmutada (RTC) entrantes y realizadas.

  - Llamadas de empresa entre usuarios del mismo sitio y entre dos sitios diferentes

  - Administración básica de llamadas, incluida la retención, recuperación y transferencia de llamadas.

  - Mensajería instantánea entre dos participantes

  - Desvío de llamadas, llamadas simultáneas a extremos, delegación de llamadas y servicios de llamada de equipo, pero solo si el delegador y el delegado (por ejemplo, un encargado y su administrador) o todos los miembros del equipo están configurados en el mismo sitio

  - Registros de detalles de las llamadas (CDR)

  - Conferencias de acceso telefónico local RTC con operador automático de conferencia

  - Funcionalidades de correo de voz, si configura los parámetros de reenrutamiento del correo de voz (Para ver más detalles, consulte [Requisitos de resistencia de sitios de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Autorización y autenticación de usuarios

Las siguientes características estarán disponibles solo si su solución de resistencia es una implementación completa de Lync Server en la sucursal:

  - Conferencia A/V, web y MI

  - Enrutamiento basado en presencia y No molestar (DND) (con el que se evita que las llamadas suenen en extensiones con DND activado)

  - Actualización de la configuración del desvío de llamadas

  - Aplicación de grupo de respuesta y Aplicación de estacionamiento de llamadas

  - Aprovisionamiento de teléfonos y clientes nuevos, pero solo si la sucursal tiene Servicios de dominio de Active Directory

  - 9-1-1 mejorado (E9-1-1)
    
    Si se ha implementado E9-1-1, y el tronco SIP del sitio central no está disponible porque se ha interrumpido el vínculo WAN, la Aplicación de sucursal con funciones de supervivencia enrutará las llamadas de E9-1-1 a la puerta de enlace de la sucursal local. Para habilitar esta característica, las directivas de voz de los usuarios de las sucursales deben enrutar las llamadas a la puerta de enlace local en caso de error de WAN.


> [!NOTE]
> Las SBA (sucursales con funciones de supervivencia) no son compatibles con XMPP. Los usuarios hospedados en configuraciones de SBA no podrán enviar mensajes instantáneos ni ver la presencia de los contactos de XMPP.


