---
title: Plan network requirements for Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumen: Revise las consideraciones del componente de red a continuación antes de implementar Skype empresarial Server.'
ms.openlocfilehash: b7b9c7e239aab5d395fcdadf0cb254df4e13cecd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802030"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Plan network requirements for Skype for Business

**Resumen:** Revise las consideraciones del componente de red a continuación antes de implementar Skype empresarial Server.

La información de estos temas también se trata en el informe sobre la [planificación, la supervisión y la solución de problemas de la red de Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) con detalles y profundidad adicionales. Aunque el contenido se refiere explícitamente a Lync 2010 y a Lync 2013, las consideraciones para Skype empresarial Server no cambian.

Del mismo modo, si su red incluye Wi-Fi y acceso por cable, el artículo técnico que [ofrece las comunicaciones en tiempo real de Lync 2013 a través de Wi-Fi](https://www.microsoft.com/en-us/download/details.aspx?id=36494) es una buena referencia y también se aplica a Skype empresarial Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

El adaptador de red de cada servidor de la topología de Skype empresarial Server debe admitir al menos 1 Gigabit por segundo (Gbps). En general, debe conectar todos los roles de servidor dentro de la topología de servidor de Skype empresarial con una red de área local (LAN) de baja latencia y ancho de banda alto. El tamaño de la LAN depende del tamaño de la topología:

- En las topologías de Standard Edition, los servidores deben estar en una red que admita 1 Gbps de Ethernet o equivalente.

- En las topologías de Enterprise Edition, la mayoría de los servidores deberían estar en una red que admita más de 1 Gbps, especialmente cuando se admiten conferencias de audio/vídeo (A/V) y uso compartido de aplicaciones.

Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.

## <a name="audiovideo-network-requirements"></a>Requisitos de red para el audio y vídeo
<a name="AV_req"> </a>

Entre los requisitos de red para audio/vídeo (A/V) en una implementación de Skype empresarial Server se incluyen los siguientes:

- Si implementa un único servidor perimetral o un grupo de límites mediante el equilibrio de carga de DNS, puede configurar el Firewall _externo_ para realizar la traducción de direcciones de red (NAT). No puede configurar el firewall _internal_ para llevar a cabo NAT. Para obtener más información, consulte [planificación de puertos y firewalls](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Si tiene un grupo perimetral y usa un equilibrador de carga de hardware, debe usar direcciones IP públicas en los servidores perimetrales y no puede usar NAT para los servidores o el grupo en el dispositivo compatible con NAT (por ejemplo, un dispositivo de firewall o un conmutador LAN. Para obtener más información, consulte [escenarios de servidores perimetrales en Skype empresarial Server](../edge-server-deployments/scenarios.md).

- Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.

- Si usa el protocolo de seguridad de Internet (IPsec), recomendamos deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener más información, consulte [excepciones de IPSec](#ipsec-exceptions).

Para proporcionar una calidad óptima de los medios, siga este procedimiento:

- Aprovisione los vínculos de red para admitir un rendimiento de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo (en caso de estar habilitados) durante los períodos de uso máximo. Una sesión bidireccional de audio o de vídeo usa dos secuencias, por lo que una conexión de audio o de vídeo necesitará 130 Kbps para cubrir cada secuencia. El vídeo también usará el total de 1000 kbps para transportar una conexión de entrada y salida.

- Para hacer frente a picos inesperados en el tráfico y aumentar el uso a lo largo del tiempo, los puntos de conexión multimedia de Skype empresarial Server pueden adaptarse a condiciones de red variables y admitir tres veces el rendimiento de audio y vídeo sin perder calidad aceptable. Pero, no se puede dar por sentado que esta capacidad de adaptación enmascarará el problema cuando una red esté mal aprovisionada. En una red de aprovisionamiento desproporcionado, la capacidad de los puntos de conexión multimedia de Skype empresarial Server para tratar dinámicamente con diversas condiciones de la red (por ejemplo, pérdida de paquetes temporales elevadas) se ha reducido.

- En el caso de los vínculos de red en los que el aprovisionamiento resulta muy costoso y difícil, puede que se vea obligado a considerar un aprovisionamiento para un volumen de tráfico menor. En este escenario, deje que la elasticidad de los puntos de conexión multimedia de Skype empresarial Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a costa de reducir la calidad de la voz. También habrá una disminución en el margen que normalmente está disponible para absorber los picos de tráfico repentinos.

- En el caso de los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio con vínculos WAN de muy poca calidad), considere la posibilidad de deshabilitar el vídeo para algunos usuarios.

- Aprovisione la red para asegurar un retraso máximo de un extremo a otro (latencia) de 150 milisegundos (ms) con carga máxima. Latencia es el posible deterioro de la red que los componentes multimedia de Skype empresarial Server no pueden reducir y es importante buscar y eliminar los puntos débiles.

- En el caso de los servidores que ejecutan software antivirus, incluya todos los servidores que ejecutan Skype empresarial Server en la lista de excepciones para proporcionar un rendimiento óptimo y una calidad de audio.

## <a name="ipsec-exceptions"></a>Excepciones de IPsec

En el caso de redes empresariales en las que se ha implementado la seguridad de protocolo de Internet (consulte IETF RFC 4301-4309), debe deshabilitarse IPsec en el rango de puertos que se usan para la entrega de video de audio, vídeo y panorámica. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios por la negociación de IPsec.

En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas.

**Excepciones de IPsec recomendadas**

|Nombre de regla |IP de origen |IP de destino |Protocolo |Puerto de origen |Puerto de destino |Requisito de autenticación |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Servidor perimetral A/V interno entrante|Cualquiera  |Servidor perimetral A/V interno|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidor perimetral A/V externo entrante|Cualquiera  |Servidor perimetral A/V externo|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidor perimetral A/V interno saliente|Servidor perimetral A/V interno  |Servidor perimetral A/V externo |UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidor perimetral A/V externo saliente|Servidor perimetral A/V externo |Cualquiera |UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidor de mediación entrante|Cualquiera  |Servidores de mediación |UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidor de mediación saliente|Servidores de mediación  |Cualquiera|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Operador de conferencia entrante|Cualquiera  |Servidor front-end que ejecuta operador de conferencia |UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Operador de conferencia saliente|Servidor front-end que ejecuta operador de conferencia  |Cualquiera|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidor de conferencia A/V entrante|Cualquiera|Servidores front-end|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Salida de conferencia A/V|Servidores front-end|Cualquiera|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Exchange entrante|Cualquiera|Mensajería unificada de Exchange|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidores de aplicaciones compartidas entrantes|Cualquiera|Servidores de aplicaciones compartidas|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Servidor de aplicaciones compartidas saliente|Servidores de aplicaciones compartidas| Cualquiera |UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Exchange saliente|Mensajería unificada de Exchange|Cualquiera|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|Clientes| Cualquiera  |Cualquiera|UDP y TCP|Cualquiera  |Cualquiera |No autenticar|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Requisitos de red de la conferencia
<a name="Conf_req"> </a>

El ancho de banda que se usa para descargar el contenido de la Conferencia del servidor de Internet Information Services (IIS) depende del tamaño del contenido. Puede optar por supervisar el uso real y ajustar la planeación del ancho de banda según convenga.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia
<a name="Conf_req"> </a>

Una parte importante de la planificación de la red es asegurarse de que la red puede controlar el tráfico multimedia generado por Skype empresarial Server. Esta sección le ayudará a planear dicho tráfico multimedia.

### <a name="media-traffic-network-usage"></a>Uso de red de tráfico de medios
<a name="Net_req"> </a>

El uso del ancho de banda de tráfico multimedia puede resultar difícil de calcular por la cantidad de variables distintas, como el uso de códecs, la resolución y los niveles de actividad. El uso del ancho de banda es una función del códec usado y la actividad de la secuencia, y ambos pueden variar entre escenarios. En la siguiente tabla se enumeran los códecs de audio que se usan normalmente en escenarios de Skype empresarial Server.

**Ancho de banda del códec de audio**

|**Códec de audio**|**Escenario**|**Velocidad de bits de carga de audio (KBPS)**|**Solo ancho de banda de carga de audio y encabezado IP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP y SRTP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP, SRTP y corrección de error de reenvío (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ancha de RTAudio  <br/> |Punto a punto  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|Banda estrecha de RTAudio  <br/> |Punto a punto, RTC  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G.722  <br/> |Conferencia  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|G.722 estéreo  <br/> |Punto a punto, conferencias  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G.711  <br/> |RTC, conferencias  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Siren  <br/> |Conferencia  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Banda ancha SILK  <br/> |Punto a punto  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|Banda ancha/banda estrecha de seda  <br/> |Punto a punto  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> Las llamadas RTC desde el cliente de Skype empresarial suelen usar el códec G. 711, que requiere un ancho de banda alto. Si no hay suficiente ancho de banda disponible para ese códec, las llamadas pueden fallar con un error similar al siguiente en los registros de medios: al **menos un códec debe estar habilitado, HR: c0042004**. Los registros de medios (archivos. blog) están cifrados y solo pueden ser descodificados el personal de soporte técnico de Microsoft.

Las cantidades del ancho de banda de la tabla anterior se basan en los paquetes de 20 ms (50 paquetes por segundo) y para los códecs Siren y G.722 se incluyen las sobrecargas adicionales del protocolo de transporte seguro en tiempo real (SRTP) de los escenarios de conferencia y asumen que la secuencia está 100 % activa. La corrección de error de reenvío (FEC) se utiliza de forma dinámica cuando existe una pérdida de paquetes en el vínculo para ayudar a mantener la calidad de la secuencia de audio.

La versión estéreo del códec G.722 se utiliza en los sistemas basados en el sistema de la Sala de reuniones de Lync, que utiliza un micrófono estéreo o un par de micrófonos mono para permitir que los oyentes puedan distinguir mejor a varios hablantes en la sala de reuniones.

**Ancho de banda de resolución de vídeo**

|**Códec de vídeo**|**Resolución y relación de aspecto**|**Velocidad de bits máxima de carga de vídeo (Kbps)**|**Velocidad de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320 x 180 (16:9)  <br/> 212 x 160 (4:3)  <br/> |250  <br/> |4,5  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320 x 240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480 x 270 (16:9)  <br/> 424 x 320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640 x 480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848 x 480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960 x 540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920 x 1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |4,5  <br/> |
|H.264  <br/> |1280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Para el vídeo, el códec predeterminado es el estándar de codificación de vídeo avanzado H.264/MPEG-4 Parte 10, junto con sus extensiones de codificación de vídeo escalable. Para mantener la interoperabilidad con clientes heredados, el códec RTVideo se usa para llamadas de punto a punto entre Skype empresarial Server y clientes heredados. En sesiones de conferencia con Skype empresarial Server y clientes heredados, el punto de conexión de Skype empresarial Server puede codificar el video con ambos códecs de vídeo y enviar el H. 264 Bitstream a los clientes de Skype empresarial Server y el RTVideo Bitstream a Legacy cliente.

El ancho de banda necesario depende de la resolución, la calidad, la velocidad de fotogramas y los movimientos o cambios de la imagen. Para cada resolución existen dos secuencias de bits interesantes:

- **Tasa de bits de carga máxima** Esta es la velocidad de bits que un extremo usará para la resolución a la velocidad máxima de fotogramas. Es el valor que permite la máxima calidad de vídeo y de sonido.

- **Tasa mínima de bits de carga** Esta es la tarifa de bits por debajo de la cual un extremo de Skype empresarial Server cambiará a la siguiente resolución más baja. Para garantizar una determinada resolución, la velocidad de bits de carga de vídeo disponible no tiene que ser menor que esta velocidad de bits mínima para dicha resolución. Este valor le ayuda a comprender el valor mínimo posible en los casos en los que la velocidad de bits máxima no está disponible o no resulta práctica. Para algunos usuarios, esta baja velocidad de bits de vídeo puede considerarse una experiencia de vídeo no aceptable, por lo que aconsejamos precaución al considerar estas velocidades de bits mínimas de vídeo. Tenga en cuenta que en las escenas de vídeo estáticas o invariables, la velocidad de bits real puede descender temporalmente por debajo de la velocidad de bits mínima.

Skype empresarial Server admite numerosas soluciones. Esto permite que Skype empresarial Server se ajuste a diferentes anchos de banda de red y funciones de cliente de recepción. La relación de aspecto predeterminada de Skype empresarial Server es 16:9. La relación de aspecto de 4:3 heredada aún se admite para cámaras Web que no permiten la captura en la relación de aspecto de 16:9.

La FEC de vídeo siempre se incluye en la velocidad de bits de carga de vídeo cuando se usa para que no existan valores independientes con la FEC de vídeo y sin esta.

Los extremos no hacen fluir los paquetes de audio y vídeo continuamente. Dependiendo del escenario existen varios niveles de actividades de secuencia que indican la frecuencia con los que los paquetes se envían a una secuencia. La actividad de una secuencia depende de los medios y el escenario, y no depende del códec que se utiliza. En un escenario entre pares:

- Los extremos solo envían secuencias de audio cuando los usuarios hablan.

- Ambos participantes reciben secuencias de audio.

- Si se utiliza el vídeo, ambos extremos envían y reciben secuencias de vídeo durante la llamada.

- Para las escenas de vídeo estáticas, la velocidad de bits real puede llegar a ser considerablemente lenta de forma temporal, ya que el códec de vídeo omitirá la codificación de las regiones del vídeo sin cambios desde la muestra anterior.

En un escenario de conferencias:

- Los extremos envían secuencias de audio solo cuando los usuarios hablan.

- Todos los participantes reciben secuencias de audio.

- Si se utiliza el vídeo, los participantes pueden recibir hasta cinco secuencias de vídeo de recepción y una panorámica (por ejemplo, con una relación de aspecto de 20:3). De forma predeterminada, las cinco secuencias de vídeo de recepción se basan en el historial de hablantes activos, pero los usuarios también pueden seleccionar de forma manual los participantes de los que desean recibir una secuencia de vídeo. Si el multivídeo está habilitado, los requisitos de resolución y de ancho de banda de cada secuencia de vídeo serán menores.

- Cada participante que enciende la secuencia de envío de vídeo del usuario enviará una o varias transmisiones de vídeo. Skype empresarial Server tiene la capacidad de enviar hasta cinco videollamadas para optimizar la calidad de video para todos los clientes receptores. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la CPU, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de vídeo. El caso más común es el de H.264 y una secuencia de vídeo de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de vídeo diferente) se envían para acomodar diferentes solicitudes de receptor.

Además del ancho de banda necesario para el tráfico del protocolo de transporte seguro en tiempo real (RTP) para los medios de audio o vídeo, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar de estadísticas y del control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda de la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo usado para RTCP y difieren entre las secuencias de audio y vídeo por las diferencias en los datos de control.

**Ancho de banda de RTCP**

|**Media**|**Ancho de banda máximo RTCP (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Vídeo (solo se envía/recibe H.264 o RTVideo)  <br/> |base10  <br/> |
|Vídeo (se envía/recibe H.264 y RTVideo)  <br/> |4,5  <br/> |

Para la planeación de la capacidad, las dos estadísticas siguientes son de interés:

- **Ancho de banda máximo sin FEC** El ancho de banda máximo que consumirá una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario sin FEC. Este es el ancho de banda cuando la transmisión está al 100% de actividad y no hay pérdida de paquetes que activen el uso de FEC. Esto es útil para calcular la cantidad de ancho de banda que se debe asignar para permitir que el códec se use en un escenario determinado. No se espera que FEC sea un requisito en una red administrada.

- **Ancho de banda máximo con FEC** El ancho de banda máximo que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario con FEC. Este es el ancho de banda cuando la transmisión está al 100% de actividad y se produce una pérdida de paquetes al activar el uso de FEC para mejorar la calidad. Esto es útil para calcular la cantidad de ancho de banda que se debe asignar para permitir que el códec se use en un escenario determinado y permitir el uso de FEC para preservar la calidad en condiciones de pérdida de paquetes.

En las siguientes tablas también se muestra un valor de ancho de banda adicional, un **ancho de banda típico**. Este es el ancho de banda medio que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario. Este ancho de banda se puede usar para aproximar cuánto ancho de banda se está consumiendo por el tráfico multimedia en un momento específico, pero no se debe usar para planear la capacidad, porque las llamadas individuales superarán este valor cuando el nivel de actividad es mayor que el promedio. El ancho de banda de la secuencia de vídeo típica de las tablas siguientes se basa en una combinación de diferentes resoluciones de video, como se observa en los datos medidos de los clientes, y es probable que las instalaciones más pequeñas tengan números reales que difieran de los datos de la tabla. Por ejemplo, en sesiones de punto a punto, la mayoría de los usuarios usaría la ventana de representación de video predeterminada, mientras que un cierto porcentaje de usuarios aumentaría o maximizaría la aplicación de Skype empresarial Server para permitir mejores resoluciones de video.

En las siguientes tablas se proporcionan los valores para los distintos escenarios.

**Planificación de la capacidad de audio/vídeo para sesiones entre pares**

|**Media**|**Códec**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda ancha de RTAudio  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |Banda ancha SILK  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal al llamar a puntos de conexión de Skype empresarial Server  <br/> |H.264  <br/> |460  <br/> |4010 (para una resolución máxima de 1920 x 1080)  <br/> |Ya incluido  <br/> |
|Vídeo principal al llamar a los puntos de conexión de Lync 2010 o de Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para una resolución máxima de 1920 x 720)  <br/> |Ya incluido  <br/> |
|Vídeo panorámico al llamar a puntos de conexión de Skype empresarial Server  <br/> |H.264  <br/> |190  <br/> |2010 (para una resolución máxima de 1920 x 288)  <br/> |Ya incluido  <br/> |
|Vídeo panorámico al llamar a puntos de conexión de Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (para una resolución máxima de 1920 x 144)  <br/> |Ya incluido  <br/> |

**Planificación de la capacidad de audio/vídeo para conferencias**

|**Media**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Audio  <br/> |Siren  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Recepción principal de vídeo  <br/> |H.264 y RTVideo¹  <br/> |260  <br/> |8015  <br/> |No aplicable  <br/> |
|Envío principal de vídeo  <br/> |H.264 y RTVideo  <br/> |270  <br/> |8015  <br/> |No aplicable  <br/> |
|Recepción de vídeo panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2010 (para una resolución máxima de 1920 x 288)  <br/> |No aplicable  <br/> |
|Envío de vídeo panorámico  <br/> |H.264 y RTVideo  <br/> |190  <br/> |2515 ²  <br/> |No aplicable  <br/> |

1. El vídeo RT se envía además de H. 264 cuando los clientes de Lync 2010 se conectan a la Conferencia.

2. Si hay varias secuencias, el ancho de banda asignado se comparte dinámicamente.

Para el vídeo principal, el ancho de banda de secuencia típico es el ancho de banda agregado sobre todas las secuencias de vídeo recibidas, mientras que la secuencia máxima es el ancho de banda sobre todas las secuencias de vídeo enviadas. Aun con varias secuencias de vídeo, el ancho de banda típico para vídeo es más pequeño que en el escenario punto a punto, ya que muchas conferencias de vídeo utilizan el uso compartido de contenidos, que hace que las ventanas de vídeo sean más pequeñas y, por lo tanto, las resoluciones de vídeo son inferiores. El ancho de banda máximo de carga de vídeo agregada compatible es de 8000 Kbps para las secuencias de envío y de recepción que se utilizarían (por ejemplo, si hay dos secuencias de vídeo entrantes de 1920 x 1080 p). Los valores máximos se ven con poca frecuencia en las implementaciones reales.

Al crear una conferencia de varias partes que usa la característica de vista de galería, la utilización del ancho de banda aumenta inicialmente a medida que se unen los participantes, y después disminuye a medida que las resoluciones se ajustan al máximo.

||**2 participantes**|**3 participantes**|**4 participantes**|**5 participantes**|**6 participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluciones máx. recibidas** <br/> |1920 x 1080  <br/> |1280 x 720  <br/> |640 x 360  <br/> |640 x 360 320 x 240  <br/> |640 x 360 320 x 240  <br/> |
|**Velocidad de bits media total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocidad de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

El ancho de banda de secuencia típico para los vídeos panorámicos se basa en los dispositivos que solo transmiten en secuencias un vídeo panorámico de hasta 960 x 144. Tenga en cuenta que el ancho de banda de secuencia típico puede aumentar al utilizar dispositivos con un vídeo panorámico de 1920 x 288.

**Planificación de la capacidad de audio para el RTC**

|**Media**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (esto incluye a los participantes de la RTC en conferencias)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

Las cifras de ancho de banda de red de estas tablas representan solamente tráfico unidireccional; incluyen 5 Kpbs para sobrecarga de tráfico RTPC de cada secuencia.

## <a name="managing-quality-of-service"></a>Administración de la Calidad de servicio (QoS)
<a name="man_QOS"> </a>

La calidad de servicio (QoS) es una tecnología de red que usan algunas organizaciones para ofrecer una experiencia de usuario final óptima para las comunicaciones de audio y vídeo. QoS se usa principalmente en las redes en las que el ancho de banda es limitado. Como hay una gran cantidad de paquetes de red compitiendo por una cantidad relativamente pequeña de ancho de banda disponible, la calidad de servicio permite a los administradores asignar prioridades más altas a los paquetes que contienen datos de audio o vídeo. Al asignar una prioridad más alta a estos paquetes, las comunicaciones de audio y vídeo probablemente se completen con mayor rapidez y con menos interrupciones que las sesiones de red que incluyen transferencias de archivos, exploración web o copias de seguridad de bases de datos. Esto se debe a que se asigna una prioridad de "mejor esfuerzo" a los paquetes de red usados para las transferencias de archivos o las copias de seguridad de bases de datos.

> [!NOTE]
> Como regla general, la QoS se aplica solamente a las sesiones de comunicación de la red interna. Al implementar la QoS necesita configurar los servidores y los enrutadores para que admitan el marcado de paquetes de un modo especial que puede que no se admita en Internet o en otras redes. Incluso si la calidad de servicio es compatible con otras redes, no hay garantía de que QoS se configure de la misma manera en que se configuró el servicio. Si utiliza MPLS tendrá que colaborar junto con su proveedor de MPLS.

Skype empresarial Server no requiere QoS, pero se recomienda encarecidamente. Si experimenta problemas de pérdida de paquetes en la red, las soluciones disponibles son agregar más ancho de banda o implementar QoS. Si no puede agregar más ancho de banda, la implementación de la QoS puede ser la única solución al problema.

Skype empresarial Server ofrece compatibilidad completa con QoS, lo que significa que las organizaciones que ya usan QoS pueden integrar fácilmente Skype empresarial Server en su infraestructura de red existente. Para ello, es necesario llevar a cabo los siguientes pasos:

- [Habilitar QoS en Skype empresarial Server para dispositivos que no se basan en Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). De forma predeterminada, la QoS está deshabilitada en los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Skype empresarial Server para habilitar y deshabilitar la calidad de servicio para los dispositivos, normalmente no puede usar el producto para modificar los códigos de DSCP usados por estos dispositivos.

- [Configurar intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencias, aplicaciones y mediación](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Es preciso reservar un conjunto único de puertos para distintos tipos de paquetes, como paquetes de audio y vídeo. Al usar Skype empresarial Server, no se habilita ni deshabilita QoS al establecer un valor de propiedad en verdadero o falso. En su lugar, la calidad de servicio se habilita al configurar intervalos de puertos y al crear y aplicar posteriormente una directiva de grupo. Si más tarde decide no usar QoS, puede "Deshabilitar" QoS si quita los objetos de directiva de grupo apropiados.

- [Configurar intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores. La configuración de una directiva de QoS solo se realiza para el lado interno de los servidores perimetrales. Esto se debe a que QoS está diseñado para su uso en su red interna y no en Internet.

- [Configurar intervalos de puertos y una directiva de calidad de servicio para sus clientes en Skype empresarial Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Estos intervalos de puertos solo se aplican a equipos cliente y, por lo general, no son los mismos que los intervalos de puertos configurados en los servidores. Tenga en cuenta que Skype empresarial Server no es compatible con QoS para sistemas operativos Windows que no sean Windows 10.


> [!NOTE]
> Si usa Windows Server 2012 o Windows Server 2012 R2, es posible que esté interesado en el nuevo conjunto de cmdlets de Windows PowerShell disponibles para administrar QoS en esa plataforma. Para obtener más información, consulte [cmdlets QoS de red en Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

La calidad de servicios también se trata en el informe sobre la [planificación, la supervisión y la solución de problemas de la red de Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) con detalles y profundidad adicionales. Aunque el contenido se refiere explícitamente a Lync 2010 y a Lync 2013, las consideraciones para Skype empresarial Server no cambian.

## <a name="see-also"></a>Vea también
<a name="man_QOS"> </a>

[Planificar IPv6 en Skype Empresarial](ipv6.md)

[Requisitos del equilibrio de carga para Skype Empresarial](load-balancing.md)

[Requisitos de DNS para Skype empresarial Server](dns.md)
