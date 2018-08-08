---
title: Planeación de la experiencia de los usuarios de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Elija los equipos cliente aplicaciones, planeación de la calidad de extremo, ver recomendaciones para implementar los extremos de Wi-Fi y selección de dispositivos de audioconferencias.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e328f591ac97ace73b2cd2bb45aab61db75f064
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "19695353"
---
# <a name="plan-my-users-experience"></a>Planeación de la experiencia de mi los usuarios

En este artículo se proporciona una visión general de los requisitos para identificar correctamente los elementos de la implementación de servicios de voz en la nube que afectan directamente a la experiencia de los usuarios. Mediante la preparación de estos elementos antes de la implementación, tendrá más posibilidades de correctamente ofrecer una experiencia de alta calidad y confiable para los usuarios. 

## <a name="client-deployment"></a>Implementación del cliente

Microsoft Teams tiene clientes disponibles para escritorio, web (Windows y Mac) y mobile (Android, iOS y Windows Phone). Para obtener más información acerca de cómo se instalan el escritorio (Windows y Mac) y los clientes móviles, vea [obtener los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Actualizaciones de clientes

Uno de los beneficios clave de los equipos es que el cliente se mantiene actualizado automáticamente. Los clientes en el PC y Mac se actualizan mediante el uso de un proceso en segundo plano que comprueba para las versiones nuevas y descarga al nuevo cliente cuando la aplicación está inactiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planeación de la calidad de extremo

Tal y como se puede ver en el diagrama siguiente, los extremos son un bloque de creación importante en proporcionar una experiencia de calidad para los usuarios.

![Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en los extremos.] (media/plan-my-users-experience-image1.png "Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en los extremos.")

Los extremos de los equipos pueden ejecutar en muchos dispositivos, incluidos PCs, Mac, tabletas y dispositivos móviles. Parte de la experiencia no sólo abarca el dispositivo, pero cómo un usuario se conecta al dispositivo — por ejemplo, utilizando un auricular con micrófono optimizada, auriculares o micrófono o altavoz integrado del dispositivo. Uso de un auricular con micrófono optimizada puede enriquecer la experiencia global del usuario.

Las siguientes instrucciones acerca de cómo planear el extremo le ayudará a asegurarse de que su organización tiene una incorporación correcta de experiencia con los equipos.

## <a name="endpoint-capability"></a>Capacidad de extremo

Es la primera parte de la planeación para asegurarse de todos los equipos y otros dispositivos de la organización pueden ejecutar los equipos. Esto implica que no solo con mirar los requisitos de hardware, pero también descripción lo está haciendo el PC en segundo plano. Muchas organizaciones ejecutan otro software, incluidos los sistemas de detección de intrusiones y el software antimalware, que puede afectar al rendimiento de un dispositivo de base.

Para obtener información acerca de los requisitos de software para los equipos de los clientes en cada plataforma (mobile, de escritorio y web), vea [obtener los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Firewalls de extremo

Firewalls de cliente pueden tener un impacto significativo en la experiencia del usuario.
Firewalls de cliente pueden afectar a la calidad de las llamadas además de impedir una llamada desde el que se establezca. Configure las exclusiones adecuadas en el firewall de cliente según la información de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips). Su proveedor de terceros tendrá instrucciones específicas sobre cómo crear las exclusiones.

>[!NOTE]
> Microsoft Teams se actualizará automáticamente el Firewall de Windows con una configuración de firewall adecuados.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendaciones de Wi-Fi para extremos

Toma importante planear la implementación de una red Wi-Fi optimizada para admitir las cargas de trabajo en tiempo real en Microsoft Teams. En las secciones siguientes proporcionan algunas instrucciones generales que pueden ayudar a evitar los errores comunes al planear los extremos.

### <a name="wi-fi-drivers"></a>Controladores de Wi-Fi

Algunos controladores Wi-Fi pueden ser un inconveniente. Por ejemplo, un controlador podría tener muy agresivos comportamientos de movilidad entre puntos de acceso, lo que provoca que la calidad de llamada deficiente.
Esto no es un ejemplo típico, pero es importante para asegurarse de que se han actualizado y probarse antes de la implementación controladores Wi-Fi en su PC.

### <a name="wi-fi-bands"></a>Bandas Wi-Fi

Existen principalmente dos tipos de bandas utilizadas en Wi-Fi equipamiento hoy en día, 2,4 GHz y 5,0 GHz. Si su organización proporciona ambas bandas, debe configurar la configuración del controlador para prefiere la banda GHz 5.0. Esta banda es mucho más densa en términos de rendimiento y es menos afectados por la interferencia que se puede apreciar en la banda de 2,4 GHz.
Esta recomendación se da por supuesto que ha optimizado correctamente la banda de red GHz 5.0.

### <a name="wi-fi-radio-type"></a>Tipo de radio Wi-Fi

Planeación de dispositivos que admiten los tipos de radio Wi-Fi más reciente. Puede obtener un rendimiento muy bueno Wi-Fi si se aprovecha la 802.11ac o posterior en los dispositivos que aprovisiona.

### <a name="wireless-avoidance"></a>Prevención de inalámbrica

Algunas organizaciones prefieren evitar por completo la Wi-Fi. En ocasiones, esta guía se proporciona a través de una recomendación a los usuarios conectarse directamente a una red por cable. En algunos casos, el orden de enlace de red podría tener la conexión inalámbrica preferida y seguir usando esa conexión, aunque el equipo esté conectado a la conexión por cable. Para evitar este comportamiento imprevisto, configure el orden de enlace para evitar este escenario.

### <a name="80211-power-save-protocol"></a>802.11 Protocolo de ahorro de energía

Si su organización utiliza puntos de acceso inalámbrico o los enrutadores que no son compatibles con el protocolo de ahorro de energía 802.11, es posible que experimente llamadas interrumpidas o calidad de llamadas deficientes en Teams Microsoft que se ejecutan en los dispositivos de Windows. Si no es posible actualizar el punto de acceso inalámbrico o los enrutadores, deberá actualizar la configuración del Plan de energía de Windows en los dispositivos que se ejecutan en energía de la batería. Se proporcionan instrucciones de detalle y la configuración adicional en el siguiente [artículo de soporte técnico](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>¿Qué clientes de los equipos se implementará en su organización?</li><li>¿Cómo inicialmente implementará los clientes de los equipos a los usuarios?</li><li>¿Quién es responsable de evaluar los extremos y dispositivos para validar cumplen los requisitos de los equipos para una experiencia de calidad?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar el proceso que se va a seguir para implementar a los clientes de los equipos.</li><li>Evaluación de los extremos y dispositivos y llevar a cabo y corrección necesarios.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos de los equipos

Microsoft Teams se puede usar para las reuniones o como un sistema telefónico. Al usar estas características, el dispositivo de interfaz que se usa para los equipos desempeña un papel importante en la experiencia del usuario.

Es posible que sonido aceptable para el usuario que tiene que la configuración con un altavoz de PC y un micrófono integrado. Normalmente, pero esos dispositivos no están optimizados para la cancelación de ruido, y cualquier tipo de ruido ambiente puede tener un impacto dirección descendente en otros en la llamada. Aprovechamiento de dispositivos optimizados para estos escenarios le ayudará a garantizar una experiencia de alta calidad.

Cada dispositivo necesita satisfacer las necesidades de los usuarios. Debe adaptar los dispositivos como los auriculares con micrófono para las diferentes personas y casos de uso en su organización.
Un ejercicio de asignación de rol para el dispositivo debe realizarse como parte del proceso de planeación.

Después de seleccionar los dispositivos, incluir en el plan de pruebas piloto para la validación final. Aproveche encuestas durante la prueba piloto a recopilar comentarios para asegurarse de la estrategia de dispositivo es óptimo.

> [!NOTE]
> En este momento, se recomienda usar dispositivos de audio que se han certificado a través de la Skype para el programa de certificación empresarial. Para buscar dispositivos certificados bajo este programa, consulte el catálogo de soluciones [Certificadas de dispositivos USB de Skype para la empresa](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decida en estrategia de dispositivo general de su organización para el usuario y experiencias de sala de la reunión.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Completar un ejercicio de asignación de rol para el dispositivo para su organización.</li><li>Documentar el proceso de obtención de dispositivos para los usuarios y las salas de reuniones.</li><li>Documentar el proceso de implementación y configuración de dispositivos para los usuarios y las salas de reuniones.</li><li>Adquirir dispositivos iniciales para comenzar la implementación.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->