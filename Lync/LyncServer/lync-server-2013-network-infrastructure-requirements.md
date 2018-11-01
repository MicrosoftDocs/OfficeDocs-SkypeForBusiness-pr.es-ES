---
title: Requisitos de la infraestructura de red
TOCTitle: Requisitos de la infraestructura de red
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48274920
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de la infraestructura de red

 

_**Última modificación del tema:** 2014-08-28_

La tarjeta de adaptador de red de cada servidor de la topología de Lync Server 2013 debe admitir al menos 1 gigabit por segundo (Gbps). En general, debería conectar todos los roles de servidor dentro de la topología de Lync Server con una latencia baja y una red de área local (LAN) con un elevado ancho de banda. El tamaño de la LAN depende del tamaño de la topología:

  - En las topologías de Standard Edition, los servidores deberían estar en una red que admita Ethernet de 1 Gbps o equivalente.

  - En las topologías de Grupo de servidores front-end, la mayoría de los servidores deberían estar en una red que admita más de 1 Gbps, sobre todo cuando se admiten conferencias de audio o vídeo y el uso compartido de aplicaciones.

Para la integración de la red telefónica conmutada (RTC), puede usar líneas T1/E1 o enlaces troncales SIP.

## Requisitos de red para el audio y vídeo

Entre los requisitos de red para audio y vídeo (A/V) en una implementación de Lync Server se incluyen los siguientes:

  - Si está implementado un Servidor perimetral único o un Grupo de servidores perimetrales con el equilibrio de carga DNS, puede configurar el firewall externo como un NAT. No puede configurar el firewall interno como un NAT. Para obtener más información sobre estos requisitos, vea [Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) en la documentación sobre planeación.
    
    > [!IMPORTANT]  
    > Si tiene un Grupo de servidores perimetrales y está usando un equilibrador de carga de hardware, debe usar las direcciones IP públicas en cada uno de los Servidores perimetrales y no puede usar NAT para los servidores o el grupo de servidores en su dispositivo NAT (por ejemplo, el firewall, u otro dispositivo de infraestructura que usaría NAT en el tráfico entrante o saliente). Para obtener detalles, vea <a href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumen de puerto - Servidor perimetral consolidado ampliado con equilibradores de carga de hardware en Lync Server 2013</a> en la documentación de planeación para acceso de usuario externo.
    


  - Si la organización usa una infraestructura QoS (Calidad de servicio), el subsistema de medios estará diseñado de modo que funcione con esta infraestructura existente.

  - Si usa el protocolo de seguridad de Internet (IPsec), se recomienda deshabilitar IPsec en los intervalos de puertos usados para el tráfico de audio y vídeo. Para obtener más información, vea [Excepciones de IPsec en Lync Server 2013](lync-server-2013-ipsec-exceptions.md) en la documentación sobre planeación.

Para asegurar una calidad óptima de los medios, siga este procedimiento:

  - Aprovisione los vínculos de red para que admitan una capacidad de proceso de 65 kilobits por segundo (Kbps) por secuencia de audio y 500 Kbps por secuencia de vídeo en los períodos de uso máximo. Una sesión bidireccional de audio o vídeo consta de dos secuencias.

  - Para hacer frente a los picos de tráfico inesperados por encima de este nivel y a un mayor uso en el tiempo, los extremos multimedia de Lync Server pueden adaptarse a condiciones de red variables y admiten cargas de tres veces la capacidad de proceso (consulte el apartado anterior) para audio y vídeo a la vez que mantienen una calidad aceptable. No obstante, no se puede dar por sentado que esta capacidad de adaptación admita una red mal aprovisionada. En una red así se reduce la capacidad de los extremos multimedia de Lync Server para afrontar dinámicamente las condiciones de red variables (como un número de pérdidas de paquetes temporalmente alto).

  - En el caso de los vínculos de red donde el aprovisionamiento resulta muy costoso y difícil, puede que se vea obligado a considerar un aprovisionamiento para un menor volumen de tráfico. En este escenario, deje que la elasticidad de los extremos multimedia de Lync Server absorba la diferencia entre el volumen de tráfico y el nivel de tráfico máximo, a expensas de una pequeña reducción en la calidad de voz. También hay una disminución en el margen que normalmente está disponible para absorber los picos de tráfico repentinos.

  - En el caso de los vínculos que no se pueden aprovisionar correctamente a corto plazo (por ejemplo, un sitio con vínculos WAN de muy poca calidad), considere la posibilidad de deshabilitar el vídeo para algunos usuarios.

  - Aprovisione la red para asegurar un retraso máximo de un extremo a otro (latencia) de 150 milisegundos (ms) con carga máxima. La latencia es el único problema de red que los componentes multimedia de Lync Server no pueden reducir, por lo que es importante encontrar y eliminar los puntos débiles.

  - En servidores que ejecutan software antivirus, todos los servidores que ejecutan Lync Server se incluyen en la lista de excepciones para proporcionar un rendimiento y una calidad de audio óptimos.

## Requisitos de red de la conferencia

El ancho de banda que se usa para descargar el contenido de una conferencia desde el servidor Servicios de Internet Information Server (IIS) depende del tamaño del contenido cargado.

