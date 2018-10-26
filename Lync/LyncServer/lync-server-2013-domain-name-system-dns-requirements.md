---
title: Requisitos del sistema de nombres de dominio (DNS)
TOCTitle: Requisitos del sistema de nombres de dominio (DNS)
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48275330
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos del sistema de nombres de dominio (DNS)

 

_**Última modificación del tema:** 2012-06-18_

Para implementar Lync Server, tiene que crear registros de Sistema de nombres de dominio (DNS) que permitan la detección de clientes y servidores y, opcionalmente, si la organización así lo quiere, la compatibilidad con el inicio de sesión automático de los clientes.

Lync Server usa el DNS de las siguientes maneras:

  - Para detectar los servidores o grupos de servidores internos para las comunicaciones entre servidores.

  - Para permitir a los clientes detectar el Grupo de servidores front-end o el Servidor Standard Edition que se usa para diversas transacciones SIP.

  - Para permitir que los dispositivos de comunicaciones unificadas (UC) que no se hayan registrado detecten el Grupo de servidores front-end o el Servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos, obtenga las actualizaciones y envíe los registros.

  - Para permitir a los clientes y servidores externos conectarse a los Servidores perimetrales o al proxy inverso HTTP para la mensajería instantánea o las conferencias.

  - Para permitir que los dispositivos externos de comunicaciones unificadas se conecten al Servicio web de actualización de dispositivos a través de Servidores perimetrales o del proxy inverso HTTP, y obtengan actualizaciones.

  - Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.

## En esta sección

  - [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Requisitos DNS para grupos Front-End](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Requisitos DNS para servidores Standard Edition](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Requisitos de DNS para movilidad](lync-server-2013-dns-requirements-for-mobility.md)

  - [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md)

