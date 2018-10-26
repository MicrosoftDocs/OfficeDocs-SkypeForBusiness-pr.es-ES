---
title: "Lync Server 2013 : Créa. des enr. DNS pour les serveurs proxy inverses"
TOCTitle: Crear registros DNS para servidores de proxy inverso
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48276407
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear registros DNS para servidores de proxy inverso en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-29_

Cree registros A de DNS externos que apunten a la interfaz externa pública de Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server o Enrutamiento de solicitud de aplicaciones de Internet Information Server, como se describe en [Configurar DNS para admitir servidores perimetrales en Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Necesita registros DNS para los FQDN de los servicios web externos de cada grupo de servidores, el Director (o el Grupo de directores) y cada dirección URL simple.

Para conseguir los registros DNS mínimos para la resolución de cliente en el proxy inverso, deben crearse los siguientes registros:

  - Registro(s) del host (A) que defina(n) los servicios web externos publicados de los Directores y los grupos de Director (por ejemplo, **webdirext.contoso.com** )

  - Registro(s) del host (A) que defina(n) los servicios web externos publicados de los servicios web externos hospedados en los roles de Grupos de servidores front-end y Servidor Standard Edition (por ejemplo, **webext.contoso.com** )

  - Registro(s) del host (A) para las direcciones URL sencillas; por ejemplo, **dialin.contoso.com** y **meet.contoso.com** )

  - Registro del host (A) para el registro de Lync Discover Externa; también facilita un indicador de AutoDiscover para todas las aplicaciones web, incluida Lync Web App, el programador y la movilidad (por ejemplo, **lyncdiscover.contoso.com** )

  - Registros del host (A) de la dirección URL del Servidor Office Web Apps (por ejemplo, **officewebapp01.contoso.com** )

Para ver información detallada, consulte [Resumen DNS - Proxy inverso en Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

