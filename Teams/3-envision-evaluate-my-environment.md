---
title: Evaluar el entorno para las cargas de trabajo de voz en la nube
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use personas y análisis de red para evaluar la disponibilidad de su organización, abrir los puertos TCP y UDP correctos y realizar cualquier corrección de red.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 350af8c004f44205c6228b0dc734da25602062d0
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739328"
---
# <a name="evaluate-my-environment"></a>Evaluar mi entorno

En este artículo se ofrece información general sobre los requisitos para evaluar correctamente el entorno actual para usar los servicios de voz en la nube. Al evaluar su entorno, identifica los riesgos y requisitos que influirán en la implementación de voz en la nube general. Mediante la identificación previa de estos elementos, puede ajustar la planificación para impulsar el éxito.

## <a name="introduction-to-evaluating-your-environment"></a>Introducción a la evaluación del entorno

Para lograr los resultados clave objetivo (OKR), previamente ha tomado decisiones clave del servicio. El paso siguiente es realizar un descubrimiento medioambiental para evaluar todos los aspectos relacionados con su infraestructura de TI y telefonía, las redes y las operaciones para confirmar que su organización está lista para implementar la solución.

El descubrimiento medioambiental debe incluir la evaluación de la preparación de la red para garantizar que su red pueda admitir la implementación de Audioconferencia o Sistema telefónico con los servicios del plan de llamadas.

Identifique los riesgos técnicos como parte de una evaluación medioambiental y evaluación de la preparación para la adopción, y desarrolle un plan de mitigación para cada riesgo identificado.
Debe incorporar esta información en el registro de riesgos.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Entorno actual

Como parte de su descubrimiento medioambiental, incluya todos los asuntos relacionados con la informática del usuario final, como la evaluación de la preparación de equipos y dispositivos móviles para admitir Audioconferencia y Sistema telefónico con casos de uso empresarial del plan de llamadas, desde requisitos de hardware hasta requisitos de software.

El descubrimiento medioambiental también puede descubrir si es necesario [transferir números de teléfono a Microsoft.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
Saber esto ayudará a su organización a ajustar en consecuencia su plan de proyecto y preparar la información necesaria para la porción de números. Puede usar el descubrimiento [medioambiental para la](environmental-discovery-for-microsoft-teams-rollout.md) implementación de Microsoft Teams para realizar el descubrimiento medioambiental.

<table>
<tr><td>Título</td><td>Descripción</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de completar una evaluación del entorno?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Documente los resultados de la evaluación del entorno.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Capacidades de evaluación de adopción y administración de cambios

La implementación pone al alcance de un usuario una nueva tecnología, pero los resultados empresariales solo se realizan después de que los usuarios la adopten como su propia solución. Para ayudar a garantizar la adopción sostenida de una nueva solución, necesitará centrar sus esfuerzos en la preparación del usuario y la administración de cambios. Para obtener resultados óptimos, realice la planificación de la preparación del usuario como flujo de trabajo paralelo a las actividades de preparación técnica e incorpore las siguientes actividades:

-   **Perfiles organizativos y de usuario:** Análisis de la adesividad organizativa para cambiar, además del análisis de mayúsculas y minúsculas de uso y de persona

-   **Preparación y preparación de recursos:** Creación de recursos de soporte, aprendizaje y concienciación dirigidos y de amplio alcance, incluida la mensajería de valor enfocado para acelerar la compra de los usuarios

Use las siguientes consideraciones para evaluar la preparación de su organización para abordar la administración de cambios de usuario.

<table>
<tr><td>Título</td><td>Descripción</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Has tenido éxito anteriormente con la adopción de software o servicios por parte del usuario?</li><li>¿Puedes realizar un seguimiento del uso?</li><li>¿Tiene los recursos para diseñar y administrar una campaña de adopción inicial y &mdash; &mdash; continua (concienciación, formación y soporte técnico)?</li><li>¿Tiene un equipo de administración de cambios o adopción de usuarios dedicado o puede invertir en esos recursos para garantizar los resultados empresariales?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Si respondió sí a todas las respuestas anteriores, identifique a las partes interesadas correctas de la administración del cambio de usuario y comience la planeación de &quot; &quot; la disponibilidad del usuario.</li><li>Si respondió no a algunas o todas las respuestas anteriores, considere la posibilidad de involucrar a los recursos externos para ayudarle a impulsar la administración del cambio y las actividades relacionadas &quot; &quot; con la adopción para su organización.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Disponibilidad de red

Teams usa tecnología de audio y vídeo (códecs) que se puede adaptar y, por tanto, tiene un mejor rendimiento en la mayoría de las condiciones de red. Para garantizar un rendimiento óptimo y coherente, debe preparar su red para Teams.

![Diagrama que describe los tres componentes de calidad](media/evaluate-my-environment-image1.png "Diagrama que describe los tres componentes de calidad y cómo la administración de servicios se superpone a los tres componentes. Con un foco en la red.")

## <a name="key-takeaways"></a>Sorteos clave

Estos son los principales sorteos de estas instrucciones. Debe:

-   Abra los puertos TCP 80 y 443 salientes de los clientes que usarán Teams.

-   Abra los puertos UDP de 3478 a 3481 salientes de clientes que usarán Teams.

-   Asegúrese de que tiene suficiente ancho de banda para implementar Teams.

-   Ejecute la [herramienta de evaluación de red](https://www.microsoft.com/download/details.aspx?id=53885) [](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) y asegúrese de que cumple los requisitos descritos en calidad de medios y rendimiento de conectividad de red tanto desde el segmento perimetral como desde el segmento de clientes.

## <a name="why-should-you-prepare-your-network"></a>¿Por qué debe preparar su red?

Antes de mirar los pasos que se deben tomar, es importante comprender lo que puede afectar al rendimiento de Teams y, por lo tanto, la satisfacción y la satisfacción del usuario.
Tres áreas de riesgo principales pueden afectar a la forma en que los usuarios perciben la calidad de la red:

-   Ancho de banda insuficiente disponible

-   Bloqueadores de firewalls y proxy

-   Deficiencias de red, como vibración y pérdida de paquetes

Los pasos descritos a continuación le ayudarán a determinar si la implementación podría verse afectada por alguno de estos factores y le ayudará a avanzar hacia una resolución.
Si no prepara su red probablemente se verán usuarios insatisfechos y correcciones ad hoc costosas. Al preparar su red, y su organización, para Teams, puede aumentar considerablemente su probabilidad de éxito.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planeamiento del ancho de banda

El primer paso para la preparación de la red es asegurarse de que su red tenga suficiente ancho de banda disponible para las modalidades que Teams proporcionará a los usuarios. Planear un ancho de banda suficiente es una tarea bastante sencilla y un inicio de muy baja barrera para asegurarse de que los usuarios tendrán una experiencia de Teams de alta calidad.

### <a name="local-internet-egress"></a>Salida local de Internet

Muchas redes se diseñaron en su momento para usar una topología tipo hub-and-spoke. En esta topología, por lo general, el tráfico de Internet atraviesa la red WAN hasta un centro de datos central antes de salir a Internet. A menudo, esto se hace para centralizar los dispositivos de seguridad de redes y reducir así el coste general.

El tráfico de transporte hacia atrás por la WAN aumenta la latencia y repercute negativamente en la calidad y la experiencia del usuario. Como Microsoft Teams se ejecuta en la gran red global de Microsoft, a menudo existe una ubicación de emparejamiento de red cerca del usuario. Es muy probable que un usuario obtenga un mejor rendimiento si sale de un punto de Internet local que se encuentra cerca de su ubicación y accede a una red optimizada para voz lo antes posible. Para algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar tráfico al servidor front-end más cercano. En estos casos, es importante que al usar un punto de salida local, esté emparejado con la resolución DNS local.

Optimizar la ruta de red a la red global de Microsoft mejorará el rendimiento y, en última instancia, proporcionará la mejor experiencia para los usuarios. Para obtener más detalles, vea la publicación del blog [Conseguir la mejor conectividad y el mejor rendimiento en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Las redes VPN ofrecen un servicio muy valioso a muchas organizaciones. Desafortunadamente, normalmente no están diseñadas ni configuradas para admitir medios en tiempo real. Algunas redes VPN también podrían no admitir UDP. Las VPN también introducen una capa adicional de cifrado sobre el tráfico multimedia que ya está cifrado. Además, es posible que la conectividad al servicio de Teams no sea eficiente debido al tráfico que se ancla a través de un dispositivo VPN.
Además, no están necesariamente diseñados desde una perspectiva de capacidad para dar cabida a las cargas previstas que Teams va a requerir.

Lo que se recomienda es ofrecer una ruta alternativa que omita el VPN para el tráfico de Teams. Esto se conoce comúnmente como *VPN de túnel dividido.* El túnel dividido significa que el tráfico de Microsoft 365 u Office 365 no cruzará la VPN, pero irá directamente a Microsoft 365 u Office 365. Este cambio tendrá un impacto positivo en la calidad, pero también proporciona el beneficio secundario de reducir la carga de los dispositivos VPN y la red de la organización.

Para implementar un túnel dividido, consulte con su proveedor de VPN para los detalles de configuración.

### <a name="wi-fi"></a>Wi-Fi

Al igual que vpnWi-Fi las redes no están necesariamente diseñadas o configuradas para admitir medios en tiempo real. Planear o optimizar una red local Wi-Fi que sea compatible con Teams es un factor importante para una implementación de alta calidad.

Hay varios factores que están en juego para optimizar una red Wi-Fi móvil:

-   Implementar QoS o Wi-Fi Multimedia (WMM) para garantizar que el tráfico multimedia se priorice de forma acorde a través de redes Wi-Fi.

-   Planear y optimizar la ubicación Wi-Fi bandas y puntos de acceso. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada en función de la ubicación del punto de acceso, pero a los puntos de acceso normalmente también le afectan otros dispositivos de consumidores que funcionan en esa gama. El intervalo de 5 GHz es mejor para los medios en tiempo real, debido a su rango denso, pero requiere más puntos de acceso para conseguir suficiente cobertura. Los puntos de conexión también necesitan admitir esa gama y configurarlos para poder aprovechar esas bandas de forma adecuada.

-   Si se implementan redes Wi-Fi banda dual, considere la posibilidad de implementar dirección de banda. La dirección de banda es una técnica implementada por Wi-Fi para influir en clientes de banda doble para usar el intervalo de 5 GHz.

-   Cuando los puntos de acceso del mismo canal están demasiado juntos, pueden producir solapamientos de señales y competencia involuntarla, lo que provoca una mala experiencia para el usuario. Asegúrese de que los puntos de acceso que están uno junto al otro están en canales que no se superponen.

Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Le recomendamos que consulte con su proveedor para obtener las indicaciones concretas.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de firewall y proxy

Microsoft Teams se conecta a Microsoft Online Services y necesita conectividad a Internet para ello. Para que Teams funcione correctamente, debe abrir los puertos TCP 80 y 443 de los clientes a Internet, y los puertos UDP 3478 a 3481 desde los clientes a Internet. Los puertos TCP se utilizan para conectarse al contenido basado en web, como SharePoint Online, Exchange Online y los servicios de chat de Teams.
Los conectores y los conectores también se conectan a través de estos puertos TCP. Los cuatro puertos UDP se usan para medios como audio y vídeo, para garantizar que fluyen correctamente.

Abrir estos puertos es esencial para una implementación confiable de Teams. El bloqueo de estos puertos no es compatible y tendrá un efecto en la calidad de medios.

Si su organización requiere que especifique los intervalos y dominios exactos de las direcciones IP a los que deben abrirse estos puertos, puede restringir los intervalos IP de destino y los dominios de estos puertos. Para obtener una lista de puertos, protocolos e intervalos IP exactos, consulte direcciones URL e intervalos de direcciones IP de [Microsoft 365 u Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)
Si elige restringir los intervalos y dominios de las direcciones IP de destino, debe asegurarse de mantener actualizada la lista de puertos e intervalos, ya que pueden cambiar. Puede suscribirse a [esta fuente RSS para actualizarla](https://go.microsoft.com/fwlink/p/?linkid=236301) cuando se produzcan cambios. También es una buena práctica comprobar si todos los puertos se abren ejecutando la Herramienta de evaluación de red de [Skype](https://www.microsoft.com/download/details.aspx?id=53885) Empresarial de forma periódica. Encontrará más información sobre la funcionalidad de esta herramienta en la sección siguiente.

En caso de que se implemente un servidor proxy, se recomienda omitir el servidor proxy para todos los servicios de Teams. Aunque usar un proxy puede funcionar, es muy probable que la calidad se reduzca debido a que los medios se ven forzados a usar TCP en lugar de UDP. Para obtener más información sobre los servidores proxy y la omisión, consulte direcciones URL e intervalos de direcciones IP de [Microsoft 365 u Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Probar la red

Una vez que haya completado la planificación y la preparación de la red, incluida la actualización del ancho de banda y la apertura de puertos en el firewall, debe comprobar el rendimiento de su red. Los resultados de estas pruebas mostrarán una imagen más clara de cualquier optimización o corrección de red necesaria para el éxito de la audioconferencia o sistema telefónico con la implementación del plan de llamadas.

Puede descargar la herramienta [de evaluación de red de Skype Empresarial](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si su red está preparada para Teams. La herramienta ofrece dos funciones: permite comprobar si se han abierto todos los puertos correctos y comprobar si hay problemas de red.

Después de descargar e instalar la herramienta, puede encontrarla en C: Archivos de programa de la herramienta de evaluación de \\ red de Microsoft Skype \\ Empresarial. En ese directorio se incluye una guía detallada sobre cómo usar Usage.docx herramienta.

### <a name="test-for-opened-ports"></a>Comprobar si hay puertos abiertos

Abra una ventana del símbolo del sistema y vaya al directorio de la herramienta de evaluación de red. Para obtener acceso al cd C: Archivos de programa, herramienta de evaluación de red **\\ de Microsoft Skype \\ Empresarial.** En el símbolo del sistema, inicie la prueba de puertos abiertos especificandonetworkassessmenttool.exe **/connectivitycheck**

Después de ejecutar las comprobaciones, la herramienta mostrará el mensaje "Comprobaciones completadas correctamente" o mostrará un informe de los puertos que se bloquearon.
También genera un archivo denominado Connectivity_results.txt, que contiene el resultado de la herramienta y lo almacena en el directorio de herramientas de evaluación de red de Microsoft Skype Empresarial local de \\ \\ \\ %userprofile%. \\

Le recomendamos que ejecute las comprobaciones de conectividad de forma periódica para asegurarse de que los puertos se han abierto y están funcionando correctamente.

### <a name="test-for-network-impairments"></a>Comprobar si hay deficiencias en la red

Para aumentar la satisfacción del usuario, debe limitar los problemas de su red.
Los problemas de red más comunes son retraso (latencia), pérdida de paquetes y vibración:

-   **Latencia:** Este es el tiempo que se tarda en obtener un paquete IP desde el punto A al punto B en la red. Este retraso en la propagación de red básicamente está vinculado a la distancia física entre los dos puntos y a la velocidad de luz, incluidas las sobrecargas adicionales tomadas por los diversos enrutadores entre ellos.
    La latencia se mide como tiempo de ida y vuelta.

-   **Pérdida de paquetes:** esto se suele definir como un porcentaje de paquetes que se pierden en un determinado período de tiempo. La pérdida de paquetes afecta directamente a la calidad del audio: desde paquetes pequeños e individuales perdidos que apenas afecten a las pérdidas de ráfagas de la parte posterior que provocan el corte del audio por completo.

-   **Vibración entre llegada de paquetes o, simplemente, vibración:** Este es el cambio medio en el retraso entre paquetes sucesivos. La mayoría del software de VoIP moderno, incluido Skype Empresarial, se puede adaptar a algunos niveles de vibración a través del almacenamiento en búfer. Solo cuando la vibración supera el almacenamiento en búfer, los participantes notan los efectos de la vibración.

Los valores máximos de estos problemas se describen en calidad [de medios y rendimiento de conectividad de red.](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)
Cuando se prueban estos problemas, se distingue entre dos segmentos independientes:

-   El *segmento de bordes* es el segmento en el que reside el enrutador. Este es el segmento de red lógico más cercano conectado a Internet en cada una de sus ubicaciones. En la mayoría de los casos, este es el punto de conexión del enrutador o, posiblemente, una red perimetral (también conocida como *DMZ,* zona *desmilitarizada* y subred *pantallada).* No debe producirse más tráfico que afecte a los dispositivos que no son el enrutador entre este segmento e Internet.

-   El *segmento de clientes* es el segmento de red lógico en el que residen sus clientes.

Debe probar ambos segmentos con la Herramienta de evaluación de red. Para probar el segmento, vaya al directorio y escriba **networkassessmenttool.exe** en el símbolo del sistema. Los resultados se escriben en un archivo denominado Results.tsv y puede compararlos con los [requisitos](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) de cada segmento.

Tenga en cuenta que ambos segmentos deben cumplir los requisitos para una implementación de alta calidad. Le recomendamos que ejecute la herramienta varias veces durante una hora recta para obtener una buena indicación del rendimiento de su red.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Corrección de red

Si los resultados de la planificación del ancho de banda, las pruebas de puerto o las pruebas de requisitos de red muestran que su red actual necesita corrección antes de implementar Teams, puede hacerlo de varias formas:

-   Para un ancho de banda insuficiente, actualice las conexiones para que el tráfico a Microsoft 365 u Office 365 pueda fluir sin problemas.

-   Para los puertos bloqueados, cambia las reglas del firewall y vuelve a probar los puertos.

-   En el caso de deficiencias de red, realice siempre un análisis de la causa raíz.

La calidad de servicio (QoS) se puede usar para enfrentarse a deficiencias al priorizar y separar el tráfico. Algunas organizaciones deciden implementar QoS para solucionar problemas de ancho de banda o restringir la cantidad de tráfico que fluye. Esto no mejorará la calidad y provocará nuevos problemas. Siempre debe realizarse un análisis de la causa raíz cuando los problemas de red superen los requisitos. QoS puede ser una solución.
Para obtener más información, [vea Calidad de servicio en Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)

>[!NOTE]
>Muchas redes van evolucionando gracias a las actualizaciones, al ampliarlas o por otros requisitos de negocio. Asegúrese de contar con procesos operativos que ayuden a mantener estas áreas como parte de su planificación de administración de servicios.


<table>
<tr><td>Título</td><td>Descripción</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de completar las evaluaciones de red adecuadas en todos los segmentos de red y ubicaciones de la organización?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Puede realizar una evaluación detallada de la red para asegurarse de que su red está preparada para la implementación de Microsoft Teams.</li><li>Ejecute la corrección de red en función de los resultados de la evaluación para cada segmento de red.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->
