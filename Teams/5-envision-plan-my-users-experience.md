---
title: Planear la experiencia de los usuarios de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Elija las aplicaciones de cliente de los equipos, planear la calidad de extremo, Obtén recomendaciones para implementar los extremos de la Wi-Fi y elegir dispositivos de audio.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 866395a4dd58016c0989ec4b34f602877251d021
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="plan-my-users-experience"></a>Planear la experiencia de los usuarios

Este artículo ofrece una visión general de los requisitos para identificar correctamente los elementos de la implementación de servicios de voz de nube que afectan directamente a la experiencia de los usuarios. Mediante la preparación de estos elementos antes de su implementación, tendrá más posibilidades de ofrecer exitosamente una experiencia confiable de alta calidad para los usuarios. 

## <a name="client-deployment"></a>Implementación de clientes

Teams Microsoft tiene disponible para escritorio, web de clientes (Windows y Mac) y mobile (Windows Phone, iOS y Android). Para obtener más información acerca de cómo se instalan los clientes móviles y escritorio (Windows y Mac), consulte [obtener los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Actualizaciones de cliente

Una de las ventajas clave de los equipos es que el cliente se mantiene actualizado automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso de segundo plano que comprueba si hay nuevas compilaciones y descarga al nuevo cliente cuando la aplicación está inactiva.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planear la calidad de extremo

Como se puede ver en el diagrama siguiente, los extremos son un pilar importante en proporcionar una experiencia de calidad para los usuarios.

![Se describen los tres componentes de calidad y la administración del servicio superpone a todos los tres componentes del diagrama. Con un enfoque en extremos.] (media/plan-my-users-experience-image1.png "Se describen los tres componentes de calidad y la administración del servicio superpone a todos los tres componentes del diagrama. Con un enfoque en extremos.")

Extremos de equipos pueden ejecutarse en muchos dispositivos, incluidos PCs, Mac, tabletas y dispositivos móviles. Parte de la experiencia no sólo incluye el dispositivo, pero ¿cómo un usuario se conecta al dispositivo, por ejemplo, utilizando un auricular optimizado, auriculares o micrófono y altavoz incorporado del dispositivo. Utilizar un auricular optimizado puede enriquecer la experiencia general del usuario.

La siguiente orientación acerca de cómo planear el extremo le ayudará a asegurarse de que su organización tiene una incorporación exitosa experiencia con los equipos.

## <a name="endpoint-capability"></a>Capacidad de extremo

Es la primera parte de la planificación asegurar los equipos y otros dispositivos de la organización pueden ejecutar en los equipos. Esto implica no sólo mirar los requisitos de hardware, pero también comprender lo que hace el PC en segundo plano. Muchas organizaciones ejecutan otro software, incluidos los sistemas de detección de intrusiones y el software antimalware, que puede afectar al rendimiento de un dispositivo de base.

Para obtener información acerca de los requisitos de software para equipos clientes en cada plataforma (web, escritorio y móvil), consulte [obtener los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Servidores de seguridad de extremo

Firewalls de cliente pueden tener un impacto significativo en la experiencia del usuario.
Firewalls de cliente pueden afectar a la calidad de las llamadas además de evitar una llamada desde que se estableció. Configure las exclusiones adecuadas en el servidor de seguridad de cliente basándose en la información de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips). El proveedor tendrá instrucciones específicas sobre cómo crear las exclusiones.

>[!NOTE]
> Teams Microsoft actualizará automáticamente el Firewall de Windows con una configuración de servidor de seguridad adecuados.

## <a name="wi-fi-recommendations-for-endpoints"></a>Recomendaciones de Wi-Fi para extremos

Toma significativa planea implementar una red Wi-Fi optimizada para soportar cargas de trabajo en tiempo real de Microsoft Teams. Las secciones siguientes proporcionan algunas instrucciones generales que pueden ayudarle a evitar errores comunes al planear de extremos.

### <a name="wi-fi-drivers"></a>Controladores de Wi-Fi

Algunos controladores de Wi-Fi pueden ser problemáticos. Por ejemplo, un controlador puede tener muy agresivos comportamientos móviles entre puntos de acceso, que producen una calidad deficiente de llamada.
Esto no es habitual, pero es importante garantizar que los controladores de Wi-Fi en el PC se han actualizado y probado antes de la implementación.

### <a name="wi-fi-bands"></a>Bandas de Wi-Fi

Existen principalmente dos tipos de bandas utilizadas en los equipos hoy en día, 2,4 GHz y 5,0 GHz Wi-Fi. Si su organización proporciona ambas bandas, debe configurar la configuración del controlador para preferir la banda de 5,0 GHz. Esta banda es mucho más densa en términos de rendimiento y es menos afectadas por la interferencia en la banda de 2,4 GHz.
Esta recomendación se supone que se ha optimizado correctamente la banda de la red de 5,0 GHz.

### <a name="wi-fi-radio-type"></a>Tipo de radio Wi-Fi

Plan para los dispositivos que admiten los tipos de radio Wi-Fi más reciente. Puede obtener un excelente rendimiento de Wi-Fi si se aprovechan los 802.11ac o posterior en los dispositivos que se aprovisiona.

### <a name="wireless-avoidance"></a>Evitación de inalámbrico

Algunas organizaciones prefieren evitar Wi-Fi. A veces, esta guía se proporciona a través de una recomendación a los usuarios conectarse directamente a una red cableada. En algunos casos, el orden de enlace de red podría tener la conexión inalámbrica preferida y seguir utilizando esa conexión, aunque el equipo esté conectado a la conexión por cable. Para evitar este comportamiento imprevisto, configure el orden de enlace para evitar esta situación.

### <a name="80211-power-save-protocol"></a>802.11 Protocolo de ahorro de energía

Si su organización utiliza puntos de acceso inalámbrico o los enrutadores que no admiten el protocolo de ahorro de energía 802.11, podría experimentar llamadas interrumpidas o llamada deficiente calidad en Teams de ejecución en dispositivos de Windows de Microsoft. Si no es posible actualizar el punto de acceso inalámbrico o los enrutadores, debe actualizar la configuración del Plan de energía de Windows en los dispositivos que se ejecutan en la energía de la batería. En el siguiente [artículo de soporte técnico](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)se proporciona más orientación detallada y configuración.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>¿Qué clientes de equipos se implementará en su organización?</li><li>¿Cómo inicialmente implementará los clientes de equipos de los usuarios?</li><li>¿Quién es responsable de evaluar los extremos y los dispositivos para validar que cumplan los requisitos de los equipos para una experiencia de calidad?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar el proceso que se seguirá para implementar a equipos clientes.</li><li>Evaluar los extremos y los dispositivos y realizar y corrección necesaria.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Dispositivos para equipos

Teams de Microsoft puede utilizarse para reuniones o como un sistema telefónico. Al utilizar estas características, el dispositivo de interfaz que se utiliza para equipos desempeña un papel importante en la experiencia del usuario.

Con un altavoz de PC y un micrófono integrado puede resultar aceptable para el usuario que tiene esa configuración. Pero por lo general, estos dispositivos no están optimizados para cancelación del ruido y cualquier tipo de ruido ambiental puede tener un impacto indirecto en otros en la llamada. Aprovechamiento de dispositivos optimizados para estos escenarios le ayudará a garantizar una experiencia de alta calidad.

Cada dispositivo necesita satisfacer las necesidades de los usuarios. Debe adaptar dispositivos como auriculares para los diferentes roles y casos de uso en su organización.
Como parte del proceso de planificación se debe completar un ejercicio de asignación de rol para el dispositivo.

Después de haber seleccionado los dispositivos, incluirlos en el plan de pruebas piloto para la validación final. Encuestas de aprovechamiento durante la prueba piloto para recopilar comentarios para asegurarse de su estrategia de dispositivo es óptima.

> [!NOTE]
> En este momento, se recomienda utilizar dispositivos de audio que se certificaron a través del Skype para el programa de certificación de empresa. Para buscar dispositivos certificados bajo este programa, consulte el catálogo de soluciones [Certificados de dispositivos USB de Skype para empresas](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>Decidir sobre la estrategia de dispositivo general de su organización para el usuario y experiencias de la sala de reuniones.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Realizar un ejercicio de asignación de rol al dispositivo para su organización.</li><li>Documentar el proceso de obtención de dispositivos para usuarios y salas de reuniones.</li><li>Documentar el proceso de implementación y configuración de dispositivos para usuarios y salas de reuniones.</li><li>Adquirir dispositivos iniciales para comenzar la implementación.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->