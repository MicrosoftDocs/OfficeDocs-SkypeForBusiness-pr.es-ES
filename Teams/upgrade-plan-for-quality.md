---
title: Planear la administración y la calidad del servicio | Preparación técnica
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Use esta guía para obtener información sobre los requisitos necesarios para proporcionar y mantener una implementación de Microsoft Teams de alta calidad.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3bc311fc2099f6162115d1c341d088a49c94da0
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198528"
---
![Actualizar el diagrama de viaje, enfatizando la fase de preparación técnica] (media/upgrade-banner-tech-readiness.png "Etapas del viaje de actualización, con énfasis en la fase de preparación técnica")

Este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad que ha completado en paralelo con la fase de preparación del usuario. Antes de continuar, confirme que ha completado estas actividades desde fases anteriores:

- [Inventar a los participantes del proyecto](upgrade-enlist-stakeholders.md)
- [Definió el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [La coexistencia y la interoperabilidad de Skype para empresas y equipos](https://aka.ms/SkypeToTeams-Coexist)
- [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->

# <a name="plan-for-quality"></a>Planificar la calidad

Si está implementando audio, vídeo o reuniones, puede realizar algunos pasos adicionales para optimizar el entorno para esa funcionalidad. En esta sección se describen los requisitos que se requieren para ofrecer y mantener una implementación de Microsoft Teams de gran calidad. Puede ayudar a garantizar una implementación correcta al planear la administración y la calidad del servicio antes de la primera implementación piloto o de producción.

La guía se compone de las siguientes secciones:

- Lo primero es una descripción de la experiencia de usuario y los componentes clave que respaldan la calidad. En ella se destacan las áreas en las que hay que centrarse antes de incorporarse a Microsoft Teams.

- En segundo lugar, se ofrece una guía para planificar un modelo de soporte con el que administrar Microsoft Teams antes de crear el primer piloto de usuario o implementación de producción. En esta sección se describen las tareas que hay que llevar a cabo de forma regular para mantener una implementación de gran calidad de Teams. Además, se ofrecen más instrucciones que puede aplicar para comenzar a comprender y poner en marcha estas tareas.

- En tercer lugar, con estas instrucciones específicas podrá planificar su red y los puntos de conexión de su organización para poder admitir Microsoft Teams.

- Por último, se resumen los pasos que se deben seguir a continuación con referencias a contenido relacionado.

## <a name="key-technical-components-that-affect-user-experience"></a>Componentes técnicos clave que afectan a la experiencia del usuario

Los componentes técnicos clave que afectan a la experiencia del usuario se revisarán en esta sección. Antes de revisar los componentes clave, es fundamental que conozca bien la experiencia de usuario y la importancia que tiene a la hora de que su organización cumpla los objetivos empresariales. Revisemos primero cómo se define la experiencia de usuario.

### <a name="user-experience-defined"></a>Definición de experiencia de usuario

Los objetivos empresariales se pueden lograr al implementar Microsoft Teams y cuando los usuarios adoptan Teams como su solución de colaboración y comunicación básica. La calidad puede ayudar a garantizar una experiencia de usuario positiva, un atributo clave para impulsar el uso y la adopción. Al ofrecer un servicio de alta calidad que deilumine personas, individuos y equipos puede tener confianza y encontrar formas nuevas e innovadoras de usar el servicio que impulsa las ventajas empresariales.

Como elemento esencial de todo esto se encuentra la experiencia de usuario con Teams: las emociones y las actitudes de las personas en relación con el servicio. Entonces, ¿de qué forma se contribuye a la experiencia de usuario? Se refiere al conocimiento de los usuarios sobre cómo y por qué usar Teams y la incorporación a su flujo de trabajo diario para disfrutar de una excelente calidad en las llamadas y poder conectarse de manera confiable, independientemente de dónde estén. La experiencia del usuario es muy extensa; Este artículo se centra únicamente en los elementos técnicos que la organización puede controlar. Puede encontrar información adicional acerca de la disponibilidad del usuario en [preparar la organización para Teams](https://aka.ms/SkypeToTeams-UserReadiness).

Hay determinados requisitos en la implementación que son extremadamente importantes para poder ofrecer una experiencia de usuario fantástica, especialmente cuando se usan las características de voz en la nube. Es fundamental tratar a Microsoft Teams como un ciudadano de primera clase con respecto a otras inversiones en comunicación y colaboración, y, de este modo, dar prioridad al tráfico en tiempo real. En la siguiente sección se describen los componentes clave que influyen de alguna manera en la experiencia de usuario. En las demás secciones se aportan instrucciones sobre cómo comenzar a plantear la implementación y el mantenimiento de los componentes clave que constituyen la calidad.

### <a name="key-components-of-quality"></a>Componentes clave de la calidad

Una organización o un socio auxiliar deberían comenzar a planear tres componentes clave durante la fase de preparación técnica de una implementación de Teams: administración de servicios, red y puntos de conexión. La combinación de todas estas tres áreas es fundamental para poder ofrecer una experiencia de usuario de calidad.

![Diagrama que ilustra los tres componentes de la calidad] (media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagrama que ilustra los tres componentes de la calidad y cómo la administración de servicios se superpone a los tres componentes.")

#### <a name="service-management"></a>Administración de servicios

La administración de servicios se puede dividir en dos categorías de responsabilidad distintas:

- **Responsabilidad de Microsoft**. Microsoft es responsable de los componentes de infraestructura de los que se componen los servicios de Office 365. Microsoft se compromete a garantizar a los clientes que los usuarios que se conecten a Teams disfrutarán de una experiencia fiable de gran calidad.

- **Responsabilidad de los clientes**. Tanto usted como su organización deben administrar diversos aspectos del servicio de Office 365, la red local y los puntos de conexión de los usuarios. Por ejemplo, cuando se agregan direcciones IP nuevas a Office 365, debe actualizar los firewalls apropiados para permitir la comunicación con los nuevos puntos de conexión y evitar que se pueda interrumpir el servicio al cliente.

Para recibir instrucciones detalladas sobre cómo planificar la administración de servicios, consulte [Plan para la administración de servicios](#plan-for-service-management).

#### <a name="network"></a>Red

En la mayoría de las organizaciones, las redes se pensaron en un principio para proporcionar acceso a los datos y las aplicaciones que residían en sus centros de datos. Sin embargo, las aplicaciones basadas en la nube, como Office 365, precisan que se apliquen cambios a estas redes para permitir el nuevo acceso y los flujos de datos que Teams requiere. Antes de habilitar a los usuarios para Teams en su organización, debe evaluar y optimizar la red actual. Es fundamental para poder aprovechar las funcionalidades de voz en la nube.

En las redes tradicionales, los usuarios tendrán que atravesar las redes perimetrales de una organización para poder acceder a Teams. Muchas organizaciones tienen dispositivos basados en la seguridad, como servidores proxy, firewalls y VPNs, que pueden bloquear o impedir el tráfico de red o bien pueden proporcionar una ruta que no sea la más optimizada para este.

Además, es necesario optimizar las redes internas centrales y asignarles el tamaño adecuado para que puedan proporcionar la capacidad y calidad que hacen falta para admitir las cargas de trabajo de Teams, incluidos los medios en tiempo real. El ancho de banda se puede planificar, corregir y optimizar para garantizar que la red pueda ofrecer una ruta eficiente y de gran calidad a Office 365.

Para recibir instrucciones detalladas sobre cómo planificar la red, consulte [Plan para la calidad de las redes](#plan-for-network-quality).

#### <a name="endpoints"></a>Puntos de conexión

Microsoft Teams admite una gran variedad de puntos de conexión. Desde equipos PC a tabletas o teléfonos, puede acceder a Teams en cualquier lugar desde prácticamente cualquier dispositivo.

Para ofrecer a los usuarios la mejor experiencia posible, debe tener en cuenta estos aspectos importantes: ¿los puntos de conexión cumplen los requisitos de hardware y software de Teams? ¿Ha configurado y optimizado los puntos de conexión para que admitan redes Wi-Fi? ¿Qué dispositivos usará para realizar y recibir llamadas de voz? ¿Esos dispositivos están optimizados para Teams?

Para recibir instrucciones detalladas sobre cómo planificar los puntos de conexión, consulte [Plan para la calidad de los puntos de conexión](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Plan para la administración de servicios

La administración de servicios es un tema muy amplio que cubre las operaciones del día a día del servicio de Microsoft Teams una vez que se ha implementado y habilitado para los usuarios. El servicio de Teams abarca Microsoft Office 365 y los componentes de infraestructura que se implementan en local (por ejemplo, las redes).

Seguramente, el concepto de "administración de servicios" no es nuevo para la mayoría de organizaciones. Probablemente ya ha implementado procesos y tareas asociados a los servicios que ya ofrece. De este modo, es posible que baste con aumentar lo que ya tiene cuando planifique la administración de servicios que respaldarán a Microsoft Teams más adelante.

En la administración de servicios se incluyen todas las actividades y procesos que se ven implicados en la administración de Microsoft Teams de un extremo a otro. Como se ha descrito anteriormente, algunos de los componentes de la administración de servicios (los componentes de infraestructura de los que consta el mismo servicio de Office 365) son responsabilidad de Microsoft, mientras que el cliente debe responder ante sus clientes de la administración de diversos aspectos de Teams, la red y los puntos de conexión que se ofrecen. En esta sección del documento se explica la responsabilidad del cliente desde la perspectiva de la administración de servicios.

![Diagrama que ilustra los tres componentes de la calidad] (media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagrama que ilustra los tres componentes de la calidad y cómo la administración de servicios se superpone a los tres componentes. Centrándose en la administración de servicios.")

### <a name="introduction-to-the-operations-guide"></a>Introducción a la guía de operaciones

**Qué**, **quién** y **cómo** son tres importantes preguntas que hay que responder cuando hablamos de la administración de servicios.

La [Guía de operaciones](1-drive-value-operate-my-service.md) se puede usar como ayuda a la hora de plantearse estas tres preguntas. La guía ofrece una lista de actividades que se realizan a diario, semanalmente, mensualmente o conforme va siendo necesario. Estas actividades y tareas son básicas para poder mantener un alto nivel de calidad en la implementación de Teams. Determinar quién será el responsable de realizar actividades específicas en la administración de servicios es un aspecto crítico de la planificación que debe llevar a cabo en las primeras fases de la [planificación](upgrade-enlist-stakeholders.md) para garantizar una implementación correcta. Una vez que se determinen las tareas y las actividades, los grupos y personas a los que se les asignen deberán comprenderlas bien y seguirlas. En la Guía de operaciones se ofrece esta información y las instrucciones necesarias para llevar a cabo cada una de estas tareas, así como referencias a contenido externo.

### <a name="operational-role-mapping"></a>Asignación de roles operativos

Planificar la administración de servicios en las primeras fases del proceso es un hito crítico, ya que la fase de operaciones comienza cuando se habilitan los primeros usuarios piloto. El equipo del proyecto debe revisar y acordar las tareas y las actividades que se requieren, identificar el equipo responsable de cada tarea operativa y, por último, lograr el compromiso y la validación de cada equipo.

Una vez que se ha completado la validación, el equipo responsable deberá entonces comenzar a poner en marcha estos roles y responsabilidades; entre ellos, la formación y la preparación, la puesta al día del modelo de personal o la comprobación de que los socios externos están listos para ofrecer los servicios.

La asignación de roles operativos a medida que se reúne el [equipo del proyecto](upgrade-enlist-stakeholders.md) permite que todos los equipos inicien sus tareas operativas durante la prueba piloto, y que se asegure de que todo está listo después de que se inicie la implementación.

En la Guía de operaciones se incluye una lista de las tareas comunes asignadas a los roles típicos que valdrá en la mayoría de situaciones. Adapte estas responsabilidades a su organización para poder reusarlas.

### <a name="the-quality-champion-role"></a>Rol de experto de calidad

Un grupo o una persona tiene que ser responsable de la calidad en todas las organizaciones. Es, sin duda, el rol más importante en la administración de servicios. El experto en calidad es un rol de cliente que se asigna a una persona o un grupo que cuida al detalle la experiencia de sus usuarios, y requiere las habilidades adecuadas para identificar tendencias del entorno y el respaldo necesario para poder trabajar con otros equipos y dirigir las correcciones que corresponda. El mejor candidato para ser experto en calidad es normalmente el propietario del servicio al cliente quien, según sea el tamaño y la complejidad de la organización, puede ser cualquier persona o grupo al que le apasione la experiencia de usuario.

El experto en calidad hace uso de las herramientas existentes y los procesos documentados, como el Panel de calidad de llamadas y la Guía de revisión de la experiencia de calidad, para supervisar la experiencia de usuario, identificar las tendencias de calidad y dirigir las correcciones cuando sea necesario. El experto en calidad trabaja con los equipos correspondientes e impulsa acciones correctivas, informa al comité directivo sobre el progreso y abre incidencias.

Las tareas y las actividades que se asocian al rol también se explican en la Guía de operaciones. Este rol se debe asignar durante la [fase de planificación](https://aka.ms/SkypeToTeams-Plan). Un paso clave a la hora de poner en funcionamiento el rol de experto en calidad es adquirir el conocimiento que se necesita del rol y garantizar que se cumplen los requisitos previos necesarios para desarrollar las tareas. Una tarea fundamental de este rol es revisar con regularidad la experiencia de calidad.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introducción a la Guía de revisión de la experiencia de calidad

La Guía de revisión de la experiencia de calidad incluye un conjunto de actividades que se utilizan para evaluar y ofrecer acciones correctivas en áreas clave que influyen en gran medida en mejorar la experiencia de usuario, como se muestra en la figura siguiente.

![Diagrama ilustrativo de las áreas examinadas durante la revisión] de la experiencia (media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Un diagrama que muestra las áreas clave que se examinan durante una revisión de la experiencia de calidad.")

Al evaluar y corregir de forma continua las áreas que se describen en este documento, se reducen los posibles efectos negativos que puedan afectar a la experiencia de usuario. La mayoría de problemas que se encuentran en la experiencia de usuario de una implementación se pueden agrupar en las siguientes categorías:

- Una configuración de proxy o firewall incompleta

- Una cobertura Wi-Fi insuficiente

- Un ancho de banda insuficiente

- VPN

- El uso de dispositivos de audio integrados o no optimizados

- Dispositivos de red o subred problemáticos

Las instrucciones que se ofrecen en la Guía de revisión de la experiencia de calidad se centran principalmente en el uso del Panel de calidad de llamadas (CQD) en línea como la herramienta principal para informar e investigar cada área que se describe, haciendo un especial hincapié en el audio para maximizar la adopción y el impacto. Las optimizaciones que se realicen en la red para mejorar la experiencia de audio se traducirán directamente en mejoras de las de vídeo y escritorio compartido.

Se recomienda que designe al experto en calidad lo antes posible y, una vez lo haya hecho, esta persona deberá comenzar a familiarizarse con el contenido de la Guía de revisión de la experiencia de calidad.

Puede encontrar esta guía [aquí](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Plan para la calidad de las redes

La planificación de la calidad de las redes se debe centrar en la siguiente sección.

![Diagrama que ilustra los tres componentes de la calidad] (media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagrama que ilustra los tres componentes de la calidad y cómo la administración de servicios se superpone a los tres componentes. Con un foco en la red.")

Como se mencionó anteriormente, es fundamental planificar la calidad de las redes antes de incorporar Microsoft Teams. Para obtener más información sobre cómo preparar las redes, consulte [Preparar la red de la organización para Microsoft Teams](prepare-network.md).

En la mayoría de organizaciones, las redes constan de redes administradas y no administradas.

Las redes administradas son componentes de la infraestructura de red que controla directamente una organización. Como resultado, las redes administradas influyen directamente en la calidad que se ofrece para las cargas de trabajo de tráfico en tiempo real.

Por el contrario, las redes no administradas son segmentos de red sobre los que un cliente tiene control limitado o ningún control.

Las conexiones de Internet entre la organización y Office 365 son redes en las que un cliente tiene control limitado. La administración de las redes corre a cargo de un ISP; sin embargo, las organizaciones también pueden influir en la calidad de la red al actualizar el ancho de banda, proponer optimizaciones de ruta o, si todo esto falla, cambiar de ISP.

Las redes domésticas o las redes en hoteles o cafeterías son ejemplos de redes en las que los clientes no tienen ningún control.

En las siguientes secciones, nos centraremos en los requisitos de calidad de las redes administradas.

### <a name="key-network-planning-areas"></a>Principales áreas de planificación de red

Las siguientes secciones se centran en las áreas más importantes para poder ofrecer una red de gran calidad.

> [!NOTE]
> Muchas redes van evolucionando gracias a las actualizaciones, al ampliarlas o por otros requisitos de negocio. Asegúrese de contar con procesos operativos que ayuden a mantener estas áreas como parte de su planificación de administración de servicios.

#### <a name="bandwidth"></a>Ancho de banda

La planificación del ancho de banda es de vital importancia para la actividad de preparación de la red. Es fundamental asegurarse de que hay suficiente ancho de banda para las cargas de trabajo de Microsoft Teams. Para poder adecuar el tamaño de una red existente, es necesario comprender qué se está aprovisionando en ese momento, el uso actual de la red y, por último, el ancho de banda que queda disponible.

Para mediar el uso actual, hay que supervisar la red y, una vez obtenida la medición, se usará como punto de partida para planificar el ancho de banda. Además, habrá que seguir supervisando la red durante la implementación y una vez esta concluya para garantizar que el aprovisionamiento de red sea siempre el adecuado.

> [!NOTE]
> Cuando se supervisa el uso de la red, es importante evitar usar valores medios de todo el día. Estos promedios pueden distorsionar los resultados al incluir horas no centrales del día y asimismo pueden ocultar períodos de pico y enmascarar un problema.

#### <a name="quality-of-service-qos"></a>Calidad de servicio (QoS)

La calidad de servicio se debe implementar en todos los segmentos de la red administrada, incluso en las redes que se hayan aprovisionado con el ancho de banda adecuado. En último caso, la calidad de servicio actúa como mitigación de riesgo en el caso de que se produzca una carga de red no anticipada. Cuando QoS se implementa, se prioriza el tráfico de voz para que estos eventos no anticipados no afecten a la calidad.

Una implementación de QoS debe incluir áreas de la red, desde el punto de conexión hasta los puntos de salida y desde los puntos de salida de nuevo al punto de conexión. De este modo nos aseguramos de que el tráfico de voz se priorice en ambos sentidos. QoS se debe implementar tanto en redes Wi-Fi como redes con cable.

Para implementar QoS en la red, las siguientes instrucciones pueden serle de ayuda: [Calidad de servicio en Microsoft Teams](qos-in-teams.md)

#### <a name="proxy-servers"></a>Servidores proxy

Muchas organizaciones consideran el tráfico que se destina a Internet como un riesgo para la seguridad y tratan de mitigarlo supervisando y evaluando el tráfico en los puntos de salida de la red. Los servidores proxy son uno de estos dispositivos que se pueden implementar para llevar a cabo esta función.

Un servidor proxy puede generar problemas cuando realiza la inspección de paquetes o cuando modifica la carga útil, lo que podría dar lugar a errores en la configuración de las llamadas, llamadas interrumpidas y una mala calidad de las llamadas. Si se fuerza a los elementos multimedia en tiempo real a atravesar un servidor proxy, se forzará a la pila de medios de Teams a realizar una conmutación por recuperación en el TCP, lo que empeoraría aún más la calidad. Siempre se prefiere UDP a TCP.

Además, es posible que un servidor proxy no esté diseñado para gestionar la carga adicional de Office 365 y, específicamente, las cargas de trabajo de Microsoft Teams, incluidos los medios en tiempo real.

Teniendo en cuenta los posibles problemas que un servidor proxy puede crear y estos inconvenientes adicionales de capacidad, Microsoft recomienda omitir el servidor proxy y realizar una conexión directa con Office 365.

La configuración que hay que aplicar para omitir el servidor proxy es diferente entre los distintos proveedores, pero el método más común requiere normalmente que se actualice el archivo de configuración automática del proxy (PAC). El archivo PAC es un archivo de configuración que describe qué tráfico pasa por el proxy y cuál lo omite.

Algunos proveedores de servidores proxy ofrecen un proceso automatizado que garantiza que la configuración está actualizada. Si el proveedor no ofrece este proceso automático, puede descargar un archivo PAC actualizado en <https://aka.ms/o365proxies>

[Servidores proxy para equipos o Skype empresarial online y Teams](proxy-servers-for-skype-for-business-online.md)

#### <a name="firewalls"></a>Firewalls

Para obtener acceso a Microsoft Teams, es necesario garantizar que los puertos y protocolos adecuados estén abiertos en todas las direcciones IP y URL de Office 365, al igual que lo es para poder ofrecer una implementación de gran calidad. Con solo hacer una llamada o unirse a una llamada de conferencia no basta para saber si el firewall está bien configurado.

Si solo está abierto el TCP en el firewall, la sesión se establecerá, pero el transporte preferido (UDP) no se negociará. Ambos protocolos TCP y UDP deben estar abiertos en el firewall para ofrecer la mejor experiencia de usuario.

Dada su naturaleza de firewall con estado, el protocolo TCP no es el preferido para los medios en tiempo real y solo se proporciona como un transporte de red para la conmutación por recuperación de Microsoft Teams. Con el TCP, si hay retraso o pérdida de paquetes, estos se deben retransmitir hasta que se reconozcan. Esta situación puede provocar que los paquetes de medios ya no sean relevantes para competir con la entrega puntual de los paquetes de medios actuales. El cliente de Teams del usuario intenta ampliar el audio y puede generar anomalías en el sonido según cuáles sean las condiciones de la red. Con la sobrecarga adicional de TCP, una experiencia que sería generalmente aceptable se podría convertir en una experiencia de usuario insatisfactoria. Por este motivo, se requiere el transporte de red UDP sin estado.

En el artículo [URL de Office 365 e intervalos de direcciones IP](https://aka.ms/o365ips) se detallan instrucciones completas para abrir el firewall de Microsoft Teams.

Una vez que el firewall esté abierto, podrá usar la  [herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885)  para validar la conectividad de las funcionalidades de voz en la nube.

> [!IMPORTANT]
> Las direcciones URL e IP de Microsoft Office 365 irán cambiando a lo largo del tiempo. Como parte de la planificación de la administración de servicios, es importante garantizar que hay un proceso operativo en vigor y un grupo designado como responsable de supervisar los [rangos de direcciones IP y URL de Office 365](https://aka.ms/o365ips) y hacer las actualizaciones oportunas.

#### <a name="local-internet-egress"></a>Salida local de Internet

Muchas redes se diseñaron en su momento para usar una topología tipo hub-and-spoke. En esta topología, por lo general, el tráfico de Internet atraviesa la red WAN hasta un centro de datos central antes de salir a Internet. A menudo, esto se hace para centralizar los dispositivos de seguridad de redes y reducir así el coste general.

El tráfico de transporte hacia atrás por la WAN aumenta la latencia y repercute negativamente en la calidad y la experiencia del usuario. Como Microsoft Teams se ejecuta en una gran red global de Microsoft, existe a menudo una ubicación de emparejamiento de red cerca del usuario. Es muy probable que un usuario obtenga un mejor rendimiento si sale de un punto de Internet local que se encuentra cerca de su ubicación y accede a una red optimizada para voz lo antes posible. Para algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar tráfico al servidor front-end más cercano. En esos casos, es importante que, cuando se usa un punto de salida local, se empareje con una resolución DNS local.

Al optimizar la ruta de red a la red global de Microsoft, mejorará el rendimiento y, en última instancia, los usuarios disfrutarán de la mejor experiencia posible. Para obtener más detalles, vea la publicación del blog [Conseguir la mejor conectividad y el mejor rendimiento en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

Las redes VPN ofrecen un servicio muy valioso a muchas organizaciones. Lamentablemente, por lo general no se diseñan ni se configuran para admitir medios en tiempo real. Algunas redes VPN también podrían no admitir UDP. Las VPN también introducen una capa extra de cifrado sobre el tráfico de medios que ya está cifrado. Además, la conectividad con el servicio de Microsoft Teams podría no ser eficaz debido al tráfico de redirección al origen a través de un dispositivo VPN. Además, no se diseñan necesariamente desde una perspectiva de la capacidad para acomodar las cargas anticipadas que Teams requerirá.

Lo que se recomienda es ofrecer una ruta alternativa que omita el VPN para el tráfico de Teams. Es lo que normalmente se conoce como VPN de túnel dividido. El túnel dividido indica que el tráfico para Office 365 no atravesará la red VPN, sino que irá directamente a Office 365. Este cambio repercutirá positivamente en la calidad, pero también proporciona la ventaja secundaria que supone reducir la carga de los dispositivos VPN y la red de la organización.

Para implementar un túnel dividido, consulte con su proveedor de VPN para los detalles de configuración.

#### <a name="wi-fi"></a>Wi-Fi

Al igual que sucede con las redes VPN, las redes Wi-Fi no se han diseñado ni configurado necesariamente para admitir los medios en tiempo real. Planificar una red Wi-Fi u optimizarla para que admita Teams es un aspecto muy relevante en la implementación de calidad.

Hay varios factores que intervienen a la hora de optimizar una red Wi-Fi.

- Implementar QoS o Wi-Fi Multimedia (WMM) para garantizar que el tráfico multimedia se priorice de forma acorde a través de redes Wi-Fi.

- Planificar y optimizar las bandas Wi-Fi y la ubicación del punto de acceso. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada en función de la ubicación del punto de acceso, pero a los puntos de acceso normalmente también le afectan otros dispositivos de consumidores que funcionan en esa gama. El intervalo de 5 GHz es mejor para los medios en tiempo real, debido a su rango denso, pero requiere más puntos de acceso para conseguir suficiente cobertura. Los puntos de conexión también necesitan admitir esa gama y configurarlos para poder aprovechar esas bandas de forma adecuada.

- Si se implementan redes Wi-Fi de doble banda, considere la posibilidad de implementar "band steering". "Band steering" es una técnica que implementaron los proveedores Wi-Fi para influenciar en clientes de doble banda para que usaran el intervalo de 5Ghz.

- Superposición de canales: cuando los puntos de acceso del mismo canal están demasiado cerca entre sí, pueden generar superposición de señales y pueden competir sin pretenderlo, lo que daría lugar a una mala experiencia para el usuario. Asegúrese de que el punto de acceso que está próximo a cada uno de ellos se encuentra en canales que no se superponen.

Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Le recomendamos que consulte con su proveedor para obtener las indicaciones concretas.

### <a name="network-readiness-assessment"></a>Evaluación de preparación de la red

Como parte de las actividades de preparación de la red se incluye una evaluación de red. Una vez que se completa la planificación y la configuración, la evaluación ofrece un conocimiento de referencia de la calidad de la red antes de que incorporar usuarios a Microsoft Teams. Gracias a los resultados de la evaluación, podrá identificar y priorizar esfuerzos de corrección antes de habilitar usuarios para Teams.

La evaluación de red se debe realizar tanto en las redes de cable como en las redes Wi-Fi de todos los edificios que se estén habilitando para las funciones de voz en la nube de Teams.

La evaluación de red se puede llevar a cabo mediante un socio de Microsoft, herramientas de terceros o la [herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885).

## <a name="plan-for-endpoint-quality"></a>Plan para la calidad de los puntos de conexión

Como se puede ver en el diagrama siguiente, los puntos de conexión son un importante bloque de creación a la hora de proporcionar una experiencia de gran calidad para los usuarios.

![Diagrama que ilustra los tres componentes de la calidad] (media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagrama que ilustra los tres componentes de la calidad y cómo la administración de servicios se superpone a los tres componentes. Centrado en los puntos de conexión.")

Los puntos de conexión de Microsoft Teams se pueden ejecutar en muchos dispositivos, incluidos PC, Mac, tabletas y dispositivos móviles. Parte de la experiencia no solo incluye el dispositivo, sino cómo se conecta un usuario al dispositivo; por ejemplo, mediante el micrófono o el altavoz del dispositivo, miniauriculares o auriculares con micrófono optimizados. El uso de un auricular con micrófono optimizado, se puede enriquecer la experiencia general del usuario.

Las siguientes directrices sobre la planificación de los puntos de conexión le ayudarán a garantizar que su organización tenga una experiencia de incorporación con Teams correcta.

### <a name="endpoint-capability"></a>Funcionalidad de puntos de conexión

La primera parte de la planificación consiste en garantizar que todos los PC y otros dispositivos de su organización puedan ejecutar Microsoft Teams. Esto no solo implica comprobar los requisitos de hardware, sino también conocer qué más hace el PC en segundo plano. Muchas organizaciones ejecutan otro software, incluidos sistemas de detección de intrusiones y software antimalware, que puede afectar al rendimiento básico de un dispositivo.

Microsoft Teams tiene clientes disponibles para web, escritorio (Windows y Mac) y móvil (Android, iOS y Windows Mobile). Si necesita información sobre los requisitos de software para cada plataforma, consulte [Obtener clientes para Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls para los puntos de conexión

Los firewalls del cliente pueden repercutir de forma significativa en la experiencia de usuario. Los firewalls del cliente pueden afectar a la calidad de las llamadas, además de impedir que la llamada se establezca. Configure las exclusiones apropiadas en el firewall del cliente según la información que aparece en [URL de Office 365 e intervalos de direcciones IP](https://aka.ms/o365ips). Su proveedor de terceros debe tener instrucciones específicas para saber cómo se crean las exclusiones.

> [!NOTE]
> Microsoft Teams actualizará automáticamente el firewall de Windows con una configuración de firewall adecuada.

### <a name="wi-fi-recommendations-for-endpoints"></a>Recomendaciones de Wi-Fi para puntos de conexión

Para planificar e implementar una red Wi-Fi optimizada que admita cargas de trabajo en tiempo real en Microsoft Teams hará falta una planificación significativa. En las siguientes secciones se ofrecen algunas directrices adicionales para evitar algunas dificultades comunes que surgen cuando se planifican los puntos de conexión.

#### <a name="wi-fi-drivers"></a>Controladores Wi-Fi

Algunos controladores Wi-Fi pueden ser bastante problemáticos. Como ejemplo, un controlador puede tener comportamientos de itinerancia muy agresivos entre los puntos de acceso dando lugar a una mala calidad en las llamadas. No es algo común, pero es importante garantizar que los controladores Wi-Fi del PC estén actualizados y se hayan probado antes de implementarlos.

#### <a name="wi-fi-bands"></a>Bandas Wi-Fi

Existen principalmente dos tipos de bandas que se utilizan en los equipos Wi-Fi de hoy en día: 2,4 GHz y 5 GHz. Si su organización proporciona ambas bandas, debe configurar el controlador para que dé prioridad a la banda de 5 GHz. Esta banda es mucho más densa en términos de rendimiento y le afectan menos las interferencias que se aprecian en la banda de 2,4 GHz. Esta recomendación da por hecho que ha optimizado correctamente la banda de red de 5 GHz.

#### <a name="wi-fi-radio-type"></a>Tipo de radio Wi-Fi

Planifique los dispositivos que admiten los tipos de radio Wi-Fi más recientes. Se puede obtener un rendimiento de Wi-Fi muy bueno si aprovecha 802.11ac o más recientes en los dispositivos que aprovisiona.

#### <a name="wireless-avoidance"></a>Elusión de redes inalámbricas

Algunas organizaciones prefieren evitar las redes Wi-Fi en general. En ocasiones, esta guía se ofrece a través de una recomendación a los usuarios para que se conecten directamente a una red de cable. En algunos casos, la orden de enlace de red podría preferir la conexión inalámbrica y seguir usando esa conexión incluso cuando el PC está conectado a la conexión de cable. Para evitar este comportamiento no intencionado, configure la orden de enlace para que esta situación no se produzca.

#### <a name="80211-power-save-protocol"></a>Protocolo de ahorro de energía 802.11

Si su organización utiliza enrutadores o puntos de acceso inalámbricos que no admiten el protocolo de ahorro de energía 802.11, podría experimentar llamadas interrumpidas o mala calidad en las llamadas en Microsoft Teams cuando se ejecuta en dispositivos Windows. Si no es posible actualizar su enrutador o su punto de acceso inalámbrico, debe actualizar la configuración del Plan de energía de Windows en los dispositivos que se ejecutan con ahorro de energía. Podrá encontrar más detalles e instrucciones de configuración en el siguiente [artículo de soporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Dispositivos para Teams

Microsoft Teams se puede usar para reuniones o como un sistema telefónico. Cuando se usan estas características, el dispositivo de interfaz que se utiliza para Teams tiene un papel fundamental en la experiencia de usuario.

Con un micrófono o altavoz de PC integrado, el sonido podría ser correcto para el usuario que tenga esa configuración. Sin embargo, normalmente esos dispositivos no están optimizados para la cancelación del ruido y cualquier tipo de ruido ambiente puede tener un impacto negativo en los otros participantes de la llamada. Si se utilizan dispositivos optimizados para estos escenarios, se podrá garantizar una experiencia de gran calidad.

Cada dispositivo tiene que cumplir las necesidades de sus usuarios. Tendrá que adaptar dispositivos, como auriculares con micrófono, para distintas personas y casos prácticos de su organización. Habría que completar un ejercicio de asignación de persona a dispositivo como parte del proceso de planificación.

Una vez que se seleccionen los dispositivos, se deben incluir en el plan de prueba piloto para su validación final. Utilice encuestas durante el piloto para recopilar comentarios con los que se pueda garantizar que su estrategia de dispositivo sea la adecuada.

En este momento, recomendamos usar dispositivos de audio que se hayan certificado mediante el programa de certificación de Skype Empresarial. Para encontrar dispositivos certificados con este programa, consulte el catálogo de soluciones de [dispositivos USB certificados para Skype Empresarial](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

## <a name="client-updates"></a>Actualizaciones del cliente

Una de las principales ventajas de Microsoft Teams es que el cliente se actualiza automáticamente. Los clientes de PC y Mac se actualizan mediante un proceso en segundo plano que comprueba si hay nuevas compilaciones y descarga el cliente nuevo cuando la aplicación está inactiva. El tamaño de descarga del cliente es de 100 MB aproximadamente.

Una organización no tiene control ni acceso a una configuración de directiva que administre el proceso de actualización. Para eliminar el riesgo de que se produzca un problema en una compilación más reciente, se mantiene la última versión en buen estado en el punto de conexión. Si existe un problema en una compilación nueva, el servicio de Microsoft Teams puede revertir el punto de conexión a la versión anterior automáticamente.

## <a name="next-steps-and-references"></a>Próximos pasos y referencias

En esta tabla se incluye un resumen de las actividades de planificación con vínculos al contenido relacionado.

| Área | Detalles | Referencias |
|---|---|---|
| Plan para la administración de servicios | Realizar un ejercicio de asignación de roles operativos <br/> Validación de equipos designados <br/> Preparación de roles | [Guía de operaciones](1-drive-value-operate-my-service.md) |
| | Nombrar expertos en calidad <br/> Preparación de expertos en calidad| <br/> [Guía de revisión de la experiencia de calidad](https://aka.ms/qerguide) |
| | Instalar las plantillas de revisión de la experiencia de calidad <br/> Cargar un archivo de compilación | [Plantillas QERLite](https://aka.ms/qertemplates) <br/> [Cargar información de compilación](turning-on-and-using-call-quality-dashboard.md)|
| Plan para la calidad de las redes | Realizar la planificación de red |  |
| | Implementar QoS | [Calidad de servicio (QoS) en Microsoft Teams](qos-in-teams.md) |
| | Omitir servidores proxy | [Instrucciones del proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | Implementar VPN de túnel dividido |  |
| | Optimizar redes Wi-Fi para medios en tiempo real | Consultar proveedores de terceros |
| | Implementar salida local de Internet | [Salida local de Internet](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implementar conectividad de red <br/> Comprobar la conectividad de red | [URL de Office 365 y direcciones IP](https://aka.ms/o365ips) |
| | Realizar evaluación de red |[Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885)  |
| Plan para la calidad de los puntos de conexión | Actualizar firewalls de puntos de conexión | [URL de Office 365 y direcciones IP](https://aka.ms/o365ips) |
| | Validar requisitos de software | [Obtener clientes para Microsoft Teams](get-clients.md) |
| | Implementar recomendaciones Wi-Fi de puntos de conexión | Consultar proveedores de terceros |
| | Realizar la asignación de personas a dispositivos <br/> Aprovisionar dispositivos y hacer un piloto |<br/> [Catálogo de dispositivos](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

Una vez que haya terminado de planificar, continúe con el siguiente paso: [preparar el entorno para Teams](https://aka.ms/SkypeToTeams-TechnicalReadiness).
