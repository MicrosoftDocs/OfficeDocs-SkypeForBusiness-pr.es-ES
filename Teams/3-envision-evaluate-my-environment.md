---
title: Evaluar su entorno para cargas de trabajo de voz de nube de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Utilice roles y análisis de redes para evaluar la preparación de su organización, abra los puertos TCP y UDP correctos, realizar la corrección de cualquier red.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b97a588a55eb1b7183315751a9483d69eeb0b6b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="evaluate-my-environment"></a>Evaluar mi entorno

Este artículo ofrece una visión general de los requisitos para evaluar correctamente el entorno actual para el uso de servicios de voz de la nube. Mediante la evaluación de su entorno, identificar los riesgos y los requisitos que afectan la implementación de voz de nube global. Al identificar estos elementos con antelación, puede ajustar el diseño para conseguir el éxito.

## <a name="introduction-to-evaluating-your-environment"></a>Introducción a la evaluación del entorno 

Para lograr los resultados clave objetivos (OKRs), que haya realizado previamente las decisiones clave del servicio. El paso siguiente consiste en realizar descubrimientos del entorno para evaluar todos los aspectos relativos a la TI y la infraestructura de telefonía, redes y operaciones para confirmar que su organización está preparada para implementar la solución.

Descubrimientos del entorno deben incluir una evaluación de disponibilidad de la red para asegurarse de que la red puede admitir la implementación de la conferencia de Audio o sistema de teléfono con los servicios de Plan de llamadas.

Identificar los riesgos técnicos como parte de una evaluación medioambiental y la evaluación de la preparación de adopción y desarrollar un plan de mitigación para cada riesgo identificado.
Debe incorporar esta información en el registro de riesgos.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Entorno actual

Como parte de la exploración del medio ambiente, se incluyen todos los asuntos relacionados con la informática de usuario final, como una evaluación de la disponibilidad de equipos y dispositivos móviles que admite conferencias de Audio y sistema de teléfono con el Plan de llamadas negocio casos de uso, de los requisitos de hardware para requisitos de software.

También pueden descubrir los descubrimientos del entorno si necesita [transferir números de teléfono de Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).
Este conocimiento le ayudará a su organización ajustará su plan del proyecto y preparar la información necesaria para el traslado de número. Puede utilizar los [descubrimientos del entorno para la implementación de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/environmental-discovery-for-microsoft-teams-rollout) desde MyAdvisor para realizar descubrimientos del entorno.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de completar una evaluación del entorno?</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Documentar los resultados de la evaluación del entorno.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Capacidades de evaluación de administración de adopción y cambio 

Implementación pone una nueva tecnología en manos de un usuario, pero sólo se obtienen los resultados del negocio después de usuarios verdaderamente adoptar esa solución como sus propios. Para asegurar la adopción sostenida de una nueva solución, deberá concentrar sus esfuerzos en la preparación de usuario y administración de cambios. Para obtener resultados óptimos, realice el planeamiento como una secuencia de trabajo paralelo a sus actividades de preparación técnica de la disponibilidad de usuario e incorporar las siguientes actividades:

-   **Organizativa y generación de perfiles de usuario:** Análisis de la receptividad organizacional para cambiar además de análisis de uso mayúsculas y minúsculas y rol

-   **Preparación de preparación y recursos:** Creación del conocimiento destino y de amplio alcance, formación y recursos de soporte, incluyendo centrado valor mensajería para acelerar la compra de usuario

Utilice las siguientes consideraciones para evaluar la preparación de su organización para la administración de cambio de usuario.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>¿Ha tenido éxito previo con la adopción de usuario del software o los servicios?</li><li>¿Puede hacer un seguimiento de absorción de uso?</li><li>¿Tiene los recursos necesarios para diseñar y administrar inicial&mdash;y&mdash;campaña de adopción (sensibilización, formación y asistencia)?</li><li>¿Tiene un equipo de gestión de la adopción o cambiar de usuario dedicada, o pueden invertir en esos recursos para garantizar los resultados del negocio?</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Si respondió "Sí" a todas las anteriores, identificar a los participantes de administración de cambio de usuario correcto y empezar la planificación de la disponibilidad de usuario.</li><li>Si respondió "no" a algunas o a todas las anteriores, considere contratar recursos externos para ayudar a impulsar la administración de cambios y actividades relacionadas con la adopción de su organización.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Preparación de la red

Equipos utiliza audio y vídeo tecnología (codecs) que puede adaptarse a — y, por tanto, funcionan mejor en: condiciones de red más. Para garantizar un rendimiento óptimo y coherente, debe preparar la red para los equipos.

![Se describen los tres componentes de calidad y la administración del servicio superpone a todos los tres componentes del diagrama. Con un enfoque en la red.] (media/evaluate-my-environment-image1.png "Se describen los tres componentes de calidad y la administración del servicio superpone a todos los tres componentes del diagrama. Con un enfoque en la red.")

## <a name="key-takeaways"></a>Impresiones clave

Éstos son los puntos principales de esta guía. Debe:

-   Abra los puertos TCP 80 y 443 saliente de los clientes que utilizarán los equipos.

-   Abra los puertos UDP 3478 mediante 3481 saliente desde clientes que utilizarán los equipos.

-   Asegúrese de que tiene suficiente ancho de banda para implementar equipos completando el [Planificador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Ejecutar la [Herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885) y garantizar que cumplen los requisitos descritos en el [rendimiento de conectividad de red y calidad Media](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) desde el segmento del borde y el segmento del cliente.

## <a name="why-should-you-prepare-your-network"></a>¿Por qué se debe preparar la red?

Antes de estudiar los pasos que deben seguirse, es importante comprender lo que puede afectar al rendimiento de los equipos y, por tanto, la satisfacción y la satisfacción del usuario.
Tres áreas de riesgo principales que pueden afectar a cómo los usuarios perciben la calidad de la red:

-   No hay suficiente ancho de banda disponible

-   Bloqueadores de Firewall y proxy

-   Dificultades como la inestabilidad y pérdida de paquetes de red

Los pasos descritos a continuación le ayudará a determinar que si su implementación podría verse afectada por cualquiera de estos factores y le ayudará a mover hacia una resolución.
Error al preparar la red probablemente llevarán a los usuarios insatisfechos y correcciones de ad hoc costosos. Mediante la preparación de la red y de su organización, para los equipos, puede aumentar considerablemente sus posibilidades de éxito.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planificación de ancho de banda

El primer paso en la preparación de la red es garantizar que la red tiene suficiente ancho de banda disponible para las modalidades que equipos proporcionará a los usuarios. Planificación de suficiente ancho de banda es una tarea bastante sencilla y un inicio muy bajo-barrera para garantizar a los usuarios tendrán una experiencia de los equipos de alta calidad.

Inicie su planificación de viaje para los equipos en el [sitio Web del Asesor de mi](https://myadvisor.fasttrack.microsoft.com/) utilizando el planificador de red de ancho de banda. El planificador de red proporciona planificación para equipos de ancho de banda de cada sitio y ofrece recomendaciones para optimizar el rendimiento de la red.

### <a name="local-internet-egress"></a>Salida de internet local

Muchas redes se diseñaron para utilizar un concentrador y radios de topología. En esta topología, el tráfico de internet recorre normalmente la WAN a un centro de datos central antes de que se desprende (corrales) a internet. A menudo, esto se realiza para centralizar los dispositivos de seguridad de red con el objetivo de reducir los costes generales.

Acarreo atrás el tráfico en la WAN aumenta la latencia y tiene un impacto negativo en la calidad y la experiencia del usuario. Como Teams de Microsoft se ejecuta en la red global grande de Microsoft, a menudo es una ubicación de interconexión de red más cercano al usuario. Un usuario probablemente obtendrá un mejor rendimiento por egressing fuera de un punto de internet local cerca de su ubicación y en nuestra red optimizado para voz tan pronto como sea posible. Algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar tráfico a la más cercana del servidor front-end. En estos casos, es importante que cuando se utiliza un punto de salida local, se corresponde con la resolución DNS local.

Optimización de la ruta de acceso de red a red global de Microsoft mejora el rendimiento y en última instancia, proporcionar la mejor experiencia para los usuarios. Para obtener más detalles, consulte el blog [obteniendo la mejor conectividad y performance en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Redes privadas virtuales proporcionan un servicio valioso para muchas organizaciones. Por desgracia, que están normalmente no diseñados o configurados para admitir los medios de comunicación en tiempo real. Algunas redes privadas virtuales también podrían no admitir UDP. Las redes privadas virtuales también introducen una capa adicional de cifrado sobre el tráfico de medios ya está cifrado. Además, la conectividad con el servicio de equipos puede no ser rentable debido a la fijación de pelo tráfico a través de un dispositivo VPN.
Además, ellos no están necesariamente diseñados desde una perspectiva de la capacidad para adaptarse a las cargas anticipadas que se requieren equipos.

La recomendación es proporcionar una ruta alternativa que omite la VPN para el tráfico de los equipos. Esto se conoce como *división túnel VPN*. La división del túnel significa que el tráfico para Office 365 no recorren la VPN pero vaya directamente a Office 365. Este cambio tendrá un impacto positivo sobre la calidad, pero también ofrece la ventaja de reducir la carga de los dispositivos VPN y la red de la organización secundaria.

Para implementar un túnel dividido, consulte a su proveedor VPN para los detalles de configuración.

### <a name="wi-fi"></a>Wi-Fi

Al igual que VPN, redes Wi-Fi no están diseñadas necesariamente o configuradas para admitir los medios de comunicación en tiempo real. Planear u optimizar, una red Wi-Fi para equipos de soporte técnico es una consideración importante para una implementación de alta calidad.

Hay varios factores que entran en juego para optimizar una red Wi-Fi:

-   Implementación de QoS o Multimedia Wi-Fi (WMM) para garantizar que el tráfico multimedia es obtener prioridad en consecuencia a través de las redes Wi-Fi.

-   Planificación y optimización de las bandas de Wi-Fi y acceso punto de colocación. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada dependiendo de la posición del punto de acceso, pero los puntos de acceso con frecuencia se ven afectados por otros dispositivos que funcionen en ese intervalo. El intervalo de 5 GHz se adapta mejor a los medios de comunicación en tiempo real debido a su alcance con gran densidad pero requiere más puntos de acceso para obtener una cobertura suficiente. Extremos también deben soportar este espectro y configurarse para aprovechar esas bandas en consecuencia.

-   Si se implementan redes Wi-Fi de doble banda, considere la implementación de control de la banda. Banda de dirección es una técnica de implementada por proveedores de Wi-Fi para influir en los clientes de doble banda para utilizar el intervalo de 5 GHz.

-   Cuando los puntos de acceso del mismo canal están demasiado juntos pueden provocar la superposición de señal y competir involuntariamente, dando como resultado una mala experiencia para el usuario. Compruebe que los puntos de acceso que están contiguos en canales que no se superponen.

Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Le recomendamos que consulte a su proveedor para obtener instrucciones específicas.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de Firewall y proxy

Teams de Microsoft se conecta a Microsoft Online Services y necesita conexión a internet para esto. Para que los equipos para que funcionen correctamente, debe abrir los puertos TCP 80 y 443 desde los clientes a internet y los puertos UDP 3478 mediante 3481 desde los clientes a internet. Los puertos TCP se utilizan para conectarse a contenido basado en web como Exchange Online, SharePoint Online y los servicios de Chat de equipos.
Plug-ins y conectores conectan también a través de los puertos TCP. Los cuatro puertos UDP se utilizan para multimedia como audio y vídeo, para garantizar que fluyan correctamente.

Abrir estos puertos es esencial para una implementación de equipos confiable. El bloqueo de estos puertos no se admite y tendrá un efecto sobre la calidad de los medios de comunicación.

Si su organización requiere que especifique los intervalos de direcciones IP y dominios a los que se deben abrir estos puertos exacta, puede restringir los intervalos IP de destino y los dominios para estos puertos. Para obtener una lista de puertos, protocolos y rangos IP, consulte [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).
Si decide restringir los intervalos de direcciones IP de destino y los dominios, debe asegurarse de que mantenga actualizada la lista de puertos y rangos porque puede cambiar. Puede suscribirse a [esta fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) se actualice cuando se producen cambios. También es una buena práctica para comprobar si todos los puertos se abren ejecutando el [Skype para la herramienta de evaluación de red empresarial](https://www.microsoft.com/download/details.aspx?id=53885) de forma regular. Puede encontrar más información acerca de la funcionalidad de esta herramienta en la sección siguiente.

En el caso de un servidor proxy que se está implementando, recomendamos que omite el servidor proxy para todos los servicios de los equipos. Aunque puede funcionar utilizando a un servidor proxy, es muy probable que se reducirá la calidad debido a la del medio se ven obligados a usar TCP en lugar de UDP. Para obtener más información acerca de servidores proxy y omitir, vea [direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Probar la red

Una vez completada la preparación de la planificación y la red, incluida la actualización de ancho de banda y abrir puertos en el firewall: debe probar el rendimiento de la red. Los resultados de esta prueba pintan una imagen clara de optimización de la red o corrección necesarios para el éxito de su sistema de teléfono o conferencias de Audio con llamar a planear la implementación.

Puede descargar el [Skype para la herramienta de evaluación de red empresarial](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si está lista para los equipos de la red. La herramienta ofrece funcionalidad dual: puede comprobar si se han abierto los puertos correctos, y puede probar problemas de red.

Después de descargar e instalar la herramienta, puede encontrarla en C:\\archivos de programa\\Microsoft Skype para la herramienta de evaluación de red empresarial. Una guía detallada acerca de cómo utilizar la herramienta, Usage.docx, está incluida en ese directorio.

### <a name="test-for-opened-ports"></a>Comprobar puertos abiertos

Abra una ventana del símbolo del sistema y desplácese al directorio de herramienta de evaluación de la red escribiendo **cd C:\\archivos de programa\\Microsoft Skype para la herramienta de evaluación de red empresarial**. En el símbolo del sistema, inicie la prueba de puertos abiertos escribiendo **networkassessmenttool.exe /connectivitycheck**

Después de ejecutar las comprobaciones, la herramienta se muestre el mensaje "Verificaciones finalizó correctamente" o informar en los puertos que se han bloqueado.
También genera un archivo denominado Connectivity_results.txt, que contiene el resultado de la herramienta y se almacena en % userprofile %\\appdata\\local\\microsoft Skype para la herramienta de evaluación de red empresarial\\ directory.

Le recomendamos que ejecute las comprobaciones de conectividad de forma periódica para asegurar los puertos se han abierto y funcionan correctamente.

### <a name="test-for-network-impairments"></a>Prueba de problemas de red

Para aumentar la satisfacción de los usuarios, debe limitar las dificultades en la red.
Las dificultades de red más comunes son el retardo (latencia), pérdida de paquetes y vibración:

-   **Latencia:** Esto es el tiempo que se tarda en obtener un paquete IP desde el punto al punto B de la red. Este retardo en la propagación red esté esencialmente ligado a la distancia física entre los dos puntos y la velocidad de la luz, incluyendo tomada por los diversos enrutadores entre una sobrecarga adicional.
    La latencia se mide como el tiempo de ida y vuelta o unidireccional.

-   **Pérdida de paquetes**: a menudo se define como un porcentaje de paquetes que se pierden en un determinado intervalo de tiempo. Pérdida de paquetes directamente afecta a la calidad de audio, desde pequeñas, individuo los paquetes perdidos no tener casi afectar a las pérdidas de ráfagas de extremo a extremo que causa el audio para cortar completamente.

-   **Vibración de llegada entre paquetes o simplemente vibración:** Éste es el cambio promedio de retardo entre envíos sucesivos de paquetes. Software de VoIP más modernas, incluyendo Skype para el negocio, puede adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Es sólo cuando la variación supera el búfer que un participante observará los efectos de vibración.

Se describen los valores máximos de estas deficiencias en el [rendimiento de conectividad de red y calidad Media](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).
Cuando se prueba para estas dificultades, podemos distinguir entre dos segmentos independientes:

-   El *segmento del borde* es el segmento en el que vive el enrutador. Éste es el segmento de red lógica más próximo conectado a internet en cada una de las ubicaciones. En la mayoría de los casos, esto es el punto de conexión del enrutador, o posiblemente una red perimetral (también conocida como *DMZ*, *zona desmilitarizada*y *subred protegida*). No hay más tráfico que afecta a los dispositivos que no sean el enrutador debe producirse entre este segmento y en internet.

-   El *segmento del cliente* es el segmento de red lógica en la que residen los clientes.

Debe probar ambos segmentos mediante la herramienta de evaluación de la red. Para probar el segmento, desplácese al directorio y escriba **networkassessmenttool.exe** en el símbolo del sistema. Los resultados se escriben en un archivo denominado Results.tsv, y se puede comparar a los [requisitos](https://docs.microsoft.com/en-us/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance?ui=en-US&rs=en-US&ad=US) de cada segmento.

Tenga en cuenta que ambos segmentos deben cumplir los requisitos de una implementación de alta calidad. Se recomienda ejecutar la herramienta varias veces durante una hora directamente para obtener una buena indicación de rendimiento de la red.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Corrección de la red

Si los resultados de la planificación de ancho de banda, puerto pruebas o pruebas de requisitos de red que la red actual necesita corrección antes de implementar los equipos, puede hacerlo de varias maneras:

-   Ancho de banda insuficiente, actualización conexiones para que fluya el tráfico a Office 365 sin obstáculos.

-   Para los puertos bloqueados, cambiar las reglas del cortafuegos y volver a probar los puertos.

-   Para deficiencias de la red, siempre que realice un análisis de causa de origen.

Calidad de servicio (QoS) puede utilizarse para dificultades de la batalla por la asignación de prioridad y separar el tráfico. Algunas organizaciones eligen implementar QoS para superar los problemas de ancho de banda o limitar la cantidad de tráfico que fluye. Esto no mejora la calidad y dará lugar a nuevos problemas. Un análisis de causa de origen deben ser realizada siempre dificultades de red superan los requisitos. QoS puede ser una solución.
Para obtener más información, vea [Calidad de servicio en equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).

>[!NOTE]
>Muchas redes evolucionan con el tiempo debido a las actualizaciones, expansión u otros requisitos empresariales. Asegúrese de que tiene los procesos operacionales en su lugar para mantener estas áreas como parte de su plan de administración de servicio.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de realizar evaluaciones de red correcta en todos los segmentos de red y ubicaciones de la organización?</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Puede realizar una evaluación detallada de red para garantizar que la red está lista para la implementación de Microsoft Teams. Para obtener más información, vea [Evaluación de disponibilidad de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness).</li><li>Realizar la corrección de la red basándose en los resultados de la evaluación de disponibilidad de red para cada segmento de red.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->