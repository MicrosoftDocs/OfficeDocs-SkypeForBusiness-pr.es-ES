---
title: Planeación de los requisitos de red para Skype empresarial
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
description: 'Resumen: Revise las consideraciones del componente de red que se indican a continuación antes de implementar Skype empresarial Server.'
ms.openlocfilehash: 709da2ddd60b5b6ee69c22264c159d5d94ab91e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025801"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planeación de los requisitos de red para Skype empresarial

**Resumen:** Revise las consideraciones del componente de red que se indican a continuación antes de implementar Skype empresarial Server.

La información contenida en estos temas también se trata en el whitepaper [planificación, supervisión y solución de problemas de red con Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) con detalles adicionales y profundidad. Aunque el contenido hace referencia explícita a Lync 2010 y Lync 2013, las consideraciones para Skype empresarial Server no cambian.

Del mismo modo, si la red incluye Wi-Fi y acceso con cable, el artículo [sobre la entrega de comunicaciones en tiempo real de Lync 2013 sobre Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494) es una buena referencia y también se aplica a Skype empresarial Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

El adaptador de red de cada servidor de la topología de Skype empresarial Server debe admitir al menos 1 Gigabit por segundo (Gbps). En general, debe conectar todos los roles de servidor dentro de la topología de Skype empresarial Server usando una red de área local (LAN) de baja latencia y gran ancho de banda. El tamaño de la LAN depende del tamaño de la topología:

- En las topologías de Standard Edition, los servidores deben estar en una red que admita Ethernet de 1 Gbps o equivalente.

- En las topologías de Enterprise Edition, la mayoría de los servidores deben estar en una red que admita más de 1 Gbps, sobre todo cuando se admiten conferencias de audio y vídeo (A/V) y uso compartido de aplicaciones.

Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.

## <a name="audiovideo-network-requirements"></a>Requisitos de red de audio y vídeo
<a name="AV_req"> </a>

Entre los requisitos de red para audio y vídeo (A/V) en una implementación de Skype empresarial Server se incluyen los siguientes:

- Si va a implementar un solo servidor perimetral o un grupo de servidores perimetrales mediante el equilibrio de carga de DNS, puede configurar el Firewall _externo_ para realizar la traducción de direcciones de red (NAT). No puede configurar el Firewall _interno_ para realizar NAT. Para obtener más información, consulte [Port and Firewall Planning](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Si tiene un grupo de servidores perimetrales y usa un equilibrador de carga de hardware, debe usar direcciones IP públicas en los servidores perimetrales y no puede usar NAT para los servidores o el grupo en el dispositivo compatible con NAT (por ejemplo, un dispositivo de firewall o un conmutador de LAN. Para obtener más información, consulte [Edge Server Scenarios in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.

- Si usa el protocolo de seguridad de Internet (IPsec), se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener información detallada, consulte [IPSec Exceptions](#ipsec-exceptions).

Para proporcionar una calidad de medios óptima, haga lo siguiente:

- Aprovisione los vínculos de red para admitir el rendimiento de 65 kilobits por segundo (kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo, si están habilitados, durante los períodos de uso máximo. Una sesión de audio o vídeo bidireccional utiliza dos secuencias, por lo que una conexión de audio/teléfono simple requerirá 130Kbps para cubrir cada secuencia. El vídeo usará igualmente el total de 1000 kbps para llevar a cabo una conexión ascendente y descendente.

- Para hacer frente a picos inesperados en el tráfico y aumentar el uso con el tiempo, los extremos de medios de Skype empresarial Server se pueden adaptar a distintas condiciones de red y admitir tres veces el rendimiento de audio y vídeo, a la vez que se mantiene una calidad aceptable. No dé por supuesto que esta adaptabilidad enmascarará el problema cuando una red esté aprovisionada. En una red aprovisionada inhabilitada, se reduce la capacidad de los extremos de medios de Skype empresarial Server para tratar dinámicamente las distintas condiciones de red (por ejemplo, la pérdida de paquetes altos temporales).

- Para los vínculos de red en los que el aprovisionamiento es muy costoso y difícil, es posible que tenga que considerar el aprovisionamiento para un menor volumen de tráfico. En este escenario, permita que la elasticidad de los puntos de conexión multimedia de Skype empresarial Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a costa de una reducción de la calidad de la voz. Además, habrá una disminución en el espacio que, de lo contrario, estará disponible para absorber picos repentinos del tráfico.

- Para los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio que usa vínculos WAN de muy mala calidad), considere la posibilidad de deshabilitar el vídeo para determinados usuarios.

- Aprovisione la red para garantizar un retraso (latencia) máximo de un extremo a otro de 150 milisegundos (MS) en carga máxima. La latencia es la única discapacidad de red que los componentes multimedia de Skype empresarial Server no pueden reducir, y es importante buscar y eliminar los puntos débiles.

- En el caso de los servidores que ejecutan software antivirus, incluya todos los servidores que ejecutan Skype empresarial Server en la lista de excepciones para proporcionar un rendimiento y una calidad de audio óptimos.

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


## <a name="conferencing-network-requirements"></a>Requisitos de red para conferencias
<a name="Conf_req"> </a>

El ancho de banda usado para descargar contenido de conferencia del servidor de Internet Information Services (IIS) depende del tamaño del contenido. Puede elegir supervisar el uso real y ajustar la planeación de ancho de banda en consecuencia.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de ancho de banda de red para el tráfico multimedia
<a name="Conf_req"> </a>

Una parte importante de la planeación de red es asegurarse de que la red puede controlar el tráfico de medios generado por Skype empresarial Server. Esta sección le ayudará a planear para ese tráfico de medios.

### <a name="media-traffic-network-usage"></a>Uso de red de tráfico de medios
<a name="Net_req"> </a>

El uso del ancho de banda de tráfico de medios puede resultar difícil de calcular debido a la cantidad de variables diferentes, como el uso de códecs, la resolución y los niveles de actividad. El uso del ancho de banda es una función del códec que se usa y la actividad de la secuencia, que puede variar entre escenarios. En la siguiente tabla se enumeran los códecs de audio que se usan normalmente en los escenarios de Skype empresarial Server.

**Ancho de banda del códec de audio**

|**Códec de audio**|**Escenario**|**Velocidad de bits de carga de audio (KBPS)**|**Solo ancho de banda de carga de audio y encabezado IP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP y SRTP (Kbps)**|**Ancho de banda de carga de audio, encabezado IP, UDP, RTP, SRTP y corrección de error de reenvío (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ancha de RTAudio  <br/> |Punto a punto  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|Banda estrecha de RTAudio  <br/> |RTC punto a punto  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G. 722  <br/> |Conferencia  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|G.722 estéreo  <br/> |Conferencia punto a punto  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G. 711  <br/> |RTC, conferencias  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Siren  <br/> |Conferencia  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|Banda ancha de seda  <br/> |Punto a punto  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|Banda ancha de seda  <br/> |Punto a punto  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Banda ancha de seda  <br/> |Punto a punto  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|Banda ancha/banda estrecha de seda  <br/> |Punto a punto  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> Las llamadas RTC desde el cliente de Skype empresarial suelen usar el códec G. 711, que requiere un ancho de banda alto. Si no hay suficiente ancho de banda disponible para ese códec, se puede producir un error en las llamadas con un error similar al siguiente en los registros de medios: al **menos un códec debe estar habilitado, HR: c0042004**. Los registros de medios (archivos. blog) están cifrados y solo pueden ser descodificados por el personal de soporte técnico de Microsoft.

Los números de ancho de banda de la tabla anterior se basan en 20 MS packettion (50 paquetes por segundo) y para los códecs Siren y G. 722 incluyen la sobrecarga adicional del Protocolo de transporte seguro en tiempo real (SRTP) de los escenarios de conferencia y se supone que la transmisión por secuencias es 100% activo. La corrección de errores de reenvío (FEC) se usa dinámicamente cuando se produce una pérdida de paquetes en el vínculo para ayudar a mantener la calidad de la secuencia de audio.

La versión estéreo del códec G. 722 se usa en sistemas que se basan en el sistema de la sala de Lync, que usa un único micrófono estéreo o un par de micrófonos mono para permitir a los oyentes distinguir mejor varios altavoces en la sala de reuniones.

**Ancho de banda de resolución de video**

|**Códec de video**|**Resolución y relación de aspecto**|**Velocidad de bits máxima de carga de vídeo (kbps)**|**Velocidad de bits de carga de vídeo mínima (kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H. 264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H. 264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H. 264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H. 264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H. 264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H. 264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H. 264  <br/> |1920 x 1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H. 264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H. 264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H. 264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

El códec predeterminado para vídeo es el estándar de codificación de vídeo avanzado H. 264/MPEG-4, parte 10, junto con sus extensiones de codificación de vídeo escalables para la escalabilidad temporal. Para mantener la interoperabilidad con los clientes heredados, el códec RTVideo se sigue usando para las llamadas punto a punto entre Skype empresarial Server y los clientes heredados. En sesiones de conferencia con Skype empresarial Server y clientes heredados, el punto de conexión de Skype empresarial Server puede codificar el vídeo con los dos códecs de vídeo y enviar la Bitstream H. 264 a los clientes de Skype empresarial Server y el RTVideo Bitstream a Legacy equipos.

El ancho de banda necesario depende de la resolución, la calidad, la velocidad de fotogramas y la cantidad de movimiento o cambio en la imagen. Para cada resolución hay dos velocidades de bits pertinentes:

- **Tasa de bits de carga máxima** Esta es la velocidad de bits que usará un extremo para la resolución a la velocidad de fotogramas máxima. Este es el valor que permite la mayor calidad de vídeo y sonido.

- **Velocidad de bits de carga mínima** Esta es la velocidad de bits por debajo de la cual un punto de conexión de Skype empresarial Server cambiará a la siguiente resolución más baja. Para garantizar una determinada resolución, la velocidad de bits de carga de vídeo disponible no debe estar por debajo de esta velocidad de bits mínima para esa resolución. Este valor le ayudará a comprender el valor más bajo posible si la velocidad de bits máxima no está disponible o no es práctica. Para algunos usuarios, un vídeo de velocidad de bits baja puede proporcionar una experiencia de vídeo inaceptable, por lo que debe tener cuidado con estas velocidades de bits de carga mínima de vídeo. Tenga en cuenta que para las escenas de vídeos estáticos y sin cambios, la velocidad de bits real puede caer temporalmente por debajo de la velocidad de bits mínima.

Skype empresarial Server admite muchas resoluciones. Esto permite que Skype empresarial Server se ajuste a diferentes anchos de banda de red y características de cliente de recepción. La relación de aspecto predeterminada de Skype empresarial Server es 16:9. La relación de aspecto 4:3 heredada todavía es compatible con las cámaras Web que no permiten la captura en la relación de aspecto 16:9.

La FEC de vídeo siempre se incluye en la velocidad de bits de carga de vídeo cuando se usa, por lo que no hay valores separados para con FEC de vídeo y sin FEC de vídeo.

Los extremos no hacen fluir los paquetes de audio y video continuamente. Dependiendo del escenario existen varios niveles de actividades de secuencia que indican la frecuencia con los que los paquetes se envían a una secuencia. La actividad de una secuencia depende de los medios y el escenario, y no depende del códec que se utiliza. En un escenario entre pares:

- Los extremos solo envían secuencias de audio cuando hablan los usuarios.

- Ambos participantes reciben secuencias de audio.

- Si se usa vídeo, ambos extremos envían y reciben secuencias de vídeo durante la llamada.

- Para las escenas de vídeo estáticos, la velocidad de bits real puede ser temporalmente baja, ya que el códec de vídeo omitirá las regiones de codificación del vídeo sin cambios desde el ejemplo anterior.

En un escenario de conferencias:

- Los extremos envían secuencias de audio solo cuando los usuarios hablan.

- Todos los participantes reciben secuencias de audio.

- Si se utiliza video, los participantes pueden recibir hasta cinco secuencias de vídeo y uno panorámico (por ejemplo, con relación de aspecto 20:3). De forma predeterminada, los cinco reciben secuencias de vídeo basadas en el historial de hablantes activos, pero los usuarios también pueden seleccionar de forma manual de los que desea recibir una secuencia de video. Si está habilitado el uso de varios vídeos, el requisito de resolución y ancho de banda para cada una de las secuencias de vídeo será menor.

- Cada participante que activa la secuencia de vídeo enviar del usuario enviará una o más secuencias de vídeo. Skype empresarial Server tiene la capacidad de enviar hasta cinco secuencias de vídeo para optimizar la calidad de vídeo para todos los clientes receptores. La cantidad real de secuencias de vídeo que se envía automáticamente está determinado por quien envía, según la capacidad de la computadora, ancho de banda ascendente disponible y la cantidad de recibir clientes que solicitan cierta secuencia de video. El caso más común es el de H.264 y una secuencia de video de RTVideo se envían en caso de que un cliente heredado se una a la conferencia. Otro escenario común es que varias secuencias de vídeo H.264 (por ejemplo, con resoluciones de video diferente) se envían para acomodar diferentes solicitudes de receptor.

Además del ancho de banda requerido para el tráfico de protocolo seguro en tiempo real (RTP) para los medios de audio o video, el ancho de banda es necesario para el protocolo de control de transporte en tiempo real (RTCP). El RTCP se utiliza para informar estadísticas y control fuera de banda de la secuencia RTP. Para la planificación, use los números del ancho de banda en la tabla siguiente para el tráfico RTCP. Estos valores representan el ancho de banda máximo usado para RTCP y son distintos para las secuencias de audio y vídeo debido a las diferencias en los datos de control.

**Ancho de banda de RTCP**

|**Medios**|**Ancho de banda máximo RTCP (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Video (solo se envía/recibe H.264 o RTVideo)  <br/> |10   <br/> |
|Video (se envía/recibe H.264 y RTVideo)  <br/> |15   <br/> |

Para la planeación de la capacidad, las dos estadísticas siguientes son de interés:

- **Ancho de banda máximo sin FEC** El ancho de banda máximo que consumirá una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario sin FEC. Este es el ancho de banda cuando la secuencia está con el 100% de actividad y no existe una pérdida de paquetes que desencadena el uso de FEC. Esto es útil para calcular la cantidad de ancho de banda que debe asignarse para permitir que se use el códec en un escenario determinado. No se espera que FEC sea un requisito en una red administrada.

- **Ancho de banda máximo con FEC** El ancho de banda máximo que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario con FEC. Este es el ancho de banda cuando la secuencia está con el 100% de actividad y existe una pérdida de paquetes que desencadena el uso de FEC para mejorar la calidad. Esto es útil para calcular la cantidad de ancho de banda que se debe asignar para permitir que el códec se use en un escenario determinado y permitir el uso de FEC para preservar la calidad en las condiciones de pérdida de paquetes.

Las siguientes tablas también enumeran un valor adicional de ancho de banda, **Ancho de banda típico**. Es el ancho de banda medio que consume una secuencia. Esto incluye la actividad típica de la secuencia y el códec típico que se usa en el escenario. Este ancho de banda se puede usar para aproximar la cantidad de ancho de banda consumida por el tráfico multimedia a una hora específica, pero no debe usarse para la planeación de la capacidad, ya que las llamadas individuales sobrepasarán este valor si el nivel de actividad es superior al promedio. El ancho de banda de la secuencia de vídeo típica de las tablas siguientes se basa en una combinación de diferentes resoluciones de vídeo, como se observa en los datos de cliente medidos, y es probable que las instalaciones más pequeñas tengan números reales que difieren de los datos de la tabla. Por ejemplo, en sesiones punto a punto, la mayoría de los usuarios utilizarían la ventana Presentación vídeo predeterminada, mientras que un porcentaje de los usuarios aumentaría o maximizaría la aplicación de Skype empresarial Server para permitir mejores resoluciones de vídeo.

En las tablas siguientes se proporcionan valores para los distintos escenarios.

**Planificación de la capacidad de audio/video para sesiones entre pares**

|**Medios**|**Códec**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda ancha de RTAudio  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |Banda ancha de seda  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal al llamar a puntos de conexión de Skype empresarial Server  <br/> |H. 264  <br/> |460  <br/> |4010 (para una resolución máxima de 1920x1080)  <br/> |Ya se ha incluido  <br/> |
|Vídeo principal al llamar a los puntos de conexión de Lync 2010 o Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para una resolución máxima de 1920x720)  <br/> |Ya se ha incluido  <br/> |
|Vídeo panorámico al llamar a puntos de conexión de Skype empresarial Server  <br/> |H. 264  <br/> |190  <br/> |2010 (para una resolución máxima de 1920x288)  <br/> |Ya se ha incluido  <br/> |
|Vídeo panorámico al llamar a los puntos de conexión de Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (para una resolución máxima de 1920x144)  <br/> |Ya se ha incluido  <br/> |

**Planificación de la capacidad de audio/video para conferencias**

|**Medios**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Audio  <br/> |Siren  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Recepción principal de video  <br/> |H. 264 y RTVideo ¹  <br/> |260  <br/> |8015  <br/> |No aplicable  <br/> |
|Envío principal de video  <br/> |H. 264 y RTVideo  <br/> |270  <br/> |8015  <br/> |No aplicable  <br/> |
|Recepción de video panorámico  <br/> |H. 264 y RTVideo  <br/> |190  <br/> |2010 (para una resolución máxima de 1920x288)  <br/> |No aplicable  <br/> |
|Envío de video panorámico  <br/> |H. 264 y RTVideo  <br/> |190  <br/> |2515 ²  <br/> |No aplicable  <br/> |

1. Se envía el vídeo RT además de H. 264 cuando los clientes de Lync 2010 están conectados a la Conferencia.

2. Si hay varias secuencias, comparten dinámicamente el ancho de banda asignado.

Para el vídeo principal, el ancho de banda de secuencia típico es el ancho de banda agregado sobre todas las secuencias de vídeo recibidas y la transmisión máxima es el ancho de banda de todas las secuencias de vídeo enviadas. Incluso con varias secuencias de vídeo, el ancho de banda de vídeo típico es más pequeño que en el caso de punto a punto, ya que muchas conferencias de vídeo usan el uso compartido de contenido que conduce a ventanas de vídeo mucho más pequeñas y, por tanto, resoluciones de vídeo más pequeñas. El ancho de banda de carga de vídeo agregado máximo admitido es de 8000 Kbps para las secuencias de envío y de recepción que se usarán (por ejemplo, si hay dos secuencias de vídeo entrantes 1920x1080p). Los valores máximos solo se muestran rara vez en implementaciones reales.

Al compilar una conferencia de varios participantes que usa la característica de vista de galería, el uso de ancho de banda aumenta inicialmente a medida que los participantes se unen y, a continuación, disminuye a medida que las resoluciones se ajustan al máximo.

||**2 participantes**|**3 participantes**|**4 participantes**|**5 participantes**|**6 participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluciones máximas recibidas** <br/> |1920  <br/> |1280x720  <br/> |640 x 360  <br/> |640 x 360 320x240  <br/> |640 x 360 320x240  <br/> |
|**Velocidad de bits promedio total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocidad de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

El ancho de banda de secuencia típico para vídeo panorámico se basa en dispositivos que solo se transmiten a 960x144 panorámico de vídeo. Se espera que el ancho de banda de secuencia típico aumente al usar dispositivos con vídeo panorámico 1920 x 288.

**Planificación de la capacidad de audio para el RTC**

|**Medios**|**Códec típico**|**Ancho de banda de secuencia típica (Kbps)**|**Ancho de banda de secuencia máximo sin FEC**|**Ancho de banda de secuencia máximo con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (esto incluye a los participantes de la RTC en conferencias)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda estrecha de RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

los números del ancho de banda de red en estas tablas representa solo el tráfico de una vía e incluye 5 Kbps para los gastos del tráfico RTCP.

## <a name="managing-quality-of-service"></a>Administración de la calidad de servicio
<a name="man_QOS"> </a>

La calidad de servicio (QoS) es una tecnología de red que se usa en algunas organizaciones para ayudar a proporcionar una experiencia del usuario final óptima para las comunicaciones de audio y vídeo. La QoS se usa con más frecuencia en redes en las que el ancho de banda es limitado: con un gran número de paquetes de red que compiten por una cantidad bastante pequeña de ancho de banda disponible, QoS permite a los administradores asignar prioridades mayores a los paquetes que transporten datos de audio o vídeo. Al dar a estos paquetes una prioridad mayor, es probable que las comunicaciones de audio y vídeo se completen más rápido y con menos interrupciones, que sesiones de red en las que se incluyen elementos como las transferencias de archivos, la exploración Web o las copias de seguridad de bases de datos. Esto se debe a que los paquetes de red que se usan para las transferencias de archivos o las copias de seguridad de bases de datos tienen una prioridad de "mejor esfuerzo".

> [!NOTE]
> Como regla, QoS solo se aplica a las sesiones de comunicación en la red interna. Cuando se implementa QoS, se configuran los servidores y los enrutadores para que admitan la marcación de paquetes de una manera determinada que puede no ser compatible con Internet o en otras redes. Incluso si la calidad de servicio se admite en otras redes, no hay ninguna garantía de que QoS se configurará exactamente del mismo modo en que se configuró el servicio. Si usa MPLS, deberá trabajar con su proveedor de MPLS.

Skype empresarial Server no requiere QoS, pero se recomienda encarecidamente. Si experimenta problemas de pérdida de paquetes en la red, las soluciones disponibles son agregar más ancho de banda o implementar QoS. Si no es posible agregar más ancho de banda, implementar QoS puede ser la única forma de pago para resolver el problema.

Skype empresarial Server ofrece compatibilidad completa con QoS: Esto significa que las organizaciones que ya usan QoS pueden integrar fácilmente Skype empresarial Server en su infraestructura de red existente. Para ello, debe seguir estos pasos:

- [Habilitación de QoS en Skype empresarial Server para dispositivos que no están basados en Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). De manera predeterminada, QoS se deshabilita para los equipos y otros dispositivos (como iPhone) que ejecutan otros sistemas operativos. Aunque puede usar Skype empresarial Server para habilitar y deshabilitar la calidad de servicio para dispositivos, normalmente no puede usar el producto para modificar los códigos de DSCP que usan estos dispositivos.

- [Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores de conferencia, aplicación y mediación](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Debe reservar un conjunto único de puertos para diferentes tipos de paquetes, como paquetes de audio y vídeo. Si usa Skype empresarial Server no puede habilitar o deshabilitar QoS estableciendo el valor de una propiedad en true o en false. En su lugar, habilite QoS mediante la configuración de intervalos de puertos y, a continuación, la creación y aplicación de la Directiva de grupo. Si más adelante decide no usar QoS, puede "Deshabilitar" QoS si quita los objetos de directiva de grupo apropiados.

- [Configuración de intervalos de puertos y una directiva de calidad de servicio para los servidores perimetrales](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Aunque no es un requisito, puede configurar los servidores perimetrales para que usen los mismos intervalos de puertos que los otros servidores. La configuración de una directiva de QoS solo debe realizarse para el lado interno de los servidores perimetrales. Esto se debe a que QoS está diseñado para su uso en la red interna y no en Internet.

- [Configuración de intervalos de puertos y una directiva de calidad de servicio para los clientes en Skype empresarial Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Estos intervalos de puertos solo se aplican a los equipos cliente y suelen ser distintos de los intervalos de puertos configurados en los servidores. Tenga en cuenta que Skype empresarial Server no es compatible con QoS para sistemas operativos Windows que no sean Windows 10.


> [!NOTE]
> Si usa Windows Server 2012 o Windows Server 2012 R2, es posible que esté interesado en el nuevo conjunto de cmdlets de Windows PowerShell disponibles para administrar QoS en esa plataforma. Para obtener más información, consulte [cmdlets de QoS de red en Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

La QoS también se trata en el whitepaper [planificación, supervisión y solución de problemas de red con Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) con detalles adicionales y profundidad. Aunque el contenido hace referencia explícita a Lync 2010 y Lync 2013, las consideraciones para Skype empresarial Server no cambian.

## <a name="see-also"></a>Consulte también
<a name="man_QOS"> </a>

[Planeación de IPv6 en Skype empresarial](ipv6.md)

[Requisitos de equilibrio de carga para Skype empresarial](load-balancing.md)

[Requisitos de DNS para Skype empresarial Server](dns.md)
