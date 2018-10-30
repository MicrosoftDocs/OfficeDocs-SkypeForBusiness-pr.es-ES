---
title: 'Lync Server 2013: Información general sobre el director'
TOCTitle: Información general sobre el director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48276734
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre el director en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Un Director es un servidor que ejecuta Lync Server 2013 y autentica solicitudes de usuario pero no hospeda cuentas de usuario. De manera opcional, se puede implementar Director en los dos escenarios que se describen a continuación:

  - Si habilita el acceso de usuarios externos al implementar Servidores perimetrales, también debe implementar un Director. En este escenario, el Director autentica a los usuarios externos y envía el tráfico a los servidores internos. Cuando se usa un Directorpara autenticar a los usuarios externos, se liberan los servidores del Grupo de servidores front-end de la carga de realizar la autenticación de estos usuarios. También ayuda a aislar los grupos de servidores Grupos de servidores front-end de tráfico malintencionado, como ataques por denegación de servicio. Si la red está saturada con tráfico externo no válido, este tráfico llega al director.

  - Si implementa varios Grupos de servidores front-end en un sitio central, mediante la adición de un Director puede simplificar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, primero recibe todas las solicitudes el Director y, a continuación, este las enrutará al Grupo de servidores front-end correcto.

