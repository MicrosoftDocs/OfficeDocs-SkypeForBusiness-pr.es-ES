---
title: 'Lync Server 2013: Telefonía IP empresarial'
TOCTitle: Telefonía IP empresarial
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48276672
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Telefonía IP empresarial en Lync Server 2013

 

_**Última modificación del tema:** 2015-04-08_

Con la Telefonía IP empresarial, Lync Server aporta un protocolo de voz a través de IP (VoIP) independiente que ofrece una mejora o sustitución de los sistemas tradicionales de centrales de conmutación (PBX). Los usuarios de Telefonía IP empresarial pueden llamar a compañeros de la red de VoIP o PBX de la organización y pueden llamar a números de teléfono convencionales fuera de la organización. La solución Telefonía IP empresarial incluye características de llamada habituales como las de respuesta, desvío, transferencia, espera, liberación y estacionamiento, así como llamadas de 9-1-1 mejorado (E9-1-1) (E9-1-1 se encuentra disponible únicamente en los Estados Unidos de América). La Telefonía IP empresarial es también compatible con una amplia gama de dispositivos IP y USB modernos y antiguos.

## Enviar y recibir llamadas

Mediante Lync, los usuarios pueden realizar llamadas si escriben un nombre o número de teléfono en el teclado o si usan el panel de marcado que aparece en la pantalla. Asimismo, los usuarios pueden iniciar llamadas directamente desde su lista de contactos. También se pueden implementar dispositivos Lync Phone Edition, dispositivos telefónicos IP que proporcionan los socios de Microsoft.

Los usuarios pueden disponer de múltiples dispositivos telefónicos registrados con Lync Server y pueden cambiar de uno a otro de forma sencilla.

Los usuarios reciben una alerta en todos sus dispositivos de forma simultánea cuando se recibe una llamada, con tonos de llamada personalizables en los dispositivos telefónicos IP y una notificación similar de mensaje instantáneo en sus equipos.

Los usuarios también pueden establecer un único número de teléfono que conecta con su teléfono de escritorio, equipo y teléfono móvil, de forma que pueden responder allí donde estén.

## Características básicas de llamada

Mientras atiende una llamada, un usuario puede responder a llamadas entrantes adicionales o realizar llamadas y la llamada activa en esos momentos pasa a estar en espera de forma automática. Las llamadas se pueden transferir de un usuario a otro, bien de forma directa o después de que el primer usuario hable en privado con el segundo. Además, los usuarios pueden transferir llamadas a otro dispositivo; por ejemplo, podrían transferir una llamada activa a su teléfono móvil si necesitan salir de la oficina.

## Comunicaciones enriquecidas

Cuando se está hablando con otro usuario con Lync, los usuarios pueden agregar con facilidad texto, vídeo o uso compartido de escritorio a la llamada. La característica No molestar se integra con la configuración de presencia en Lync.

Con Mensajería unificada de Exchange (UM), Lync y Lync Server se integran con Microsoft Exchange Server 2013 y Microsoft Outlook 2013. Los usuarios pueden ver si tienen correos de voz nuevos tanto en la ventana de Lync como en el correo electrónico. Si están en el correo electrónico, pueden hacer clic en un mensaje de correo electrónico para reproducir el audio del correo de voz o ver una transcripción del mensaje del correo de voz.

## Características avanzadas de llamada

Telefonía IP empresarial incluye asimismo diversas características avanzadas de llamada, como la delegación, la llamada de equipo, la atención de llamadas grupales y los grupos de respuesta.

Con la delegación los usuarios delegan la administración de llamadas a uno o más asistentes. El delegado puede llevar a cabo múltiples tareas de llamada en nombre del usuario, lo cual incluye la selección de llamadas, envío de llamadas e inicio de conferencias.

Con las llamadas de equipo, un usuario puede hacer que las llamadas entrantes suenen en los teléfonos de sus compañeros de equipo al mismo tiempo, de forma que cualquiera de ellos pueda atenderla.

La atención a llamadas grupales, que es una característica nueva incorporada con las actualizaciones acumuladas para Lync Server 2013 de febrero de 2013, permite a los usuarios atender las llamadas entrantes de sus compañeros desde sus propios teléfonos. La diferencia primordial con las llamadas de equipo reside en que la llamada entrante suena únicamente en el teléfono del usuario al que vaya destinada, pero cualquier otro puede decidir atenderla marcando un número de grupo de atención de llamadas.

Los grupos de respuesta pueden establecer el envío a cola y enrutamiento inteligente de llamadas para agentes designados. Entre los usos habituales se incluyen la asistencia técnica de TI, línea directa a recursos humanos y otros centros de contacto internos.

## Administración de la Telefonía IP empresarial

Lync Server usa normas e interfaces publicadas para operar con la infraestructura existente. Admite las opciones de puerta de enlace y SIP (como la conexión basada en troncos SIP) para la interconexión a sistemas PBX IP y las redes RTC, de forma que se pueden migrar usuarios a Telefonía IP empresarial de forma continuada, a la vez que se minimiza el riesgo de interrupción. Lync Server es compatible con los códecs habituales como G.711, G.722 y G.723.1 para la interoperabilidad con soluciones de VoIP tradicionales.

Gracias al servicio de control de admisión de llamadas (CAC), los administradores pueden establecer límites en la cantidad de tráfico y vídeo de Lync Server que se transmite en vínculos restringidos de red y especificar la acción a emprender si una llamada excediera tal límite. Las acciones pueden incluir el enrutamiento hacia una ruta alternativa o rechazar la llamada.

Lync Server funciona con aplicaciones de sucursal con funciones de supervivencia de terceros para proporcionar servicios de llamada local y de conexión a RTC en sucursales en caso de fallo en la WAN del sitio central.

