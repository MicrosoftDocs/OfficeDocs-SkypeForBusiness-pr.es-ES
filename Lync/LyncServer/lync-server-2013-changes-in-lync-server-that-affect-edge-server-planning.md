---
title: "Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral"
TOCTitle: Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48275494
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambios en Lync Server 2013 que afectan a la planificación del servidor perimetral

 

_**Última modificación del tema:** 2012-10-22_

Lync Server 2013 incluye nuevas características que amplían las características y los métodos de comunicación de los usuarios. Además, Lync Server 2013 presenta cambios en los servicios existentes para integrar y ampliar de mejor forma los servicios que están disponibles para la organización. A continuación figura un resumen de los cambios que pueden afectar a la planeación e implementación de servicios del Servidor perimetral de Lync Server 2013.

## Compatibilidad con direcciones IPv6

Lync Server 2013 admite direcciones IPv6 para todos los servicios del Servidor perimetral. Si ha proporcionado direcciones IPv6 para las interfaces a través de la configuración de Windows Server, puede usarlas en la configuración del Servidor perimetral a través de la configuración de dirección IP en la Generador de topologías. Además, el protocolo extensible de mensajería y presencia (XMPP) es compatible con IPv6. No es necesaria ninguna configuración más. XMPP usará IPv6 (cuando sea necesario) si IPv6 está configurado en la topología.

Un requisito extra que comporta la compatibilidad con IPv6 en Lync Server 2013 es que se deben crear registros del Sistema de nombres de dominio correspondientes a los registros que se deben detectar y resolver en una dirección IPv6. DNS IPv6 usa registros de host definidos como **AAAA** que se denominan de “cuádruple A”. Otros tipos de registro son coherentes con sus homólogos de IPv4.

## Compatibilidad para implementar el protocolo extensible de mensajería y presencia (XMPP)

El Servidor perimetral tiene un proxy XMPP totalmente integrado (implementado en los servidores perimetrales) y una puerta de enlace XMPP (implementada en los servidores front-end). Puede implementar la federación XMPP como un componente opcional. Si agrega y configura el proxy XMPP y la puerta de enlace XMPP, permitirá a los usuarios de Microsoft Lync 2013 agregar contactos de asociados basados en XMPP para mensajería instantánea y presencia.


> [!NOTE]
> Actualmente, los servicios de XMPP en el Servidor perimetral solo proporcionan mensajería instantánea y presencia entre los clientes de Lync Server y los contactos basados en XMPP. Además, XMPP está hospedado en un único sitio.



> [!IMPORTANT]  
> La capacidad XMPP de Lync Server 2013 está probada y es compatible con Microsoft para la federación de mensajería instantánea con Google Talk. Para otros sistemas XMPP, póngase en contacto con el proveedor para comprobar que son compatibles con la federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.



## Compatibilidad para acumular certificados de autenticación de audio/vídeo y autenticación entre servidores

Un certificado sirve para generar tokens que se envían a los clientes y a otros usuarios del servicio de autenticación A/V y también se usan en la autenticación entre servidores. El certificado de autenticación de audio/vídeo es de tipo *AudioVideoAuthentication* , mientras que el de autenticación entre servidores es de tipo *OAuthTokenIssuer* .

En el caso de la autenticación de audio/vídeo, los tokens sirven para autenticar las solicitudes de asignación de puertos y se almacenan en la memoria caché durante un máximo de ocho horas (que es la duración predeterminada de un token). En condiciones de funcionamiento normales, se trata de un método muy fiable para crear y distribuir material de autenticación entre los usuarios de A/V. Sin embargo, los certificados tienen una duración limitada y expiran en una fecha y hora predefinidas, dependiendo de la fecha de creación y de las directivas que haya en vigor en la entidad de certificación que creó el certificado (suele ser dos años para este tipo de certificado). Cuando el certificado expire, los tokens que se hayan creado y que los usuarios hayan almacenado en caché pasarán a invalidarse. Si se intenta usar un token creado con un certificado expirado, se producirán errores en las asignaciones de transmisiones de medios y en las sesiones de audio/vídeo actualmente en curso. El cliente deberá adquirir un token nuevo creado por un certificado válido para que el audio y el vídeo vuelvan a funcionar con normalidad.

La autenticación entre servidores se administra por medio de un certificado global que se solicita y aplica a todos los servidores de la implementación. El certificado se encarga de autenticar servidores tanto en Lync Server 2013 como en Exchange 2013 y Microsoft SharePoint Server 2013. Para obtener más información sobre el funcionamiento de la autenticación entre servidores, consulte [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Una diferencia sustancial entre el proceso de autenticación de audio/vídeo y el proceso de autenticación entre servidores reside en la duración de la autenticación (o tokens). En la autenticación de audio/vídeo, la autenticación expira transcurridas ocho horas, mientras que en la autenticación entre servidores la duración es de 24 horas. La planeación que realice debe ser acorde al tipo de certificado que elija.

Una novedad en Lync Server 2013 es que se pueden almacenar provisionalmente certificados de reemplazo de autenticación de audio/vídeo y de autenticación entre servidores antes de que el certificado actual expire. El nuevo certificado se usa para generar nuevos tokens o nuevas solicitudes de autenticación, si bien el antiguo se conserva para comprobar las sesiones y autenticaciones actuales. Con esto, se consigue evitar eficazmente prácticamente cualquier error provocado por la expiración de un token o certificado. Para obtener información detallada sobre esta característica y cómo configurarla, consulte [Prueba de certificados de OAuth y audio y vídeo en Lync Server 2013 utilizando -Roll en Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

## Menor dependencia en la afinidad basada en cookies

En versiones anteriores de Lync Server y Office Communications Server, los servicios web usaban la afinidad basada en cookies para garantizar que se conservaba el estado de la sesión de cliente y servicios web. Los servicios web de Lync Server 2013 emplean un mecanismo de afinidad integrado que acaba con casi todos los requisitos de la afinidad basada en cookies.

> [!WARNING]  
> El cliente de Microsoft Lync 2010 Mobile deberá seguir usando y configurando la afinidad basada en cookies hasta que todos los clientes se hayan migrado al próximo cliente de Microsoft Lync Mobile (cuya fecha de lanzamiento aún está fijada).



Para obtener información detallada sobre la afinidad basada en cookies en Lync Server 2013, vea [Componentes necesarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

## Mejoras en la Detección automática

La característica Detección automática de Lync Server 2013 permite a los clientes encontrar más características que hay disponibles para comunicarse. Detección automática surgió en la actualización acumulada de Lync Server 2010 de noviembre de 2011 para movilidad y Microsoft Lync 2010 Mobile. Mediante esta característica (que también se conoce por sus nombres de registro DNS LyncDiscover y LyncDiscoverInternal), los clientes pueden encontrar y usar servicios de movilidad (para clientes de Microsoft Lync 2010 Mobile), Microsoft Lync Web App y el programador web de Lync, así como comunicaciones con Microsoft Exchange Server y SharePoint Server. Detección automática se instala como una parte más del proceso de instalación e implementación de la infraestructura de los servidores de Lync Server 2013. El Generador de topologías y el Asistente para la implementación de Lync Server ponen fin a la mayoría de las tareas de configuración que se precisaba en la actualización acumulada de Lync Server 2010 de noviembre de 2011.

## Servicios para clientes móviles

Los servicios móviles de Lync Server 2010 (que se incluyeron en la actualización acumulada de Lync Server 2013 de noviembre de 2011) permiten que los teléfonos móviles que ejecutan Lync Mobile y los dispositivos de tableta que usan dispositivos móviles Apple iOS, Android, Windows Phone o Nokia compatibles puedan realizar actividades como enviar y recibir mensajes instantáneos, ver contactos y ver la presencia. Además, los dispositivos móviles admiten algunas de las características de Telefonía IP empresarial, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y notificación de llamadas perdidas.


> [!NOTE]
> Los servicios de movilidad usan proxy inverso y los servicios publicados que se implementan en los servidores front-end. No se requieren cambios en los servidores perimetrales. Como mínimo, necesita SIP/TCP/5061 saliente del servidor perimetral de acceso de Lync Server.



## El rol de director es opcional

El rol del servidor Director en la topología de Lync Server 2013 no ha cambiado. Aún hospeda servicios web, autentica previamente las solicitudes de usuarios entrantes y dirige a los usuarios externos a su grupo de servidores principal. La intención de Microsoft al cambiar el Director de rol recomendado a rol opcional no es disminuir el valor del Director, sino reducir el número de servidores y otros requisitos de hardware (por ejemplo, los equilibradores de carga de hardware del Director), sin que ello afecte a las características y a la funcionalidad. Puesto que los Servidores front-end pueden hacer el mismo trabajo que el Director sin impacto alguno en los servicios proporcionados, puede implementar Directores de manera opcional si así lo decide. Puede excluir de manera segura el Director con la certeza de que los Servidores front-end prestarán los mismos servicios que el Director.

