---
title: Planificar la experiencia de usuario de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Elija los equipos cliente aplicaciones, planeación de la calidad de extremo, ver recomendaciones para implementar los extremos de Wi-Fi y selección de dispositivos de audioconferencias.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: abef4c9e1096396d7844002ebda38a32876b403b
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400975"
---
# <a name="plan-my-users-experience"></a>Planeación de la experiencia de mi los usuarios

En este artículo se proporciona una visión general de los requisitos para identificar correctamente los elementos de la implementación de servicios de voz en la nube que afectan directamente a la experiencia de los usuarios. Mediante la preparación de estos elementos antes de la implementación, tendrá más posibilidades de correctamente ofrecer una experiencia de alta calidad y confiable para los usuarios. 

## <a name="client-deployment"></a>Implementación del cliente

Microsoft Teams tiene clientes disponibles para escritorio, web (Windows y Mac) y mobile (Android y iOS). Para obtener más información acerca de cómo se instalan el escritorio (Windows y Mac) y los clientes móviles, vea [obtener los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Actualizaciones del cliente

Uno de los beneficios clave de los equipos es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Plan para la calidad de los puntos de conexión

Tal y como se puede ver en el diagrama siguiente, los extremos son un bloque de creación importante en proporcionar una experiencia de calidad para los usuarios.

![Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en los extremos.] (media/plan-my-users-experience-image1.png "Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en los extremos.")

Los extremos de los equipos pueden ejecutar en muchos dispositivos, incluidos PCs, Mac, tabletas y dispositivos móviles. Parte de la experiencia no sólo abarca el dispositivo, pero cómo un usuario se conecta al dispositivo — por ejemplo, utilizando un auricular con micrófono optimizada, auriculares o micrófono o altavoz integrado del dispositivo. El uso de un auricular con micrófono optimizado, se puede enriquecer la experiencia general del usuario.

Las siguientes directrices sobre la planificación de los puntos de conexión le ayudarán a garantizar que su organización tenga una experiencia de incorporación con Teams correcta.

## <a name="endpoint-capability"></a>Funcionalidad de puntos de conexión

Es la primera parte de la planeación para asegurarse de todos los equipos y otros dispositivos de la organización pueden ejecutar los equipos. Esto no solo implica comprobar los requisitos de hardware, sino también conocer qué más hace el PC en segundo plano. Muchas organizaciones ejecutan otro software, incluidos sistemas de detección de intrusiones y software antimalware, que puede afectar al rendimiento básico de un dispositivo.

Para obtener información acerca de los requisitos de software para los equipos de los clientes en cada plataforma (mobile, de escritorio y web), vea [obtener los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario.
Los firewalls del cliente pueden afectar a la calidad de las llamadas, además de impedir que la llamada se establezca. Configure las exclusiones apropiadas en el firewall del cliente según la información que aparece en [URL de Office 365 e intervalos de direcciones IP](https://aka.ms/o365ips). Su proveedor de terceros debe tener instrucciones específicas para saber cómo se crean las exclusiones.

>[!NOTE]
> Microsoft Teams actualizará automáticamente el firewall de Windows con una configuración de firewall adecuada.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendaciones de Wi-Fi para puntos de conexión

Toma importante planear la implementación de una red Wi-Fi optimizada para admitir las cargas de trabajo en tiempo real en Microsoft Teams. En las secciones siguientes proporcionan algunas instrucciones generales que pueden ayudar a evitar los errores comunes al planear los extremos.

### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Algunos controladores Wi-Fi pueden ser un inconveniente. Como ejemplo, un controlador puede tener comportamientos de itinerancia muy agresivos entre los puntos de acceso dando lugar a una mala calidad en las llamadas.
Esto no es un ejemplo típico, pero es importante para asegurarse de que se han actualizado y probarse antes de la implementación controladores Wi-Fi en su PC.

### <a name="wi-fi-bands"></a>Bandas Wi-Fi

Existen principalmente dos tipos de bandas que se utilizan en los equipos Wi-Fi de hoy en día: 2,4 GHz y 5 GHz. Si su organización proporciona ambas bandas, debe configurar el controlador para que dé prioridad a la banda de 5 GHz. Esta banda es mucho más densa en términos de rendimiento y le afectan menos las interferencias que se aprecian en la banda de 2,4 GHz.
Esta recomendación da por hecho que ha optimizado correctamente la banda de red de 5 GHz.

### <a name="wi-fi-radio-type"></a>Tipo de radio Wi-Fi

Planifique los dispositivos que admiten los tipos de radio Wi-Fi más recientes. Se puede obtener un rendimiento de Wi-Fi muy bueno si aprovecha 802.11ac o más recientes en los dispositivos que aprovisiona.

### <a name="wireless-avoidance"></a>Elusión de redes inalámbricas

Algunas organizaciones prefieren evitar las redes Wi-Fi en general. En ocasiones, esta guía se ofrece a través de una recomendación a los usuarios para que se conecten directamente a una red de cable. En algunos casos, la orden de enlace de red podría preferir la conexión inalámbrica y seguir usando esa conexión incluso cuando el PC está conectado a la conexión de cable. Para evitar este comportamiento no intencionado, configure la orden de enlace para que esta situación no se produzca.

### <a name="80211-power-save-protocol"></a>802.11 Protocolo de ahorro de energía

Si su organización utiliza puntos de acceso inalámbrico o los enrutadores que no son compatibles con el protocolo de ahorro de energía 802.11, es posible que experimente llamadas interrumpidas o calidad de llamadas deficientes en Teams Microsoft que se ejecutan en los dispositivos de Windows. Si no es posible actualizar su enrutador o su punto de acceso inalámbrico, debe actualizar la configuración del Plan de energía de Windows en los dispositivos que se ejecutan con ahorro de energía. Podrá encontrar más detalles e instrucciones de configuración en el siguiente [artículo de soporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>¿Qué clientes de los equipos se implementará en su organización?</li><li>¿Cómo inicialmente implementará los clientes de los equipos a los usuarios?</li><li>¿Quién es responsable de evaluar los extremos y dispositivos para validar cumplen los requisitos de los equipos para una experiencia de calidad?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Documentar el proceso que se va a seguir para implementar a los clientes de los equipos.</li><li>Evaluación de los extremos y dispositivos y llevar a cabo y corrección necesarios.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos para Teams

Microsoft Teams se puede usar para reuniones o como un sistema telefónico. Cuando se usan estas características, el dispositivo de interfaz que se utiliza para Teams tiene un papel fundamental en la experiencia de usuario.

Con un micrófono o altavoz de PC integrado, el sonido podría ser correcto para el usuario que tenga esa configuración. Normalmente, pero esos dispositivos no están optimizados para la cancelación de ruido, y cualquier tipo de ruido ambiente puede tener un impacto dirección descendente en otros en la llamada. Si se utilizan dispositivos optimizados para estos escenarios, se podrá garantizar una experiencia de gran calidad.

Cada dispositivo tiene que cumplir las necesidades de sus usuarios. Tendrá que adaptar dispositivos, como auriculares con micrófono, para distintas personas y casos prácticos de su organización.
Habría que completar un ejercicio de asignación de persona a dispositivo como parte del proceso de planificación.

Una vez que se seleccionen los dispositivos, se deben incluir en el plan de prueba piloto para su validación final. Utilice encuestas durante el piloto para recopilar comentarios con los que se pueda garantizar que su estrategia de dispositivo sea la adecuada.

> [!NOTE]
> En este momento, recomendamos usar dispositivos de audio que se hayan certificado mediante el programa de certificación de Skype Empresarial. Para buscar dispositivos certificados bajo este programa, consulte el catálogo de soluciones [Certificadas de dispositivos USB de Skype para la empresa](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>Decida en estrategia de dispositivo general de su organización para el usuario y experiencias de sala de la reunión.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Completar un ejercicio de asignación de rol para el dispositivo para su organización.</li><li>Documentar el proceso de obtención de dispositivos para los usuarios y las salas de reuniones.</li><li>Documentar el proceso de implementación y configuración de dispositivos para los usuarios y las salas de reuniones.</li><li>Adquirir dispositivos iniciales para comenzar la implementación.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->