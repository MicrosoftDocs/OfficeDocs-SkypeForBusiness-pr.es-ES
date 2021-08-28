---
title: Planear los requisitos de red para Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Summary: Review the network component considerations below before implementing Skype Empresarial Server.'
ms.openlocfilehash: 272ac60f4322d1d9153a6518e20d02c07e066def
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623582"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planear los requisitos de red para Skype Empresarial

**Resumen:** Revise las consideraciones del componente de red que se indican a continuación antes de implementar Skype Empresarial Server.

La información de estos temas también se describe en las notas del producto Sobre planeación [de red,](https://www.microsoft.com/download/details.aspx?id=39084) supervisión y solución de problemas con Lync Server con detalles y profundidad adicionales. Aunque el contenido hace referencia explícitamente a Lync 2010 y Lync 2013, las consideraciones para Skype Empresarial Server no cambian.

Del mismo modo, si la red implica wi-fi y acceso por cable, el documento técnico Que entrega comunicaciones de [Lync 2013 Real-Time](https://www.microsoft.com/download/details.aspx?id=36494) a través de Wi-Fi es una buena referencia y es igualmente aplicable a Skype Empresarial Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

El adaptador de red de cada servidor de la topología Skype Empresarial Server debe admitir al menos 1 gigabit por segundo (Gbps). En general, debe conectar todos los roles de servidor dentro de la topología Skype Empresarial Server con una red de área local (LAN) de baja latencia y ancho de banda alto. El tamaño de la LAN depende del tamaño de la topología:

- En Standard Edition topologías, los servidores deben estar en una red que admita Ethernet de 1 Gbps o equivalente.

- En Enterprise Edition topologías, la mayoría de los servidores deben estar en una red que admita más de 1 Gbps, especialmente cuando admiten conferencias de audio/vídeo (A/V) y uso compartido de aplicaciones.

Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.

## <a name="audiovideo-network-requirements"></a>Requisitos de red de audio y vídeo
<a name="AV_req"> </a>

Los requisitos de red para audio y vídeo (A/V) en una implementación Skype Empresarial Server incluyen lo siguiente:

- Si va a implementar un único servidor perimetral o un grupo de servidores perimetrales mediante el equilibrio de carga dns, puede configurar el  _firewall_ externo para realizar la traducción de direcciones de red (NAT). No puede configurar el firewall interno _para_ que realice NAT. Para obtener más información, vea [Planeación de puertos y firewall.](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)

    > [!IMPORTANT]
    > Si tiene un grupo de servidores perimetrales y usa un equilibrador de carga de hardware, debe usar direcciones IP públicas en los servidores perimetrales y no puede usar NAT para los servidores o el grupo de servidores en el dispositivo compatible con NAT (por ejemplo, un dispositivo de firewall o un conmutador LAN. Para obtener más información, [vea Escenarios del servidor](../edge-server-deployments/scenarios.md)perimetral en Skype Empresarial Server .

- Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.

- Si usa el protocolo de seguridad de Internet (IPsec), se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener más información, vea [Excepciones de IPsec](#ipsec-exceptions).

Para proporcionar una calidad de medios óptima, haga lo siguiente:

- Aprovisione los vínculos de red para admitir un rendimiento de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo, si están habilitados, durante los períodos de uso máximo. Una sesión de audio o vídeo de dos vías usa dos secuencias, por lo que una conexión de audio y teléfono sencilla requerirá 130 Kbps para cubrir cada secuencia. El vídeo también usará un total de 1000 Kbps para llevar una conexión ascendente y descendente.

- Para hacer frente a picos inesperados de tráfico y un mayor uso con el tiempo, los puntos de conexión multimedia Skype Empresarial Server pueden adaptarse a condiciones de red variables y admitir tres veces el rendimiento de audio y vídeo mientras se mantiene una calidad aceptable. No suponga que esta capacidad de adaptación enmascarará el problema cuando una red está infra aprovisionada. En una red poco aprovisionada, se reduce la capacidad de los puntos de conexión multimedia de Skype Empresarial Server para tratar dinámicamente las distintas condiciones de red (por ejemplo, pérdida de paquetes alta temporal).

- Para los vínculos de red en los que el aprovisionamiento es muy costoso y difícil, es posible que deba considerar el aprovisionamiento para un menor volumen de tráfico. En este escenario, permita que la elasticidad de los extremos multimedia de Skype Empresarial Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a costa de una reducción en la calidad de voz. Además, habrá una disminución en el espacio principal de lo contrario disponible para absorber picos repentinos en el tráfico.

- Para los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio que usa vínculos WAN muy deficientes), considere la posibilidad de deshabilitar el vídeo para determinados usuarios.

- Aprovisione la red para garantizar un retraso máximo de extremo a extremo (latencia) de 150 milisegundos (ms) en carga máxima. La latencia es el único impedimento de red que Skype Empresarial Server los componentes multimedia no pueden reducir, y es importante encontrar y eliminar los puntos débiles.

- Para los servidores que ejecutan software antivirus, incluya todos los servidores que Skype Empresarial Server en la lista de excepciones para proporcionar un rendimiento y una calidad de audio óptimas.

## <a name="ipsec-exceptions"></a>Excepciones de IPsec

En aquellas redes empresariales donde el protocolo de seguridad de Internet o IPsec (consulte IETF RFC 4301-4309) está implementado, IPsec se debe deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.

En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.

**Excepciones de IPsec recomendadas**

|Nombre de regla |IP de origen |IP de destino |Protocolo |Puerto de origen |Puerto de destino |Requisito de autenticación |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Servidor perimetral A/V interno entrante|Cualquiera  |Servidor perimetral A/V interno|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor perimetral A/V externo entrante|Cualquiera  |Servidor perimetral A/V externo|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor perimetral A/V interno saliente|Servidor perimetral A/V interno  |Servidor perimetral A/V externo |UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor perimetral A/V externo saliente|Servidor perimetral A/V externo |Cualquiera |UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor de mediación entrante|Cualquiera  |Servidor(s) de mediación |UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor de mediación saliente|Servidor(s) de mediación  |Cualquiera|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Operador de conferencia entrante|Cualquiera  |Servidor front-end que ejecuta operador de conferencia |UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Operador de conferencia saliente|Servidor front-end que ejecuta operador de conferencia  |Cualquiera|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor de conferencia A/V entrante|Cualquiera|Servidores front-end|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Salida de conferencia A/V|Servidores front-end|Cualquiera|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Exchange entrante|Cualquiera|Mensajería unificada de Exchange|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidores de aplicaciones compartidas entrantes|Cualquiera|Servidores de aplicaciones compartidas|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor de aplicaciones compartidas saliente|Servidores de aplicaciones compartidas| Cualquiera |UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Exchange saliente|Mensajería unificada de Exchange|Cualquiera|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Clientes| Cualquiera  |Cualquiera|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Requisitos de red de conferencia
<a name="Conf_req"> </a>

El ancho de banda usado para descargar contenido de conferencia desde el servidor Internet Information Services (IIS) depende del tamaño del contenido. Puede elegir supervisar el uso real y ajustar la planeación del ancho de banda según corresponda.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia
<a name="Conf_req"> </a>

Una parte importante de la planeación de red es garantizar que la red pueda controlar el tráfico multimedia generado por Skype Empresarial Server. Esta sección le ayudará a planear para ese tráfico de medios.

### <a name="media-traffic-network-usage"></a>Uso de red de tráfico multimedia
<a name="Net_req"> </a>

El uso del ancho de banda de tráfico de medios puede resultar difícil de calcular debido a la cantidad de variables diferentes, como el uso de códecs, la resolución y los niveles de actividad. El uso de ancho de banda es una función del códec que se usa y la actividad de la secuencia, que puede variar entre escenarios. En la tabla siguiente se enumeran los códecs de audio usados normalmente en Skype Empresarial Server escenarios.

**Ancho de banda de códec de audio**

|**Códec de audio**|**Escenario**|**Velocidad de bits de carga de audio (KBPS)**|**Solo ancho de banda de carga de audio y encabezado IP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP y SRTP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP, SRTP y corrección de error de reenvío (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ancha de RTAudio  <br/> |Punto a punto  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Banda estrecha de RTAudio  <br/> |RTC punto a punto  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conferencias  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 estéreo  <br/> |Conferencia punto a punto  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |RTC, conferencia  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Conferencias  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|Banda ancha/banda estrecha SILK  <br/> |Punto a punto  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> Las llamadas RTC desde Skype Empresarial cliente suelen usar el códec G.711, que requiere un ancho de banda alto. Si no hay suficiente ancho de banda disponible para ese códec, las llamadas pueden producir un error similar al siguiente en los registros multimedia: al menos un códec debe estar **habilitado, hr: c0042004**. Los registros multimedia (archivos .blog) se cifran y solo el personal de soporte técnico de Microsoft puede descodificar.

Los números de ancho de banda de la tabla anterior se basan en la paqueteización de 20 ms (50 paquetes por segundo) y para los códecs Siren y G.722 incluyen la sobrecarga adicional del protocolo de transporte seguro en tiempo real (SRTP) de los escenarios de conferencia y suponen que la secuencia está 100% activa. La corrección de errores hacia delante (FEC) se usa dinámicamente cuando hay pérdida de paquetes en el vínculo para ayudar a mantener la calidad de la secuencia de audio.

La versión estéreo del códec G.722 la usan los sistemas basados en el sistema de salas de Lync, que usa un solo micrófono estéreo o un par de micrófonos mono para permitir a los agentes de escucha distinguir mejor varios altavoces en la sala de reuniones.

**Ancho de banda de resolución de video**

|**Códec de video**|**Resolución y relación de aspecto**|**Velocidad de bits de carga máxima de vídeo (Kbps)**|**Velocidad mínima de bits de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H.264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

El códec predeterminado para vídeo es el estándar de codificación avanzada de vídeo H.264/MPEG-4 Parte 10, junto con sus extensiones de codificación de vídeo escalables para la escalabilidad temporal. Para mantener la interoperabilidad con clientes heredados, el códec RTVideo se sigue utilizando para llamadas punto a punto entre clientes Skype Empresarial Server y heredados. En las sesiones de conferencia con clientes Skype Empresarial Server y heredados, el extremo de Skype Empresarial Server puede codificar el vídeo con ambos códecs de vídeo y enviar el flujo de bits H.264 a los clientes de Skype Empresarial Server y el flujo de bits RTVideo a clientes heredados.

El ancho de banda necesario depende de la resolución, la calidad, la velocidad de fotogramas y la cantidad de movimiento o cambio en la imagen. Para cada resolución, hay dos velocidades de bits pertinentes:

- **Velocidad de bits de carga máxima** Esta es la velocidad de bits que usará un punto de conexión para la resolución a la velocidad máxima de fotogramas. Este es el valor que permite la mayor calidad de vídeo y sonido.

- **Velocidad de bits de carga mínima** Esta es la velocidad de bits por debajo de Skype Empresarial Server punto de conexión cambiará a la siguiente resolución inferior. Para garantizar una resolución determinada, la velocidad de bits de carga de vídeo disponible no debe estar por debajo de esta velocidad de bits mínima para esa resolución. Este valor le ayuda a comprender el valor más bajo posible si la velocidad de bits máxima no está disponible o es práctica. Para algunos usuarios, un vídeo de velocidad de bits tan baja puede proporcionar una experiencia de vídeo inaceptable, por lo que tenga cuidado con estas velocidades de bits mínimas de carga de vídeo. Tenga en cuenta que para las escenas de vídeo estáticas e invariables, la velocidad de bits real puede estar temporalmente por debajo de la velocidad de bits mínima.

Skype Empresarial Server admite muchas resoluciones. Esto permite que Skype Empresarial Server a diferentes anchos de banda de red y capacidades de recepción de cliente. La relación de aspecto predeterminada para Skype Empresarial Server es 16:9. La relación de aspecto 4:3 heredada sigue siendo compatible con cámaras web que no permiten la captura en la relación de aspecto de 16:9.

El FEC de vídeo siempre se incluye en la velocidad de bits de carga de vídeo cuando se usa para que no haya valores independientes para con FEC de vídeo y sin FEC de vídeo.

Los extremos no hacen fluir los paquetes de audio y video continuamente. Dependiendo del escenario existen varios niveles de actividades de secuencia que indican la frecuencia con los que los paquetes se envían a una secuencia. La actividad de una secuencia depende de los medios y el escenario, y no depende del códec que se utiliza. En un escenario entre pares:

- Los extremos solo envían secuencias de audio cuando los usuarios hablan.

- Ambos participantes reciben secuencias de audio.

- Si se usa vídeo, ambos extremos envían y reciben secuencias de vídeo durante la llamada.

- Para las escenas de vídeo estático, la velocidad de bits real puede ser temporalmente muy baja, ya que el códec de vídeo omitirá las regiones de codificación del vídeo sin cambiar desde el ejemplo anterior.

En un escenario de conferencias:

- Los extremos envían secuencias de audio solo cuando los usuarios hablan.

- Todos los participantes reciben secuencias de audio.

- Si se utiliza video, los participantes pueden recibir hasta cinco secuencias de vídeo y uno panorámico (por ejemplo, con relación de aspecto 20:3). De forma predeterminada, los cinco reciben secuencias de vídeo basadas en el historial de hablantes activos, pero los usuarios también pueden seleccionar de forma manual de los que desea recibir una secuencia de video. Si se habilita multi-vídeo, el requisito de resolución y ancho de banda para cada una de las secuencias de vídeo será menor.

- Cada participante que activa la secuencia de vídeo de envío del usuario enviará una o más secuencias de vídeo. Skype Empresarial Server tiene la capacidad de enviar hasta cinco secuencias de vídeo para optimizar la calidad de vídeo de todos los clientes receptores. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la computadora, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de video. El caso más común es el de H.264 y una secuencia de video de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de video diferente) se envían para acomodar diferentes solicitudes de receptor.

Además del ancho de banda requerido para el tráfico de protocolo seguro en tiempo real (RTP) para los medios de audio o video, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar estadísticas y control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda en la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo usado para RTCP y son diferentes para las secuencias de audio y vídeo debido a las diferencias en los datos de control

**Ancho de banda de RTCP**

|**Media**|**Ancho de banda máximo RTCP (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Video (solo se envía/recibe H.264 o RTVideo)  <br/> |10  <br/> |
|Video (se envía/recibe H.264 y RTVideo)  <br/> |15   <br/> |

Para la planeación de capacidad, las dos estadísticas siguientes son de interés:

- **Ancho de banda máximo sin FEC** El ancho de banda máximo que consumirá una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario sin FEC. Este es el ancho de banda cuando la secuencia está con el 100% de actividad y no existe una pérdida de paquetes que desencadena el uso de FEC. Esto es útil para calcular cuánto ancho de banda se debe asignar para permitir que el códec se utilice en un escenario determinado. No se espera que FEC sea un requisito en una red administrada.

- **Ancho de banda máximo con FEC** El ancho de banda máximo que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario con FEC. Este es el ancho de banda cuando la secuencia está con el 100% de actividad y existe una pérdida de paquetes que desencadena el uso de FEC para mejorar la calidad. Esto es útil para calcular cuánto ancho de banda se debe asignar para permitir que el códec se use en un escenario determinado y permitir el uso de FEC para conservar la calidad en condiciones de pérdida de paquetes.

Las siguientes tablas también enumeran un valor adicional de ancho de banda, **Ancho de banda típico**. Este es el ancho de banda promedio que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario. Este ancho de banda se puede usar para aproximarse a la cantidad de ancho de banda que consume el tráfico multimedia en un momento específico, pero no debe usarse para la planeación de capacidad, ya que las llamadas individuales superarán este valor cuando el nivel de actividad sea mayor que el promedio. El ancho de banda de secuencias de vídeo típico de las tablas siguientes se basa en una combinación de diferentes resoluciones de vídeo observadas en los datos de clientes medidos, y es probable que las instalaciones más pequeñas tengan números reales que difieren de los datos de la tabla. Por ejemplo, en sesiones punto a punto, la mayoría de los usuarios usarían la ventana de representación de vídeo predeterminada, mientras que un porcentaje de usuarios aumentaría o maximizaría la aplicación Skype Empresarial Server para permitir mejores resoluciones de vídeo.

Las tablas siguientes proporcionan valores para los distintos escenarios.

**Planificación de la capacidad de audio/video para sesiones entre pares**

|**Media**|**Códec**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda ancha de RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |Banda ancha SILK  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal al llamar a Skype Empresarial Server de conexión  <br/> |H.264  <br/> |460  <br/> |4010 (para una resolución máxima de 1920x1080)  <br/> |Ya incluido  <br/> |
|Vídeo principal al llamar a Lync 2010 o Office Communicator extremos de 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para una resolución máxima de 1920x720)  <br/> |Ya incluido  <br/> |
|Vídeo panorámico al llamar a Skype Empresarial Server de conexión  <br/> |H.264  <br/> |190  <br/> |2010 (para una resolución máxima de 1920x288)  <br/> |Ya incluido  <br/> |
|Vídeo panorámico al llamar a puntos de conexión de Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (para una resolución máxima de 1920x144)  <br/> |Ya incluido  <br/> |

**Planificación de la capacidad de audio/video para conferencias**

|**Media**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Recepción principal de video  <br/> |H.264 y RTVideo¹  <br/> |260  <br/> |8015  <br/> |No aplicable  <br/> |
|Envío principal de video  <br/> |H.264 y RTVideo  <br/> |270  <br/> |8015  <br/> |No aplicable  <br/> |
|Recepción de video panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2010 (para una resolución máxima de 1920x288)  <br/> |No aplicable  <br/> |
|Envío de video panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2515 ²  <br/> |No aplicable  <br/> |

1. Rt Video se envía además de H.264 cuando los clientes de Lync 2010 están conectados a la conferencia.

2. Si hay varias secuencias, comparten dinámicamente el ancho de banda asignado.

Para el vídeo principal, el ancho de banda típico de la secuencia es el ancho de banda agregado sobre todas las secuencias de vídeo recibidas y el flujo máximo es el ancho de banda sobre todas las secuencias de vídeo de envío. Incluso con varias secuencias de vídeo, el ancho de banda de vídeo típico es menor que en el escenario punto a punto porque muchas videoconferencias usan el uso compartido de contenido que lleva a ventanas de vídeo mucho más pequeñas y, por lo tanto, resoluciones de vídeo más pequeñas. El ancho de banda máximo de carga de vídeo agregado admitido es de 8000 Kbps para las secuencias de envío y recepción que se usarían (por ejemplo, si hay dos secuencias de vídeo entrantes de 1920 x 1080p). Los valores máximos solo se ven en raras ocasiones en implementaciones reales.

Al crear una conferencia multiparte que usa la característica de vista de galería, el uso del ancho de banda aumenta inicialmente a medida que los participantes se unen y, a continuación, disminuye a medida que las resoluciones se descartan para ajustarse al máximo.

||**2 Participantes**|**3 participantes**|**4 participantes**|**5 participantes**|**6 participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluciones máximas recibidas** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Velocidad de bits media total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocidad de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

El ancho de banda de secuencia típico para vídeo panorámico se basa en dispositivos que solo reproducen vídeo panorámico de hasta 960 x 144. Espere que el ancho de banda de secuencia típico aumente al usar dispositivos con vídeo panorámico de 1920 x 288.

**Planificación de la capacidad de audio para el RTC**

|**Media**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (esto incluye participantes de RTC en conferencias)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

los números del ancho de banda de red en estas tablas representa solo el tráfico de una vía e incluye 5 Kbps para los gastos del tráfico RTCP.

## <a name="managing-quality-of-service"></a>Administración de la calidad del servicio
<a name="man_QOS"> </a>

Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia óptima del usuario final para las comunicaciones de audio y vídeo. QoS se usa con más frecuencia en redes donde el ancho de banda es limitado: con un gran número de paquetes de red que compiten por una cantidad bastante pequeña de ancho de banda disponible, QoS permite a los administradores asignar prioridades más altas a paquetes que transportan datos de audio o vídeo. Al dar a estos paquetes una prioridad superior, es probable que las comunicaciones de audio y vídeo se completen más rápido y con menos interrupciones que las sesiones de red que implican cosas como transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que a los paquetes de red usados para transferencias de archivos o copias de seguridad de bases de datos se les asigna una prioridad de "esfuerzo máximo".

> [!NOTE]
> Como regla general, QoS solo se aplica a las sesiones de comunicación de la red interna. Al implementar QoS, configura los servidores y enrutadores para admitir el marcado de paquetes de una manera determinada que puede no ser compatible con Internet o en otras redes. Incluso si la calidad del servicio se admite en otras redes, no hay ninguna garantía de que QoS se configurará exactamente de la misma manera que configuró el servicio. Si usa MPLS, deberá trabajar con su proveedor de MPLS.

Skype Empresarial Server no requiere QoS, pero se recomienda encarecidamente. Si experimenta problemas de pérdida de paquetes en la red, las soluciones disponibles son agregar más ancho de banda o implementar QoS. Si no es posible agregar más ancho de banda, la implementación de QoS podría ser el único peaje para resolver el problema.

Skype Empresarial Server ofrece compatibilidad completa con QoS: esto significa que las organizaciones que ya usan QoS pueden integrar fácilmente Skype Empresarial Server en su infraestructura de red existente. Para ello, debe seguir estos pasos:

- [Habilitar QoS en Skype Empresarial Server dispositivos que no se basan en Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). De manera predeterminada, QoS se deshabilita para los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puedes usar Skype Empresarial Server para habilitar y deshabilitar la calidad del servicio para dispositivos, normalmente no puedes usar el producto para modificar los códigos DSCP usados por estos dispositivos.

- [Configurar intervalos de puertos y una directiva de calidad](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)de servicio para los servidores de conferencia, aplicación y mediación. Debe reservar un conjunto único de puertos para diferentes tipos de paquetes, como paquetes de audio y vídeo. Al usar Skype Empresarial Server no se habilita ni deshabilita QoS estableciendo un valor de propiedad en True o false. En su lugar, se habilita QoS mediante la configuración de intervalos de puertos y, a continuación, la creación y aplicación de la directiva de grupo. Si más adelante decide no usar QoS, puede "deshabilitar" QoS quitando los objetos de directiva de grupo adecuados.

- [Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales.](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md) Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores. La configuración de una directiva de QoS solo se realiza para el lado interno de los servidores perimetrales. Esto se debe a que QoS está diseñado para su uso en la red interna y no en Internet.

- [Configurar intervalos de puertos y una directiva de calidad](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md)de servicio para los clientes en Skype Empresarial Server . Estos intervalos de puertos solo se aplican a los equipos cliente y suelen ser diferentes de los intervalos de puertos configurados en los servidores. Tenga en cuenta que Skype Empresarial Server no admite QoS para Windows sistemas operativos distintos de Windows 10.


> [!NOTE]
> Si usa Windows Server 2012 o Windows Server 2012 R2, es posible que le interese el nuevo conjunto de cmdlets Windows PowerShell disponibles para administrar QoS en esa plataforma. Para obtener más información, consulte [Network QoS Cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

QoS también se describe en las notas del producto Sobre planeación [de red,](https://www.microsoft.com/download/details.aspx?id=39084) supervisión y solución de problemas con Lync Server con detalles y profundidad adicionales. Aunque el contenido hace referencia explícitamente a Lync 2010 y Lync 2013, las consideraciones para Skype Empresarial Server no cambian.

## <a name="see-also"></a>Consulte también
<a name="man_QOS"> </a>

[Planear IPv6 en Skype Empresarial](ipv6.md)

[Requisitos de equilibrio de carga para Skype Empresarial](load-balancing.md)

[Requisitos dns para Skype Empresarial Server](dns.md)
