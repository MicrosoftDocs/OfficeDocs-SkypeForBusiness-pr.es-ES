---
title: 'Lync Server 2013: Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Lync Server 2013 presenta nuevas características que amplían las características y los métodos de comunicación para los usuarios. Además, Lync Server 2013 introduce cambios en los servicios existentes para mejorar la integración y la ampliación de los servicios que están disponibles para su organización. A continuación se resume un resumen de los cambios que pueden afectar a la planificación y la implementación de los servicios del servidor perimetral 2013 de Lync Server.

<div>

## <a name="support-for-ipv6-addressing"></a>Compatibilidad con direcciones IPv6

Lync Server 2013 admite el direccionamiento IPv6 para todos los servicios de servidor perimetral. Si ha proporcionado direcciones IPv6 para las interfaces mediante la configuración de Windows Server, puede usar direcciones IPv6 en la configuración de su servidor perimetral a través de la configuración de dirección IP en el generador de topologías. Además, el protocolo de presencia y mensajería extensible (XMPP) admite IPv6. No se necesita ninguna configuración adicional. Si IPv6 está configurado en la topología, XMPP usará IPv6 (donde sea necesario).

Un requisito adicional para admitir IPv6 en Lync Server 2013 es crear registros del sistema de nombres de dominio para los registros que deben detectarse y resolverse en una dirección IPv6. IPv6 DNS usa registros de host que se definen como **AAAA** y se denomina "Quad-a". Otros tipos de registro son coherentes con sus homólogos IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Compatibilidad con la implementación de protocolo de presencia y mensajería extensible (XMPP)

Edge Server presenta un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP (implementada en los servidores front-end). Puede implementar la Federación XMPP como un componente opcional. Al agregar y configurar el proxy XMPP y la puerta de enlace XMPP, puede habilitar a los usuarios de Microsoft Lync 2013 para que agreguen contactos de socios basados en XMPP para la mensajería instantánea (mi) y la presencia.

<div>


> [!NOTE]  
> Por el momento, los servicios XMPP en el servidor perimetral solo proporcionan la mensajería instantánea y la presencia entre los clientes de Lync Server y los contactos basados en XMPP. Además, XMPP está hospedado en un solo sitio.



</div>

<div>


> [!IMPORTANT]  
> La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Compatibilidad con la autenticación de audio/vídeo y los certificados de autenticación de servidor a servidor

Un certificado se usa para generar tokens emitidos para clientes y otros consumidores del servicio de autenticación A/V y para la autenticación de servidor a servidor. El certificado de autenticación de audio y vídeo es de tipo *AudioVideoAuthentication* y el certificado de autenticación de servidor a servidor es de tipo *OAuthTokenIssuer*.

Para la autenticación de audio y vídeo, los tokens se usan para autenticar las solicitudes de asignación de puertos y los tokens se almacenan en la memoria caché durante un máximo de 8 horas, es decir, la duración predeterminada del token. Bajo el funcionamiento normal, este es un método muy confiable para crear y distribuir material de autenticación a los consumidores a/V. Sin embargo, los certificados tienen una duración finita y vencen en una fecha y hora predefinidas (según la fecha de creación y las directivas que se aplican en la entidad emisora de certificados que creó el certificado, normalmente 2 años para este tipo de certificado). Cuando el certificado expira, todos los tokens creados por el certificado expirado y almacenados en caché por consumidores no son válidos. Si los intentos de usar un token creado con un certificado caducado, se producía un error en las asignaciones de retransmisión multimedia y se producirá un error en las sesiones de audio o vídeo actuales. El cliente necesitaría adquirir un nuevo token creado por un certificado válido para reanudar la funcionalidad de audio y vídeo normal.

La autenticación de servidor a servidor se administra mediante un certificado global que se solicita y se aplica a todos los servidores de la implementación. El certificado es responsable de autenticar los servidores en Lync Server 2013, así como de autenticar a Exchange 2013 y Microsoft SharePoint Server 2013. Para obtener más información sobre cómo funciona la autenticación de servidor a servidor, vea [administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Una diferencia muy importante entre el proceso de autenticación de audio y vídeo y el proceso de autenticación de servidor a servidor es la duración de la autenticación o los tokens. Para la autenticación de audio y vídeo, la autenticación vence después de ocho horas. La autenticación de servidor a servidor tiene una duración de 24 horas. Debe planificar según corresponda para cada uno de los tipos de certificados.

Novedades de Lync Server 2013 es la capacidad de ensayar un certificado de autenticación de audio y vídeo de reemplazo y un certificado de autenticación de servidor a servidor antes de la fecha de expiración del certificado actual. El nuevo certificado se usa para generar nuevos tokens o solicitudes de autenticación nuevas. pero conserva el certificado antiguo para comprobar las sesiones actuales y las autenticaciones.. Lo que logra es evitar de forma eficaz casi todos los errores debido a la expiración de los tokens y los certificados. Para obtener más información sobre esta característica y cómo configurarla, consulte [almacenamiento provisional de certificados AV y OAuth en Lync Server 2013 usar-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Disminución de la dependencia de afinidad basada en cookies

En versiones anteriores de Lync Server y Office Communications Server, los servicios web usaban la afinidad basada en cookies para garantizar que se mantuvo el estado de la sesión de los servicios web y del cliente. Los servicios Web de Lync Server 2013 usan un mecanismo de afinidad integrado que elimina la mayoría de los requisitos de afinidad basada en cookies.

<div>


> [!WARNING]  
> El cliente móvil de Microsoft Lync 2010 aún debe usar afinidad basada en cookies y necesitará la configuración de la afinidad basada en cookies hasta que haya migrado todos los clientes al próximo cliente móvil de Microsoft Lync (fecha de lanzamiento no establecida aún).



</div>

Para obtener detalles sobre la afinidad basada en cookies en Lync Server 2013, vea [componentes necesarios para el acceso de usuarios externos en Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Mejoras de detección automática

La característica de detección automática de Lync Server 2013 permite a los clientes localizar características adicionales que estén disponibles para la comunicación. Detección automática se presentó por primera vez en la actualización acumulativa para Lync Server 2010:2011 de noviembre para movilidad y Microsoft Lync 2010 Mobile. La característica de detección automática (también conocida por los nombres de registros DNS LyncDiscover y LyncDiscoverInternal) permite a los clientes ubicar y usar los servicios de movilidad (para clientes móviles de Microsoft Lync 2010), Microsoft Lync Web App y Lync web Scheduler, así como comunicaciones con Microsoft Exchange Server y SharePoint Server. Detección automática se instala como parte normal de la configuración e implementación de su infraestructura y los servidores de Lync Server 2013. El generador de topología y el Asistente para la implementación de Lync Server eliminan la mayoría de las tareas de configuración que se requirieron en la actualización acumulativa para Lync Server 2010:2011 de noviembre.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Servicios para clientes móviles

Presentado en la actualización acumulativa para Lync Server 2010:2011 de noviembre, servicios de movilidad en Lync Server 2013 habilitar teléfonos móviles con dispositivos móviles y tabletas Lync compatibles con Apple iOS, Android, Windows Phone o dispositivos móviles Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver presencia. Además, los dispositivos móviles admiten algunas características de Enterprise Voice, como hacer clic para unirse a una conferencia, llamar a través del trabajo, acceso a un número único, correo de voz y notificación de llamada perdida.

<div>


> [!NOTE]  
> Los servicios de movilidad usan el proxy inverso y los servicios publicados que se implementan en los servidores front-end. No es necesario realizar cambios en los servidores perimetrales. En el servidor que ejecuta el servicio perimetral de acceso de Lync Server, lo mínimo que se necesita es SIP/TCP/5061from.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>El rol de director es opcional

La función del servidor Director en la topología de Lync Server 2013 no ha cambiado. Aún, hospeda servicios Web, preautentica las solicitudes de usuario entrantes y dirige a los usuarios externos a su grupo de servidores principales. Al cambiar el director de un rol recomendado a un rol opcional, Microsoft no pretende disminuir el valor del director. La intención es reducir el número de servidores y otros requisitos de hardware (por ejemplo, los equilibradores de carga de hardware del Director) sin comprometer las características ni la funcionalidad. Como los servidores de aplicaciones para el usuario pueden hacer el mismo trabajo que el director sin impacto alguno en los servicios proporcionados, puede implementar directores si así lo prefiere. Puede excluir sin riesgos al director con la confianza de que los servidores front-end proporcionarán los mismos servicios en lugar de un director.

</div>

</div>

<span> </span>

</div>

</div>

</div>

