---
title: "Lync Server 2013: Implem. servidores mediación y definir servidores del mismo nivel"
TOCTitle: Implementar servidores de mediación y definir servidores del mismo nivel
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48276198
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar servidores de mediación y definir servidores del mismo nivel en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

La carga de trabajo de Telefonía IP empresarial, la conferencia de acceso telefónico local y las aplicaciones avanzadas de Telefonía IP empresarial ( Aplicación de grupo de respuesta, Aplicación de estacionamiento de llamadas, control de admisión de llamadas (CAC), etc.) están disponibles en Grupos de servidores front-end. Con Lync Server 2013, la funcionalidad del Servidor de mediación se integra en el Servidor front-end. Ya no es necesario un Servidor de mediación aparte e independiente. Grupos de servidores front-end puede comunicar directamente con las puertas de enlace compatibles (una puerta de enlace de red telefónica conmutada (RTC) o un IP-PBX), con lo que ya no es necesario que actúe como intermediario un Servidor de mediación.

La única excepción es si se configura un tronco SIP para conectar un controlador de borde de sesión en un proveedor de servicios de telefonía por Internet. Para conectar su infraestructura de Telefonía IP empresarial a su proveedor de tronco SIP, deberá implementar un Servidor de mediación aparte.

La conexión entre Lync Server (el componente de Servidor de mediación en un Grupo de servidores front-end o Servidor de mediación independiente) y una puerta de enlace se define como una asociación lógica llamada *tronco* . En los temas de esta sección se describe cómo definir un tronco y cómo implementar un servidor de mediación independiente (si conecta con un tronco SIP).

## En esta sección

  - [Definir un servidor de mediación en el Generador de topologías en Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Definir una puerta de enlace en el Generador de topologías en Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Instalar los archivos del servidor de mediación en Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Definir troncos adicionales en el Generador de topologías en Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

## Secciones relacionadas

[Configurar una conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

