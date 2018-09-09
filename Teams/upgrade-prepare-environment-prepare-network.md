---
title: Preparar la red para la actualización a los equipos - Microsoft Teams
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Use esta guía para preparar la red para la implantación y la implementación de los equipos
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 465112aa154620f4cabf59aa1e6d4c70aa74eb16
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887808"
---
![Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica] (media/upgrade-banner-tech-readiness.png "Fases de la actualización viaje, con especial hincapié en la fase de preparación técnica")

En este artículo forma parte de la fase de preparación técnica de su viaje de actualización, una actividad completar en paralelo con la fase de preparación del usuario. Antes de continuar, confirme que ha realizado estas actividades de fases anteriores:

-   [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
-   [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
-   [Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos](https://aka.ms/SkypeToTeams-Coexist)
-   [Elegido su viaje por la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>Preparar la red para la actualización a los equipos

Si va a implementar las reuniones, audio o vídeo, puede realizar algunos pasos adicionales para optimizar la red para que la funcionalidad. Los equipos utiliza audio y vídeo tecnología (códecs) que puede adaptarse a — y, por tanto, tener un mejor rendimiento en: más de las condiciones de la red. Para garantizar un rendimiento óptimo y coherente, debe preparar la red para los equipos.

![Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la red.] (media/evaluate-my-environment-image1.png "Diagrama que describe los tres componentes de calidad, y cómo administración de servicios superpone todos los tres componentes. Con un enfoque en la red.")

## <a name="why-should-you-prepare-your-network"></a>¿Por qué se debe preparar la red?

Antes de estudiar los pasos que deben seguirse, es importante comprender lo que pueden afectar al rendimiento de los equipos y, desde allí, satisfacción y satisfacción del usuario. Tres áreas principales de riesgo pueden afectar a cómo los usuarios perciben la calidad de la red:

-   No hay suficiente ancho de banda disponible

-   Bloqueadores de elementos de Firewall y proxy

-   Dificultades como vibración y pérdida de paquetes de red

Los pasos descritos a continuación le ayudará a determinar que si su implementación podría verse afectada por cualquiera de estos factores y le ayudará a mover hacia una resolución. Con errores preparar la red probablemente llevarán a los usuarios insatisfechos y costosa, ad-hoc corrige. Mediante la preparación de su red y su organización: para los equipos, puede aumentar considerablemente sus posibilidades de éxito.

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>Planeación de ancho de banda

El primer paso para la preparación de la red es garantizar que la red tiene suficiente ancho de banda disponible para las modalidades de los equipos que va a proporcionar a los usuarios. La planeación de suficiente ancho de banda es una tarea bastante sencilla y un inicio de muy baja-barrera para garantizar que los usuarios tendrán una experiencia de los equipos de alta calidad.

Inicie el ancho de banda planear viaje para los equipos en el [sitio Web de mi asesor](https://myadvisor.fasttrack.microsoft.com/) mediante el uso del organizador de la red. El organizador de la red proporciona ancho de banda por sitio planeación de los equipos y ofrece recomendaciones para optimizar el rendimiento de la red.

> [!IMPORTANT]
> Si el ancho de banda necesario no está disponible, la pila de medios dentro de los equipos degrada la calidad de la sesión de audio y vídeo para dar cabida a ese menor cantidad de ancho de banda disponible, lo que afecta a la calidad de la llamada o reunión. El cliente de los equipos intenta dar prioridad a la calidad del audio a través de la calidad de vídeo. Por lo tanto, es muy importante tener el ancho de banda esperado disponible.


|Actividad  |Descargar el ancho de banda  |Cargar el ancho de banda  |Flujo de tráfico |
|---------|---------|---------|---------|
|**Llamada de audio punto a punto**     |0,1 Mbps         |0,1 Mbps        |Cliente <> Cliente         |
|**Llamada de vídeo punto a punto (pantalla completa)**     |4 Mbps         |4 Mbps         |Cliente <> Cliente          |
|**Uso compartido de escritorio punto a punto (1920 & #215; 1080 resolución)**     |4 Mbps         |4 Mbps         |Cliente <> Cliente          |
|**Reunión de dos participantes**     |4 Mbps         |4 Mbps         |Cliente <> Office 365         |
|**Reunión de tres participantes**     |8 Mbps         |6.5 Mbps         |Cliente <> Office 365           |
|**Reunión de cuatro participante**     |5,5 Mbps         |4 Mbps         |Cliente <> Office 365           |
|**Cinco o más – participante reunión**     |6 Mbps         |1,5 Mbps         |Cliente <> Office 365           |

### <a name="local-internet-egress"></a>Salida de internet local

Muchas redes se diseñaron para usar un concentrador y radio de topología. En esta topología, el tráfico de internet recorre normalmente la WAN a un centro de datos central antes de que se desprende (egresses) a internet. A menudo, esto se realiza para centralizar los dispositivos de seguridad de red con el objetivo de reducir los costos generales.

Back-tomando el tráfico a través de la WAN aumenta la latencia y tiene un impacto negativo en la calidad y la experiencia del usuario. Debido a que Microsoft Teams se ejecuta en la red global grandes de Microsoft, a menudo es una ubicación de interconexión de red más cercano al usuario. Un usuario es muy probable que va a obtener un mejor rendimiento por egressing fuera de un punto de internet local cerca de su ubicación y sesión en nuestra red optimizado para voz tan pronto como sea posible. Para algunas cargas de trabajo, las solicitudes DNS se utilizan para enviar el tráfico a la más cercana del servidor front-end. En estos casos, es importante que cuando se utiliza un punto de salida local, se corresponde con la resolución DNS local.

Optimización de la ruta de acceso de red a red global de Microsoft va a mejorar el rendimiento y en última instancia proporcionar la mejor experiencia para los usuarios. Para obtener más detalles, consulte el blog [Introducción la mejor conectividad y rendimiento en Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).


Para obtener una experiencia óptima al usar multimedia en tiempo real dentro de Microsoft Teams, debe cumplir los requisitos de red para Office 365. Para obtener más información, consulte [Calidad de medios y rendimiento de conectividad de la red en Skype Empresarial Online](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Los dos segmentos de red definitivos (cliente a Microsoft Edge y perímetro de cliente a Microsoft Edge) deben cumplir con los siguientes requisitos:


|**Valor**  |**Cliente a Microsoft Edge**  |**Perímetro de cliente a Microsoft Edge**  |
|---------|---------|---------|
|**Latencia (unidireccional)**     |< 50 ms          |< 30 ms          |
|**Latencia (tiempo de ida y vuelta o RTT)** |< 100 ms         |< 60 ms         |
|**Pérdida de paquetes de ráfaga**    |< 10% durante un intervalo de 200 ms         |< % 1 durante cualquier intervalo de 200 ms         |
|**Pérdida de paquetes**     |< % 1 durante cualquier intervalo de 15 segundos          |< 0,1% durante un intervalo de 15 segundos         |
|**Vibración de llegada entre granjas de paquetes**    |< 30 ms durante un intervalo de 15 segundos         |< 15 ms durante un intervalo de 15 segundos         |
|**Reordenamiento de paquetes**    |< 0,05% paquetes sin ordenar         |< 0,01% paquetes sin ordenar         |

Para probar los dos segmentos de red, puede usar la [herramienta de evaluación de red](https://go.microsoft.com/fwlink/?linkid=855799). Esta herramienta puede implementarse en el equipo cliente directamente y en un equipo que esté conectado al perímetro de red de cliente. La herramienta incluye documentación limitada, pero se puede ver una documentación más profunda sobre el uso de la herramienta aquí: [herramienta de evaluación de red](https://go.microsoft.com/fwlink/?linkid=855800). Al ejecutar la evaluación de preparación de la red, puede validar la preparación de la red para ejecutar aplicaciones multimedia en tiempo real, como Microsoft Teams.

> [!NOTE]
> Esto es lo mismo evaluación de disponibilidad de red que se recomienda ejecutar por los clientes que desean para implementar correctamente Skype para la empresa.


### <a name="vpn"></a>VPN

Las redes privadas virtuales proporcionan un servicio valioso para muchas organizaciones. Desafortunadamente, normalmente no diseñados o mientras está configurados para admitir multimedia en tiempo real. Algunas redes privadas virtuales también podrían no admitir UDP. Las redes privadas virtuales también presentan un nivel adicional de cifrado sobre el tráfico de medios que ya está cifrado. Además, la conectividad con el servicio de los equipos no sea eficaz debido a la fijación de cursor en forma de tráfico a través de un dispositivo VPN. Además, no están necesariamente diseñados desde una perspectiva de la capacidad para dar cabida a las cargas anticipadas que requieren los equipos.

La recomendación es proporcionar una ruta de acceso alternativa que omite la VPN para el tráfico de los equipos. Normalmente, esto se conoce como *división túnel VPN*. La división del túnel significa que el tráfico de Office 365 no atravesar la VPN pero vaya directamente a Office 365. Este cambio tendrá un impacto positivo en calidad, pero también proporciona la ventaja secundaria de reducir la carga de los dispositivos VPN y la red de la organización.

Para implementar un túnel dividido, póngase en contacto con su proveedor de VPN para los detalles de configuración.

### <a name="wi-fi"></a>Wi-Fi

Al igual que VPN, redes Wi-Fi no están diseñadas necesariamente o configuradas para admitir multimedia en tiempo real. Planeación de, o la optimización de, una red Wi-Fi para equipos de soporte técnico es una consideración importante para una implementación de alta calidad.

Hay varios factores que se precie para optimizar una red Wi-Fi:

-   Implementación de QoS o Multimedia Wi-Fi (WMM) para asegurarse de que el tráfico de medios se Introducción prioriza según corresponda a través de las redes Wi-Fi.

-   Planeación y optimización de la Wi-Fi bandas y el acceso de punto de colocación. El intervalo de 2,4 GHz podría proporcionar una experiencia adecuada según la posición del punto de acceso, pero los puntos de acceso a menudo se ven afectados por otros dispositivos del consumidor que operan en ese intervalo. El intervalo de 5 GHz se adapta mejor a medios en tiempo real debido a su intervalo denso, pero requiere más puntos de acceso para obtener la cobertura suficiente. Los extremos también deben admitir dicho rango y configurarse para aprovechar las bandas en consecuencia.

-   Si se implementan redes Wi-Fi de doble banda, considere la posibilidad de implementar el control de banda. _El control de banda_ es una técnica de implementada por proveedores de Wi-Fi para influir en los clientes de banda dual para utilizar el intervalo de 5 GHz.

-   Cuando los puntos de acceso del mismo canal están demasiado cerca pueden provocar la superposición de señal y compiten por equivocación, lo que resulta en una mala experiencia para el usuario. Asegurarse de que los puntos de acceso que están junto a otra en canales que no se superpongan.

Cada proveedor inalámbrico tiene sus propias recomendaciones para la implementación de su solución inalámbrica. Se recomienda que consulte a su proveedor para obtener instrucciones específicas.

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>Requisitos de Firewall y proxy

Microsoft Teams se conecta a Microsoft Online Services y necesita conectividad a internet para esto. Para que los equipos para que funcione correctamente, debe abrir los puertos TCP 80 y 443 desde los clientes a internet y los puertos UDP 3478 a través de 3481 desde los clientes a internet. Los puertos TCP se usan para conectarse a contenido basado en web, como Exchange Online, SharePoint Online y los servicios de conversaciones en los equipos. Plug-ins y conectores también se conectan a través de estos puertos TCP. Los cuatro puertos UDP se usan para los medios, como audio y vídeo, para asegurarse de que fluyen correctamente.

Abrir estos puertos es esencial para una implementación de los equipos confiable. Bloqueo de estos puertos no es compatible y afectará a la calidad de los medios.

Si su organización requiere que se especifican los intervalos de direcciones IP y dominios a los que se deben abrir estos puertos exacta, puede restringir los intervalos IP de destino y los dominios para estos puertos. Para obtener una lista de puertos exactas, protocolos y rangos IP, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). Si elige restringir los intervalos de direcciones IP de destino y los dominios, debe asegurarse de mantener la lista de puertos y rangos actualizados porque puede cambiar. Puede suscribirse a [esta fuente RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) a actualizarse cuando se producen cambios. También es una práctica recomendada para comprobar si se abren todos los puertos mediante la ejecución de la [Skype para la herramienta de evaluación de red empresarial](https://www.microsoft.com/download/details.aspx?id=53885) de forma regular. Puede encontrar más información acerca de la funcionalidad de esta herramienta en la siguiente sección.

En el caso de un servidor proxy que se va a implementar, se recomienda que se pasan por alto el servidor proxy para todos los servicios de los equipos. Aunque es posible que funcione el uso de un servidor proxy, es muy probable que se reducirá la calidad debido a la del elemento multimedia que se ve obligado a usar TCP en lugar de UDP. Para obtener más información acerca de los servidores proxy y no usar, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges).

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>Otras consideraciones sobre la red
### <a name="external-name-resolution"></a>Resolución de nombres externos

Asegúrese de que todos los equipos cliente que ejecutan al cliente de los equipos pueden resolver consultas DNS externas para descubrir los servicios proporcionados por Office 365.

### <a name="nat-pool-size"></a>Tamaño del grupo de servidores NAT

Cuando varios usuarios y dispositivos de acceso a Office 365 mediante el uso de traducción de direcciones de red (NAT) o traducción de direcciones de puerto (PAT), debe asegurarse de que los dispositivos ocultos detrás de cada dirección IP enrutable públicamente no superen el número compatible.

Para mitigar este riesgo, asegúrese de adecuada direcciones IP públicas se asignan a los grupos de NAT para evitar el agotamiento de puerto. El agotamiento de puertos ocasionará que los usuarios internos y los dispositivos tengan problemas al conectarse con los servicios de Office 365. Para obtener más información, consulte [Compatibilidad de NAT con Office 365](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365).

### <a name="intrusion-detection-and-prevention-guidance"></a>Instrucciones de detección y prevención de intrusiones

Si su entorno tiene un sistema de detección de intrusiones o sistema de prevención de intrusiones implementado para obtener un nivel adicional de seguridad para las conexiones salientes, asegúrese de que todo el tráfico que tiene las direcciones URL de Office 365 como su destino está en la lista blanca.

## <a name="test-the-network"></a>La red de prueba

Una vez completada la preparación de la planeación y la red, incluida la actualización de ancho de banda y la apertura de puertos en el firewall: debe probar el rendimiento de la red. Los resultados de esta prueba pintan una imagen más clara de optimización de la red o corrección necesarios para el éxito de su implementación de los equipos.

Puede descargar el [Skype para la herramienta de evaluación de red empresarial](https://www.microsoft.com/download/details.aspx?id=53885) para comprobar si está lista para los equipos de la red. La herramienta ofrece una funcionalidad dual: puede comprobar si se han abierto todos los puertos correctos, y puede probar de dificultades de red.

Después de descargar e instalar la herramienta, puede encontrar en C:\\archivos de programa\\Microsoft Skype para la herramienta de evaluación de red empresarial. Una guía detallada de cómo usar la herramienta, Usage.docx, se incluye en ese directorio.

### <a name="test-for-opened-ports"></a>Prueba de puertos abiertos

Abra una ventana del símbolo del sistema y navegue hasta el directorio de la herramienta de evaluación de la red escribiendo **cd C:\\archivos de programa\\Microsoft Skype para la herramienta de evaluación de red empresarial**. En el símbolo del sistema, inicie la prueba de puertos abiertos escribiendo **networkassessmenttool.exe /connectivitycheck**

Después de ejecutar las comprobaciones, la herramienta se muestre el mensaje "Las comprobaciones se terminó correctamente" o un informe sobre los puertos que se han bloqueado. También genera un archivo denominado Connectivity_results.txt, que contiene el resultado de la herramienta y lo almacena en la carpeta % userprofile %\\appdata\\local\\microsoft Skype para la herramienta de evaluación de red empresarial\\ Active directory.

Se recomienda ejecutar las comprobaciones de conectividad con regularidad para asegurarse de los puertos se han abierto y funcionan correctamente.

### <a name="test-for-network-impairments"></a>Pruebas en busca de problemas de red

Para aumentar la satisfacción de los usuarios, debe limitar cualquier dificultades en la red. Las dificultades de red más comunes son retraso (latencia), pérdida de paquetes y vibración:

-   **Latencia:** Esto es el tiempo necesario para obtener un paquete IP de punto A punto b en la red. Este retraso de propagación de red básicamente está asociado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una sobrecarga adicional realizada por los diversos enrutadores intermedios. Latencia se mide como el tiempo de ida y vuelta o unidireccional.

-   **Pérdida de paquetes**: a menudo se define como un porcentaje de paquetes que se pierden en una determinada ventana de tiempo. Pérdida de paquetes afecta directamente a la calidad de audio: desde pequeñas, individual los paquetes perdidos no tener casi afectar a las pérdidas de ráfagas opuesta que causa el audio para recortar completamente.

-   **Vibración de llegada entre paquetes, o simplemente vibración:** Éste es el cambio promedio de retraso entre envíos sucesivos de paquetes. Puede adaptar el software más moderno de VoIP, incluidos Skype para la empresa, para algunos niveles de vibración a través de almacenamiento en búfer. Es sólo cuando la vibración supera el almacenamiento en búfer que un participante se tenga en cuenta los efectos de vibración.

Los valores máximos de estas dificultades se describen en el [rendimiento de conectividad de red y calidad Media](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance). Cuando las pruebas para estas dificultades, podemos distinguir entre dos segmentos independientes:

-   El *segmento del borde* es el segmento en el que reside el enrutador. Éste es el segmento de red lógica más cercano conectado a internet en cada una de las ubicaciones. En la mayoría de los casos, es el punto de conexión del enrutador o, posiblemente, una red perimetral (también conocida como *DMZ*, *zona desmilitarizada*y *subred protegida*). No hay más tráfico que afecta a los dispositivos que no sean el enrutador debe producirse entre este segmento e internet.

-   El *segmento del cliente* es el segmento de red lógica en la que residen los clientes.

Debe probar ambos segmentos mediante el uso de la herramienta de evaluación de la red. Para probar el segmento, navegue hasta el directorio y escriba **networkassessmenttool.exe** en el símbolo del sistema. Los resultados se escriben en un archivo denominado Results.tsv, y se puede comparar con los [requisitos](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) para cada segmento.

Tenga en cuenta que ambos segmentos deben cumplir los requisitos para una implementación de alta calidad. Se recomienda ejecutar la herramienta varias veces para una hora directamente para obtener una buena indicación de rendimiento de la red.

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>Corrección de red

Si los resultados de la planeación de ancho de banda, las pruebas de puerto o los requisitos de red para las pruebas muestran que su red actual necesita corrección antes de implementar los equipos, puede hacerlo de varias maneras: 

-   Para el ancho de banda insuficiente, actualización conexiones de modo que puede flujo de tráfico a Office 365 no les afectan.

-   Para los puertos bloqueados, cambie las reglas de firewall y vuelva a probar los puertos.

-   Para problemas de red, siempre que realice un análisis de causa de origen.

Calidad de servicio (QoS) puede usarse para auditiva batalla por orden de prioridad y separar el tráfico. Algunas organizaciones optan por implementar QoS para resolver los problemas de ancho de banda o restringir la cantidad de tráfico que fluyen. Esto no mejora la calidad y va a dar lugar a problemas nuevo. Siempre debe realizar un análisis de causa raíz cuando dificultades de red superan los requisitos. QoS puede ser una solución. Para obtener más información, vea [Calidad de servicio en los equipos de Microsoft](qos-in-teams.md).

>[!NOTE]
>Muchas redes evolucionan con el tiempo debido a las actualizaciones, la expansión u otros requisitos empresariales. Asegúrese de que tiene los procesos operativos en contexto a mantener estas áreas como parte de la planeación de la administración de servicio.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul><li>¿Quién será responsable de completar las evaluaciones de red adecuada en todos los segmentos de red y ubicaciones de la organización?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul><li>Puede realizar una evaluación de red detallada para ayudar a garantizar que la red está preparada para la implementación de Microsoft Teams. Para obtener más información, vea [Evaluación de preparación de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness).</li><li>Realizar la corrección de red en función de los resultados de la evaluación de disponibilidad de red para cada segmento de red.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>Impresiones clave

Estos son los principales puntos de esta guía. Debe:

-   Abra los puertos TCP 80 y 443 saliente desde clientes que utilizarán los equipos.

-   Abra los puertos UDP 3478 a través de 3481 saliente desde clientes que utilizarán los equipos.

-   Asegúrese de que dispone de suficiente ancho de banda para la implementación de los equipos al completar el [Organizador de la red](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).

-   Ejecutar la [Herramienta de evaluación de la red](https://www.microsoft.com/download/details.aspx?id=53885) y asegúrese de que cumple con los requisitos descritos en el [rendimiento de conectividad de red y calidad Media](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) desde el segmento del borde y el segmento del cliente.
