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
ms.openlocfilehash: 2536e5079009d508765055d31e80efb1b998aa0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Requisitos del sistema de nombres de dominio (DNS) para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-18_

Para implementar Lync Server, debe crear registros de sistema de nombres de dominio (DNS) que permitan la detección de clientes y servidores y, opcionalmente, la compatibilidad con el inicio de sesión automático de los clientes si su organización desea ser compatible.

Lync Server usa DNS de las siguientes maneras:

  - Para detectar los servidores o grupos de servidores internos para las comunicaciones entre servidores.

  - Para permitir que los clientes detecten el grupo de servidores front-end o el servidor Standard Edition usado para diversas transacciones SIP.

  - Para permitir que los dispositivos de comunicaciones unificadas (UC) que no han iniciado sesión detecten el grupo de servidores front-end o el servidor Standard Edition que ejecuta el servicio Web de actualización de dispositivos, obtenga las actualizaciones y envíe los registros.

  - Para permitir que los servidores externos y los clientes se conecten a los servidores perimetrales o al proxy inverso HTTP para la mensajería instantánea (mi) o las conferencias.

  - Para permitir que los dispositivos de comunicaciones unificadas externas se conecten al servicio Web de actualización de dispositivos a través de servidores perimetrales o el proxy inverso HTTP, y obtenga actualizaciones.

  - Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Determinación de los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Requisitos de DNS para grupos de servidores front-end en Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Requisitos de DNS para servidores Standard Edition en Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Requisitos de DNS para direcciones URL sencillas en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Requisitos de DNS para la movilidad con Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

