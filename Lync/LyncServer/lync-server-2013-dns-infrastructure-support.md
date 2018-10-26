---
title: 'Lync Server 2013: Compatibilidad con infraestructura de DNS'
TOCTitle: Compatibilidad con infraestructura de sistema de nombre de dominio (DNS)
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48274946
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad con infraestructura de DNS en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-08_

Lync Server 2013 precisa el sistema de nombres de dominio (DNS) y lo usa de las siguientes maneras:

  - Para detectar los servidores o grupos de servidores internos para las comunicaciones entre servidores.

  - Para permitir a los clientes detectar el servidor Standard Edition o el grupo front-end que se usa para diversas transacciones SIP.

  - Para asociar las direcciones URL simples para conferencias con los servidores que hospedan dichas conferencias.

  - Para permitir a los clientes y servidores externos conectarse a los servidores perimetrales o el proxy inverso HTTP para la mensajería instantánea o las conferencias.

  - Para permitir que los dispositivos de comunicaciones unificadas (UC) que no se hayan registrado detecten el grupo front-end o el servidor Standard Edition que ejecuta el servicio web de actualización de dispositivos, obtenga las actualizaciones y envíe los registros.

  - Para permitir que los clientes móviles detecten automáticamente recursos de servicios web sin que los usuarios tengan que escribir manualmente las direcciones URL en la configuración del dispositivo.

  - Para el equilibrio de carga de DNS.


> [!NOTE]
> Lync Server 2013 no admite nombres de dominio internacionalizados (IDN).



> [!IMPORTANT]  
> El nombre que especifique debe ser idéntico al nombre de equipo configurado en el servidor. De forma predeterminada, el nombre de equipo en el caso de un equipo que no está unido a un dominio es un nombre corto, no un nombre de dominio completo (FQDN). Generador de topologías usa FQDN, no nombres cortos. Por lo tanto, debe configurar un sufijo DNS en el nombre del equipo para implementarse como servidor perimetral que no está unido a un dominio. <strong>Utilice únicamente caracteres estándar</strong> (incluyendo A–Z, a–z, 0–9 y guiones) a la hora de asignar FQDN de sus Lync Server, servidores perimetrales y grupos. No utilice caracteres Unicode ni de subrayado. Los caracteres no estándar en una dirección URL o un FQDN a menudo no son compatibles con DNS externas y CA públicas (es decir, cuando el FQDN debe asignarse al SN en el certificado).


