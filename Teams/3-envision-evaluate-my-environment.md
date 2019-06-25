---
title: Evaluar su entorno para las cargas de trabajo de voz de nube de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use los roles y el análisis de red para evaluar la disponibilidad de su organización, abrir los puertos TCP y UDP correctos, realizar cualquier corrección de la red.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8aed7b648a3cd742fa7cf160d34aefced97ae31c
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198368"
---
# <a name="evaluate-my-environment"></a>Evaluar mi entorno

Este artículo proporciona una descripción general de los requisitos para evaluar correctamente su entorno actual para usar los servicios de voz en la nube. Al evaluar su entorno, usted identifica los riesgos y los requisitos que influirán en la implementación de voz de nube general. Al identificar estos elementos previamente, puede ajustar la planificación para que funcione correctamente.

## <a name="introduction-to-evaluating-your-environment"></a>Introducción a la evaluación de su entorno 

Para lograr los resultados clave objetivo (OKRs), ya has tomado decisiones clave sobre el servicio. El siguiente paso consiste en realizar el descubrimiento medioambiental para evaluar todos los aspectos relacionados con su infraestructura de telefonía, redes y de TI para confirmar que su organización está lista para implementar la solución.

El descubrimiento medioambiental debe incluir la evaluación de la disponibilidad de red para asegurarse de que su red sea compatible con la implementación de la audioconferencia o del sistema telefónico con servicios de plan de llamadas.

Identifique los riesgos técnicos como parte de una evaluación del medio ambiente y de la evaluación de la preparación de la adopción, y desarrolle un plan de mitigación por cada riesgo identificado.
Debes incorporar esta información en el registro de riesgos.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Entorno actual

Como parte de su descubrimiento medioambiental, incluya todos los asuntos relacionados con la informática del usuario final, como una evaluación de la disponibilidad de equipos y dispositivos móviles para admitir la audioconferencia y el sistema telefónico con los casos de uso empresarial de plan de llamadas, de los requisitos de hardware para requisitos de software.

El descubrimiento medioambiental también puede descubrir si necesita [transferir números de teléfono a Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).
Conocer esto ayudará a su organización a ajustar el plan del proyecto según corresponda y preparar la información necesaria para la portabilidad de números. Puede usar el [descubrimiento medioambiental para la implementación de Microsoft Teams](environmental-discovery-for-microsoft-teams-rollout.md) para realizar el descubrimiento medioambiental.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será el responsable de completar una evaluación del entorno?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Documente los resultados de la evaluación del entorno.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Capacidades de evaluación de la administración de cambios y adopción 

La implementación pone a disposición de los usuarios una nueva tecnología, pero los resultados empresariales solo se devuelven cuando los usuarios realmente adoptan esa solución como suya. Para ayudarle a garantizar la adopción sostenida de una nueva solución, tendrá que centrar sus esfuerzos en la preparación del usuario y la administración de cambios. Para obtener resultados óptimos, realice la planeación de la disponibilidad de usuarios como una secuencia de tareas paralela a sus actividades técnicas de preparación e incorpore las siguientes actividades:

-   **Generación de perfiles de organización y usuario:** Análisis de la reutilización de la organización con la que cambiar además del caso de uso y el análisis de los roles

-   **Preparación de recursos y preparación:** Creación de recursos de reconocimiento, formación y asistencia específicos y de alcance amplio, como la mensajería de valor focalizada para acelerar el uso de los usuarios

Use las siguientes consideraciones para evaluar la preparación de la organización para dirigir la administración de los cambios de usuario.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Ha tenido éxito previamente con la adopción por el usuario de software o servicios?</li><li>¿Puede hacer un seguimiento del uso?</li><li>¿Tiene los recursos para diseñar y administrar una campaña inicial&mdash;y constante&mdash;de adopción (conciencia, aprendizaje y soporte)?</li><li>¿Tiene un equipo de administración de cambios/adopción de usuarios dedicado o puede invertir en esos recursos para garantizar el resultado empresarial?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Si respondió &quot;afirmativamente&quot; a todo lo anterior, identifique los participantes de la administración de cambios de los usuarios correctos y empiece la planeación de la disponibilidad de los usuarios.</li><li>Si ha &quot;respondido&quot; a una parte o a todas las anteriores, considere la posibilidad de repartir recursos externos para ayudarle a impulsar las actividades de administración de cambios y relacionadas con la adopción de su organización.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Disponibilidad de red

Teams usa tecnología de audio y vídeo (códecs) que puede adaptarse y, por lo tanto, funcionar mejor en la mayoría de las condiciones de la red. Para garantizar un rendimiento óptimo y coherente, debe preparar su red para los equipos.

![Diagrama que describe los tres componentes de la calidad] (media/evaluate-my-environment-image1.png "Diagrama que describe los tres componentes de la calidad y cómo se superpone la administración de servicios de los tres componentes. Con un foco en la red.")

## <a name="key-takeaways"></a>Impresiones clave

Estas son las principales impresiones de esta guía. Debes:

-   Abra los puertos TCP 80 y 443 salientes de los clientes que usarán Teams.

-   Abra los puertos UDP 3478 a 3481 salientes de los clientes que usarán Teams.

-   Asegúrese de que tiene suficiente ancho de banda para implementar Teams.

-   Ejecute la [herramienta de evaluación de redes](https://www.microsoft.com/download/details.aspx?id=53885) y asegúrese de que cumple con los requisitos descritos en [calidad de medios y rendimiento de conectividad de red](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) tanto del segmento perimetral como del segmento de cliente.

## <a name="why-should-you-prepare-your-network"></a>¿Por qué debería preparar su red?

Antes de ver los pasos que se deben realizar, es importante comprender lo que puede afectar al rendimiento de Teams y, por lo tanto, a la satisfacción y satisfacción del usuario.
Tres de las principales áreas de riesgo pueden afectar al modo en que los usuarios perciben la calidad de la red:

-   Ancho de banda insuficiente

-   Firewalls y bloqueadores de proxy

-   Deficiencias de red, como la vibración y la pérdida de paquetes

Los pasos que se describen a continuación le ayudarán a determinar si su implementación podría verse afectada por alguno de estos factores y le ayudarán a desplazarse hacia una solución.
Si no se prepara su red, es probable que se produzcan usuarios insatisfechos y costosas soluciones ad-hoc. Al preparar su red, y su organización, para Teams, puede aumentar enormemente sus posibilidades de éxito.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planeamiento del ancho de banda

El primer paso para la preparación de la red es asegurarse de que su red tenga suficiente ancho de banda disponible para las modalidades que los equipos proporcionarán a los usuarios. Planear un ancho de banda suficiente es una tarea bastante sencilla y un inicio de barrera muy bajo para garantizar que los usuarios tengan una experiencia de alta calidad en los equipos.

### <a name="local-internet-egress"></a>Salida local de Internet

Muchas redes se diseñaron en su momento para usar una topología tipo hub-and-spoke. En esta topología, por lo general, el tráfico de Internet atraviesa la red WAN hasta un centro de datos central antes de salir a Internet. A menudo, esto se hace para centralizar los dispositivos de seguridad de redes y reducir así el coste general.

El tráfico de transporte hacia atrás por la WAN aumenta la latencia y repercute negativamente en la calidad y la experiencia del usuario. Como Microsoft Teams se ejecuta en una gran red global de Microsoft, existe a menudo una ubicación de emparejamiento de red cerca del usuario. Es muy probable que un usuario obtenga un mejor rendimiento si sale de un punto de Internet local que se encuentra cerca de su ubicación y accede a una red optimizada para voz lo antes posible. Para algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar tráfico al servidor front-end más cercano. En esos casos, es importante que, cuando se usa un punto de salida local, se empareje con una resolución DNS local.

Al optimizar la ruta de red a la red global de Microsoft, mejorará el rendimiento y, en última instancia, los usuarios disfrutarán de la mejor experiencia posible. Para obtener más detalles, vea la publicación del blog [Conseguir la mejor conectividad y el mejor rendimiento en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Las redes VPN ofrecen un servicio muy valioso a muchas organizaciones. Lamentablemente, generalmente no están diseñados o configurados para admitir medios en tiempo real. Algunas redes VPN también podrían no admitir UDP. Las redes privadas virtuales también introducen una capa adicional de cifrado sobre el tráfico de medios que ya está cifrado. Además, es posible que la conectividad con el servicio de los equipos no sea eficaz debido al tráfico de fijación de cabello a través de un dispositivo VPN.
Además, no están diseñados necesariamente desde una perspectiva de capacidad para dar cabida a las cargas anticipadas que necesitará Teams.

Lo que se recomienda es ofrecer una ruta alternativa que omita el VPN para el tráfico de Teams. Esto se conoce comúnmente como *VPN de túnel dividido*. Los túneles divididos hacen que el tráfico de Office 365 no atraviese la VPN, pero irá directamente a Office 365. Este cambio repercutirá positivamente en la calidad, pero también proporciona la ventaja secundaria que supone reducir la carga de los dispositivos VPN y la red de la organización.

Para implementar un túnel dividido, consulte con su proveedor de VPN para los detalles de configuración.

### <a name="wi-fi"></a>Wi-Fi

Al igual que VPN, las redes Wi-Fi no tienen por qué estar diseñadas o configuradas para admitir medios en tiempo real. La planeación o la optimización de una red Wi-Fi para admitir equipos es una consideración importante para una implementación de alta calidad.

Hay varios factores que se deben tener en cuenta para optimizar una red Wi-Fi:

-   Implementar QoS o Wi-Fi Multimedia (WMM) para garantizar que el tráfico multimedia se priorice de forma acorde a través de redes Wi-Fi.

-   Planear y optimizar las bandas Wi-Fi y la ubicación de puntos de acceso. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada en función de la ubicación del punto de acceso, pero a los puntos de acceso normalmente también le afectan otros dispositivos de consumidores que funcionan en esa gama. El intervalo de 5 GHz es mejor para los medios en tiempo real, debido a su rango denso, pero requiere más puntos de acceso para conseguir suficiente cobertura. Los puntos de conexión también necesitan admitir esa gama y configurarlos para poder aprovechar esas bandas de forma adecuada.

-   Si se implementan redes Wi-Fi de banda dual, considere la posibilidad de implementar la dirección de banda. El manejo de bandas es una técnica implementada por los proveedores de Wi-Fi para que los clientes de banda dual usen el intervalo de 5 GHz.

-   Cuando los puntos de acceso del mismo canal están demasiado juntos, pueden provocar la superposición de señales y competir involuntariamente, lo que provoca una mala experiencia para el usuario. Asegúrese de que los puntos de acceso que se encuentran junto a los demás estén en canales que no se superponen.

Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Le recomendamos que consulte con su proveedor para obtener las indicaciones concretas.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de firewall y proxy

Microsoft Teams se conecta a Microsoft Online Services y necesita conexión a Internet para esto. Para que los equipos funcionen correctamente, debe abrir los puertos TCP 80 y 443 de los clientes a Internet, y los puertos UDP 3478 a 3481 desde los clientes a Internet. Los puertos TCP se usan para conectarse a contenido basado en Web, como SharePoint Online, Exchange Online y los servicios de chat de Teams.
Los complementos y conectores también se conectan a través de estos puertos TCP. Los cuatro puertos UDP se usan para medios como audio y vídeo, para garantizar que fluyen correctamente.

La apertura de estos puertos es esencial para una implementación de equipos confiable. No se admite el bloqueo de estos puertos y afectará la calidad de los medios.

Si su organización requiere que especifique los intervalos de direcciones IP y los dominios exactos en los que se deben abrir estos puertos, puede restringir los dominios y los intervalos IP de destino para estos puertos. Para obtener una lista de los puertos, protocolos e intervalos de IP exactos, consulte [direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams).
Si elige restringir los intervalos de direcciones IP de destino y los dominios, debe asegurarse de que mantiene actualizada la lista de puertos y intervalos porque pueden cambiar. Puede suscribirse a [esta fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para que se actualice cuando se produzcan cambios. También es una buena práctica comprobar si todos los puertos se abren ejecutando la herramienta de [evaluación de redes de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=53885) de forma periódica. Puede obtener más información sobre la funcionalidad de esta herramienta en la siguiente sección.

En el caso de que se implemente un servidor proxy, le recomendamos que omita el servidor proxy para todos los servicios de Teams. Aunque el uso de un proxy puede funcionar, es muy probable que se reduzca la calidad debido a que los elementos multimedia se ven obligados a usar TCP en lugar de UDP. Para obtener más información sobre los servidores proxy y la omisión, consulte [direcciones URL e intervalos de direcciones IP de Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Probar la red

Una vez completada la planificación y la preparación de la red (incluida la actualización del ancho de banda y la apertura de puertos en el firewall), debe comprobar el rendimiento de la red. Los resultados de esta prueba pintarán una imagen más nítida de cualquier optimización de red o corrección necesaria para el éxito de su sistema de audioconferencia o teléfono con la implementación del plan de llamadas.

Puede descargar la [herramienta de evaluación de redes de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si su red está lista para los equipos. La herramienta ofrece funcionalidad dual: puede comprobar si se han abierto todos los puertos correctos y puede probar las deficiencias de red.

Después de descargar e instalar la herramienta, puede encontrarla en C:\\archivos\\de programa herramienta Evaluación de red de Microsoft Skype empresarial. En ese directorio se incluye una guía detallada sobre cómo usar la herramienta, Usage. docx.

### <a name="test-for-opened-ports"></a>Probar los puertos abiertos

Abra una ventana del símbolo del sistema y navegue al directorio de la herramienta de evaluación de redes escribiendo **\\CD\\C: archivos de programa herramienta Evaluación de red de Microsoft Skype**empresarial. En el símbolo del sistema, inicie la prueba de puertos abiertos escribiendo **networkassessmenttool. exe/connectivitycheck**

Después de ejecutar las comprobaciones, la herramienta mostrará el mensaje "comprobaciones completadas correctamente" o informe sobre los puertos bloqueados.
También genera un archivo denominado Connectivity_results. txt, que contiene el resultado de la herramienta y lo almacena en el\\directorio de herramientas\\\\\\ de evaluación de redes locales de% userprofile% AppData de Microsoft Skype empresarial.

Le recomendamos que ejecute las comprobaciones de conectividad de forma regular para asegurarse de que los puertos se hayan abierto y funcionen correctamente.

### <a name="test-for-network-impairments"></a>Probar las deficiencias de red

Para aumentar la satisfacción del usuario, debe limitar cualquier deficiencia de la red.
Los problemas de red más comunes son el retraso (latencia), la pérdida de paquetes y la vibración:

-   **Latencia:** Este es el tiempo que se tarda en obtener un paquete IP desde el punto a al punto B de la red. Este retraso de propagación de red está esencialmente unido a la distancia física entre los dos puntos y la velocidad de luz, incluida la sobrecarga adicional que realizan los distintos enrutadores entre.
    La latencia se mide como tiempo unidireccional o de ida y vuelta.

-   **Pérdida de paquetes**: suele definirse como un porcentaje de paquetes que se pierden en una ventana determinada de tiempo. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales sin apenas repercusiones en pérdidas de ráfagas en el fondo que hacen que el audio se recorte por completo.

-   **Vibración de llegada entre paquetes o simplemente vibración:** Este es el cambio medio en el retraso entre paquetes sucesivos. La mayoría de los programas de VoIP modernos, incluido Skype empresarial, pueden adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Solo cuando la vibración supera el búfer que un participante observará de los efectos de la vibración.

Los valores máximos de estos problemas se describen en la [calidad de los medios y](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)en el rendimiento de conectividad de red.
Al probar estas deficiencias, distinguimos entre dos segmentos diferentes:

-   El *segmento de borde* es el segmento en el que vive el router. Este es el segmento de red lógica más cercano conectado a Internet en cada una de sus ubicaciones. En la mayoría de los casos, este es el punto de conexión del enrutador o, posiblemente, una red perimetral (también conocida como *DMZ*, *zona desmilitarizada*y *subred filtrada*). No debe ocurrir más tráfico que afecte a dispositivos que no sean el router entre este segmento e Internet.

-   El *segmento de cliente* es el segmento de red lógica en el que residen los clientes.

Para probar ambos segmentos, use la herramienta Evaluación de red. Para probar el segmento, navegue hasta el directorio y escriba **networkassessmenttool. exe** en el símbolo del sistema. Los resultados se escriben en un archivo denominado resultados. TSV y puede compararlos con los [requisitos](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) de cada segmento.

Tenga en cuenta que ambos segmentos deben cumplir los requisitos para una implementación de alta calidad. Le recomendamos que ejecute la herramienta varias veces durante una hora directamente para obtener una buena indicación del rendimiento de su red.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Corrección de red

Si los resultados de las pruebas de planeación de ancho de banda, prueba de puertos o requisitos de red muestran que su red actual necesita corrección antes de implementar Teams, puede hacerlo de varias maneras:

-   Para un ancho de banda insuficiente, actualice las conexiones para que el tráfico a Office 365 pueda fluir.

-   Para los puertos bloqueados, cambie las reglas del firewall y pruebe de todos los puertos.

-   Para discapacidades de red, siempre realice un análisis de causa de origen.

La calidad de servicio (QoS) se puede usar para luchar contra las dificultades al priorizar y separar el tráfico. Algunas organizaciones eligen implementar QoS para superar los problemas de ancho de banda o restringir la cantidad de tráfico que fluye. Esto no mejorará la calidad y provocará nuevos problemas. Un análisis de causa de origen debe realizarse siempre cuando las discapacidades de red superen los requisitos. QoS puede ser una solución.
Para obtener más información, consulte [calidad de servicio en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).

>[!NOTE]
>Muchas redes van evolucionando gracias a las actualizaciones, al ampliarlas o por otros requisitos de negocio. Asegúrese de contar con procesos operativos que ayuden a mantener estas áreas como parte de su planificación de administración de servicios.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será el responsable de realizar las evaluaciones de red apropiadas en todos los segmentos de red y ubicaciones de la organización?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Puede realizar una evaluación de red detallada para asegurarse de que su red está lista para su implementación de Microsoft Teams.</li><li>Realizar correcciones de red basadas en los resultados de la evaluación de cada segmento de red.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->