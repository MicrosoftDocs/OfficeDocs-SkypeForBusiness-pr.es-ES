---
title: Preparar la red para Microsoft Teams |  Requisitos de Firewall del puerto
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Use esta guía para preparar la red para la implementación y el lanzamiento de Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 950786a6d1014b322c76d1f4cd35afaec789f177
ms.sourcegitcommit: 889295b507c77a93b10b3a5e826f2b0c79c31f75
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2019
ms.locfileid: "30771785"
---
![Etapas del recorrido de la actualización, con énfasis en la etapa de preparación técnica](media/upgrade-banner-tech-readiness.png "Etapas del recorrido de la actualización, con énfasis en la etapa de preparación técnica")

Este artículo forma parte de la etapa de preparación técnica del recorrido de actualización, una actividad que se completa en paralelo a la etapa de preparación del usuario. Antes de continuar, confirme que ha completado estas actividades de las etapas anteriores:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ha elegido su recorrido de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> Vea la sesión siguiente para obtener más información cómo los equipos aprovecha la red y cómo planear mejor para la conectividad de red óptima: [Planeación de los equipos de red](https://aka.ms/teams-networking)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Preparar la red para la actualización a los equipos

Si va a implementar las reuniones, audio o vídeo, puede realizar algunos pasos adicionales para optimizar la red para que la funcionalidad. Los equipos utiliza audio y vídeo tecnología (códecs) que puede adaptarse a — y, por tanto, tener un mejor rendimiento en: más de las condiciones de la red. Para garantizar un rendimiento óptimo y coherente, debe preparar la red para los equipos.

![Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la red.] (media/evaluate-my-environment-image1.png "Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la red.")

## <a name="why-should-you-prepare-your-network"></a>¿Por qué se debe preparar la red?

Antes de estudiar los pasos que deben seguirse, es importante comprender lo que pueden afectar al rendimiento de los equipos y, desde allí, satisfacción y satisfacción del usuario. Tres áreas principales de riesgo pueden afectar a cómo los usuarios perciben la calidad de la red:

- No hay suficiente ancho de banda disponible

- Bloqueadores de elementos de Firewall y proxy

- Dificultades como vibración y pérdida de paquetes de red

Los pasos descritos a continuación le ayudará a determinar que si su implementación podría verse afectada por cualquiera de estos factores y le ayudará a mover hacia una resolución. Con errores preparar la red probablemente llevarán a los usuarios insatisfechos y costosa, ad-hoc corrige. Mediante la preparación de su red y su organización: para los equipos, puede aumentar considerablemente sus posibilidades de éxito.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planeamiento del ancho de banda


Teams Microsoft le ofrece la mejor audio, vídeo y uso compartido experiencia independientemente de las condiciones de red del contenido. Con códecs variables, se pueden negociar medios en entornos de ancho de banda limitado con un impacto mínimo. Pero donde ancho de banda no es una preocupación, experiencias pueden ser optimizadas para calidad, incluida una resolución de vídeo 1080p, hasta 30fps para vídeo y 15fps para contenido y audio de alta fidelidad.


En este artículo se describe una versión concisa de forma se utiliza el ancho de banda por modalidades en distintos casos de uso de uso compartido de escritorio, vídeo y audio en tiempo real de los equipos. Los equipos siempre es conservadoras sobre la utilización de ancho de banda y puede ofrecer una calidad de vídeo HD en 1.2Mbps. El consumo de ancho de banda real en cada llamada de audio y vídeo o una reunión variará en función de varios factores, como el diseño de vídeo, la resolución de vídeo y de fotogramas de vídeo por segundo.Cuando hay más ancho de banda disponible calidad y uso aumentará para ofrecer la mejor experiencia.

|Bandwidth(Up/Down) |Escenarios |
|---|---|
|30 kbps |Llamada de audio punto a punto |
|130 kbps |Llamadas de audio de punto a punto y uso compartido de la pantalla |
|500 kbps |Vídeo de una llamada a p 360 a 30fps de calidad de punto a punto |
|1.2 Mbps |Vídeo de calidad de alta definición Peer-to-peer de llamada con resolución de alta definición 720p a 30fps |
|1,5 Mbps |Vídeo de calidad de alta definición Peer-to-peer de llamada con resolución de HD 1080p a 30fps |
|500kbps y 1 Mbps |Llamada de vídeo de grupo |
|1 Mbps/2 Mbps |Grupo de HD vídeo llamada (vídeos 540p en pantalla 1080p) |

### <a name="local-internet-egress"></a>Salida local de Internet

Muchas redes se diseñaron en su momento para usar una topología tipo hub-and-spoke. En esta topología, por lo general, el tráfico de Internet atraviesa la red WAN hasta un centro de datos central antes de salir a Internet. A menudo, esto se hace para centralizar los dispositivos de seguridad de redes y reducir así el coste general.

El tráfico de transporte hacia atrás por la WAN aumenta la latencia y repercute negativamente en la calidad y la experiencia del usuario. Como Microsoft Teams se ejecuta en una gran red global de Microsoft, existe a menudo una ubicación de emparejamiento de red cerca del usuario. Es muy probable que un usuario obtenga un mejor rendimiento si sale de un punto de Internet local que se encuentra cerca de su ubicación y accede a una red optimizada para voz lo antes posible. Para algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar tráfico al servidor front-end más cercano. En esos casos, es importante que, cuando se usa un punto de salida local, se empareje con una resolución DNS local.

Al optimizar la ruta de red a la red global de Microsoft, mejorará el rendimiento y, en última instancia, los usuarios disfrutarán de la mejor experiencia posible. Para obtener más detalles, vea la publicación del blog [Conseguir la mejor conectividad y el mejor rendimiento en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

Para obtener una experiencia óptima al usar multimedia en tiempo real dentro de Microsoft Teams, debe cumplir los requisitos de red para Office 365. Para obtener más información, vea [calidad de los medios y el rendimiento de la conectividad de red para Skype para profesionales en línea](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Los dos segmentos de red definen (cliente a Microsoft Edge) y borde de cliente a Microsoft Edge deben cumplir los siguientes requisitos:

|**Valor** |**Cliente hasta el borde de Microsoft** |**Borde de cliente hasta el borde de Microsoft** |
|---|---|---|
|**Latencia (unidireccional)** |< 50 ms |< 30 ms |
|**Latencia (tiempo de ida y vuelta o RTT)** |< 100 ms |< ms 60 |
|**Ráfagas de pérdida de paquetes** |% de <10 durante un intervalo de 200 ms |% de <1 durante un intervalo de 200 ms |
|**Pérdida de paquetes** |% de <1 durante un intervalo de 15 segundos |<0.1% durante un intervalo de 15 segundos |
|**Vibración de llegada entre granjas de paquetes** |<30 ms durante un intervalo de 15 segundos |<15 ms durante un intervalo de 15 segundos |
|**Reaprovisionamiento de paquetes** |paquetes de salida de orden <0.05% |paquetes de salida de orden <0.01% |

Para probar ambos segmentos de red, puede usar la [Herramienta de evaluación de la red](https://go.microsoft.com/fwlink/?linkid=855799). Esta herramienta se puede implementar en el cliente PC directamente y en un PC conectado hasta el borde de la red del cliente. La herramienta incluye documentación limitada, pero una documentación más profunda alrededor el uso de la herramienta se puede encontrar aquí: [Evaluación de preparación de la red](https://go.microsoft.com/fwlink/?linkid=855800). Mediante la ejecución de esta evaluación de disponibilidad de red, puede validar preparación de su red para ejecutar aplicaciones de multimedia en tiempo real, como Microsoft Teams.

> [!NOTE]
> Esto es lo mismo evaluación de disponibilidad de red que se recomienda ejecutar por los clientes que desean para implementar correctamente Skype para la empresa.

### <a name="vpn"></a>VPN

Las redes VPN ofrecen un servicio muy valioso a muchas organizaciones. Desafortunadamente, normalmente no diseñados o mientras está configurados para admitir multimedia en tiempo real. Algunas redes VPN también podrían no admitir UDP. Las redes privadas virtuales también presentan un nivel adicional de cifrado sobre el tráfico de medios que ya está cifrado. Además, la conectividad con el servicio de los equipos no sea eficaz debido a la fijación de cursor en forma de tráfico a través de un dispositivo VPN. Además, no están necesariamente diseñados desde una perspectiva de la capacidad para dar cabida a las cargas anticipadas que requieren los equipos.

Lo que se recomienda es ofrecer una ruta alternativa que omita el VPN para el tráfico de Teams. Normalmente, esto se conoce como *división túnel VPN*. La división del túnel significa que el tráfico de Office 365 no atravesar la VPN pero vaya directamente a Office 365. Este cambio repercutirá positivamente en la calidad, pero también proporciona la ventaja secundaria que supone reducir la carga de los dispositivos VPN y la red de la organización.

Para implementar un túnel dividido, consulte con su proveedor de VPN para los detalles de configuración.

### <a name="wi-fi"></a>Wi-Fi

Al igual que VPN, redes Wi-Fi no están diseñadas necesariamente o configuradas para admitir multimedia en tiempo real. Planeación de, o la optimización de, una red Wi-Fi para equipos de soporte técnico es una consideración importante para una implementación de alta calidad.

Hay varios factores que se precie para optimizar una red Wi-Fi:

- Implementar QoS o Wi-Fi Multimedia (WMM) para garantizar que el tráfico multimedia se priorice de forma acorde a través de redes Wi-Fi.

- Planeación y optimización de la Wi-Fi bandas y el acceso de punto de colocación. El intervalo de 2,4 GHz podría proporcionar una experiencia adecuada según la posición del punto de acceso, pero los puntos de acceso a menudo se ven afectados por otros dispositivos del consumidor que operan en ese intervalo. El intervalo de 5 GHz es mejor para los medios en tiempo real, debido a su rango denso, pero requiere más puntos de acceso para conseguir suficiente cobertura. Los puntos de conexión también necesitan admitir esa gama y configurarlos para poder aprovechar esas bandas de forma adecuada.

- Si se implementan redes Wi-Fi de doble banda, considere la posibilidad de implementar el control de banda. _El control de banda_ es una técnica de implementada por proveedores de Wi-Fi para influir en los clientes de banda dual para utilizar el intervalo de 5 GHz.

- Cuando los puntos de acceso del mismo canal están demasiado cerca pueden provocar la superposición de señal y compiten por equivocación, lo que resulta en una mala experiencia para el usuario. Asegurarse de que los puntos de acceso que están junto a otra en canales que no se superpongan.

Cada proveedor inalámbrico tiene sus propias recomendaciones para implementar su solución inalámbrica. Le recomendamos que consulte con su proveedor para obtener las indicaciones concretas.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de Firewall y proxy

Microsoft Teams se conecta a Microsoft Online Services y necesita conectividad a internet para esto. Para que los equipos para que funcione correctamente, debe abrir los puertos TCP 80 y 443 desde los clientes a internet y los puertos UDP 3478 a través de 3481 desde los clientes a internet. Los puertos TCP se usan para conectarse a contenido basado en web, como Exchange Online, SharePoint Online y los servicios de conversaciones en los equipos. Plug-ins y conectores también se conectan a través de estos puertos TCP. Los cuatro puertos UDP se usan para los medios, como audio y vídeo, para asegurarse de que fluyen correctamente.

Abrir estos puertos es esencial para una implementación de los equipos confiable. Bloqueo de estos puertos no es compatible y afectará a la calidad de los medios.

Si su organización requiere que se especifican los intervalos de direcciones IP y dominios a los que se deben abrir estos puertos exacta, puede restringir los intervalos IP de destino y los dominios para estos puertos. Para obtener una lista de puertos exactas, protocolos y rangos IP, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Si elige restringir los intervalos de direcciones IP de destino y los dominios, debe asegurarse de mantener la lista de puertos y rangos actualizados porque puede cambiar. Puede suscribirse a [esta fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) a actualizarse cuando se producen cambios. También es una práctica recomendada para comprobar si se abren todos los puertos mediante la ejecución de la [Skype para la herramienta de evaluación de red empresarial](https://www.microsoft.com/download/details.aspx?id=53885) de forma regular. Puede encontrar más información acerca de la funcionalidad de esta herramienta en la siguiente sección.

En el caso de un servidor proxy que se va a implementar, se recomienda que se pasan por alto el servidor proxy para todos los servicios de los equipos. Aunque es posible que funcione el uso de un servidor proxy, es muy probable que se reducirá la calidad debido a la del elemento multimedia que se ve obligado a usar TCP en lugar de UDP. Para obtener más información acerca de los servidores proxy y no usar, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Consideraciones de red adicionales

### <a name="external-name-resolution"></a>Resolución de nombres externos

Asegúrese de que todos los equipos cliente que ejecutan al cliente de los equipos pueden resolver consultas DNS externas para descubrir los servicios proporcionados por Office 365.

### <a name="nat-pool-size"></a>Tamaño del grupo de servidores NAT

Cuando varios usuarios y dispositivos de acceso a Office 365 mediante el uso de traducción de direcciones de red (NAT) o traducción de direcciones de puerto (PAT), debe asegurarse de que los dispositivos ocultos detrás de cada dirección IP enrutable públicamente no superen el número compatible.

Para mitigar este riesgo, asegúrese de adecuada direcciones IP públicas se asignan a los grupos de NAT para evitar el agotamiento de puerto. Agotamiento del puerto hará que los usuarios finales internos y los dispositivos hacer frente a problemas al conectarse a los servicios de Office 365. Para obtener más información, vea [admitir NAT con Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Instrucciones de detección y prevención de intrusiones

Si su entorno tiene un sistema de detección de intrusiones o sistema de prevención de intrusiones implementado para obtener un nivel adicional de seguridad para las conexiones salientes, asegúrese de que todo el tráfico que tiene las direcciones URL de Office 365 como su destino está en la lista blanca.

## <a name="test-the-network"></a>La red de prueba

Una vez completada la preparación de la planeación y la red, incluida la actualización de ancho de banda y la apertura de puertos en el firewall: debe probar el rendimiento de la red. Los resultados de esta prueba pintan una imagen más clara de optimización de la red o corrección necesarios para el éxito de su implementación de los equipos.

Puede descargar el [Skype para la herramienta de evaluación de red empresarial](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si está lista para los equipos de la red. La herramienta ofrece una funcionalidad dual: puede comprobar si se han abierto todos los puertos correctos, y puede probar de dificultades de red.

Después de descargar e instalar la herramienta, puede encontrar en los archivos de C:\Program (x86) \Microsoft Skype para la herramienta de evaluación de red empresarial. Una guía detallada de cómo usar la herramienta, Usage.docx, se incluye en ese directorio.

### <a name="test-for-opened-ports"></a>Prueba de puertos abiertos

Abra una ventana del símbolo del sistema y navegue hasta el directorio de la herramienta de evaluación de la red, escriba **cd archivos de C:\Program (x86) \Microsoft Skype para la herramienta de evaluación de red empresarial**. En el símbolo del sistema, inicie la prueba de puertos abiertos escribiendo **networkassessmenttool.exe /connectivitycheck**

Después de ejecutar las comprobaciones, la herramienta se muestre el mensaje "Las comprobaciones se terminó correctamente" o un informe sobre los puertos que se han bloqueado. También genera un archivo denominado Connectivity_results.txt, que contiene el resultado de la herramienta y lo almacena en la carpeta % userprofile %\\appdata\\local\\microsoft Skype para la herramienta de evaluación de red empresarial\\ Active directory.

Se recomienda ejecutar las comprobaciones de conectividad con regularidad para asegurarse de los puertos se han abierto y funcionan correctamente.

### <a name="test-for-network-impairments"></a>Pruebas en busca de problemas de red

Para aumentar la satisfacción de los usuarios, debe limitar cualquier dificultades en la red. Las dificultades de red más comunes son retraso (latencia), pérdida de paquetes y vibración:

- **Latencia:** Esto es el tiempo necesario para obtener un paquete IP de punto A punto b en la red. Este retraso de propagación de red básicamente está asociado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una sobrecarga adicional realizada por los diversos enrutadores intermedios. Latencia se mide como el tiempo de ida y vuelta o unidireccional.

- **Pérdida de paquetes**: a menudo se define como un porcentaje de paquetes que se pierden en una determinada ventana de tiempo. Pérdida de paquetes afecta directamente a la calidad de audio: desde pequeñas, individual los paquetes perdidos no tener casi afectar a las pérdidas de ráfagas opuesta que causa el audio para recortar completamente.

- **Vibración de llegada entre paquetes, o simplemente vibración:** Éste es el cambio promedio de retraso entre envíos sucesivos de paquetes. Puede adaptar el software más moderno de VoIP, incluidos Skype para la empresa, para algunos niveles de vibración a través de almacenamiento en búfer. Es sólo cuando la vibración supera el almacenamiento en búfer que un participante se tenga en cuenta los efectos de vibración.

Los valores máximos de estas dificultades se describen en el [rendimiento de conectividad de red y calidad Media](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Cuando las pruebas para estas dificultades, podemos distinguir entre dos segmentos independientes:

- El *segmento del borde* es el segmento en el que reside el enrutador. Éste es el segmento de red lógica más cercano conectado a internet en cada una de las ubicaciones. En la mayoría de los casos, es el punto de conexión del enrutador o, posiblemente, una red perimetral (también conocida como *DMZ*, *zona desmilitarizada*y *subred protegida*). No hay más tráfico que afecta a los dispositivos que no sean el enrutador debe producirse entre este segmento e internet.

- El *segmento del cliente* es el segmento de red lógica en la que residen los clientes.

Debe probar ambos segmentos mediante el uso de la herramienta de evaluación de la red. Para probar el segmento, navegue hasta el directorio y escriba **networkassessmenttool.exe** en el símbolo del sistema. Los resultados se escriben en un archivo denominado Results.tsv, y se puede comparar con los [requisitos](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para cada segmento.

Tenga en cuenta que ambos segmentos deben cumplir los requisitos para una implementación de alta calidad. Se recomienda ejecutar la herramienta varias veces para una hora directamente para obtener una buena indicación de rendimiento de la red.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Corrección de red

Si los resultados de la planeación de ancho de banda, las pruebas de puerto o los requisitos de red para las pruebas muestran que su red actual necesita corrección antes de implementar los equipos, puede hacerlo de varias maneras:

- Para el ancho de banda insuficiente, actualización conexiones de modo que puede flujo de tráfico a Office 365 no les afectan.

- Para los puertos bloqueados, cambie las reglas de firewall y vuelva a probar los puertos.

- Para problemas de red, siempre que realice un análisis de causa de origen.

Calidad de servicio (QoS) puede usarse para auditiva batalla por orden de prioridad y separar el tráfico. Algunas organizaciones optan por implementar QoS para resolver los problemas de ancho de banda o restringir la cantidad de tráfico que fluyen. Esto no mejora la calidad y va a dar lugar a problemas nuevo. Siempre debe realizar un análisis de causa raíz cuando dificultades de red superan los requisitos. QoS puede ser una solución. Para obtener más información, vea [Calidad de servicio en los equipos de Microsoft](qos-in-teams.md).

>[!NOTE]
>Muchas redes van evolucionando gracias a las actualizaciones, al ampliarlas o por otros requisitos de negocio. Asegúrese de contar con procesos operativos que ayuden a mantener estas áreas como parte de su planificación de administración de servicios.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de completar las evaluaciones de red adecuada en todos los segmentos de red y ubicaciones de la organización?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Pasos siguientes</td><td><ul><li>Puede realizar una evaluación de red detallada para ayudar a garantizar que la red está preparada para la implementación de Microsoft Teams. Para obtener más información, vea <a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">Evaluación de preparación de la red</a>.</li><li>Realizar la corrección de red en función de los resultados de la evaluación de disponibilidad de red para cada segmento de red.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Impresiones clave

Estos son los principales puntos de esta guía. Debe:

- Abra los puertos TCP 80 y 443 saliente desde clientes que utilizarán los equipos.

- Abra los puertos UDP 3478 a través de 3481 saliente desde clientes que utilizarán los equipos.

- Asegúrese de que dispone de suficiente ancho de banda para la implementación de los equipos al completar el [Organizador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

- Ejecutar la [Herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885) y asegúrese de que cumple con los requisitos descritos en el [rendimiento de conectividad de red y calidad Media](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) desde el segmento del borde y el segmento del cliente.

## <a name="related-topics"></a>Temas relacionados

[Vídeo: Planeación de red](https://aka.ms/teams-networking)
