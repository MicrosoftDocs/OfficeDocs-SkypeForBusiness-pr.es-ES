---
title: 'Lync Server 2013: requisitos del sistema de nombres de dominio (DNS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Requisitos del sistema de nombres de dominio (DNS) para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-18_

Para implementar Lync Server, debe crear registros de sistema de nombres de dominio (DNS) que permitan el descubrimiento de clientes y servidores y, opcionalmente, soporte técnico para el inicio de sesión automático de cliente si su organización quiere admitirlo.

Lync Server usa DNS de las siguientes maneras:

  - Para detectar los servidores o grupos de servidores internos para las comunicaciones de servidor a servidor.

  - Para permitir que los clientes descubran el grupo de servidores front-end o el servidor Standard Edition usado para varias transacciones SIP.

  - Para permitir los dispositivos de comunicaciones unificadas (UC) que no han iniciado sesión para descubrir el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio Web de actualización de dispositivos, obtener actualizaciones y enviar registros.

  - Para permitir que los servidores y clientes externos se conecten a servidores perimetrales o al proxy inverso HTTP para mensajería instantánea (mi) o conferencias.

  - Para permitir que los dispositivos de comunicaciones unificadas externos se conecten al servicio Web de actualización de dispositivos a través de servidores perimetrales o el proxy inverso HTTP y obtener actualizaciones.

  - Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Requisitos de DNS para las agrupaciones front-end en Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Requisitos de DNS para servidores Standard Edition en Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de DNS para el inicio de sesión automático de cliente en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Requisitos de DNS para movilidad con Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

