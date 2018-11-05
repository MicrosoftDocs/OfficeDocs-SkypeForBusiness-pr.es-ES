---
title: 'Lync Server 2013: Planear acceso de usuarios externos'
TOCTitle: Planear acceso de usuarios externos
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48277053
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planear acceso de usuarios externos en Lync Server 2013

 

_**Última modificación del tema:** 2013-01-19_

Es probable que una gran parte de la comunicación en su organización implique a gente que se encuentra fuera del firewall: empleados que trabajan de forma temporal o permanente fuera del puesto de trabajo, empleados de organizaciones de socios o clientes, gente que usa los servicios de mensajería instantánea pública y posibles clientes o socios que usted invite a reuniones y presentaciones. En esta documentación, se hace referencia a estas personas como *usuarios externos* .

Con el Microsoft Lync Server 2013, los usuarios de su organización pueden usar la mensajería instantánea y la presencia para comunicarse con usuarios externos, además de poder participar en conferencias de audio y vídeo (A/V) y conferencias web con los empleados que se encuentran fuera del puesto de trabajo y otros tipos de usuarios externos. Asimismo, puede permitir el acceso externo desde dispositivos móviles y a través de la Telefonía IP empresarial. Los usuarios externos que no sean miembros de su organización pueden participar en reuniones de Lync Server 2013, permitiéndose asistentes anónimos.

Para admitir comunicaciones en el firewall de su organización, implemente el servidor perimetral de Lync Server 2013 en la red perimetral (también conocida como DMZ y subred filtrada). El servidor perimetral controla la forma en que los usuarios que se encuentran fuera del firewall pueden conectarse a la implementación interna de Lync Server 2013. Además, controla las comunicaciones con usuarios externos que se originan dentro del firewall.

Según sus requisitos, puede implementar uno o más servidores perimetrales en una o más ubicaciones. En esta sección se describen escenarios para el acceso de usuarios externos en Lync Server 2013 y se explica cómo planear una topología perimetral y de proxy inverso.


> [!NOTE]
> A pesar de que para permitir el acceso de usuarios externos y la Telefonía IP empresarial se necesita un servidor perimetral, esta sección se centra en la compatibilidad con la mensajería instantánea, la presencia, las conferencias A/V, la federación, las conferencias web y Lync Mobile. Para más información sobre la compatibilidad con la Telefonía IP empresarial, consulte <A href="lync-server-2013-planning-for-enterprise-voice.md">Planear la telefonía IP empresarial en Lync Server 2013</A> en la documentación sobre planeación.



## En esta sección

  - [Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Requisitos del sistema para componentes perimetrales para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Información general sobre el acceso de usuarios externos en Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Comprender la detección automática](lync-server-2013-understanding-autodiscover.md)

  - [Elección de una topología en Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Recopilación de datos en Lync Server 2013](lync-server-2013-data-collection.md)

  - [Determinar los requisitos DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Plan para certificados de servidores perimetrales en Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

