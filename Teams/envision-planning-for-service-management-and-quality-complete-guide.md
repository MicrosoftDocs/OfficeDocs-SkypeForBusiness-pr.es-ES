---
title: Plan para la Guía de administración de servicios para Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Ofrecen la experiencia de usuario de los equipos de alta calidad mediante la administración de extremo, la red y el servicio de salud y definición operativa y funciones de experto en calidad.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cccd06cd9bd5ee458497fbb41db56955bb9a5ee9
ms.sourcegitcommit: d70e5a5e7d05a2226c1d011895fb12187d73fad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2018
---
# <a name="plan-for-service-management-and-quality"></a>Plan de administración de servicios y calidad

Este documento es acerca de la fase de previsión para Teams de Microsoft.
 
## <a name="introduction"></a>Introducción

Este contenido se proporcionará una visión general de los requisitos que son necesarios para ofrecer y mantener una implementación de Microsoft Teams de alta calidad. Planificación para la gestión de servicio y calidad durante la fase de previsión, antes de su primera implementación piloto o de producción para garantizar una implementación exitosa.

La guía se divide en las siguientes secciones:

-   En primer lugar, es una visión general de la experiencia del usuario y los componentes clave que respaldan la calidad. Esto resalta las áreas centrarse en antes de la incorporación de Microsoft Teams.

-   En segundo lugar, se dan orientaciones para el diseño de un modelo de soporte para administrar Microsoft Teams antes de la primera implementación de usuario piloto o de producción. Esta sección describe las tareas que deben realizarse regularmente para mantener una implementación de equipos de calidad. Además, esta sección presenta más orientación que puede utilizar para comenzar a entender y el ejercicio de estas tareas.

-   Orientación específica, tercer ayuda con la planificación de la red y los extremos de la organización a Microsoft Teams de soporte técnico.

-   Por último, pasos a seguir se resumen con referencias a contenido relacionado.

## <a name="key-components-that-affect-user-experience"></a>Componentes clave que influyen en la experiencia de usuario

En esta sección, se examinarán los componentes clave que influyen en la experiencia de usuario. Antes de revisar los componentes clave, es fundamental comprender la experiencia del usuario y su importancia en la consecución de los objetivos de negocio de su organización. Analicemos cómo definimos la experiencia del usuario en primer lugar.

### <a name="user-experience-defined"></a>Experiencia de usuario definida

Objetivos empresariales pueden llevarse a cabo al implementar Microsoft Teams y comunicaciones de incorporar en sus procesos empresariales para mejorar su flujo de trabajo. Calidad impulsa la adopción y uso: si su organización ofrece un servicio de alta calidad que encanta a personas, personas y equipos pueden ganar la confianza y encontrar maneras nuevas e innovadoras de utilizar el servicio que impulsan los beneficios para el negocio.

En el corazón de esto es la experiencia del usuario con los equipos, las emociones y actitudes hacia el servicio de la persona. ¿Así que lo que contribuye a la experiencia del usuario? Que oscila entre los usuarios saber utilizar equipos e incorporarla en su trabajo diario experimenta calidad de sonido excepcional y ser capaz de conectarse de forma fiable, independientemente de dónde estén. Experiencia del usuario es muy amplia en la naturaleza; Este documento se centra sólo en aquellos elementos que pueden ser controlados por la organización.

Existen requisitos específicos para la implementación que son de importancia crítica para ofrecer una experiencia de usuario fantástica — especialmente al uso de la voz de nube características en equipos. Es fundamental para tratar Teams de Microsoft como un ciudadano de primera clase con otras inversiones de comunicación y colaboración, dar prioridad al tráfico en tiempo real en consecuencia. En la siguiente sección proporciona una visión general de los componentes clave que influyen en la experiencia de usuario. En más secciones, le ofrecemos orientación sobre cómo comenzar a planear implementar y mantener los componentes clave que comprenden la calidad.

### <a name="key-components-of-quality"></a>Componentes clave de la calidad

Una organización o un socio auxiliar debe empezar por planear para tres componentes clave durante la fase de previsión de una implementación de equipos: servicio de administración de red y extremos. La combinación de las tres áreas es fundamental para la calidad de la experiencia del usuario.

![Esquema que describe los componentes de calidad y cómo administración de servicios superpone a todos los componentes de 3 3.](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png)

#### <a name="service-management"></a>Administración de servicios

Administración de servicios puede dividirse en dos categorías distintas de responsabilidad:

-   **Responsabilidad de Microsoft**. Microsoft es responsable de los componentes de infraestructura que comprende el servicio Office 365. Microsoft es responsable ante los clientes para asegurarse de que cualquiera de sus usuarios que se conectan a los equipos se proporciona un rendimiento fiable y de alta calidad.

-   **Responsabilidad del cliente**. Usted y su organización están responsables de administrar diversos aspectos del servicio Office 365, red local y extremos del usuario. Por ejemplo, cuando se agregan nuevas direcciones IP a Office 365, debe actualizar los servidores de seguridad adecuados para permitir la comunicación a los extremos para evitar la interrupción de usuario nuevo.

Para obtener instrucciones detalladas para la planificación de la administración de servicio, vea [Planear la administración de servicios](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-service-management).

#### <a name="network"></a>Red 

En la mayoría de las organizaciones, las redes se diseñaron inicialmente para proporcionar acceso a datos y aplicaciones que residía en sus centros de datos. Aplicaciones basadas en la nube como Office 365 requieren cambios en estas redes para admitir los nuevos flujos de datos y el acceso que requiere de equipos. Antes de poder habilitar a los usuarios para los equipos en su organización, debe evaluar y optimizar la red actual. Esto es muy importante cuando aprovechando las capacidades de voz de la nube.

En las redes tradicionales, los usuarios necesitarán recorrer las redes perimetrales de una organización para tener acceso a los equipos. Muchas organizaciones tienen dispositivos de seguridad como servidores proxy, firewalls y VPN que pueden bloquear, obstaculizar o proporcionar una ruta de acceso no optimizada para el tráfico de red.

Además, las redes internas del núcleo deben ser optimizados y adecuada para proporcionar calidad y capacidad suficientes para soportar las cargas de trabajo de equipos, incluidos los medios de comunicación en tiempo real. Puede utilizar planificación, corrección, el ancho de banda y optimización para ayudar a asegurar la red proporciona una ruta de acceso eficiente y de alta calidad a Office 365.

Para obtener instrucciones detalladas acerca de la planificación de una red, vea [Planear la calidad de la red](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-network-quality).

#### <a name="endpoints"></a>Puntos de conexión

Teams de Microsoft admite una variedad de extremos. Desde equipos para tabletas de teléfonos, puede tener acceso los equipos en cualquier lugar desde prácticamente cualquier dispositivo.

Para ofrecer a los usuarios la mejor experiencia posible, debe tener en cuenta estos aspectos importantes durante la fase de previsión: ¿los extremos cumplen los requisitos de hardware y software de los equipos? ¿Ha configurado y optimizado extremos para admitir redes Wi-Fi? ¿Los dispositivos que utilizará para realizar y recibir llamadas de voz? ¿Dichos dispositivos optimizados para equipos?

Para obtener instrucciones detalladas acerca de la planificación de extremo, vea [Planear la calidad del extremo](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Plan de administración de servicios

Administración de servicios es un tema muy amplio que abarque las operaciones diarias del servicio Teams de Microsoft después de que se ha implementado y habilitado para los usuarios. El servicio de equipos incluye Microsoft Office 365 y los componentes de infraestructura que implementan en locales (por ejemplo, redes).

El concepto de administración del servicio no es probablemente un nuevo concepto para la mayoría de las organizaciones. Probablemente ya ha implementado los procesos y tareas que están asociadas con servicios existentes. Dicho esto, probablemente puede aumentar lo que tiene en su lugar al planear la administración del servicio de hoy admitir Microsoft Teams en el futuro.

Administración del servicio abarca todas las actividades y los procesos implicados en la administración integral de Microsoft Teams. Tal como se describe anteriormente, algunos de los componentes de administración de servicios: los componentes de infraestructura que comprende el propio servicio Office 365, son responsabilidad de Microsoft, mientras que el cliente es responsable de sus usuarios para administrar los diversos aspectos de los equipos, el red y extremos que se proporcionan. En esta sección del documento se centrará en la responsabilidad del cliente desde una perspectiva de administración de servicio.

![Esquema que describe los componentes de calidad y cómo administración de servicios superpone a todos los componentes de 3 3. Con un enfoque en la administración de servicios.](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png)

### <a name="introduction-to-the-operations-guide"></a>Introducción a la Guía de operaciones 

**¿Qué**, **quién**y **cómo** son tres preguntas importantes que necesitan ser respondidas en cuanto a la administración de servicios.

Puede utilizar a la Guía de operaciones [Link to Operations Guide] para ayudarlo a enfrentar los tres de estas preguntas. La guía proporciona una lista de actividades que se realizará en forma diaria, semanal, mensual y según sea necesario. Estas actividades y tareas son esenciales para el mantenimiento de una implementación de equipos de alta calidad. Determinar quién será responsable de realizar actividades específicas en la administración de servicios es un aspecto fundamental de la planeación debe hacer temprano en la fase de previsión para garantizar una implementación satisfactoria. Una vez se haya imaginado las tareas y actividades, deben ser entendido y seguido por los grupos o individuos a los que se les asigne. La Guía de operaciones proporciona los conocimientos y orientación sobre cómo realizar cada una de las tareas, o referencias a contenido externo.

### <a name="operational-role-mapping"></a>Asignación de funciones operacionales

Planear la administración de servicio temprano es un hito crítico, porque la fase de operaciones comienza cuando se habilitan los primeros usuarios piloto. El equipo del proyecto debe revisar y acordar las tareas y actividades necesarias, identificar el equipo que es responsable de cada tarea operativa, obtenga un compromiso y cierre de sesión de cada equipo respectivo.

Cuando cierre la sesión finalice, el equipo responsable debe iniciar el ejercicio de estas funciones y responsabilidades. Esto podría incluir la formación y preparación, actualización del modelo de personal, o garantizando que los socios externos están listos para entregar.

Asignar funciones operativas temprano en la fase de previsión permite todos los equipos iniciar sus tareas operativas durante la prueba piloto y operaciones de impulso y asegúrese de que todo está listo, después de la implementación.

La Guía de operaciones proporciona una lista de tareas comunes que se asignan a funciones típicas que deben ser válidas en la mayoría de los escenarios. Debe personalizar estas responsabilidades para su organización.

### <a name="the-quality-champion-role"></a>La función de calidad experto

Un grupo o individual debe ser responsable de la calidad en todas las organizaciones. Esto es el papel más importante en la administración de servicios. El experto de calidad es una función de cliente que se asigna a una persona o grupo que es un apasionado de la experiencia de sus usuarios. Esta función requiere los conocimientos necesarios para identificar tendencias en el entorno y el patrocinio para trabajar con otros equipos de la unidad de corrección. El mejor candidato para el Campeón de calidad suele ser el propietario del servicio al cliente, que, según el tamaño y la complejidad de la organización, puede ser cualquier persona o grupo que es un apasionado de la experiencia del usuario.

El experto de calidad aprovecha las herramientas existentes y procesos documentados, como el panel de calidad llamar (CQD) y la Guía de revisión de experiencia de calidad, para controlar la experiencia del usuario, identifican tendencias de calidad y corrección de la unidad donde sea necesario. El experto de calidad funciona con los equipos correspondientes a las acciones de corrección de unidad, informar a un Comité de dirección de su progreso y problemas abiertos.

Las tareas y actividades asociadas a la función se han documentado en la Guía de operaciones. Esta función debe asignarse a principios de la fase de previsión. Un paso clave en el ejercicio de la función de calidad experto está adquiriendo los conocimientos necesarios para la función y garantizar los requisitos previos estén en su lugar para entregar en las tareas. Una tarea clave para esta función está ejecutando una revisión regular de experiencia de calidad.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introducción a la Guía de revisión de experiencia de calidad

La Guía de revisión de calidad de experiencia tiene un conjunto de actividades que evaluar y proporcionar orientaciones sobre correcciones en áreas clave que tienen el mayor impacto para mejorar la experiencia del usuario como se muestra en la figura siguiente.

![Un diagrama que indica las áreas clave que se examinan durante una revisión de la experiencia de calidad.](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png)

Continuamente evaluar y remediar las zonas descritas en este documento, podrá reducir su potencial de afectar negativamente a la experiencia del usuario. Problemas de experiencia de usuario más encontrados en una implementación pueden agruparse en las siguientes categorías:

-   Configuración de firewall o proxy incompleto

-   Mala cobertura Wi-Fi

-   No hay suficiente ancho de banda

-   VPN

-   Uso de dispositivos de audio integrados o no optimizados

-   Subredes problemáticas o dispositivos de red

Las instrucciones proporcionadas en la Guía de revisión de experiencia de calidad se centra en usar Online llame calidad Dashboard (CQD) como herramienta principal para informar e investigar cada área descrita, con énfasis en audio para maximizar la adopción y el impacto. Se traducirá también directamente cualquier optimizaciones realizadas a la red para mejorar la experiencia de sonido a mejoras en el uso compartido de escritorio y vídeo.

Recomendamos encarecidamente que se nombra al Campeón de calidad desde el principio. Después de que se ha designado, deberían empezar a familiarizarse con el contenido de la Guía de revisión de experiencia de calidad.

La Guía de revisión de calidad experiencia puede encontrarse [aquí](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true).

## <a name="plan-for-network-quality"></a>Planear la calidad de la red 

Planear la calidad de la red será el enfoque de la sección siguiente.

![Esquema que describe los componentes de calidad y cómo administración de servicios superpone a todos los componentes de 3 3. Con un enfoque en la red.](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png)

Como se mencionó, planificación de calidad de la red antes de la incorporación de Microsoft Teams es crítica. Para obtener más información para la preparación de la red, vea [Preparar la red de su organización para los equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/prepare-network).

En la mayoría de las organizaciones, las redes pueden constar de redes administradas y no administradas.

Redes administradas son componentes de la infraestructura de red que una organización ejerce un control directo. Como resultado, redes administradas tienen una influencia directa sobre la calidad que puede proporcionarse a las cargas de trabajo de tráfico en tiempo real.

Por el contrario, las redes no administradas son los segmentos de la red que un cliente no ha limitado controles, o, más.

Conexiones a Internet entre la organización y Office 365 son redes donde un cliente dispone de control limitado. Las redes son administradas por un ISP, pero las organizaciones deben ser capaces de influir en la calidad de la red al actualizar su ancho de banda, abogar por las optimizaciones de ruta, o, si todo lo demás falla, cambiar de ISP.

Redes domésticas o redes en hoteles o cafeterías son ejemplos de redes donde un cliente no tiene control.

En las secciones siguientes, nos centraremos en los requisitos de calidad de redes administradas.

### <a name="key-network-planning-areas"></a>Las áreas de planificación de red clave

En las secciones siguientes se centran en las áreas importantes para la entrega de una red de alta calidad.

> [!NOTE]
> Muchas redes evolucionan con el tiempo debido a las actualizaciones, expansión u otros requisitos empresariales. Asegúrese de que tiene los procesos operacionales en su lugar para mantener estas áreas como parte de su plan de administración de servicio.

#### <a name="bandwidth"></a>Ancho de banda

Planificación de ancho de banda es un aspecto fundamental de la actividad de preparación de la red. Es imprescindible asegurarse de que hay suficiente ancho de banda para las cargas de trabajo de Microsoft Teams. Para poder ajustar correctamente una red existente, debe comprender lo que se está aprovisionado, la utilización actual, y, en última instancia, el ancho de banda disponible restante.

Para medir la utilización actual, debe supervisar la red. Esta medida puede utilizarse como punto de partida para el planeamiento de ancho de banda. Además, durante la implementación y después de la implementación para asegurarse de que la red se ha aprovisionado suficientemente debe supervisar de forma constante la red.

> [!NOTE]
> Al supervisar la utilización de la red, es importante evitar el uso de promedios durante el día. Los promedios pueden incluir horas complementarios que sesgar el resultado. Promedios pueden ocultar los períodos y enmascarar un problema subyacente.

El [Planificador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) le ayuda a determinar y organizar los requisitos de red para su implementación en pocos pasos sencillos. Mediante la herramienta para recopilar detalles de red y el uso de la voz de la nube de su organización, puede obtener un cálculo aproximado de los requisitos de red que necesitará para la implementación de voz de la nube, administrar y exportar estos detalles para reporting y ver las áreas para realizar una investigación adicional y los próximos pasos.

#### <a name="quality-of-service-qos"></a>Calidad de servicio (QoS)

QoS debe implementarse en todos los segmentos de la red gestionada, incluso redes configurados adecuadamente para el ancho de banda. En este último caso, QoS actúa como una mitigación del riesgo en caso de carga de red no previstos. Cuando se implementa QoS, se dará prioridad al tráfico de voz para que estos eventos no previstos no afectan a la calidad.

Una implementación de QoS debe incluir áreas de la red, desde el extremo hasta los puntos de salida y de los puntos de salida hacia el extremo. Esto asegurará que se que se priorice el tráfico de voz en ambas direcciones. QoS debe implementarse en ambos por cable y redes Wi-Fi.

Para implementar QoS en la red, las instrucciones siguientes pueden ayudar a [Calidad de servicio en equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)

#### <a name="proxy-servers"></a>Servidores proxy

Muchas organizaciones ven el tráfico destinado a internet como un riesgo de seguridad y pueden mitigar este riesgo mediante la supervisión y evaluación de tráfico en los puntos de salida en la red. Los servidores proxy son una clase de dispositivos que se pueden implementar para cumplir con este requisito.

Un servidor proxy puede presentar problemas al realizar la inspección de paquetes o de modificación de la carga. This can lead to call setup failures, dropped calls, and poor call quality. Si los medios de comunicación en tiempo real se ve obligado a atravesar un servidor proxy, se forzará la pila de multimedia en equipos no TCP, que puede reducir aún más la calidad. Siempre es preferible el UDP sobre TCP.

Además, un servidor proxy no puede estar diseñado para controlar la carga adicional de Office 365 y específicamente las cargas de trabajo Teams de Microsoft, incluidos los medios de comunicación en tiempo real.

Debido a los posibles problemas que puede presentar un servidor proxy y estas preocupaciones capacidad adicional, Microsoft recomienda omitir el servidor proxy y establecer una conexión directa a Office 365.

La configuración necesaria para omitir el servidor proxy varía entre los proveedores, pero el enfoque común normalmente implica la actualización del archivo de configuración automática (PAC) de proxy. El archivo PAC es un archivo de configuración que describe qué tráfico pasa a través del proxy y el tráfico que pasa por alto.

Algunos proveedores de servidor proxy proporcionan un proceso automatizado para asegurar la configuración está actualizado. Si el proveedor no proporciona este proceso automático, puede descargar un archivo PAC actualizado de <https://aka.ms/o365proxies>.

[Servidores proxy para Skype para negocios en línea y equipos](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>Firewalls

Garantizar que los protocolos y puertos derecha están abiertos a todas las direcciones URL y Office 365 IPs es necesaria para tener acceso a Teams de Microsoft. También es fundamental para una implementación de alta calidad. Basta con hacer una llamada o unirse a una llamada de conferencia no es suficiente para estar seguro de que el servidor de seguridad está configurado correctamente.

Si sólo TCP está abierto en el firewall, se establecerá la sesión, pero no se negocia el transporte preferido (UDP). TCP y UDP deben estar abiertos en el firewall para proporcionar la mejor experiencia de usuario.

Debido a su naturaleza con estado, TCP no es preferido para multimedia en tiempo real y sólo se proporciona como un transporte de red de conmutación por recuperación de Teams de Microsoft. Con TCP, si no hay retraso de paquete o pérdida, esos paquetes deben volverse hasta que están confirmadas. Esto puede resultar en paquetes de media que ya no son relevantes que compiten con la entrega oportuna de los paquetes de media actual. El cliente del usuario equipos intenta expandir el audio y puede producir artefactos audibles dependiendo de las condiciones de la red. Con la sobrecarga adicional de TCP, puede desplazar una experiencia generalmente aceptable para una experiencia de usuario pobre. Por este motivo, se requiere el transporte de red sin estado UDP.

Guía completa para abrir el firewall para Microsoft Teams se proporciona en el artículo de [Office 365 URL y los intervalos de direcciones IP](https://aka.ms/o365ips) .

Después de abre el servidor de seguridad, puede utilizar la [Herramienta de evaluación de red de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=53885) para validar la conectividad para capacidades de voz de la nube.

> [!IMPORTANT]
> Las direcciones URL y Microsoft Office 365 IPs cambiará con el tiempo. Como parte del planeamiento de la administración de servicio, es importante garantizar un proceso operativo está en su lugar y un grupo es responsable de supervisar [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://aka.ms/o365ips) y realizar actualizaciones en consecuencia.

#### <a name="local-internet-egress"></a>Salida de internet local

Muchas redes se diseñaron para utilizar un concentrador y radios de topología. En esta topología, el tráfico de internet recorre normalmente la WAN a un centro de datos central antes de que se desprende (corrales) a internet. A menudo, esto se realiza para centralizar los dispositivos de seguridad de red con el objetivo de reducir los costes generales.

Acarreo atrás el tráfico en la WAN aumenta la latencia y tiene un impacto negativo en la calidad y la experiencia del usuario. Como Teams de Microsoft se ejecuta en la red global grande de Microsoft, a menudo es una ubicación de interconexión de red más cercano al usuario. Un usuario probablemente obtendrá un mejor rendimiento por egressing fuera de un punto de internet local cerca de su ubicación y en nuestra red optimizado para voz tan pronto como sea posible. Algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar tráfico a la más cercana del servidor front-end. En estos casos, es importante que cuando se utiliza un punto de salida local, se corresponde con la resolución DNS local.

Optimización de la ruta de acceso de red a red global de Microsoft mejora el rendimiento y en última instancia, proporcionar la mejor experiencia para los usuarios. Para obtener más detalles, consulte el blog [obteniendo la mejor conectividad y performance en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

Redes privadas virtuales proporcionan un servicio valioso para muchas organizaciones. Por desgracia, están normalmente no diseñados o configurados para admitir los medios de comunicación en tiempo real. Algunas redes privadas virtuales también podrían no admitir UDP. Las redes privadas virtuales también introducen una capa adicional de cifrado sobre el tráfico de medios ya cifrados. Además, la conectividad con el servicio de Teams de Microsoft puede no ser rentable debido a la fijación de pelo tráfico a través de un dispositivo VPN. Furthermore, they are not necessarily designed from a capacity perspective to accommodate the anticipated loads that Teams will require.

The recommendation is to provide an alternate path that bypasses the VPN for Teams traffic. This is commonly known as split-tunnel VPN. Split tunneling significa que el tráfico para Office 365 no recorrerán la red VPN pero vaya directamente a Office 365. Este cambio tendrá un impacto positivo sobre la calidad, pero también ofrece la ventaja de reducir la carga de los dispositivos VPN y la red de la organización secundaria.

Para implementar un túnel dividido, consulte a su proveedor VPN para los detalles de configuración.

#### <a name="wi-fi"></a>Wi-Fi

Al igual que VPN, redes Wi-Fi no necesariamente son diseñadas o configuradas para admitir los medios de comunicación en tiempo real. Planear y optimizar, una red Wi-Fi para equipos de soporte técnico es una consideración importante para una implementación de calidad.

Hay varios factores que entran en juego para optimizar una red Wi-Fi.

-   Implementación de QoS o Multimedia Wi-Fi (WMM) para garantizar que el tráfico multimedia es obtener prioridad en consecuencia a través de las redes Wi-Fi.

-   Planificación y optimización de las bandas de conexión Wi-Fi y acceso punto de colocación. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada dependiendo de la posición del punto de acceso, pero los puntos de acceso con frecuencia se ven afectados por otros dispositivos que funcionen en ese intervalo. El intervalo de 5 GHz se adapta mejor a los medios de comunicación en tiempo real debido a su alcance con gran densidad pero requiere más puntos de acceso para obtener una cobertura suficiente. Extremos también deben soportar este espectro y configurarse para aprovechar esas bandas en consecuencia.

-   Si se implementan redes Wi-Fi de doble banda, considere la implementación de control de la banda. Banda de dirección es una técnica de implementada por proveedores de Wi-Fi para influir en los clientes de doble banda para utilizar el intervalo de 5Ghz.

-   Superposición de canal – cuando los puntos de acceso del mismo canal están demasiado juntos pueden provocar la superposición de señal y competir involuntariamente, dando como resultado una mala experiencia para el usuario. Compruebe que el punto de acceso que son contiguos en canales que no se superpongan.

Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. We recommend that you consult your vendor for specific guidance.

### <a name="network-readiness-assessment"></a>Evaluación de preparación de la red

Parte de las actividades de preparación de red incluye una evaluación de la red. Una vez completada la configuración y planificación, la evaluación puede proporcionarle un conocimiento de base de la calidad de la red antes de que los usuarios incorporados a Teams de Microsoft. Los resultados de la evaluación le ayudará también a identificar y asignar prioridades a los esfuerzos de corrección antes de habilitar los usuarios para los equipos.

The network assessment should be performed on both wired and Wi-Fi networks for all buildings that are being enabled for cloud voice capabilities in Teams.

The network assessment can be conducted by using a Microsoft partner, third-party tools, or the [Microsoft Network Assessment tool](https://www.microsoft.com/en-us/download/details.aspx?id=53885). We also provide further guidance on how to run the assessment using the Microsoft Network Assessment tool as part of our readiness guidance [here](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11)..

## <a name="plan-for-endpoint-quality"></a>Planear la calidad de extremo

As you can see from the diagram below, endpoints are an important building block in providing a quality experience for end users.

![Diagram describing the 3 components of quality, and how service management overlaps all 3 components. With a focus on Endpoints.](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png)

Extremos de Teams de Microsoft se pueden ejecutar en múltiples dispositivos, incluidos PCs, Mac, tabletas y dispositivos móviles. Parte de la experiencia no sólo incluye el dispositivo, pero ¿cómo un usuario se conecta al dispositivo, por ejemplo, utilizando el micrófono y altavoz incorporado del dispositivo, juego de auriculares o un auricular optimizado. Using an optimized headset can enrich the overall user experience.

La siguiente orientación acerca de cómo planear el extremo le ayudará a asegurarse de que su organización tiene una incorporación exitosa experiencia con los equipos.

### <a name="endpoint-capability"></a>Capacidad de extremo

Es la primera parte de la planificación asegurar los equipos y otros dispositivos de la organización pueden ejecutar Teams de Microsoft. Esto implica no sólo mirar los requisitos de hardware, pero también comprender lo que hace el PC en segundo plano. Many organizations run other software, including intrusion detection systems and antimalware software which can affect the base performance of a device.

Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Mobile). For information about the software requirements for each platform, see [Get Clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).

### <a name="endpoint-firewalls"></a>Endpoint firewalls

Firewalls de cliente pueden tener un impacto significativo en la experiencia del usuario. Firewalls de cliente pueden afectar a la calidad de las llamadas además de evitar una llamada desde que se estableció. Configure the appropriate exclusions on the client firewall based on the information in [Office 365 URLs and IP address ranges](https://aka.ms/o365ips). El proveedor tendrá instrucciones específicas sobre cómo crear las exclusiones.

> [!NOTE]
> Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.

### <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi recommendations for endpoints

Planning and deploying an optimized Wi-Fi network to support real-time workloads in Microsoft Teams will require significant planning. The following sections provide some general guidance that can help you avoid some common pitfalls when planning for endpoints.

#### <a name="wi-fi-drivers"></a>Wi-Fi drivers

Algunos controladores de Wi-Fi pueden ser problemáticos. As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality. Esto no es algo habitual, pero es importante garantizar que los controladores de Wi-Fi en el PC se han actualizado y probado antes de la implementación.

#### <a name="wi-fi-bands"></a>Wi-Fi bands

Existen principalmente dos tipos de bandas utilizadas en los equipos hoy en día, 2,4 GHz y 5,0 GHz Wi-Fi. If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band. This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band. This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.

#### <a name="wi-fi-radio-type"></a>Wi-Fi radio type

Plan for devices that support the newer Wi-Fi radio types. You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.

#### <a name="wireless-avoidance"></a>Wireless avoidance

Some organizations prefer to avoid Wi-Fi altogether. Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network. In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection. To avoid this unintended behavior, configure the binding order to avoid this scenario.

#### <a name="80211-power-save-protocol"></a>802.11 power save protocol

If your organization uses wireless access points or routers that don’t support the 802.11 power save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices. If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power. Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Devices for Teams

Microsoft Teams can be used for meetings or as a phone system. When using these features, the interface device that is used for Teams plays an important role in the user experience.

Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration. But typically those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call. Leveraging devices optimized for these scenarios will help ensure a high-quality experience.

Each device needs to meet the needs of your users. You’ll need to tailor devices such as headsets for the different personas and use cases in your organization. A persona-to-device mapping exercise should be completed as part of the planning process.

After you’ve selected the devices, include them in the pilot test plan for final validation. Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.

At this time, we recommend using audio devices that were certified through the Skype for Business Certification program. To find devices certified under this program, refer to the [USB Devices Certified for Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) solutions catalog.

For more details, see [Client and Devices - Readiness Workshop](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>Client updates

One of the key benefits of Microsoft Teams is that the client is kept up to date automatically. The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle. The client download size is roughly 100 MB.

An organization doesn’t have any control or access to a policy setting to manage the update process. To mitigate the risk of a problem that might be discovered in a newer build, the last known good version is kept on the endpoint. If there’s a problem with a new build, the Microsoft Teams service can revert the endpoint to the previous version automatically.

## <a name="next-steps-and-references"></a>Next steps and references

This table includes a summary of planning activities with links to related content.

| Area | Detalles | References |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Plan for service management | Conduct an operational role mapping exercise <br/> Signoff from accountable teams <br/> Role readiness | [Operations Guide](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) |
| | Nominate Quality Champion(s) <br/> Quality Champion readiness| [Learn CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Quality Experience Review Guide](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) |
| | Install Quality Experience Review templates <br/> Upload a building file | [QERLite templates](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true) <br/> [Upload Building Information](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?ui=en-US&rs=en-US&ad=US#upload-building-information)|
| Plan for network quality | Run the Network Planner | [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Implement QoS | [Quality of Service in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| | Bypass proxy servers | [Proxy Guidance](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ad=US#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies) |
| | Implement split-tunnel VPN | [VPN Split Tunnel Guidance](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Optimize Wi-Fi networks for real-time media  | Consult 3rd Party Vendors |
| | Implement local internet egress | [Local Internet Egress](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implement network connectivity <br/> Validate network connectivity | [Office 365 URLs and IP addresses](https://aka.ms/o365ips) |
| | | [Network Assessment Tool](https://www.microsoft.com/en-us/download/details.aspx?id=53885) |
| | Perform network assessment | [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Plan for endpoint quality | Update endpoint firewalls | [Direcciones IP y direcciones URL de Office 365](https://aka.ms/o365ips) |
| | Validate software requirements | [Obtener a los clientes de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients) |
| | Implementar las recomendaciones de extremo Wi-Fi | Consulte a los proveedores de terceros 3 |
| | Rol de conducta para la asignación de dispositivos <br/> Suministrar dispositivos y ellos la prueba piloto | [Cliente y dispositivos - taller de preparación](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Catálogo de dispositivo](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |