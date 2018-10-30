---
title: 'Lync Server 2013: Características de la mensajería unificada integrada'
TOCTitle: Características de la mensajería unificada integrada y Lync Server 2013
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48274368
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Características de la mensajería unificada integrada y Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Lync Server 2013, Telefonía IP empresarial usa la infraestructura de Mensajería unificada de Exchange (UM) para proporcionar los servicios de contestador automático, acceso de voz (incluido el correo de voz) y operador automático.

## Contestador automático

El contestador automático recibe mensajes de voz en nombre de los usuarios cuyas llamadas no responden o no están disponibles. Reproduce un saludo personal, permite grabar un mensaje y envía el mensaje con el fin de ponerlo en la cola para la entrega en el buzón del usuario, que se almacena en el servidor de Buzón de correo de Exchange.

Si el autor de la llamada deja un mensaje, el mensaje se trasfiere a la bandeja de entrada del usuario. Si decide no dejar un mensaje, se almacena una notificación de llamada perdida en el buzón del usuario. Los usuarios pueden acceder a sus bandejas de entrada mediante el cliente de mensajería y colaboración de Microsoft Outlook, Outlook Web Access, la tecnología Exchange ActiveSync o Outlook Voice Access. Se pueden mostrar el asunto y la prioridad de las llamadas de manera similar al correo electrónico.

## Outlook Voice Access

Outlook Voice Access permite a un usuario de Telefonía IP empresarial tener acceso no solo al correo de voz, sino también a la bandeja de entrada de Exchange, incluidos el correo electrónico, el calendario y los contactos de una interfaz de telefonía. El número de acceso de suscriptor lo asigna un administrador de Mensajería unificada de Exchange.

## Operador automático

Un operador automático es una característica de Mensajería unificada de Exchange que se puede usar para configurar un número de teléfono que los usuarios externos pueden marcar para localizar a representantes de la compañía. Concretamente, proporciona una serie de indicadores de voz que ayudan al autor de una llamada externa a usar un sistema de menús. La lista de opciones disponibles la configura el administrador de Mensajería unificada de Exchange en el servidor de Mensajería unificada de Exchange.

## Servicios de fax

Mensajería unificada de Exchange incluye características de fax, que permiten a los usuarios recibir faxes en sus buzones de Exchange. Para obtener más información, consulte "Mensajería unificada" en la documentación de Microsoft Exchange Server en [http://go.microsoft.com/fwlink/?linkid=135652\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=135652%26clcid=0xc0a).


> [!NOTE]
> Los servicios de fax que proporciona el servidor de mensajería unificada de Exchange no se encuentran disponibles en las implementaciones de Lync Server integradas con Microsoft Exchange Server 2010 o Exchange 2010 con el último service pack o Exchange 2013.


