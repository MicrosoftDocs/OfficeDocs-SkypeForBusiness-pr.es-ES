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
description: Elija las aplicaciones cliente de Teams, planee la calidad del extremo, obtenga recomendaciones para implementar Wi-Fi de conexión y elegir dispositivos de audio.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad827244baaacde8ee5c7166590c81347c8eea5b
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610025"
---
# <a name="plan-my-users-experience"></a>Planear la experiencia de mis usuarios

En este artículo se proporciona información general sobre los requisitos para identificar correctamente los elementos de la implementación de los servicios de voz en la nube que afectan directamente a la experiencia de los usuarios. Al preparar estos elementos antes de la implementación, aumentará sus posibilidades de proporcionar correctamente una experiencia confiable y de alta calidad para los usuarios. 

## <a name="client-deployment"></a>Implementación de cliente

Microsoft Teams tiene clientes disponibles para la web, el escritorio (Windows y Mac) y los dispositivos móviles (Android e iOS). Para obtener más información sobre cómo se instalan el escritorio (Windows y Mac) y los clientes móviles, consulte Obtener [clientes de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/get-clients)

## <a name="client-updates"></a>Actualizaciones del cliente

Una de las principales ventajas de Teams es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Plan para la calidad de los puntos de conexión

Como puede ver en el siguiente diagrama, los puntos de conexión son un bloque de creación importante para proporcionar una experiencia de calidad para los usuarios.

![Diagrama que describe los tres componentes de calidad](media/plan-my-users-experience-image1.png "Diagrama que describe los tres componentes de calidad y cómo la administración de servicios se superpone a los tres componentes. Con el foco en los puntos de conexión.")

Los puntos de conexión de Teams se pueden ejecutar en muchos dispositivos, incluidos PC, Mac, tabletas y dispositivos móviles. Parte de la experiencia no solo abarca el dispositivo, sino el modo en que el usuario se conecta al dispositivo (por ejemplo, con los auriculares o el micrófono/altavoz integrados del dispositivo o auriculares optimizados). El uso de un auricular con micrófono optimizado, se puede enriquecer la experiencia general del usuario.

Las siguientes directrices sobre la planificación de los puntos de conexión le ayudarán a garantizar que su organización tenga una experiencia de incorporación con Teams correcta.

## <a name="endpoint-capability"></a>Funcionalidad de puntos de conexión

La primera parte de la planificación es asegurarse de que todos los equipos y otros dispositivos de su organización puedan ejecutar Teams. Esto no solo implica comprobar los requisitos de hardware, sino también conocer qué más hace el PC en segundo plano. Muchas organizaciones ejecutan otro software, incluidos sistemas de detección de intrusiones y software antimalware, que puede afectar al rendimiento básico de un dispositivo.

Para obtener información sobre los requisitos de software para los clientes de Teams en cada plataforma (web, de escritorio y móvil), consulte Obtener [clientes de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/get-clients)

## <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario.
Los firewalls del cliente pueden afectar a la calidad de las llamadas, además de impedir que la llamada se establezca. Configure las exclusiones adecuadas en el firewall del cliente en función de la información de las direcciones URL de [Microsoft 365 u Office 365 e intervalos](https://aka.ms/o365ips)de direcciones IP. Su proveedor de terceros debe tener instrucciones específicas para saber cómo se crean las exclusiones.

>[!NOTE]
> Microsoft Teams actualizará automáticamente el firewall de Windows con una configuración de firewall adecuada.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendaciones de Wi-Fi para puntos de conexión

Se necesita una planeación significativa para implementar una red Wi-Fi trabajo optimizada para admitir cargas de trabajo en tiempo real en Microsoft Teams. En las secciones siguientes se proporcionan algunas directrices generales que pueden ayudarle a evitar problemas comunes al planear los puntos de conexión.

### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Algunos Wi-Fi controladores pueden ser problemáticos. Como ejemplo, un controlador puede tener comportamientos de itinerancia muy agresivos entre los puntos de acceso dando lugar a una mala calidad en las llamadas.
Esta no es una repetición común, pero es importante asegurarse de que los controladores de Wi-Fi del equipo se han actualizado y probado antes de la implementación.

### <a name="wi-fi-bands"></a>Bandas Wi-Fi

Existen principalmente dos tipos de bandas que se utilizan en los equipos Wi-Fi de hoy en día: 2,4 GHz y 5 GHz. Si su organización proporciona ambas bandas, debe configurar el controlador para que dé prioridad a la banda de 5 GHz. Esta banda es mucho más densa en términos de rendimiento y le afectan menos las interferencias que se aprecian en la banda de 2,4 GHz.
Esta recomendación da por hecho que ha optimizado correctamente la banda de red de 5 GHz.

### <a name="wi-fi-radio-type"></a>Tipo de radio Wi-Fi

Planifique los dispositivos que admiten los tipos de radio Wi-Fi más recientes. Se puede obtener un rendimiento de Wi-Fi muy bueno si aprovecha 802.11ac o más recientes en los dispositivos que aprovisiona.

### <a name="wireless-avoidance"></a>Elusión de redes inalámbricas

Algunas organizaciones prefieren evitar las redes Wi-Fi en general. En ocasiones, esta guía se ofrece a través de una recomendación a los usuarios para que se conecten directamente a una red de cable. En algunos casos, la orden de enlace de red podría preferir la conexión inalámbrica y seguir usando esa conexión incluso cuando el PC está conectado a la conexión de cable. Para evitar este comportamiento no intencionado, configure la orden de enlace para que esta situación no se produzca.

### <a name="80211-power-save-protocol"></a>802.11 Protocolo Power Save

Si su organización usa puntos de acceso inalámbricos o enrutadores que no son compatibles con el protocolo Power Save 802.11, es posible que experimente cortes en las llamadas o una mala calidad de las llamadas en Microsoft Teams cuando se ejecuta en dispositivos Windows. Si no es posible actualizar su enrutador o su punto de acceso inalámbrico, debe actualizar la configuración del Plan de energía de Windows en los dispositivos que se ejecutan con ahorro de energía. Podrá encontrar más detalles e instrucciones de configuración en el siguiente [artículo de soporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Qué clientes de Teams se implementarán en su organización?</li><li>¿Cómo implementará inicialmente los clientes de Teams a los usuarios?</li><li>¿Quién es responsable de evaluar los puntos de conexión y dispositivos para validar que cumplen los requisitos de Teams para obtener una experiencia de calidad?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Documente el proceso que se seguirá para implementar clientes de Teams.</li><li>Evaluar puntos de conexión y dispositivos, realizar y corregir los problemas necesarios.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos para Teams

Microsoft Teams se puede usar para reuniones o como un sistema telefónico. Cuando se usan estas características, el dispositivo de interfaz que se utiliza para Teams tiene un papel fundamental en la experiencia de usuario.

Con un micrófono o altavoz de PC integrado, el sonido podría ser correcto para el usuario que tenga esa configuración. Pero normalmente, esos dispositivos no están optimizados para la cancelación de ruido y cualquier tipo de ruido ambiente puede afectar a la baja a otros usuarios de la llamada. Si se utilizan dispositivos optimizados para estos escenarios, se podrá garantizar una experiencia de gran calidad.

Cada dispositivo tiene que cumplir las necesidades de sus usuarios. Tendrá que adaptar dispositivos, como auriculares con micrófono, para distintas personas y casos prácticos de su organización.
Habría que completar un ejercicio de asignación de persona a dispositivo como parte del proceso de planificación.

Una vez que se seleccionen los dispositivos, se deben incluir en el plan de prueba piloto para su validación final. Utilice encuestas durante el piloto para recopilar comentarios con los que se pueda garantizar que su estrategia de dispositivo sea la adecuada.

> [!NOTE]
> En este momento, recomendamos usar dispositivos de audio que se hayan certificado mediante el programa de certificación de Skype Empresarial. Para buscar dispositivos certificados en este programa, consulte los dispositivos [de Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices) y los dispositivos de audio y vídeo [USB.](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Decida la estrategia general del dispositivo de su organización para las experiencias de usuario y sala de reuniones.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Complete un ejercicio de asignación de rol a dispositivo para su organización.</li><li>Documente el proceso para obtener dispositivos para usuarios y salas de reuniones.</li><li>Documente el proceso de implementación y configuración de dispositivos para usuarios y salas de reuniones.</li><li>Adquirir dispositivos iniciales para comenzar la implementación.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
