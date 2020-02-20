---
title: 'Lync Server 2013: cambios en Lync Server que afectan a la planificación del servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be2944125e5338dcc9b90b54f19fac003ec07287
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Cambios en Lync Server 2013 que afectan a la planeación del servidor perimetral

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Lync Server 2013 presenta nuevas características que amplían las características y los métodos de comunicación para los usuarios. Además, Lync Server 2013 introduce cambios en los servicios existentes para una mejor integración y ampliación de los servicios que están disponibles para su organización. A continuación, se resumen los cambios que pueden afectar a la planeación y la implementación de los servicios del servidor perimetral de Lync Server 2013.

<div>

## <a name="support-for-ipv6-addressing"></a>Compatibilidad con direccionamiento IPv6

Lync Server 2013 admite direccionamiento IPv6 para todos los servicios del servidor perimetral. Si ha proporcionado direcciones IPv6 para las interfaces mediante la configuración de Windows Server, puede usar direcciones IPv6 en la configuración del servidor perimetral a través de la configuración de dirección IP en el generador de topologías. Además, el protocolo extensible de mensajería y presencia (XMPP) es compatible con IPv6. No es necesario realizar ninguna configuración adicional. Si IPv6 está configurado en la topología, XMPP usará IPv6 (donde sea necesario).

Un requisito agregado para admitir IPv6 en Lync Server 2013 es crear registros del sistema de nombres de dominio para los registros que deben detectarse y resolverse en una dirección IPv6. El DNS de IPv6 usa registros de host que se definen como **AAAA** y reciben el nombre de "Quad-a". Otros tipos de registros son coherentes con sus homólogos IPv4.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Compatibilidad con la implementación del protocolo extensible de mensajería y presencia (XMPP)

El servidor perimetral presenta un proxy XMPP completamente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP (implementada en los servidores front-end). Puede implementar la federación de XMPP como componente opcional. Al agregar y configurar el proxy XMPP y la puerta de enlace XMPP, puede habilitar a los usuarios de Microsoft Lync 2013 para que agreguen contactos de socios basados en XMPP para la mensajería instantánea (mi) y la presencia.

<div>


> [!NOTE]  
> Actualmente, los servicios XMPP en el servidor perimetral solo proporcionan la mensajería instantánea y la presencia entre clientes de Lync Server y contactos basados en XMPP. Además, XMPP se hospeda en un solo sitio.



</div>

<div>


> [!IMPORTANT]  
> La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk. Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Compatibilidad con la autenticación de audio y vídeo y los certificados de autenticación de servidor a servidor

Un certificado se usa para generar tokens que se emiten a los clientes y otros consumidores del servicio de autenticación A/V y para la autenticación de servidor a servidor. El certificado de autenticación de audio y vídeo es del tipo *AudioVideoAuthentication* y el certificado de autenticación de servidor a servidor es del tipo *OAuthTokenIssuer*.

Para la autenticación de audio y vídeo, los tokens se usan para autenticar solicitudes de asignación de puertos y los tokens se almacenan en la memoria caché durante un máximo de 8 horas, la duración predeterminada del token. En condiciones normales, se trata de un método muy fiable para crear y distribuir material de autenticación a los consumidores de A/V. Sin embargo, los certificados tienen una duración finita y expiran en una fecha y hora predefinidas (en función de la fecha de creación y las directivas que se aplican en la entidad de certificación que creó el certificado, normalmente 2 años para este tipo de certificado). Cuando el certificado expira, los tokens creados por el certificado expirado y almacenados en caché por los consumidores dejan de ser válidos. Si se intenta usar un token creado con un certificado expirado, se producirá un error en las asignaciones de retransmisión multimedia y se producirá un error en cualquier sesión de audio o vídeo actual. El cliente debe adquirir un nuevo token creado por un certificado válido para reanudar la funcionalidad de audio y vídeo normal.

La autenticación de servidor a servidor se administra mediante un certificado global que se solicita y se aplica a todos los servidores de la implementación. El certificado es responsable de autenticar los servidores en Lync Server 2013, así como de autenticarse en Exchange 2013 y en Microsoft SharePoint Server 2013. Para obtener más información sobre cómo funciona la autenticación de servidor a servidor, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Una diferencia muy importante entre el proceso de autenticación de audio y vídeo y el proceso de autenticación de servidor a servidor es la duración de la autenticación o los tokens. Para la autenticación de audio y vídeo, la autenticación expira después de ocho horas. La autenticación de servidor a servidor tiene una duración de 24 horas. Debe planear en consecuencia cada uno de los tipos de certificado.

Nueva para Lync Server 2013 es la capacidad de ensayar un certificado de autenticación de audio y vídeo de reemplazo y un certificado de autenticación de servidor a servidor antes de la fecha de expiración del certificado actual. A continuación, el nuevo certificado se usa para generar nuevos tokens o solicitudes de autenticación nuevas. pero conserva el certificado antiguo para comprobar las autenticaciones y las sesiones actuales. Esto es así para evitar de manera eficaz casi todos los errores debido a la expiración de los tokens y los certificados. Para obtener más información sobre esta característica y cómo configurarla, consulte staging de los [certificados AV y OAuth en Lync Server 2013 usando-Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Menor dependencia de la afinidad basada en cookies

En versiones anteriores de Lync Server y Office Communications Server, los servicios web usaban la afinidad basada en cookies para garantizar que se mantuvo el estado de sesión del cliente y de los servicios Web. Los servicios Web de Lync Server 2013 usan un mecanismo de afinidad integrado que elimina la mayoría de los requisitos para la afinidad basada en cookies.

<div>


> [!WARNING]  
> El cliente móvil de Microsoft Lync 2010 debe seguir usando la afinidad basada en cookies y necesitará la configuración de la afinidad basada en cookies hasta que haya migrado todos los clientes al próximo cliente móvil de Microsoft Lync (fecha de lanzamiento que aún no se ha determinado).



</div>

Para obtener información detallada acerca de la afinidad basada en cookies en Lync Server 2013, consulte [Components required for external User Access in Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Mejoras de detección automática

La característica detección automática de Lync Server 2013 permite a los clientes buscar características adicionales que están disponibles para la comunicación. Detección automática se introdujo por primera vez en la actualización acumulativa de Lync Server 2010:2011 de noviembre de para movilidad y Microsoft Lync 2010 Mobile. La característica de detección automática (también conocida por los nombres de registro DNS LyncDiscover y LyncDiscoverInternal) permite a los clientes localizar y usar los servicios de movilidad (para clientes móviles de Microsoft Lync 2010), Microsoft Lync Web App y el programador web de Lync, así como comunicaciones con Microsoft Exchange Server y SharePoint Server. Detección automática se instala como parte normal de la instalación y la implementación de la infraestructura y de los servidores de Lync Server 2013. El generador de topologías y el Asistente para la implementación de Lync Server eliminan la mayoría de las tareas de configuración necesarias en la actualización acumulativa para Lync Server 2010:2011 de noviembre de.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Servicios para clientes móviles

Se incorporó en la actualización acumulativa de Lync Server 2010:2011 de noviembre de Mobility Services en Lync Server 2013 habilitar teléfonos móviles que ejecuten dispositivos móviles de Lync y tabletas que usen dispositivos móviles compatibles con Apple iOS, Android, Windows Phone o Nokia para realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver presencia. Además, los dispositivos móviles admiten algunas características de Telefonía IP empresarial como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y notificación de llamadas perdidas.

<div>


> [!NOTE]  
> Los servicios de movilidad usan el proxy inverso y los servicios publicados que se implementan en los servidores front-end. No es necesario realizar cambios en los servidores perimetrales. Como mínimo, el servidor que ejecuta el servicio perimetral de acceso de Lync Server debe tener el SIP/TCP/5061from saliente.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>El rol de director es opcional

El rol del servidor Director en la topología de Lync Server 2013 no ha cambiado. Sigue hospedando servicios Web, realiza la autenticación previa de las solicitudes de usuario entrantes y dirige a los usuarios externos a su grupo de servidores principal. Al cambiar el director de un rol recomendado a un rol opcional, Microsoft no pretende disminuir el valor del director. La intención es reducir el número de servidores y otros requisitos de hardware (por ejemplo, equilibradores de carga de hardware para el director) sin poner en peligro las características y la funcionalidad. Como los servidores front-end pueden realizar el mismo trabajo que el director sin afectar a los servicios proporcionados, puede implementar directores si lo prefiere. Puede excluir con seguridad el director con confianza de que los servidores front-end proporcionarán los mismos servicios en vez de un director.

</div>

</div>

<span> </span>

</div>

</div>

</div>

