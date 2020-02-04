---
title: 'Lync Server 2013: Planear acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17d38abe775a915fc3357610ad2b741eb0e77628
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Planear acceso de usuarios externos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-19_

Las comunicaciones en la mayoría de las organizaciones implican a servicios y usuarios que no se encuentran dentro de la red interna. Estos servicios y usuarios incluyen empleados que están fuera del sitio temporal o permanentemente, empleados de organizaciones de clientes o socios, personas que usan servicios de mensajería instantánea pública (mi) y clientes potenciales, socios y usuarios anónimos a los que invite a reuniones y presentaciones. En esta documentación, estas personas se conocen colectivamente como *usuarios externos*.

Con Microsoft Lync Server 2013, los usuarios de su organización pueden usar la mensajería instantánea y la presencia para comunicarse con los usuarios externos y pueden participar en conferencias de audio y vídeo (A/V) y en conferencias web con sus empleados fuera del sitio y otros tipos de usuarios externos. También puedes admitir el acceso externo desde dispositivos móviles y con la telefonía IP empresarial. Los usuarios externos que no son miembros de su organización pueden participar en reuniones de Lync Server 2013, lo que permite a los asistentes anónimos.

Para admitir las comunicaciones en el Firewall de la organización, debe implementar el servidor perimetral 2013 de Lync Server en la red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada). El servidor perimetral controla cómo los usuarios externos al firewall se pueden conectar a la implementación interna de Lync Server 2013. También controla las comunicaciones con usuarios externos que se originan dentro del firewall.

En función de sus necesidades, puede implementar uno o varios servidores perimetrales en una o más ubicaciones. En esta sección se describen escenarios para el acceso de usuarios externos en Lync Server 2013, y se explica cómo planear la topología perimetral y de proxy inverso.

<div>


> [!NOTE]  
> Aunque necesita un servidor perimetral para admitir la telefonía IP empresarial y el acceso de usuarios externos, esta sección se centra en la compatibilidad con la mensajería instantánea, la presencia, las conferencias A/V, la Federación, la conferencia web y Lync Mobile. Para obtener más información sobre la compatibilidad de telefonía IP empresarial, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">planificación de telefonía empresarial en Lync Server 2013</A> en la documentación de planeación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Requisitos del sistema para componentes perimetrales para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Información general sobre el acceso de usuarios externos en Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Descripción de la detección automática en Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Elección de una topología en Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Recopilación de datos en Lync Server 2013](lync-server-2013-data-collection.md)

  - [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

