---
title: 'Lync Server 2013: Características y funcionalidad de movilidad'
TOCTitle: Características y funcionalidad de movilidad
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48274490
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Características y funcionalidad de movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

La característica de movilidad incorporada en las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 admite la funcionalidad de clientes móviles de Lync 2010 Mobile y Lync 2013. Al implementar el servicio de movilidad de Lync Server 2013, los usuarios pueden usar dispositivos móviles admitidos de Apple iOS, Android, Windows Phone o Nokia Symbian para realizar ciertas actividades, como enviar y recibir mensajes instantáneos, ver contactos y ver el estado de presencia. Asimismo, los dispositivos móviles admiten algunas características de Telefonía IP empresarial, como hacer clic para unirse a una conferencia, Vía trabajo, conexión con un solo número, correo de voz y llamadas perdidas. Las características nuevas incorporadas en las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 incluyen la funcionalidad de voz sobre IP (VoIP) y vídeo (H.264) para los asistentes de la reunión.

La característica de movilidad incorporada en las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 admite la funcionalidad de clientes móviles de Lync 2013. Las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 instalan la API web de comunicaciones unificadas, o UCWA. UCWA es el componente que se usa para los clientes móviles de Lync 2013. En Lync Server 2013, se usa Mcx para los clientes de Lync 2010 Mobile. Las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 incorporan UCWA como el nuevo punto de entrada de los servicios de movilidad. Al mismo tiempo, Lync Server 2013 implementa el servicio de movilidad (Mcx), incorporado en las actualizaciones acumulativas de Lync Server 2010 de noviembre de 2011, y proporciona compatibilidad con Lync 2010 Mobile. Al implementar las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013, los usuarios pueden usar dispositivos móviles admitidos de Apple iOS, Android y Windows Phone para realizar ciertas actividades, como las siguientes:

> [!IMPORTANT]  
> Las características admitidas por el servicio de movilidad de las actualizaciones acumulativas de Lync Server 2010 de noviembre de 2011 se marcan con &quot;(Mcx)&quot;. Todas las características de la lista son compatibles con UCWA, incorporado en las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013.



  - Enviar y recibir mensajes instantáneos (Mcx)

  - Ver presencia (Mcx)

  - Ver contactos (Mcx)

  - Hacer clic para unirse a una conferencia (Mcx)

  - Vía trabajo (Mcx)

  - Conexión con un solo número (Mcx)

  - Correo de voz (Mcx)

  - Notificación de llamada perdida (Mcx)

  - Voz sobre IP (VoIP)

  - Vídeo para asistentes (H.264)


> [!NOTE]
> Lync 2010 Mobile proporcionaba un cliente para dispositivos de Nokia Symbian. Lync 2013 Mobile no tendrá un cliente para los dispositivos basados en Nokia Symbian.



Los usuarios de iPad de Apple tendrán acceso a funcionalidades mejoradas. Tras unirse a una reunión mediante la devolución de llamada de audio, los usuarios de iPad podrán ver las presentaciones de Microsoft PowerPoint cargadas durante una reunión, compartir aplicaciones y escritorios, ver la lista de participantes de la reunión y recibir notificaciones de otros tipos de contenidos que se estén compartiendo en la reunión.

> [!TIP]  
> Mediante la conexión con un solo número, los usuarios reciben las llamadas que se marcaron a su número de trabajo en un teléfono móvil. Mediante Vía trabajo, el usuario realiza una llamada saliente desde el cliente de Lync Mobile usando un número de teléfono del trabajo en lugar de su número de teléfono móvil. Con la aceptación de llamada, el cliente envía una solicitud a Mcx o UCWA (en función de la versión de Lync Mobile) para que realice la llamada en su nombre. El servidor inicia la llamada y, a continuación, devuelve la llamada al usuario en el teléfono móvil. Cuando el usuario responde, el servidor completa la llamada marcando el número de la otra parte. Mediante Vía trabajo, los usuarios pueden mantener su identidad de trabajo durante una llamada, lo que significa que el destinatario de la llamada no ve el número de teléfono móvil del autor de la llamada y este último evita incurrir en cargos de llamadas salientes.




> [!NOTE]
> No todas las características funcionan exactamente igual en todos los dispositivos móviles. Para obtener información detallada sobre las características admitidas en dispositivos móviles, vea las tablas de comparación de clientes móviles en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=234777">http://go.microsoft.com/fwlink/?linkid=234777</A>. Para obtener información detallada sobre los dispositivos y sistemas operativos admitidos, vea los temas de requisitos en <A href="lync-server-2013-planning-for-mobile-clients.md">Planeación de clientes móviles</A>.



Al usar la característica de Detección automática de Lync Server 2013, las aplicaciones móviles pueden localizar automáticamente los servicios web de Lync Server 2013 sin necesidad de que los usuarios deban escribir manualmente las direcciones URL en la configuración de su dispositivo. También se admite la escritura manual de direcciones URL en la configuración de dispositivos móviles, principalmente con el fin de solucionar problemas.

> [!IMPORTANT]  
> Mcx y UCWA son servicios complementarios y ambos se implementan para admitir clientes móviles de Lync 2010 Mobile y Lync 2013. Lync 2013 Mobile no podrá iniciar sesión en implementaciones de Lync Server 2010. Lync 2010 Mobile y Lync 2013 Mobile podrán usar una implementación de Lync Server 2013 con las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 aplicadas.



La característica de movilidad también admite *notificaciones de inserción* para los dispositivos móviles que no admiten aplicaciones que se ejecutan en segundo plano. Una notificación de inserción es una notificación que se envía a un dispositivo móvil sobre un evento que ocurre cuando una aplicación móvil está inactiva. Por ejemplo, una invitación de mensajería instantánea perdida puede dar lugar a una notificación de inserción.

En Lync Server 2013 se proporcionan Mcx, UCWA, el servicio Detección automática y compatibilidad con las notificaciones de inserción. En las actualizaciones acumulativas de Lync Server 2013 de febrero de 2013 se incorporan funcionalidades y características de cliente actualizadas y el uso de UCWA como punto de entrada de la movilidad.

