---
title: Planificar la experiencia de usuario de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Elija aplicaciones cliente de Teams, planear la calidad del extremo, obtener recomendaciones para implementar puntos de conexión Wi-Fi y elegir dispositivos de audio.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f12b80fa1914166d48860b15cda7a928ca94ece
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069201"
---
# <a name="plan-my-users-experience"></a>Planear la experiencia de mis usuarios

Este artículo proporciona una descripción general de los requisitos para identificar correctamente los elementos de la implementación de los servicios de voz en la nube que afectan directamente a la experiencia de los usuarios. Al prepararse para estos elementos antes de la implementación, aumentará las posibilidades de ofrecer con éxito una experiencia de alta calidad y confiable para los usuarios. 

## <a name="client-deployment"></a>Implementación de cliente

Microsoft Teams tiene clientes disponibles para Web, equipos de escritorio (Windows y Mac) y teléfonos móviles (Android e iOS). Para obtener más información sobre cómo se instalan los clientes de escritorio (Windows y Mac) y móviles, vea [obtener clientes de Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Actualizaciones del cliente

Uno de los beneficios clave de Teams es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Plan para la calidad de los puntos de conexión

Como puede ver en el siguiente diagrama, los puntos de conexión son un importante bloque de creación para proporcionar una experiencia de calidad a los usuarios.

![Diagrama que describe los tres componentes de la calidad](media/plan-my-users-experience-image1.png "Diagrama que describe los tres componentes de la calidad y cómo se superpone la administración de servicios de los tres componentes. Centrado en los puntos de conexión.")

Los puntos de conexión de equipos se pueden ejecutar en muchos dispositivos, como equipos PC, Mac, tabletas y dispositivos móviles. Parte de la experiencia no abarca solo el dispositivo, sino que se conecta al dispositivo, por ejemplo, usando el micrófono/altavoz incorporado del dispositivo, Earbuds o un auricular con micrófono optimizado. El uso de un auricular con micrófono optimizado, se puede enriquecer la experiencia general del usuario.

Las siguientes directrices sobre la planificación de los puntos de conexión le ayudarán a garantizar que su organización tenga una experiencia de incorporación con Teams correcta.

## <a name="endpoint-capability"></a>Funcionalidad de puntos de conexión

La primera parte de la planificación es asegurarse de que todos los equipos y otros dispositivos de su organización puedan ejecutar Teams. Esto no solo implica comprobar los requisitos de hardware, sino también conocer qué más hace el PC en segundo plano. Muchas organizaciones ejecutan otro software, incluidos sistemas de detección de intrusiones y software antimalware, que puede afectar al rendimiento básico de un dispositivo.

Para obtener información sobre los requisitos de software para los clientes de Teams en cada plataforma (Web, escritorio y móvil), consulte [obtener clientes de Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario.
Los firewalls del cliente pueden afectar a la calidad de las llamadas, además de impedir que la llamada se establezca. Configure las exclusiones apropiadas en el firewall del cliente según la información que aparece en [URL de Office 365 e intervalos de direcciones IP](https://aka.ms/o365ips). Su proveedor de terceros debe tener instrucciones específicas para saber cómo se crean las exclusiones.

>[!NOTE]
> Microsoft Teams actualizará automáticamente el firewall de Windows con una configuración de firewall adecuada.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendaciones de Wi-Fi para puntos de conexión

La implementación de una red Wi-Fi optimizada para admitir cargas de trabajo en tiempo real en Microsoft Teams tiene una planificación significativa. En las siguientes secciones se ofrece una orientación general que puede ayudarle a evitar errores comunes al planear puntos de conexión.

### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Algunos controladores Wi-Fi pueden ser problemáticos. Como ejemplo, un controlador puede tener comportamientos de itinerancia muy agresivos entre los puntos de acceso dando lugar a una mala calidad en las llamadas.
Esto no suele ocurrir, pero es importante asegurarse de que los drivers Wi-Fi en el equipo se hayan actualizado y probado antes de la implementación.

### <a name="wi-fi-bands"></a>Bandas Wi-Fi

Existen principalmente dos tipos de bandas que se utilizan en los equipos Wi-Fi de hoy en día: 2,4 GHz y 5 GHz. Si su organización proporciona ambas bandas, debe configurar el controlador para que dé prioridad a la banda de 5 GHz. Esta banda es mucho más densa en términos de rendimiento y le afectan menos las interferencias que se aprecian en la banda de 2,4 GHz.
Esta recomendación da por hecho que ha optimizado correctamente la banda de red de 5 GHz.

### <a name="wi-fi-radio-type"></a>Tipo de radio Wi-Fi

Planifique los dispositivos que admiten los tipos de radio Wi-Fi más recientes. Se puede obtener un rendimiento de Wi-Fi muy bueno si aprovecha 802.11ac o más recientes en los dispositivos que aprovisiona.

### <a name="wireless-avoidance"></a>Elusión de redes inalámbricas

Algunas organizaciones prefieren evitar las redes Wi-Fi en general. En ocasiones, esta guía se ofrece a través de una recomendación a los usuarios para que se conecten directamente a una red de cable. En algunos casos, la orden de enlace de red podría preferir la conexión inalámbrica y seguir usando esa conexión incluso cuando el PC está conectado a la conexión de cable. Para evitar este comportamiento no intencionado, configure la orden de enlace para que esta situación no se produzca.

### <a name="80211-power-save-protocol"></a>802,11 de ahorro de energía

Si su organización usa puntos de acceso o routers inalámbricos que no admiten el protocolo de ahorro de energía 802,11, es posible que se produzcan llamadas o una mala calidad de llamada en Microsoft teams que se ejecuten en dispositivos Windows. Si no es posible actualizar su enrutador o su punto de acceso inalámbrico, debe actualizar la configuración del Plan de energía de Windows en los dispositivos que se ejecutan con ahorro de energía. Podrá encontrar más detalles e instrucciones de configuración en el siguiente [artículo de soporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Qué clientes de equipos se implementarán en la organización?</li><li>¿Cómo se implementarán inicialmente los clientes de Teams para los usuarios?</li><li>¿Quién es el responsable de evaluar los extremos y dispositivos para validar que cumplen con los requisitos de Teams para obtener una experiencia de calidad?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Siguientes pasos</td><td><ul><li>Documente el proceso que se va a seguir para implementar los clientes de Teams.</li><li>Evaluar los extremos y dispositivos, y realizar y corregir el requisito.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos para Teams

Microsoft Teams se puede usar para reuniones o como un sistema telefónico. Cuando se usan estas características, el dispositivo de interfaz que se utiliza para Teams tiene un papel fundamental en la experiencia de usuario.

Con un micrófono o altavoz de PC integrado, el sonido podría ser correcto para el usuario que tenga esa configuración. Pero generalmente esos dispositivos no están optimizados para la cancelación de ruidos, y cualquier tipo de ruido ambiental puede repercutir en otras personas en la llamada. Si se utilizan dispositivos optimizados para estos escenarios, se podrá garantizar una experiencia de gran calidad.

Cada dispositivo tiene que cumplir las necesidades de sus usuarios. Tendrá que adaptar dispositivos, como auriculares con micrófono, para distintas personas y casos prácticos de su organización.
Habría que completar un ejercicio de asignación de persona a dispositivo como parte del proceso de planificación.

Una vez que se seleccionen los dispositivos, se deben incluir en el plan de prueba piloto para su validación final. Utilice encuestas durante el piloto para recopilar comentarios con los que se pueda garantizar que su estrategia de dispositivo sea la adecuada.

> [!NOTE]
> En este momento, recomendamos usar dispositivos de audio que se hayan certificado mediante el programa de certificación de Skype Empresarial. Para buscar dispositivos certificados en este programa, consulte los dispositivos de [Microsoft Teams](https://products.office.com/en-us/microsoft-teams/across-devices/devices) y los [dispositivos de audio y vídeo USB](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices).



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decidir la estrategia general de dispositivos de su organización para experiencias de usuarios y salas de reuniones.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Siguientes pasos</td><td><ul><li>Complete un ejercicio de asignación entre dispositivos para su organización.</li><li>Documente el proceso de obtención de dispositivos para usuarios y salas de reuniones.</li><li>Documente el proceso de implementación y configuración de dispositivos para usuarios y salas de reuniones.</li><li>Adquirir dispositivos iniciales para comenzar la implementación.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
