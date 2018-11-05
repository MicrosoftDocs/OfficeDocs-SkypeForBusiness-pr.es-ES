---
title: 'Lync Server 2013: Compatibilidad de mensajería unificada (UM) de Exchange'
TOCTitle: Compatibilidad de mensajería unificada (UM) de Exchange
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48274434
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Compatibilidad de mensajería unificada (UM) de Exchange en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Lync Server 2013 admite la integración con Mensajería unificada de Exchange (UM) para la combinación de mensajes de voz y mensajes de correo electrónico en una única infraestructura de mensajería. En Exchange 2013, Mensajería unificada de Exchange consiste en el servicio Mensajería unificada de Exchange, que se instala y se ejecuta en el servidor de Buzón de correo, y el Enrutador de llamadas de mensajería unificada, que se instala y se ejecuta en el servidor Acceso de cliente. Para las implementaciones de Enterprise Voice de Lync Server 2013, Mensajería unificada de Exchange combina los mensajes de voz y los mensajes de correo electrónico en un único almacén al que se puede acceder por vía telefónica (es decir, Outlook Voice Access) o desde un equipo. Mensajería unificada de Exchange y Lync Server 2013 trabajan conjuntamente para proporcionar respuesta a las llamadas, Outlook Voice Access y servicios de operador automático a los usuarios de Enterprise Voice.

Además de la compatibilidad que proporcionaban las versiones anteriores de Mensajería unificada de Exchange con respecto a la integración con implementaciones locales de Lync Server 2013, Mensajería unificada de Exchange admite ahora la integración con nm-exch-um-2nd hospedados. Esto le permite proporcionar mensajería de voz a sus usuarios si los migra, en su totalidad o en parte, a un proveedor de servicios de Exchange hospedado como Microsoft Exchange Online

Lync Server 2013 admite las versiones siguientes:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (obligatorio) o con el último service pack (recomendado)

  - Microsoft Exchange Server 2007 con Service Pack 1 (SP1) (obligatorio) o el último service pack (recomendado)

No es posible combinar Mensajería unificada de Exchange con Lync Server 2013 o una base de datos de Lync Server 2013. Puede instalar Mensajería unificada de Exchange y Lync Server 2013 en bosques independientes.


> [!NOTE]
> Es posible que no se requiera Mensajería unificada de Exchange para implementaciones de Enterprise Voice que tengan implementado un sistema PBX, ya que el sistema PBX puede continuar proporcionando correo de voz y servicios relacionados a todos los usuarios. Si retira el sistema PBX (por ejemplo, si implementa troncos SIP para la conectividad con la red telefónica conmutada pública o RTC), deberá volver a configurar Mensajería unificada de Exchange para proporcionar correo de voz a los usuarios que anteriormente usaban el sistema de correo de voz de PBX.



## En esta sección

  - [Componentes y topologías para mensajería unificada local en Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Compatibilidad con la integración de mensajería unificada de Exchange hospedada en Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

