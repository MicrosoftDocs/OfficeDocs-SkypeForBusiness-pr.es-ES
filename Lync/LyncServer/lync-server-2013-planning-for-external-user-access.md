---
title: 'Lync Server 2013: Planeación del acceso de usuarios externos'
description: 'Lync Server 2013: Planeación del acceso de usuarios externos.'
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
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562786"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Planeación del acceso de usuarios externos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-19_

Es probable que una gran parte de la comunicación en su organización implique a gente que se encuentra fuera del firewall: empleados que trabajan de forma temporal o permanente fuera del puesto de trabajo, empleados de organizaciones de socios o clientes, gente que usa los servicios de mensajería instantánea pública y posibles clientes o socios que usted invite a reuniones y presentaciones. En esta documentación, se hace referencia a estas personas como *usuarios externos*.

Con Microsoft Lync Server 2013, los usuarios de su organización pueden usar la mensajería instantánea y la presencia para comunicarse con los usuarios externos y pueden participar en conferencias de audio y vídeo (A/V) y conferencias web con los empleados fuera del sitio y otros tipos de usuarios externos. Asimismo, puede permitir el acceso externo desde dispositivos móviles y a través de la Telefonía IP empresarial. Los usuarios externos que no son miembros de su organización pueden participar en reuniones de Lync Server 2013, lo que permite a los asistentes anónimos.

Para admitir las comunicaciones en el Firewall de la organización, debe implementar el servidor perimetral de Lync Server 2013 en la red perimetral (también denominada DMZ, zona desmilitarizada y subred filtrada). El servidor perimetral controla el modo en que los usuarios externos al firewall pueden conectarse a la implementación interna de Lync Server 2013. Además, controla las comunicaciones con usuarios externos que se originan dentro del firewall.

Según sus requisitos, puede implementar uno o más servidores perimetrales en una o más ubicaciones. En esta sección se describen los escenarios para el acceso de usuarios externos en Lync Server 2013 y se explica cómo planear la topología perimetral y de proxy inverso.

<div>


> [!NOTE]  
> Aunque es necesario disponer de un servidor perimetral que admita la telefonía IP empresarial y el acceso de usuarios externos, esta sección se centra en la compatibilidad con la mensajería instantánea, la presencia, las conferencias A/V, la Federación, la conferencia web y Lync Mobile. Para obtener más información sobre la compatibilidad con Enterprise Voice, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> en la documentación referente a la planeación.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Cambios en Lync Server 2013 que afectan a la planeación del servidor perimetral](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Requisitos del sistema para componentes de acceso de usuarios externos para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Información general sobre el acceso de usuarios externos en Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Descripción de la detección automática en Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Elección de una topología en Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Recopilación de datos en Lync Server 2013](lync-server-2013-data-collection.md)

  - [Determinación de los requisitos de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planeación de certificados de servidor perimetral en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

