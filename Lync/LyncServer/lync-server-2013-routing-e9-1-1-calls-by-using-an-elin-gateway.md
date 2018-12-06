---
title: 'Lync Server 2013: Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN'
TOCTitle: Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48275356
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado. Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC). Para obtener información detallada sobre los asociados que ofrecen puertas de enlace ELIN, así como vínculos a sus respectivas documentaciones, consulte <http://go.microsoft.com/fwlink/?linkid=248425>.

Al igual que las conexiones troncales SIP con los proveedores de servicios E9-1-1, las puertas de enlace ELIN también ofrecen los medios necesarios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública (PSAP) más adecuado para el autor de la llamada, pero estas puertas de enlace usan un número ELIN para identificar la ubicación. Los ELIN se definen para cada ubicación de respuesta de emergencia (ERL) de la organización (para ver más detalles, consulte [Administrar ubicaciones para puertas de enlace ELIN en Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Cuando se usa una puerta de enlace ELIN para las llamadas de emergencia, se emplea la misma infraestructura de E9-1-1 de Lync Server que se usaría en una conexión troncal SIP; es decir, la base de datos del Servicio de información de ubicaciones suministra la ubicación al cliente de Lync Server y la directiva de ubicación habilita la característica y define el enrutamiento. Sin embargo, en el caso de una puerta de enlace ELIN es necesario agregar los ELIN a la base de datos del Servicio de información de ubicaciones y hacer que el operador de RTC los cargue en la base de datos de identificación de ubicación automática (ALI).

Cuando un cliente de Lync obtiene su ubicación del Servicio de información de ubicaciones, dicha ubicación refleja el ELIN. En el transcurso de una llamada de emergencia, el ELIN se incluye con la ubicación enviada a la puerta de enlace ELIN, que identifica la llamada como una llamada de emergencia e intercambia el número del autor de la llamada por el ELIN. Después, la puerta de enlace ELIN enruta la llamada a la RTC con dicho ELIN como número de la llamada. El proveedor de servicios E9-1-1 de la RTC busca el ELIN en la base de datos ALI, que es la base de datos complementaria de la base de datos de Guía de calles maestra (MSAG). Así, la RTC envía la llamada al PSAP más adecuado según la búsqueda en ALI y, a su vez, el PSAP envía los primeros respondedores a la ubicación del autor de la llamada, también de acuerdo a la búsqueda en ALI. El número de la llamada se almacena en caché en la puerta de enlace ELIN durante el tiempo que se haya establecido para las devoluciones de llamada. Durante una devolución de llamada, el PSAP se comunica con la puerta de enlace ELIN, que intercambia el ELIN por el número de llamada directa a la extensión (DID) del autor de la llamada.

Las puertas de enlace ELIN admiten llamadas de emergencia únicamente desde dentro de la red de la organización; no admite llamadas externas.


> [!NOTE]
> Para obtener información detallada sobre cómo usar una conexión troncal SIP en las llamadas de emergencia, consulte <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Enrutamiento de llamadas E9-1-1 mediante un SIP troncal en Lync Server 2013</A>.



En el siguiente diagrama se ilustra el modo en que una llamada de emergencia se enruta desde Lync Server al PSAP cuando se usa una puerta de enlace ELIN.

**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**

![Enrutamiento de llamadas de ELIN](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "Enrutamiento de llamadas de ELIN")

1.  Una solicitud SIP INVITE que contiene la ubicación, el número de devolución de llamada del autor de la llamada y, opcionalmente, la dirección URL de notificación y el número de devolución de llamada de conferencia se enruta a Lync Server.

2.  Lync Server busca una coincidencia con el número de emergencia y, después, enruta la llamada (en función del valor de **Uso de RTC** que se haya definido en la directiva de ubicación vigente) a un Servidor de mediación y, desde ahí, a una puerta de enlace ELIN.

3.  La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.

4.  La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI.

5.  Si ha configurado la directiva de ubicación para que envíe notificaciones, se enviarán mensajes instantáneos de notificación de emergencia especiales de Lync a sus responsables de seguridad. Este mensaje siempre se muestra en la pantalla de los equipos de los responsables de seguridad y proporciona información sobre el nombre, el número de teléfono, la hora y la ubicación de la persona que realiza la llamada, lo que permite al personal de seguridad responder con rapidez a la persona que realiza la llamada de emergencia mediante un mensaje instantáneo o de voz.

6.  En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.

