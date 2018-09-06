---
title: Planeación de la administración de servicios y calidad - Microsoft Teams
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Use esta guía para obtener más información acerca de los requisitos que son necesarios para entregar y mantener una implementación de Microsoft Teams de alta calidad.
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6114120998425acdd443ab852b3f39fd2549b5ff
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779951"
---
![Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica] (media/upgrade-banner-tech-readiness.png "Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica")

En este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad completar en paralelo con la fase de preparación del usuario. Antes de continuar, confirme que ha realizado estas actividades de fases anteriores:

-   [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
-   [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
-   [Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos](https://aka.ms/SkypeToTeams-Coexist)
-   [Elegido su viaje por la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->
# <a name="plan-for-quality"></a>Planeación de la calidad

Si va a implementar las reuniones, audio o vídeo, puede realizar algunos pasos adicionales para optimizar el entorno para que la funcionalidad. Este contenido proporcionará una descripción general de los requisitos que son necesarios para entregar y mantener una implementación de Microsoft Teams de alta calidad. Puede ayudar a garantizar una correcta implementación mediante la planificación de administración de servicios y la calidad, antes de la primera implementación piloto o de producción.

Las instrucciones se organizan en las secciones siguientes:

-   En primer lugar es una visión general de la experiencia de usuario y los componentes principales que respaldan calidad. Esto destaca las áreas para centrarse en antes de incorporación a Microsoft Teams.

-   En segundo lugar, se dan orientaciones para la planeación de un modelo de soporte técnico para administrar Microsoft Teams antes de la primera implementación piloto o de producción de usuario. En esta sección se describe las tareas que deben realizarse de forma periódica para mantener una implementación de los equipos de alta calidad. Además, esta sección presentan instrucciones adicionales que puede usar para comenzar a entender y en marcha la estas tareas.

-   Instrucciones en tercer lugar, específico ayuda con la planificación de la red y los extremos de la organización para admitir Microsoft Teams.

-   Por último, se resumen los pasos siguientes con referencias a contenido relacionado.

## <a name="key-technical-components-that-affect-user-experience"></a>Componentes técnicos clave que afectan a la experiencia del usuario

Los componentes técnicos clave que afectan a la experiencia del usuario se analizará en esta sección. Antes de revisar los componentes clave, es fundamental comprender la experiencia del usuario y su importancia en la obtención de los objetivos de negocio de su organización. Vamos a revisar cómo se define la experiencia del usuario en primer lugar.

### <a name="user-experience-defined"></a>Experiencia del usuario definida

Los objetivos del negocio pueden llevarse a cabo al implementar Microsoft Teams y cuando los usuarios adoptarán los equipos como su solución de colaboración y comunicación principal. Calidad puede ayudar a garantizar una experiencia de usuario positiva, un atributo key en fuerzas de uso y adopción. Al ofrecer un servicio de alta calidad que delights personas, personas y equipos pueden tener confianza y encontrar maneras nuevas e innovadoras del uso del servicio que beneficios de negocio de unidad.

En el centro de esto es la experiencia del usuario con los equipos: emociones y actitud hacia el servicio de la persona. ¿Por lo tanto, lo que contribuye a la experiencia del usuario? Que oscila entre los usuarios saber cómo y por qué utilizar los equipos y la incorporación de información a su flujo de trabajo diario a experimentar con la calidad de la llamada excepcionales y ser capaz de conectarse de forma confiable, independientemente de dónde se. Experiencia del usuario es muy amplia en la naturaleza; en este artículo se centra únicamente en los elementos técnicos que pueden ser controlados por su organización. Obtener información adicional acerca de la preparación del usuario puede encontrarse en [Prepare la organización para los equipos](https://aka.ms/SkypeToTeams-UserReadiness).

Existen requisitos específicos para la implementación que son de importancia crítica ofrecer una experiencia de usuario fantástico, especialmente cuando mediante la voz en la nube sobre las características en los equipos. Es fundamental para tratar Microsoft Teams como participante principal con otras inversiones de comunicación y colaboración, dar prioridad al tráfico en tiempo real en consecuencia. En la siguiente sección proporciona una introducción a los componentes clave que afectan a la experiencia del usuario. En aún más secciones, le ofrecemos instrucciones sobre cómo empezar a planear, implementar y mantener los componentes clave que conforman la calidad.

### <a name="key-components-of-quality"></a>Componentes clave de calidad

Una organización o un socio auxiliar debe comenzar durante la fase de preparación técnica de una implementación de los equipos de planeación de tres componentes principales: administración, la red y los extremos de servicio. La combinación de las tres áreas es fundamental para la calidad de la experiencia del usuario.

![Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes.] (media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes.")

#### <a name="service-management"></a>Administración de servicios

Administración de servicios se puede dividir en dos categorías diferentes de responsabilidad:

-   **Responsabilidad de Microsoft**. Microsoft es responsable de los componentes de infraestructura que comprende el servicio Office 365. Microsoft es responsable de los clientes para asegurarse de que cualquiera de sus usuarios que se conectan a los equipos se proporciona con una experiencia confiable y de alta calidad.

-   **Responsabilidad del cliente**. Usted y su organización son responsables de administrar los diversos aspectos de los extremos del usuario, red local y servicio de Office 365. Por ejemplo, cuando se agregan nuevas direcciones IP a Office 365, debe actualizar los servidores de seguridad adecuadas para permitir la comunicación a los extremos de nuevo para evitar la interrupción del usuario.

Para obtener instrucciones detalladas para la planeación de la administración de servicio, consulte [Plan para la administración de servicio](#plan-for-service-management).

#### <a name="network"></a>Red 

En la mayoría de las organizaciones, las redes inicialmente se diseñaron para proporcionar acceso a datos y las aplicaciones que se encontraba en sus centros de datos. Aplicaciones basadas en la nube como Office 365 requieren los cambios realizados en estas redes para admitir los nuevos flujos de acceso y los datos que requiere que los equipos. Para poder habilitar a los usuarios para los equipos de la organización, debe evaluar y optimizar la red actual. Esto es muy importante cuando aprovechar las capacidades de voz en la nube.

En las redes tradicionales, los usuarios deberán pasar por la red perimetral de una organización para tener acceso a los equipos. Muchas organizaciones tienen dispositivos basados en la seguridad, como los servidores proxy, servidores de seguridad y redes privadas virtuales que se pueden bloquear, obstaculizar o proporcionar una ruta de acceso no optimizado para el tráfico de red.

Además, las redes internas principales deben ser optimizada y adecuada para proporcionar calidad y capacidad suficiente para admitir las cargas de trabajo de los equipos, incluidos los medios en tiempo real. Puede usar la planeación, la corrección, el ancho de banda y optimización para ayudar a garantizar la red proporciona una ruta de acceso de alta calidad y eficaz a Office 365.

Para obtener instrucciones detalladas acerca de la planificación de red, vea [Planear la calidad de la red](#plan-for-network-quality).

#### <a name="endpoints"></a>Puntos de conexión

Microsoft Teams admite una gran variedad de extremos. Desde equipos para tabletas a teléfonos, puede obtener acceso los equipos en cualquier lugar desde prácticamente cualquier dispositivo.

Para ofrecer a los usuarios la mejor experiencia posible, debe tener en cuenta estos aspectos importantes: ¿los extremos que cumplen los requisitos de hardware y software de los equipos? ¿Ha configurado y optimizado extremos para admitir redes Wi-Fi? ¿Los dispositivos que va a usar para realizar y recibir llamadas de voz? ¿Esos dispositivos están optimizados para los equipos?

Para obtener instrucciones detalladas acerca de la planeación de extremo, consulte [Plan para la calidad del extremo](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Plan para la administración de servicio

Administración de servicios es un tema amplio que se describen las operaciones diarias del servicio Microsoft Teams después de que se ha implementado y se habilita para los usuarios. El servicio de los equipos incluye Microsoft Office 365 y los componentes de infraestructura que están implementan en servidores locales (por ejemplo, la red).

La noción de administración de servicios no lo más probable es un concepto nuevo para la mayoría de las organizaciones. Probablemente ya ha implementado los procesos y las tareas que están asociadas con servicios existentes. Dicho esto, probablemente puede aumentar lo que tiene en su lugar al planear la administración del servicio de hoy en día admitir Microsoft Teams en el futuro.

Administración del servicio abarca todas las actividades y procesos implicados en administración de Microsoft Teams de un extremo a otro. Tal y como se ha descrito anteriormente, algunos componentes de administración de servicios: los componentes de infraestructura que se compone del propio servicio de Office 365, son responsabilidad de Microsoft, mientras que el cliente es responsable de sus usuarios para administrar los diversos aspectos de los equipos, el red y los extremos que proporcionan. En esta sección del documento se centrará en la responsabilidad del cliente desde una perspectiva de administración de servicio.

![Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la administración de servicio.] (media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la administración de servicio.")

### <a name="introduction-to-the-operations-guide"></a>Introducción a la Guía de operaciones 

**¿Qué**, **quién**y **cómo** son tres preguntas importantes que necesitan ser respondidas en lo que respecta a la administración de servicio.

Puede usar la [Guía de operaciones](1-drive-value-operate-my-service.md) que le ayudarán a solucionar los tres de estas preguntas. La guía proporciona una lista de actividades que se debe realizar de forma diaria, semanal, mensual y según sea necesario. Estas tareas y actividades son esenciales para el mantenimiento de una implementación de los equipos de alta calidad. Determinar quién será responsable de realizar actividades específicas de la administración de servicio es un aspecto fundamental de la planeación que se debe hacer en la [fase de planificación](upgrade-enlist-stakeholders.md) para garantizar una correcta implementación. Después de que ha podido averiguar las tareas y actividades, deben ser entiende y seguido de los grupos o las personas que les asigne. La Guía de operaciones proporciona los conocimientos y las instrucciones sobre cómo realizar cada una de las tareas o las referencias a contenido externo.

### <a name="operational-role-mapping"></a>Asignación de funciones operativas

Primeras fases de planeación para la administración de servicio es un hito crítico, debido a que la fase de operaciones comienza cuando se habilitan la primera que los usuarios pilotos. El equipo del proyecto debe revisar y está de acuerdo en las tareas y actividades necesarias, identificar el equipo que es responsable de cada tarea operativa, y, a continuación, obtenga un compromiso y cierre de sesión de cada equipo respectivo.

Después de cerrar la sesión es completa, el equipo responsable, a continuación, debe iniciar en marcha la estas funciones y responsabilidades. Esto podría incluir formación y preparación, actualizar el modelo de personal, o asegurarse de que están listos para entregar socios externos.

Asignación de funciones operativas como recopilar el [equipo del proyecto](upgrade-enlist-stakeholders.md) permite a todos los equipos iniciar sus tareas operativas durante la prueba piloto y trayectoria de operaciones y asegúrese de que todo está listo después de la implementación se inicia.

La Guía de operaciones proporciona una lista de tareas comunes que se asignan a funciones típicas que deben ser válidas en la mayoría de los escenarios. Necesita para personalizar estas responsabilidades para que funcione para su organización.

### <a name="the-quality-champion-role"></a>La función de los pesos pesados calidad

Un grupo o individual debe ser responsable de la calidad en todas las organizaciones. Esta es la función más importante de la administración de servicio. La calidad de los pesos es una función de cliente que se asigna a una persona o grupo que es entusiastas acerca de la experiencia de sus usuarios. Esta función requiere las aptitudes para identificar las tendencias en el entorno y el apoyo para trabajar con otros equipos para la corrección de unidad. Los mejores candidatos para la calidad de los pesos suele ser el propietario del servicio de atención al cliente, que, según el tamaño y la complejidad de la organización, podría ser cualquier persona o grupo que es entusiastas acerca de la experiencia del usuario.

La calidad de los pesos aprovecha las herramientas existentes y procesos documentados, como el panel de calidad de llamadas (CQD) y la calidad de experiencia guía para la revisión, para supervisar la experiencia del usuario, identifican las tendencias de calidad y corrección de la unidad donde sea necesario. La calidad de los pesos funciona con los equipos respectivos a las acciones de corrección de unidad, informes a un Comité de dirección de su progreso y problemas pendientes.

Las tareas y actividades asociadas a la función se han documentado en la Guía de operaciones. Este rol debe asignarse durante la [fase de planeación](https://aka.ms/SkypeToTeams-Plan). Un paso en la función de los pesos pesados calidad en marcha la clave es obtener los conocimientos necesarios para la función y garantizar los requisitos previos se encuentran disponibles para ofrecer en las tareas. Una tarea clave para esta función se está ejecutando una revisión regular de la experiencia de calidad.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introducción a la Guía de revisión de la experiencia de calidad

La Guía de revisión de calidad de experiencia tiene un conjunto de actividades que evaluar y se proporcionan instrucciones de corrección en áreas clave que tienen el mayor impacto para mejorar la experiencia del usuario tal como se muestra en la figura siguiente.

![Un diagrama que ilustra las áreas clave que se examinan durante una revisión de la experiencia de calidad.] (media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Un diagrama que ilustra las áreas clave que se examinan durante una revisión de la experiencia de calidad.")

Al continuamente evaluar y solucionar relativos a las áreas que se describen en este documento, puede reducir su potencial de afectar negativamente a la experiencia del usuario. Mayoría de experiencia de usuario los problemas encontrada en una implementación puede agruparse en las siguientes categorías:

-   Configuración de firewall o proxy incompleto

-   Cobertura Wi-Fi deficiente

-   Ancho de banda insuficiente

-   VPN

-   Uso de dispositivos de audio integrados o no optimizados

-   Subredes problemáticas o dispositivos de red

Las instrucciones proporcionadas en la Guía de revisión de calidad de experiencia se centra en uso en pantalla de panel de calidad de llamadas (CQD) como la principal herramienta para notificar e investigar cada área que se ha descrito, con un enfoque en audio para maximizar la adopción y el impacto. Cualquier optimizaciones realizadas a la red para mejorar la experiencia de audio traducirá también directamente a las mejoras en uso compartido de escritorio y de vídeo.

Se recomienda encarecidamente que se nombra al Campeón de calidad desde el principio. Después de que se ha designado, debe comenzar a familiarizarse con el contenido de la Guía de revisión de la experiencia de calidad.

La Guía de revisión de calidad de experiencia puede encontrarse [aquí](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Planeación de la calidad de la red 

Planear la calidad de la red será el foco de la siguiente sección.

![Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la red.] (media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la red.")

Como se mencionó, planeación de calidad de la red antes de incorporación a Microsoft Teams es crítica. Para obtener más instrucciones para la preparación de la red, vea [Preparar la red de su organización para que los equipos de Microsoft](prepare-network.md).

En la mayoría de las organizaciones, las redes pueden conforman redes administradas y no administradas.

Redes administradas son componentes de la infraestructura de red que una organización tiene control directo sobre. Como resultado, redes administradas tienen un efecto directo sobre la calidad que se puede proporcionar a las cargas de trabajo de tráfico en tiempo real.

Por el contrario, las redes no administradas son segmentos de la red que un cliente no ha limitado controles, o, más.

Conexiones a Internet entre la organización y Office 365 son redes donde un cliente dispone de control limitado. Las redes son administradas por un ISP, pero las organizaciones puedan influir en la calidad de la red mediante la actualización de su ancho de banda, abogan por para las optimizaciones de ruta, o, si se produce un error en todo lo demás: cambiar de ISP.

Redes particulares o en hoteles o cafeterías son ejemplos de redes donde un cliente no tiene control.

En las secciones siguientes, nos centraremos en los requisitos de calidad de redes administradas.

### <a name="key-network-planning-areas"></a>Planeación de áreas de red clave

En las secciones siguientes se centran en las áreas importantes para la entrega de una red de alta calidad.

> [!NOTE]
> Muchas redes evolucionan con el tiempo debido a las actualizaciones, la expansión u otros requisitos empresariales. Asegúrese de que tiene los procesos operativos en contexto a mantener estas áreas como parte de la planeación de la administración de servicio.

#### <a name="bandwidth"></a>Ancho de banda

Planeación de ancho de banda es un aspecto fundamental de la actividad de preparación de la red. Asegurarse de que hay suficiente ancho de banda para las cargas de trabajo de Microsoft Teams es imprescindible. Para poder derecha-tamaño de una red existente, debe comprender lo que actualmente aprovisionado, la utilización actual, y, en última instancia, el ancho de banda disponible restante.

Para medir el uso actual, es necesario supervisar la red. A continuación, se puede usar esta medida como el punto de partida para la planeación de ancho de banda. Además, durante la implementación y después de la implementación para asegurarse de que la red está aprovisionada suficientemente debe supervisarse de forma continua la red.

> [!NOTE]
> Cuando se supervisa el uso de la red, es importante evitar el uso de promedios sobre el día. Estos promedios pueden incluir horas que no sean principales que contraer el resultado. Promedios pueden ocultar períodos de máximo y enmascarar un problema subyacente.

El [Organizador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) le ayudará a determinar y organizar los requisitos de red para la implementación en unos pocos pasos sencillos. Mediante el uso de la herramienta para recopilar detalles de red y el uso de voz en la nube de su organización, puede obtener un cálculo aproximado de los requisitos de red aquí necesite para la implementación de voz en la nube, administrar y exportar estos detalles para la creación de informes y ver las áreas para una mayor investigación y pasos siguientes.

#### <a name="quality-of-service-qos"></a>Calidad de servicio (QoS)

QoS debe implementarse en todos los segmentos de la red administrada, incluso las redes que ya han aprovisionados adecuadamente de ancho de banda. En este último caso, QoS actúa como una mitigación de riesgos en el caso de carga de red consecuencias. Cuando se implementa QoS, el tráfico de voz le dará prioridad para que estos eventos consecuencias no afectan a la calidad.

Una implementación de QoS debe incluir las áreas de la red, desde el punto final hasta los puntos de salida y de los puntos de salida al extremo. Esto le permitirá garantizar que se va a prioriza el tráfico de voz en ambas direcciones. QoS debe implementarse en ambos con cable y redes Wi-Fi.

Para la implementación de QoS en la red, las siguientes instrucciones pueden ayudar a [Calidad de servicio en los equipos de Microsoft](qos-in-teams.md)

#### <a name="proxy-servers"></a>Servidores proxy

Muchas organizaciones ven el tráfico dirigido a internet como un riesgo de seguridad, y pueden mitigar este riesgo mediante la supervisión y evaluación de tráfico en los puntos de salida en la red. Los servidores proxy son una clase de dispositivos que se pueden implementar para satisfacer este requisito.

Un servidor proxy puede provocar problemas al realizar la inspección de paquetes o modificación de la carga. Esto puede provocar errores en la instalación, llamadas interrumpidas y calidad de llamadas deficientes de llamadas. Si se fuerza la multimedia en tiempo real para atravesar un servidor proxy, se forzará la conmutación por recuperación TCP, que puede reducir aún más la calidad de la pila de medios en los equipos. UDP siempre se prefiere a través de TCP.

Además, un servidor proxy no puede estar diseñado para controlar la carga adicional de Office 365 y cargas de trabajo de Microsoft Teams específicamente, incluidos los medios en tiempo real.

Debido a los posibles problemas que puede presentar un servidor proxy y estos problemas de capacidad adicional, Microsoft recomienda no usar el servidor proxy y realizar una conexión directa a Office 365.

La configuración necesaria para omitir el servidor proxy varía entre los proveedores, pero el enfoque común normalmente implica la actualización del archivo de proxy (PAC) la configuración automática. El archivo PAC es un archivo de configuración que describe qué tráfico circula a través del proxy y el tráfico que pasa por alto.

Algunos proveedores de servidores proxy proporcionan un proceso automatizado para garantizar la configuración está actualizado. Si el proveedor no proporciona este proceso automático, puede descargar un archivo PAC actualizado desde <https://aka.ms/o365proxies>.

[Servidores proxy de Skype para empresas en línea y los equipos](/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>Firewalls

Asegurarse de que los protocolos y puertos derecho están abiertos a todas las direcciones URL y Office 365 IP es necesario para obtener acceso a Microsoft Teams. También es fundamental para una implementación de alta calidad. Basta con realizar una llamada o unirse a una llamada de conferencia no es suficiente para garantizar que el servidor de seguridad está configurado correctamente.

Si sólo TCP se abre en el servidor de seguridad, se establecerá la sesión, pero no se puede negociar el transporte preferido (UDP). TCP y UDP deben estar abiertos en el firewall para proporcionar la mejor experiencia de usuario.

Debido a su naturaleza con seguimiento de estado, TCP no está preferido para multimedia en tiempo real y sólo se proporciona como un transporte de red de la conmutación por recuperación para Microsoft Teams. Con TCP, si no hay retraso de paquete o pérdida de paquetes, esos paquetes deben ser retransmitidos hasta que está confirmados. Esto se puede producir en los paquetes multimedia que ya no son relevantes que compiten con la entrega puntual de los paquetes de multimedia actual. Cliente de los equipos del usuario intenta expandir el audio y puede producir artefactos audibles según las condiciones de red. Con la sobrecarga adicional de TCP, puede desplazar una experiencia generalmente aceptable para una experiencia de usuario deficiente. Por este motivo, se requiere el transporte de red sin estado UDP.

Se proporcionan instrucciones completas para abrir el firewall para Microsoft Teams en el artículo de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips) .

Después de abre el servidor de seguridad, puede usar la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para validar la conectividad de las capacidades de voz en la nube.

> [!IMPORTANT]
> Las direcciones URL y Microsoft Office 365 IP cambiará a través del tiempo. Como parte de la planeación del servicio de administración, es importante garantizar un proceso operativo está en su lugar y un grupo es responsable de supervisar [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips) y realizar actualizaciones según corresponda.

#### <a name="local-internet-egress"></a>Salida de internet local

Muchas redes se diseñaron para usar un concentrador y radio de topología. En esta topología, el tráfico de internet recorre normalmente la WAN a un centro de datos central antes de que se desprende (egresses) a internet. A menudo, esto se realiza para centralizar los dispositivos de seguridad de red con el objetivo de reducir los costos generales.

Back-tomando el tráfico a través de la WAN aumenta la latencia y tiene un impacto negativo en la calidad y la experiencia del usuario. Debido a que Microsoft Teams se ejecuta en la red global grandes de Microsoft, a menudo es una ubicación de interconexión de red más cercano al usuario. Un usuario es muy probable que va a obtener un mejor rendimiento por egressing fuera de un punto de internet local cerca de su ubicación y sesión en nuestra red optimizado para voz tan pronto como sea posible. Para algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar el tráfico a la más cercana del servidor front-end. En estos casos, es importante que cuando se utiliza un punto de salida local, se corresponde con la resolución DNS local.

Optimización de la ruta de acceso de red a red global de Microsoft va a mejorar el rendimiento y en última instancia proporcionar la mejor experiencia para los usuarios. Para obtener más detalles, consulte el blog [Introducción la mejor conectividad y rendimiento en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

Las redes privadas virtuales proporcionan un servicio valioso para muchas organizaciones. Desafortunadamente, normalmente no se ha diseñado ni se configurado para admitir multimedia en tiempo real. Algunas redes privadas virtuales también podrían no admitir UDP. Las redes privadas virtuales también presentan un nivel adicional de cifrado sobre el tráfico de medios ya cifrados. Además, la conectividad con el servicio de Microsoft Teams podría no ser eficaz debido a la fijación de cursor en forma de tráfico a través de un dispositivo VPN. Además, no están necesariamente diseñados desde una perspectiva de la capacidad para dar cabida a las cargas anticipadas que requieren los equipos.

La recomendación es proporcionar una ruta de acceso alternativa que omite la VPN para el tráfico de los equipos. Normalmente, esto se conoce como división túnel VPN. División tunelización significa que el tráfico para Office 365 no atravesará la VPN pero vaya directamente a Office 365. Este cambio tendrá un impacto positivo en calidad, pero también proporciona la ventaja secundaria de reducir la carga de los dispositivos VPN y la red de la organización.

Para implementar un túnel dividido, póngase en contacto con su proveedor de VPN para los detalles de configuración.

#### <a name="wi-fi"></a>Wi-Fi

Al igual que VPN, redes Wi-Fi no necesariamente están diseñadas o configuradas para admitir la media de tiempo real. Planeación de u optimización, una red Wi-Fi para equipos de soporte técnico es una consideración importante para una implementación de calidad.

Hay varios factores que se precie para optimizar una red Wi-Fi.

-   Implementación de QoS o Multimedia Wi-Fi (WMM) para asegurarse de que el tráfico de medios se Introducción prioriza según corresponda a través de las redes Wi-Fi.

-   Planeación y optimización de la W-Fi bandas y el acceso de punto de colocación. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada según la posición del punto de acceso, pero los puntos de acceso a menudo se ven afectados por otros dispositivos del consumidor que operan en ese intervalo. El intervalo de 5 GHz se adapta mejor a medios en tiempo real debido a su intervalo denso, pero requiere más puntos de acceso para obtener la cobertura suficiente. Los extremos también deben admitir dicho rango y configurarse para aprovechar las bandas en consecuencia.

-   Si se implementan redes Wi-Fi de banda dual, considere la posibilidad de implementar el control de banda. El control de banda es una técnica de implementada por proveedores de Wi-Fi para influir en los clientes de banda dual para utilizar el intervalo de 5Ghz.

-   Superposición de canal – cuando los puntos de acceso del mismo canal son demasiado juntos puede provocar la superposición de señal y compiten por equivocación, lo que resulta en una mala experiencia para el usuario. Asegúrese de que el punto de acceso que están junto a los demás están en canales que no se superpongan.

Cada proveedor inalámbrico tiene sus propias recomendaciones para la implementación de su solución inalámbrica. Se recomienda que consulte a su proveedor para obtener instrucciones específicas.

### <a name="network-readiness-assessment"></a>Evaluación de preparación de la red

Parte de las actividades de preparación de la red incluye una evaluación de la red. Una vez completada la configuración y la planeación, la evaluación puede proporcionarle una descripción de línea de base de la calidad de la red antes de que los usuarios incorporados a Microsoft Teams. Los resultados de la evaluación le ayudará también a identificar y asignar prioridades a los esfuerzos de corrección antes de habilitar a los usuarios para los equipos.

La evaluación de la red debe realizarse en ambos con cable y redes Wi-Fi para todos los edificios que se están habilitados para la nube capacidades de voz en los equipos.

La evaluación de la red se puede llevar a cabo mediante el uso de la [herramienta de evaluación de la red de Microsoft](https://www.microsoft.com/download/details.aspx?id=53885), las herramientas de terceros o un socio de Microsoft. También proporcionamos más instrucciones acerca de cómo realizar la evaluación mediante la herramienta de evaluación de la red de Microsoft como parte de nuestra guía de preparación [aquí](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11).

## <a name="plan-for-endpoint-quality"></a>Planeación de la calidad de extremo

Tal y como se puede ver en el diagrama siguiente, los extremos son un bloque de creación importante en proporcionar una experiencia de alta calidad para los usuarios.

![Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en los extremos.] (media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagrama que ilustra los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en los extremos.")

Los extremos de Microsoft Teams pueden ejecutarse en muchos dispositivos, incluidos PCs, Mac, tabletas y dispositivos móviles. Parte de la experiencia no sólo abarca el dispositivo, pero cómo un usuario se conecta al dispositivo — por ejemplo, mediante el uso de un auricular con micrófono optimizada, auriculares o micrófono o altavoz integrado del dispositivo. Uso de un auricular con micrófono optimizada puede enriquecer la experiencia global del usuario.

Las siguientes instrucciones acerca de cómo planear el extremo le ayudará a asegurarse de que su organización tiene una incorporación correcta de experiencia con los equipos.

### <a name="endpoint-capability"></a>Capacidad de extremo

Es la primera parte de la planeación para asegurarse de todos los equipos y otros dispositivos de la organización pueden ejecutar Microsoft Teams. Esto implica que no solo con mirar los requisitos de hardware, pero también descripción lo está haciendo el PC en segundo plano. Muchas organizaciones ejecutan otro software, incluidos los sistemas de detección de intrusiones y el software antimalware, que puede afectar al rendimiento de un dispositivo de base.

Microsoft Teams tiene clientes disponibles para escritorio, web (Windows y Mac) y mobile (Android, iOS y Windows Mobile). Para obtener información acerca de los requisitos de software para cada plataforma, vea [obtener los clientes de equipos de Microsoft](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls de extremo

Firewalls de cliente pueden tener un impacto significativo en la experiencia del usuario. Firewalls de cliente pueden afectar a la calidad de las llamadas además de impedir una llamada desde el que se establezca. Configure las exclusiones adecuadas en el firewall de cliente según la información de [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips). Su proveedor de terceros tendrá instrucciones específicas sobre cómo crear las exclusiones.

> [!NOTE]
> Microsoft Teams se actualizará automáticamente el Firewall de Windows con una configuración de firewall adecuados.

### <a name="wi-fi-recommendations-for-endpoints"></a>Recomendaciones de Wi-Fi para extremos

Planeación e implementación de una red Wi-Fi optimizada para admitir las cargas de trabajo en tiempo real en Microsoft Teams requiere planeación significativo. En las secciones siguientes proporcionan algunas instrucciones generales que pueden ayudarle a evitar algunos problemas comunes al planear los extremos.

#### <a name="wi-fi-drivers"></a>Controladores de Wi-Fi

Algunos controladores Wi-Fi pueden ser un inconveniente. Por ejemplo, un controlador podría tener muy agresivos comportamientos de movilidad entre puntos de acceso, lo que provoca que la calidad de llamada deficiente. Esto no es algo común, pero es importante para asegurarse de que se han actualizado y probarse antes de la implementación controladores Wi-Fi en su PC.

#### <a name="wi-fi-bands"></a>Bandas Wi-Fi

Existen principalmente dos tipos de bandas utilizadas en Wi-Fi equipamiento hoy en día, 2,4 GHz y 5,0 GHz. Si su organización proporciona ambas bandas, debe configurar la configuración del controlador para prefiere la banda GHz 5.0. Esta banda es mucho más densa en términos de rendimiento y es menos afectados por la interferencia que se puede apreciar en la banda de 2,4 GHz. Esta recomendación se da por supuesto que ha optimizado correctamente la banda de red GHz 5.0.

#### <a name="wi-fi-radio-type"></a>Tipo de radio Wi-Fi

Planeación de dispositivos que admiten los tipos de radio Wi-Fi más reciente. Puede obtener un rendimiento muy bueno Wi-Fi si se aprovecha la 802.11ac o posterior en los dispositivos que aprovisiona.

#### <a name="wireless-avoidance"></a>Prevención de inalámbrica

Algunas organizaciones prefieren evitar por completo la Wi-Fi. En ocasiones, esta guía se proporciona a través de una recomendación a los usuarios conectarse directamente a una red por cable. En algunos casos, el orden de enlace de red podría tener la conexión inalámbrica preferida y seguir usando esa conexión, aunque el equipo esté conectado a la conexión por cable. Para evitar este comportamiento imprevisto, configure el orden de enlace para evitar este escenario.

#### <a name="80211-power-save-protocol"></a>Protocolo de ahorro de energía 802.11

Si su organización utiliza puntos de acceso inalámbrico o los enrutadores que no admiten la energía 802.11 guardar protocolo, es posible que experimente llamadas interrumpidas o calidad de llamadas deficientes en Teams Microsoft que se ejecutan en los dispositivos de Windows. Si no es posible actualizar el punto de acceso inalámbrico o los enrutadores, deberá actualizar la configuración del Plan de energía de Windows en los dispositivos que se ejecutan en energía de la batería. Se proporcionan instrucciones de detalle y la configuración adicional en el siguiente [artículo de soporte técnico](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Dispositivos de los equipos

Microsoft Teams se puede usar para las reuniones o como un sistema telefónico. Al usar estas características, el dispositivo de interfaz que se usa para los equipos desempeña un papel importante en la experiencia del usuario.

Es posible que sonido aceptable para el usuario que tiene que la configuración con un altavoz de PC y un micrófono integrado. Pero normalmente esos dispositivos no están optimizados para cancelación de ruido y cualquier tipo de ruido ambiente puede tener un impacto dirección descendente en otros en la llamada. Aprovechamiento de dispositivos optimizados para estos escenarios le ayudará a garantizar una experiencia de alta calidad.

Cada dispositivo necesita satisfacer las necesidades de los usuarios. Debe adaptar los dispositivos como los auriculares con micrófono para las diferentes personas y casos de uso en su organización. Un ejercicio de asignación de rol para el dispositivo debe realizarse como parte del proceso de planeación.

Después de seleccionar los dispositivos, incluir en el plan de pruebas piloto para la validación final. Aproveche encuestas durante la prueba piloto a recopilar comentarios para asegurarse de la estrategia de dispositivo es óptimo.

En este momento, se recomienda usar dispositivos de audio que se han certificado a través de la Skype para el programa de certificación empresarial. Para buscar los dispositivos certificados bajo este programa, consulte el catálogo de soluciones [Certificadas de dispositivos USB de Skype para la empresa](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

Para obtener más información, vea [dispositivos - taller de preparación y clientes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>Actualizaciones de clientes

Uno de los beneficios clave de Microsoft Teams es que el cliente se mantiene actualizado automáticamente. Los clientes en el PC y Mac se actualizan mediante el uso de un proceso en segundo plano que comprueba para las versiones nuevas y descarga al nuevo cliente cuando la aplicación está inactiva. El tamaño de descarga del cliente es aproximadamente 100 MB.

Una organización no tiene ningún control o acceso a una configuración de directiva para administrar el proceso de actualización. Para mitigar el riesgo de que un problema en el que es posible que se encuentra en una compilación más reciente, la última versión buena conocida se mantiene en el extremo. Si hay un problema con la nueva versión, el servicio de Microsoft Teams puede revertir automáticamente el extremo a la versión anterior.

## <a name="next-steps-and-references"></a>Siguientes pasos y referencias

En esta tabla se incluye un resumen de las actividades de planeación con vínculos a contenido relacionado.

| Área | Detalles | Referencias |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Plan para la administración de servicio | Llevar a cabo un ejercicio de asignación de rol operativas <br/> Firma de equipos responsables <br/> Preparación de roles | [Guía de operaciones](1-drive-value-operate-my-service.md) |
| | Sea propietaria Champion(s) de calidad <br/> Preparación de campeones de calidad| [Obtenga información sobre CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Consulte la Guía de experiencia calidad](https://aka.ms/qerguide) |
| | Instalar las plantillas de revisión de la experiencia de calidad <br/> Cargar un archivo de creación | [Plantillas de QERLite](https://aka.ms/qertemplates) <br/> [Información de creación de carga](turning-on-and-using-call-quality-dashboard.md)|
| Planeación de la calidad de la red | Ejecute el organizador de la red | [Organizador de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Implementar QoS | [Calidad de servicio en los equipos de Microsoft](qos-in-teams.md) |
| | Omita los servidores proxy | [Instrucciones de proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ad=US#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies) |
| | Implementar dividido túnel VPN | [Instrucciones de túnel dividido VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Optimizar las redes Wi-Fi para multimedia en tiempo real  | Consulte a los proveedores de terceros |
| | Implementar la salida de internet local | [Salida de Internet local](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implementar la conectividad de red <br/> Validar la conectividad de red | [Direcciones IP y URL de Office 365](https://aka.ms/o365ips) |
| | | [Herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885) |
| | Realización de evaluación de la red | [Evaluación de disponibilidad de red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Planeación de la calidad de extremo | Actualizar los servidores de seguridad de extremo | [Direcciones IP y URL de Office 365](https://aka.ms/o365ips) |
| | Validar los requisitos de software | [Obtener clientes para Microsoft Teams](get-clients.md) |
| | Implementar las recomendaciones de extremo Wi-Fi | Consulte a los proveedores de terceros |
| | Rol de llevar a cabo en los dispositivos de asignación <br/> Aprovisionar dispositivos y prueba piloto ellos | [Cliente y dispositivos - taller de preparación](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Catálogo de dispositivo](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

Una vez haya terminado de planeación, continúe con el siguiente paso: [Preparar el entorno para los equipos](https://aka.ms/SkypeToTeams-TechnicalReadiness).