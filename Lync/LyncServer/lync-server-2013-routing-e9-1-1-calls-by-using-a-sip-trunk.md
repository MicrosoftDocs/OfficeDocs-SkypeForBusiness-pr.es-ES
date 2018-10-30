---
title: 'Lync Server 2013: Enrutamiento de llamadas E9-1-1 mediante un SIP troncal'
TOCTitle: Enrutamiento de llamadas E9-1-1 mediante un SIP troncal
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48274526
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enrutamiento de llamadas E9-1-1 mediante un SIP troncal en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-29_

El uso de un tronco SIP para conectarse a un proveedor de servicios E9-1-1 certificado es una manera de implementar E9-1-1. Para obtener más detalles sobre el uso de una puerta de enlace ELIN para conectarse a un proveedor de servicios E9-1-1 basado en una red telefónica conmutada (RTC), vea [Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

El diagrama siguiente muestra cómo se enruta una llamada de emergencia desde Lync Server al PSAP (Punto de respuesta de seguridad pública) cuando se usa un tronco SIP y un proveedor de servicios E9-1-1 certificado.

**Enrutamiento de llamadas E9-1-1 mediante un tronco SIP**

![Enrutar llamada de emergencia de Lync Server a un punto de respuesta de seguridad pública (PSAP)](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Enrutar llamada de emergencia de Lync Server a un punto de respuesta de seguridad pública (PSAP)")

Cuando se realiza una llamada de emergencia desde un cliente Lync Server:

1.  La invitación SIP, que contiene la ubicación, el número de devolución de llamada de la persona que realiza la llamada y la URL de notificación (opcional), así como el número de devolución de llamada de la conferencia, se enruta a Lync Server.

2.  Lync Server identifica el número de emergencia y enruta la llamada (en función del valor **Uso de RTC** definido en la directiva de ubicación correspondiente) a un Servidor de mediación y, desde allí, al proveedor de servicios E9-1-1 mediante un tronco SIP.

3.  El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.

4.  Si ha configurado la directiva de ubicación para que envíe notificaciones, se enviarán mensajes instantáneos de notificación de emergencia especiales de Lync a sus responsables de seguridad. Este mensaje siempre se muestra en la pantalla de los equipos de los responsables de seguridad y proporciona información sobre el nombre, el número de teléfono, la hora y la ubicación de la persona que realiza la llamada, lo que permite al personal de seguridad responder con rapidez a la persona que realiza la llamada de emergencia mediante un mensaje instantáneo o de voz.

5.  Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.

6.  Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.

