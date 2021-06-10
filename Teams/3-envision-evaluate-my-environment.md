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
description: Use personas y análisis de red para evaluar la preparación de su organización, abrir los puertos TCP y UDP correctos, realizar cualquier corrección de red.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b65e6f2f6db4f5e824e55368d0a7a097eb39ad9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094778"
---
# <a name="evaluate-my-environment"></a>Evaluar mi entorno

En este artículo se proporciona información general sobre los requisitos para evaluar correctamente el entorno actual para usar los servicios de voz en la nube. Al evaluar su entorno, identificará riesgos y requisitos que influirán en la implementación global de voz en la nube. Al identificar estos elementos previamente, puede ajustar la planificación para impulsar el éxito.

## <a name="introduction-to-evaluating-your-environment"></a>Introducción a la evaluación del entorno

Para lograr los resultados clave objetivo (OKR), anteriormente tomó decisiones clave del servicio. El siguiente paso es realizar detección ambiental para evaluar todos los aspectos relacionados con su infraestructura de TI y telefonía, redes y operaciones para confirmar que su organización está lista para implementar la solución.

La detección ambiental debe incluir una evaluación de preparación de red para asegurarse de que su red puede admitir la implementación de las audioconferencias o Sistema telefónico con los servicios del Plan de llamadas.

Identifique los riesgos técnicos como parte de una evaluación ambiental y evaluación de preparación para la adopción, y desarrolle un plan de mitigación para cada riesgo identificado.
Debe incorporar esta información en el registro de riesgos.

<!--ENDOFSECTION-->

## <a name="current-environment"></a>Entorno actual

Como parte de su detección ambiental, incluya todos los asuntos relacionados con la informática del usuario final, como una evaluación de preparación de equipos y dispositivos móviles para admitir audioconferencias y Sistema telefónico con casos de uso empresarial del Plan de llamadas, desde requisitos de hardware hasta requisitos de software.

La detección ambiental también puede descubrir si necesita [transferir números de teléfono a Microsoft.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
Conocer esto ayudará a su organización a ajustar su plan de proyecto en consecuencia y preparar la información necesaria para la porción de números. Puede usar la detección [ambiental para Microsoft Teams implementación para](environmental-discovery-for-microsoft-teams-rollout.md) realizar la detección ambiental.

<table>
<tr><td>Título</td><td>Descripción</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Quién será responsable de completar una evaluación del entorno?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Documente los resultados de la evaluación del entorno.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>Capacidades de evaluación de la adopción y la administración de cambios

La implementación pone una nueva tecnología al alcance de un usuario, pero los resultados empresariales solo se realizan después de que los usuarios realmente adopten esa solución como propia. Para garantizar la adopción sostenida de una nueva solución, deberá centrar sus esfuerzos en la preparación de los usuarios y la administración de cambios. Para obtener resultados óptimos, realice la planificación de la preparación del usuario como un flujo de trabajo paralelo a sus actividades de preparación técnica e incorpore las siguientes actividades:

-   **Creación de perfiles de usuario y organización:** Análisis de la receptividad organizativa para cambiar, además de usar el análisis de mayúsculas y minúsculas

-   **Preparación y preparación de recursos:** Creación de recursos de conciencia, aprendizaje y soporte técnico dirigidos y de amplio alcance, incluida la mensajería de valor centrada para acelerar la compra de usuarios

Use las siguientes consideraciones para evaluar la preparación de su organización para abordar la administración de cambios de usuario.

<table>
<tr><td>Título</td><td>Descripción</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>¿Ha tenido éxito con la adopción por parte del usuario de software o servicios?</li><li>¿Puede realizar un seguimiento de la captación de uso?</li><li>¿Tiene recursos para diseñar y administrar una campaña de adopción inicial y &mdash; &mdash; continua (concienciación, formación y soporte técnico)?</li><li>¿Tiene un equipo de administración de cambios o adopción de usuarios dedicado o puede invertir en esos recursos para garantizar resultados empresariales?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Si respondió sí a todo lo anterior, identifique las partes interesadas de la administración de cambios de usuario correctas y comience la planificación de &quot; &quot; la preparación del usuario.</li><li>Si respondió que no a algunas o a todas las anteriores, considere la posibilidad de participar en recursos externos para ayudar a impulsar la administración de cambios y las actividades relacionadas &quot; &quot; con la adopción para su organización.</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>Preparación de red

Teams tecnología de audio y vídeo (códecs) que puede adaptarse a la mayoría de las condiciones de red y, por lo tanto, mejorar su rendimiento. Para garantizar un rendimiento óptimo y coherente, debe preparar la red para Teams.

![Diagrama que describe los tres componentes de calidad](media/evaluate-my-environment-image1.png "Diagrama que describe los tres componentes de calidad y cómo la administración de servicios se superpone a los tres componentes. Con un foco en la red.")

## <a name="key-takeaways"></a>Sorteos clave

Estos son los principales puntos de esta guía. Debe:

-   Abra los puertos TCP 80 y 443 salientes desde clientes que usarán Teams.

-   Abra los puertos UDP 3478 a 3481 salientes desde clientes que usarán Teams.

-   Asegúrese de que tiene ancho de banda suficiente para implementar Teams.

-   Ejecute la [Herramienta de evaluación de red](https://www.microsoft.com/download/details.aspx?id=53885) [](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) y asegúrese de que cumple los requisitos descritos en Calidad de medios y rendimiento de conectividad de red desde el segmento perimetral y el segmento de cliente.

## <a name="why-should-you-prepare-your-network"></a>¿Por qué debe preparar su red?

Antes de ver los pasos que se deben seguir, es importante comprender qué puede afectar al rendimiento de Teams y, por lo tanto, la satisfacción y la felicidad del usuario.
Tres áreas de riesgo principales pueden afectar a la forma en que los usuarios perciben la calidad de la red:

-   Ancho de banda insuficiente disponible

-   Firewall y bloqueadores de proxy

-   Deficiencias de red como vibración y pérdida de paquetes

Los pasos que se describen a continuación le ayudarán a determinar si la implementación podría verse afectada por cualquiera de estos factores y le ayudarán a avanzar hacia una resolución.
Si no se prepara la red, es probable que esto lleve a usuarios insatisfechos y a costosas correcciones ad hoc. Al preparar su red y su organización para Teams, puede aumentar considerablemente sus posibilidades de éxito.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planeamiento del ancho de banda

El primer paso para la preparación de la red es garantizar que su red tenga suficiente ancho de banda disponible para las Teams proporcionará a los usuarios. Planear un ancho de banda suficiente es una tarea bastante sencilla y un comienzo de barrera muy bajo para asegurarse de que los usuarios tendrán una experiencia de Teams alta calidad.

### <a name="local-internet-egress"></a>Salida local de Internet

Muchas redes se diseñaron en su momento para usar una topología tipo hub-and-spoke. En esta topología, por lo general, el tráfico de Internet atraviesa la red WAN hasta un centro de datos central antes de salir a Internet. A menudo, esto se hace para centralizar los dispositivos de seguridad de redes y reducir así el coste general.

El tráfico de transporte hacia atrás por la WAN aumenta la latencia y repercute negativamente en la calidad y la experiencia del usuario. Como Microsoft Teams se ejecuta en la gran red global de Microsoft, a menudo hay una ubicación de emparejamiento de red cerca del usuario. Es muy probable que un usuario obtenga un mejor rendimiento si sale de un punto de Internet local que se encuentra cerca de su ubicación y accede a una red optimizada para voz lo antes posible. Para algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar tráfico al servidor front-end más cercano. En estos casos, es importante que al usar un punto de salida local, se empareja con la resolución dns local.

Optimizar la ruta de red a la red global de Microsoft mejorará el rendimiento y, en última instancia, proporcionará la mejor experiencia para los usuarios. Para obtener más detalles, vea la publicación del blog [Conseguir la mejor conectividad y el mejor rendimiento en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

### <a name="vpn"></a>VPN

Las redes VPN ofrecen un servicio muy valioso a muchas organizaciones. Desafortunadamente, normalmente no están diseñados o configurados para admitir medios en tiempo real. Algunas redes VPN también podrían no admitir UDP. Las VPN también introducen una capa adicional de cifrado en el tráfico multimedia que ya está cifrado. Además, es posible que la conectividad al Teams no sea eficiente debido a la inmovilización del tráfico a través de un dispositivo VPN.
Además, no están diseñados necesariamente desde una perspectiva de capacidad para adaptarse a las cargas anticipadas que Teams requerirán.

Lo que se recomienda es ofrecer una ruta alternativa que omita el VPN para el tráfico de Teams. Esto se conoce comúnmente como *VPN de túnel dividido.* El túnel dividido significa que el tráfico de Microsoft 365 o Office 365 no atravesará la VPN, pero irá directamente a Microsoft 365 o Office 365. Este cambio tendrá un impacto positivo en la calidad, pero también proporciona el beneficio secundario de reducir la carga de los dispositivos VPN y la red de la organización.

Para implementar un túnel dividido, consulte con su proveedor de VPN para los detalles de configuración.

### <a name="wi-fi"></a>Wi-Fi

Al igual que vpn, Wi-Fi redes no están necesariamente diseñadas o configuradas para admitir medios en tiempo real. Planear o optimizar una red de Wi-Fi para admitir Teams es una consideración importante para una implementación de alta calidad.

Hay varios factores que están en juego para optimizar una red Wi-Fi red:

-   Implementar QoS o Wi-Fi Multimedia (WMM) para garantizar que el tráfico multimedia se priorice de forma acorde a través de redes Wi-Fi.

-   Planear y optimizar las bandas Wi-Fi y la ubicación del punto de acceso. El intervalo de 2,4 GHz puede proporcionar una experiencia adecuada en función de la ubicación del punto de acceso, pero a los puntos de acceso normalmente también le afectan otros dispositivos de consumidores que funcionan en esa gama. El intervalo de 5 GHz es mejor para los medios en tiempo real, debido a su rango denso, pero requiere más puntos de acceso para conseguir suficiente cobertura. Los puntos de conexión también necesitan admitir esa gama y configurarlos para poder aprovechar esas bandas de forma adecuada.

-   Si se implementan redes Wi-Fi banda doble, considere la posibilidad de implementar la dirección de banda. Dirección de banda es una técnica implementada por Wi-Fi proveedores para influir en los clientes de doble banda para usar el rango de 5 GHz.

-   Cuando los puntos de acceso del mismo canal están demasiado cerca juntos, pueden causar superposición de señales y competir involuntarlamente, lo que resulta en una mala experiencia para el usuario. Asegúrese de que los puntos de acceso que están próximos entre ellos se encuentran en canales que no se superponen.

Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Le recomendamos que consulte con su proveedor para obtener las indicaciones concretas.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de firewall y proxy

Microsoft Teams se conecta a Microsoft Online Services y necesita conectividad a Internet para ello. Para que Teams funcione correctamente, debe abrir los puertos TCP 80 y 443 desde los clientes a Internet, y los puertos UDP 3478 a 3481 desde los clientes a Internet. Los puertos TCP se usan para conectarse al contenido basado en web, como SharePoint Online, Exchange Online y los Teams chat.
Los complementos y conectores también se conectan a través de estos puertos TCP. Los cuatro puertos UDP se usan para medios como audio y vídeo, para asegurarse de que fluyan correctamente.

Abrir estos puertos es esencial para una implementación Teams confianza. Bloquear estos puertos no es compatible y tendrá un efecto en la calidad de los medios.

Si su organización requiere que especifique los intervalos y dominios de direcciones IP exactos a los que deben abrirse estos puertos, puede restringir los rangos y dominios IP de destino para estos puertos. Para obtener una lista de puertos, protocolos e intervalos IP exactos, vea Microsoft 365 o Office 365 direcciones URL e [intervalos de direcciones IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)
Si elige restringir los rangos y dominios de direcciones IP de destino, debe asegurarse de mantener actualizada la lista de puertos y rangos porque pueden cambiar. Puede suscribirse a [esta fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para actualizarla cuando se produzcan cambios. También es una buena práctica comprobar si todos los puertos se abren ejecutando la [herramienta](https://www.microsoft.com/download/details.aspx?id=53885) de evaluación de Skype Empresarial red de forma periódica. Puede obtener más información sobre la funcionalidad de esta herramienta en la sección siguiente.

En caso de que se implemente un servidor proxy, se recomienda omitir el servidor proxy para todos los Teams servidor proxy. Aunque usar un proxy puede funcionar, es muy probable que la calidad se reduzca debido a que los medios se ven obligados a usar TCP en lugar de UDP. Para obtener más información sobre los servidores proxy y la omisión, vea Microsoft 365 o Office 365 direcciones URL e [intervalos de direcciones IP.](./office-365-urls-ip-address-ranges.md)

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>Probar la red

Después de completar la planificación y la preparación de la red(incluida la actualización del ancho de banda y la apertura de puertos en el firewall), debe probar el rendimiento de la red. Los resultados de estas pruebas mostrarán una imagen más clara de cualquier optimización o corrección de red necesaria para el éxito de las audioconferencias o Sistema telefónico con la implementación del plan de llamadas.

Puede descargar la herramienta de [evaluación Skype Empresarial red](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si su red está lista para Teams. La herramienta ofrece una doble funcionalidad: puede comprobar si se han abierto todos los puertos correctos y puede comprobar si hay deficiencias de red.

Después de descargar e instalar la herramienta, puede encontrarla en C: Archivos de programa \\ de Microsoft Skype Empresarial herramienta de evaluación de \\ red. En ese directorio se incluye una guía detallada sobre cómo usar Usage.docx herramienta.

### <a name="test-for-opened-ports"></a>Probar los puertos abiertos

Abra una ventana del símbolo del sistema y vaya al directorio de la Herramienta de evaluación de red especificando cd C: Archivos de programa **de Microsoft Skype Empresarial Herramienta de evaluación de \\ \\ red.** En el símbolo del sistema, inicie la prueba de puertos abiertosnetworkassessmenttool.exe **/connectivitycheck**

Después de ejecutar las comprobaciones, la herramienta mostrará el mensaje "Comprobaciones completadas correctamente" o informe sobre los puertos bloqueados.
También genera un archivo denominado Connectivity_results.txt, que contiene el resultado de la herramienta y lo almacena en el directorio de herramientas de evaluación de red local de Microsoft Skype Empresarial de \\ \\ \\ %userprofile%. \\

Le recomendamos que ejecute periódicamente las comprobaciones de conectividad para asegurarse de que los puertos se han abierto y funcionan correctamente.

### <a name="test-for-network-impairments"></a>Comprobar si hay deficiencias en la red

Para aumentar la satisfacción de los usuarios, debe limitar las deficiencias de su red.
Las deficiencias de red más comunes son retraso (latencia), pérdida de paquetes y vibración:

-   **Latencia:** Este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B en la red. Este retraso de propagación de red está esencialmente vinculado a la distancia física entre los dos puntos y la velocidad de la luz, incluida la sobrecarga adicional que han tomado los distintos enrutadores entre sí.
    La latencia se mide como tiempo de ida o de ida y vuelta.

-   **Pérdida de paquetes:** a menudo se define como un porcentaje de paquetes que se pierden en una ventana de tiempo determinada. La pérdida de paquetes afecta directamente a la calidad del audio: desde pequeños paquetes perdidos individuales que casi no tienen ningún impacto a las pérdidas de ráfagas de back-to-back que hacen que el audio se corte por completo.

-   **Vibración de llegada entre paquetes o simplemente vibración:** Este es el cambio promedio de retraso entre paquetes sucesivos. La mayoría del software VoIP moderno, incluido Skype Empresarial, puede adaptarse a algunos niveles de vibración mediante el almacenamiento en búfer. Solo cuando el vibración supera el almacenamiento en búfer, un participante notará los efectos de la vibración.

Los valores máximos para estas deficiencias se describen en [Calidad multimedia y rendimiento de conectividad de red.](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)
Al realizar pruebas para estas deficiencias, distinguimos entre dos segmentos diferentes:

-   El *segmento perimetral* es el segmento en el que vive el enrutador. Este es el segmento de red lógica más cercano conectado a Internet en cada una de sus ubicaciones. En la mayoría de los casos, este es el punto de conexión del enrutador, o posiblemente una red perimetral (también conocida como *DMZ,* zona *desmilitarizada* y subred *con pantalla).* No debe producirse más tráfico que afecte a dispositivos distintos del enrutador entre este segmento e Internet.

-   El *segmento de cliente* es el segmento de red lógico en el que residen los clientes.

Debe probar ambos segmentos con la Herramienta de evaluación de red. Para probar el segmento, vaya al directorio y **escribanetworkassessmenttool.exe** en el símbolo del sistema. Los resultados se escriben en un archivo denominado Results.tsv y puede compararlos con [los](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) requisitos de cada segmento.

Tenga en cuenta que ambos segmentos deben cumplir los requisitos para una implementación de alta calidad. Le recomendamos que ejecute la herramienta varias veces durante una hora directamente para obtener una buena indicación del rendimiento de su red.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Corrección de red

Si los resultados de la planificación de ancho de banda, las pruebas de portabilidad o las pruebas de requisitos de red muestran que su red actual necesita corrección antes de implementar Teams, puede hacerlo de varias maneras:

-   Para un ancho de banda insuficiente, actualice las conexiones para que el tráfico Microsoft 365 o Office 365 pueda fluir sin obstáculos.

-   Para los puertos bloqueados, cambie las reglas del firewall y vuelva a probar los puertos.

-   Para deficiencias de red, realice siempre un análisis de causa raíz.

La calidad del servicio (QoS) se puede usar para combatir deficiencias priorizando y separando el tráfico. Algunas organizaciones eligen implementar QoS para superar problemas de ancho de banda o restringir la cantidad de tráfico que fluye. Esto no mejorará la calidad y dará lugar a nuevos problemas. Siempre se debe realizar un análisis de causa raíz cuando los problemas de red superan los requisitos. QoS puede ser una solución.
Para obtener más información, vea Calidad del servicio [en Microsoft Teams](./qos-in-teams.md).

>[!NOTE]
>Muchas redes van evolucionando gracias a las actualizaciones, al ampliarlas o por otros requisitos de negocio. Asegúrese de contar con procesos operativos que ayuden a mantener estas áreas como parte de su planificación de administración de servicios.


<table>
<tr><td>Título</td><td>Descripción</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Puntos de decisión</td><td><ul><li>Quién será responsable de completar evaluaciones de red adecuadas en todos los segmentos de red y ubicaciones de la organización?</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Pasos siguientes</td><td><ul><li>Puede realizar una evaluación de red detallada para asegurarse de que su red está lista para su Microsoft Teams implementación.</li><li>Realice la corrección de red en función de los resultados de la evaluación para cada segmento de red.</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->