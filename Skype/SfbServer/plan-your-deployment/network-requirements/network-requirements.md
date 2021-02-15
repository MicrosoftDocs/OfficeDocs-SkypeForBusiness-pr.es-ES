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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Resumen: revise las consideraciones de componentes de red siguientes antes de implementar Skype Empresarial Server.'
ms.openlocfilehash: 0b5d183ecc11d09569427e432121fab7de8f401b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834360"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planear los requisitos de red para Skype Empresarial

**Resumen:** Revise las consideraciones de componentes de red siguientes antes de implementar Skype Empresarial Server.

La información de estos temas también se describe en las notas del producto sobre planeación, supervisión y solución de problemas de red con [Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) con detalles y profundidad adicionales. Aunque el contenido hace referencia explícitamente a Lync 2010 y Lync 2013, las consideraciones para Skype Empresarial Server no cambian.

Del mismo modo, si la red implica acceso wi-fi y por cable, las notas del documento de entrega de comunicaciones de [lync 2013 Real-Time](https://www.microsoft.com/download/details.aspx?id=36494) a través de Wi-Fi son una buena referencia y son igualmente aplicables a Skype Empresarial Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

El adaptador de red de cada servidor de la topología de Skype Empresarial Server debe admitir al menos 1 gigabit por segundo (Gbps). En general, debe conectar todos los roles de servidor dentro de la topología de Skype Empresarial Server con una latencia baja y una red de área local (LAN) de ancho de banda alto. El tamaño de la LAN depende del tamaño de la topología:

- En las topologías Standard Edition, los servidores deben estar en una red que admita Ethernet de 1 Gbps o equivalente.

- En las topologías Enterprise Edition, la mayoría de los servidores deben estar en una red que admita más de 1 Gbps, especialmente cuando se admiten conferencias de audio y vídeo (A/V) y el uso compartido de aplicaciones.

Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.

## <a name="audiovideo-network-requirements"></a>Requisitos de red de audio y vídeo
<a name="AV_req"> </a>

Entre los requisitos de red para audio y vídeo (A/V) en una implementación de Skype Empresarial Server se incluyen los siguientes:

- Si va a implementar un único servidor perimetral o un grupo de servidores perimetrales mediante el equilibrio de carga de DNS, puede configurar el  _firewall_ externo para realizar la traducción de direcciones de red (NAT). No puede configurar el _firewall_ interno para realizar NAT. Para obtener más información, consulte [Planeación de puertos y firewalls.](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)

    > [!IMPORTANT]
    > Si tiene un grupo de servidores perimetrales y usa un equilibrador de carga de hardware, debe usar direcciones IP públicas en los servidores perimetrales y no puede usar NAT para los servidores o el grupo en el dispositivo compatible con NAT (por ejemplo, un dispositivo de firewall o un conmutador LAN. Para obtener más información, [consulte escenarios de servidor perimetral en Skype Empresarial Server.](../edge-server-deployments/scenarios.md)

- Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.

- Si usa el protocolo de seguridad de Internet (IPsec), se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener más información, vea [excepciones de IPsec](#ipsec-exceptions).

Para proporcionar una calidad de medios óptima, haga lo siguiente:

- Aprovisionar los vínculos de red para admitir un rendimiento de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo, si están habilitados, durante los períodos de uso máximo. Una sesión de audio o vídeo de dos vías usa dos secuencias, por lo que una conexión de audio y teléfono simple requerirá 130 Kbps para cubrir cada secuencia. El vídeo también usará un total de 1000 Kbps para llevar una conexión ascendente y descendente.

- Para enfrentarse a picos inesperados de tráfico y un mayor uso a lo largo del tiempo, los puntos de conexión de medios de Skype Empresarial Server pueden adaptarse a distintas condiciones de red y admitir tres veces el rendimiento de audio y vídeo, a la vez que mantienen una calidad aceptable. No suponga que esta capacidad de adaptación enmascarará el problema cuando una red no esté aprovisionada. En una red no aprovisionada, se reduce la capacidad de los extremos multimedia de Skype Empresarial Server para tratar dinámicamente las distintas condiciones de red (por ejemplo, la pérdida de paquetes alta temporal).

- Para los vínculos de red en los que el aprovisionamiento es muy costoso y difícil, es posible que deba considerar el aprovisionamiento para un menor volumen de tráfico. En este escenario, deje que la elasticidad de los extremos multimedia de Skype Empresarial Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a costa de una reducción en la calidad de voz. Además, habrá una disminución en la cabecera disponible para absorber picos repentinos en el tráfico.

- Para los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio que usa vínculos WAN muy deficientes), considere la posibilidad de deshabilitar el vídeo para determinados usuarios.

- Aprovisione la red para garantizar un retraso máximo de un extremo a otro (latencia) de 150 milisegundos (ms) bajo carga máxima. La latencia es el único problema de red que los componentes multimedia de Skype Empresarial Server no pueden reducir y es importante encontrar y eliminar los puntos débiles.

- Para los servidores que ejecutan software antivirus, incluya todos los servidores que ejecutan Skype Empresarial Server en la lista de excepciones para proporcionar un rendimiento y una calidad de audio óptimos.

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
|Servidor de mediación entrante|Cualquiera  |Servidores de mediación |UDP y TCP|Cualquiera |Cualquiera |No autenticar|
|Servidor de mediación saliente|Servidores de mediación  |Cualquiera|UDP y TCP|Cualquiera |Cualquiera |No autenticar|
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

El ancho de banda usado para descargar contenido de conferencia desde el servidor de Internet Information Services (IIS) depende del tamaño del contenido. Puede elegir supervisar el uso real y ajustar la planeación del ancho de banda según corresponda.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico de medios
<a name="Conf_req"> </a>

Una parte importante de la planeación de la red es garantizar que su red pueda controlar el tráfico multimedia generado por Skype Empresarial Server. Esta sección le ayudará a planear para ese tráfico de medios.

### <a name="media-traffic-network-usage"></a>Uso de red de tráfico multimedia
<a name="Net_req"> </a>

El uso del ancho de banda de tráfico de medios puede resultar difícil de calcular debido a la cantidad de variables diferentes, como el uso de códecs, la resolución y los niveles de actividad. El uso de ancho de banda es una función del códec que se usa y la actividad de la secuencia, que puede variar entre escenarios. En la tabla siguiente se enumeran los códecs de audio que se usan normalmente en escenarios de Skype Empresarial Server.

**Ancho de banda del códec de audio**

|**Códec de audio**|**Escenario**|**Velocidad de bits de carga de audio (KBPS)**|**Solo ancho de banda de carga de audio y encabezado IP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP y SRTP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP, SRTP y corrección de error de reenvío (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ancha de RTAudio  <br/> |Punto a punto  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Banda estrecha de RTAudio  <br/> |RTC punto a punto  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conferencias  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 estéreo  <br/> |Conferencia punto a punto  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |RTC, conferencias  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Conferencias  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|Banda ancha DE BANDA ANCHA  <br/> |Punto a punto  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|Banda ancha DE BANDA ANCHA  <br/> |Punto a punto  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|Banda ancha DE BANDA ANCHA  <br/> |Punto a punto  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|BANDA ANCHA/banda estrecha  <br/> |Punto a punto  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> Las llamadas RTC del cliente de Skype Empresarial suelen usar el códec G.711, que requiere un ancho de banda alto. Si no hay suficiente ancho de banda disponible para ese códec, las llamadas pueden producir un error similar al siguiente en los registros multimedia: **atleast one codec must be enabled, hr: c0042004**. Los registros multimedia (archivos .blog) se cifran y solo el personal de soporte técnico de Microsoft puede descodificar los registros multimedia.

Los números de ancho de banda de la tabla anterior se basan en la packetization de 20 ms (50 paquetes por segundo) y para los códecs Siren y G.722 incluyen la sobrecarga adicional del protocolo de transporte seguro en tiempo real (SRTP) de los escenarios de conferencia y suponen que la secuencia está activa al 100 %. La corrección de errores de reenvío (FEC) se usa dinámicamente cuando hay pérdida de paquetes en el vínculo para ayudar a mantener la calidad de la secuencia de audio.

La versión estéreo del códec G.722 se usa en sistemas basados en el sistema Lync Room, que usa un solo micrófono estéreo o un par de micrófonos mono para permitir a los agentes de escucha distinguir mejor varios altavoces en la sala de reuniones.

**Ancho de banda de resolución de video**

|**Códec de video**|**Resolución y relación de aspecto**|**Velocidad de bits máxima de carga de vídeo (Kbps)**|**Velocidad de bits de carga de vídeo mínima (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320 x 180 (16:9)  <br/> 212 x 160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H.264/RTVideo  <br/> |424 x 240 (16:9)  <br/> 320 x 240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480 x 270 (16:9)  <br/> 424 x 320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640 x 480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848 x 480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H.264  <br/> |1280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

El códec predeterminado para vídeo es el estándar de codificación avanzada de vídeo H.264/MPEG-4 Parte 10, junto con sus extensiones de codificación de vídeo escalables para la escalabilidad temporal. Para mantener la interoperabilidad con clientes heredados, el códec RTVideo se sigue utilizando para llamadas punto a punto entre Skype Empresarial Server y clientes heredados. En las sesiones de conferencia con Skype Empresarial Server y clientes heredados, el punto de conexión de Skype Empresarial Server puede codificar el vídeo con ambos códecs de vídeo y enviar la secuencia de bits H.264 a los clientes de Skype Empresarial Server y la secuencia de bits RTVideo a los clientes heredados.

El ancho de banda necesario depende de la resolución, la calidad, la velocidad de fotogramas y la cantidad de movimiento o cambio en la imagen. Para cada resolución, hay dos velocidades de bits pertinentes:

- **Velocidad de bits de carga máxima** Esta es la velocidad de bits que un punto de conexión usará para la resolución a la velocidad de fotogramas máxima. Este es el valor que permite la mejor calidad de vídeo y sonido.

- **Velocidad de bits de carga mínima** Esta es la velocidad de bits por debajo de la cual un extremo de Skype Empresarial Server pasará a la siguiente resolución inferior. Para garantizar una resolución determinada, la velocidad de bits de carga de vídeo disponible no debe estar por debajo de esta velocidad de bits mínima para esa resolución. Este valor le ayuda a comprender el valor más bajo posible si la velocidad de bits máxima no está disponible o no es práctica. Para algunos usuarios, un vídeo de velocidad de bits baja puede proporcionar una experiencia de vídeo inaceptable, por lo que debe tener cuidado con estas velocidades de bits mínimas de carga de vídeo. Ten en cuenta que para escenas de vídeo estáticas sin cambiar, la velocidad de bits real puede estar temporalmente por debajo de la velocidad de bits mínima.

Skype Empresarial Server admite muchas resoluciones. Esto permite que Skype Empresarial Server se ajuste a diferentes anchos de banda de red y reciba capacidades de cliente. La relación de aspecto predeterminada para Skype Empresarial Server es de 16:9. La relación de aspecto 4:3 heredada sigue siendo compatible con cámaras web que no permiten la captura en la relación de aspecto de 16:9.

El FEC de vídeo siempre se incluye en la velocidad de bits de carga de vídeo cuando se usa, por lo que no hay valores independientes para fec de vídeo y sin FEC de vídeo.

Los extremos no hacen fluir los paquetes de audio y video continuamente. Dependiendo del escenario existen varios niveles de actividades de secuencia que indican la frecuencia con los que los paquetes se envían a una secuencia. La actividad de una secuencia depende de los medios y el escenario, y no depende del códec que se utiliza. En un escenario entre pares:

- Los puntos de conexión solo envían secuencias de audio cuando los usuarios hablan.

- Ambos participantes reciben secuencias de audio.

- Si se usa vídeo, ambos puntos de conexión envían y reciben secuencias de vídeo durante la llamada.

- Para las escenas de vídeo estático, la velocidad de bits real puede ser temporalmente muy baja, ya que el códec de vídeo omitirá las regiones de codificación del vídeo sin ningún cambio desde la muestra anterior.

En un escenario de conferencias:

- Los extremos envían secuencias de audio solo cuando los usuarios hablan.

- Todos los participantes reciben secuencias de audio.

- Si se utiliza video, los participantes pueden recibir hasta cinco secuencias de vídeo y uno panorámico (por ejemplo, con relación de aspecto 20:3). De forma predeterminada, los cinco reciben secuencias de vídeo basadas en el historial de hablantes activos, pero los usuarios también pueden seleccionar de forma manual de los que desea recibir una secuencia de video. Si se habilita el vídeo múltiple, el requisito de resolución y ancho de banda para cada una de las secuencias de vídeo será menor.

- Cada participante que activa la secuencia de vídeo de envío del usuario enviará una o más secuencias de vídeo. Skype Empresarial Server tiene la capacidad de enviar hasta cinco secuencias de vídeo para optimizar la calidad de vídeo para todos los clientes receptores. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la computadora, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de video. El caso más común es el de H.264 y una secuencia de video de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de video diferente) se envían para acomodar diferentes solicitudes de receptor.

Además del ancho de banda requerido para el tráfico de protocolo seguro en tiempo real (RTP) para los medios de audio o video, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar estadísticas y control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda en la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo usado para RTCP y son diferentes para las secuencias de audio y vídeo debido a las diferencias en los datos de control.

**Ancho de banda de RTCP**

|**Media**|**Ancho de banda máximo RTCP (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Video (solo se envía/recibe H.264 o RTVideo)  <br/> |10    <br/> |
|Video (se envía/recibe H.264 y RTVideo)  <br/> |15   <br/> |

Para la planeación de la capacidad, son de interés las dos estadísticas siguientes:

- **Ancho de banda máximo sin FEC** Ancho de banda máximo que consumirá una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario sin FEC. Este es el ancho de banda cuando la secuencia está con el 100% de actividad y no existe una pérdida de paquetes que desencadena el uso de FEC. Esto es útil para calcular cuánto ancho de banda se debe asignar para permitir que el códec se utilice en un escenario determinado. No se espera que FEC sea un requisito en una red administrada.

- **Ancho de banda máximo con FEC** Ancho de banda máximo que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario con FEC. Este es el ancho de banda cuando la secuencia está con el 100% de actividad y existe una pérdida de paquetes que desencadena el uso de FEC para mejorar la calidad. Esto es útil para calcular cuánto ancho de banda se debe asignar para permitir que el códec se use en un escenario determinado y permitir el uso de FEC para conservar la calidad en condiciones de pérdida de paquetes.

Las siguientes tablas también enumeran un valor adicional de ancho de banda, **Ancho de banda típico**. Este es el ancho de banda promedio que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario. Este ancho de banda se puede usar para aproximar la cantidad de ancho de banda que consume el tráfico de medios en un momento específico, pero no debe usarse para la planeación de la capacidad, ya que las llamadas individuales superarán este valor cuando el nivel de actividad sea mayor que el promedio. El ancho de banda típico de la secuencia de vídeo en las tablas siguientes se basa en una combinación de diferentes resoluciones de vídeo como se observa en los datos de cliente medidos, y es probable que las instalaciones más pequeñas tengan números reales que difieren de los datos de la tabla. Por ejemplo, en sesiones punto a punto, la mayoría de los usuarios usarían la ventana de representación de vídeo predeterminada, mientras que un porcentaje de usuarios aumentaría o maximizaría la aplicación de Skype Empresarial Server para permitir mejores resoluciones de vídeo.

Las tablas siguientes proporcionan valores para los distintos escenarios.

**Planificación de la capacidad de audio/video para sesiones entre pares**

|**Media**|**Códec**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda ancha de RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |Banda ancha DE BANDA ANCHA  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal al llamar a puntos de conexión de Skype Empresarial Server  <br/> |H.264  <br/> |460  <br/> |4010 (para una resolución máxima de 1920x1080)  <br/> |Ya incluido  <br/> |
|Vídeo principal al llamar a los puntos de conexión de Lync 2010 u Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para una resolución máxima de 1920x720)  <br/> |Ya incluido  <br/> |
|Vídeo panorámico al llamar a puntos de conexión de Skype Empresarial Server  <br/> |H.264  <br/> |190  <br/> |2010 (para una resolución máxima de 1920x288)  <br/> |Ya incluido  <br/> |
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

Para el vídeo principal, el ancho de banda de secuencia típico es el ancho de banda agregado en todas las secuencias de vídeo recibidas y la secuencia máxima es el ancho de banda sobre todas las secuencias de vídeo de envío. Incluso con varias secuencias de vídeo, el ancho de banda de vídeo típico es menor que en el escenario punto a punto porque muchas videoconferencias usan el uso compartido de contenido que da lugar a ventanas de vídeo mucho más pequeñas y, por lo tanto, resoluciones de vídeo más pequeñas. El ancho de banda máximo de carga de vídeo agregado admitido es de 8000 Kbps para las secuencias de envío y recepción que se usarían (por ejemplo, si hay dos secuencias de vídeo entrantes de 1920 x 1080p). Los valores máximos solo se ven rara vez en implementaciones reales.

Al crear una conferencia con varios participantes que usa la característica de vista de galería, el uso del ancho de banda aumenta inicialmente a medida que los participantes se unen y, a continuación, disminuye a medida que se descartan las resoluciones para ajustarse al máximo.

||**2 participantes**|**3 participantes**|**4 participantes**|**5 participantes**|**6 participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluciones máximas recibidas** <br/> |1920x1080  <br/> |1280 x 720  <br/> |640 x 360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Velocidad de bits promedio total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocidad de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

El ancho de banda de secuencia típico para vídeo panorámico se basa en dispositivos que solo transmite vídeo panorámico de hasta 960 x 144. Espera que el ancho de banda de secuencia típico aumente al usar dispositivos con vídeo panorámico de 1920 x 288.

**Planificación de la capacidad de audio para el RTC**

|**Media**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (esto incluye a los participantes rtc en conferencias)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

los números del ancho de banda de red en estas tablas representa solo el tráfico de una vía e incluye 5 Kbps para los gastos del tráfico RTCP.

## <a name="managing-quality-of-service"></a>Administración de la calidad de servicio
<a name="man_QOS"> </a>

Calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia óptima para el usuario final para las comunicaciones de audio y vídeo. QoS se usa con más frecuencia en redes en las que el ancho de banda es limitado: con un gran número de paquetes de red que compiten por una cantidad bastante pequeña de ancho de banda disponible, QoS permite a los administradores asignar prioridades más altas a paquetes que transportan datos de audio o vídeo. Al dar una prioridad mayor a estos paquetes, es probable que las comunicaciones de audio y vídeo se completen más rápidamente y con menos interrupciones que las sesiones de red que implican cosas como transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que a los paquetes de red usados para transferencias de archivos o copias de seguridad de bases de datos se les asigna una prioridad de "mejor esfuerzo".

> [!NOTE]
> Como regla general, QoS solo se aplica a las sesiones de comunicación de la red interna. Al implementar QoS, configure los servidores y enrutadores para que admitan el marcado de paquetes de una manera particular que puede no ser compatible con Internet o en otras redes. Incluso si la calidad de servicio es compatible con otras redes, no hay ninguna garantía de que qos se configurará exactamente de la misma manera que configuró el servicio. Si usa MPLS, tendrá que trabajar con su proveedor de MPLS.

Skype Empresarial Server no requiere QoS, pero se recomienda encarecidamente. Si experimenta problemas de pérdida de paquetes en la red, las soluciones disponibles son agregar más ancho de banda o implementar QoS. Si no es posible agregar más ancho de banda, la implementación de QoS podría ser el único pago para resolver el problema.

Skype Empresarial Server ofrece compatibilidad completa con QoS: esto significa que las organizaciones que ya usan QoS pueden integrar fácilmente Skype Empresarial Server en su infraestructura de red existente. Para ello, debe seguir estos pasos:

- [Habilitar QoS en Skype Empresarial Server para](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md)dispositivos que no se basan en Windows . De manera predeterminada, QoS se deshabilita para los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Skype Empresarial Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, normalmente no puede usar el producto para modificar los códigos DSCP usados por estos dispositivos.

- [Configurar intervalos de puertos y una directiva de calidad](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)de servicio para los servidores de conferencia, aplicación y mediación. Debe reservar un conjunto único de puertos para diferentes tipos de paquetes, como paquetes de audio y vídeo. Al usar Skype Empresarial Server, no habilita ni deshabilita QoS estableciendo un valor de propiedad en True o False. En su lugar, debe habilitar QoS configurando intervalos de puertos y, a continuación, creando y aplicando la directiva de grupo. Si más adelante decide no usar QoS, puede "deshabilitar" QoS quitando los objetos de directiva de grupo adecuados.

- [Configurar intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales.](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md) Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores. La configuración de una directiva de QoS solo se realiza para el lado interno de los servidores perimetrales. Esto se debe a que QoS está diseñado para su uso en la red interna y no en Internet.

- [Configurar intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype Empresarial Server.](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md) Estos intervalos de puertos solo se aplican a los equipos cliente y normalmente son diferentes de los intervalos de puertos configurados en los servidores. Tenga en cuenta que Skype Empresarial Server no admite QoS para sistemas operativos Windows distintos de Windows 10.


> [!NOTE]
> Si usa Windows Server 2012 o Windows Server 2012 R2, es posible que le interese el nuevo conjunto de cmdlets de Windows PowerShell disponibles para administrar QoS en esa plataforma. Para obtener más información, consulte [Cmdlets de QoS de red en Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

QoS también se describe en las notas del producto sobre planeación, supervisión y solución de problemas de red con [Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) con detalles y profundidad adicionales. Aunque el contenido hace referencia explícitamente a Lync 2010 y Lync 2013, las consideraciones para Skype Empresarial Server no cambian.

## <a name="see-also"></a>Vea también
<a name="man_QOS"> </a>

[Planear IPv6 en Skype Empresarial](ipv6.md)

[Requisitos de equilibrio de carga para Skype Empresarial](load-balancing.md)

[Requisitos de DNS para Skype Empresarial Server](dns.md)
