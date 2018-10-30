---
title: 'Lync Server 2013: Componentes VoIP de la red perimetral'
TOCTitle: Componentes VoIP de la red perimetral
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48275691
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes VoIP de la red perimetral para Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Los autores de llamadas externos que usen clientes de comunicaciones unificadas para llamadas individuales o de conferencia usarán el Servidor perimetral para la comunicación de voz con sus compañeros de trabajo.

En un Servidor perimetral, el servicio perimetral de acceso proporciona la señalización de SIP para llamadas de usuarios de Lync que están fuera del firewall de la organización. El servicio perimetral A/V habilita el paso de los medios a través de NAT y firewalls. Un autor de llamadas que use un cliente de comunicaciones unificadas (UC) desde fuera del firewall corporativo usará el servicio perimetral A/V para las llamadas individuales y de conferencia.

El servicio de autenticación A/V se coloca con el servicio perimetral A/V y le proporciona servicios de autenticación. Los usuarios externos que intenten conectarse al servicio perimetral A/V necesitarán un token de autenticación proporcionado por el servicio de autenticación A/V para que se acepten sus llamadas.

