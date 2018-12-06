---
title: 'Lync Server 2013: Directrices de implementación para el servidor de mediación'
TOCTitle: Directrices de implementación para el servidor de mediación
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48275795
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Directrices de implementación para el servidor de mediación en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En este tema se describen las guías para la planeación de la implementación de Servidor de mediación. Después de repasar estas instrucciones, le recomendamos que use la Herramienta de planeación para crear y ver posibles topologías alternativas, que pueden servir de modelo para saber cómo sería la topología definitiva adaptada que decida implementar.

## ¿ Servidor de mediación independientes o combinados?

Servidor de mediación se combina de forma predeterminada en el Servidor Standard Edition o en el Servidor front-end de un Grupo de servidores front-end en los sitios centrales. El número de llamadas por la red telefónica conmutada (RTC) que se pueden administrar y el número de equipos necesarios en el grupo de servidores dependerán de los siguientes factores:

  - El número de puertas de enlace del mismo nivel que controla el Grupo de servidores de mediación

  - Los períodos de gran tráfico que atraviesa las puertas de enlace

  - El porcentaje de llamadas cuyos medios omiten el Servidor de mediación

Al planear, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y conferencias de A/V no configuradas para omisión de medios, además del procesamiento necesario para administrar las interacciones de señalización del número de llamadas que es necesario admitir en las horas de más actividad. Si no hay suficiente CPU, deberá implementar un grupo de Servidores de mediación independiente, y las puertas de enlace RTC, los IP-PBX y los SBC deberán dividirse en subconjuntos controlados por los Servidores de mediación combinados en el primer grupo de servidores y los Servidores de mediación en uno o más grupos de servidores independientes.

Si implementó puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBC) incompatibles con las funcionalidades adecuadas para interactuar con un grupo de Servidores de mediación, incluidas las siguientes, estas deberán asociarse a un grupo de servidores independiente formado por un solo Servidor de mediación:

  - Llevar a cabo el equilibrio de carga de Sistema de nombre de dominio (DNS) del nivel de capa de red en los Servidores de mediación de un grupo de servidores (o enrutar el tráfico uniformemente a través de cualquier otro medio a todos los Servidores de mediación de un grupo)

  - Aceptar tráfico de cualquier Servidor de mediación de un grupo de servidores

Puede utilizar el Microsoft Lync Server 2013, herramienta de planeación para evaluar si la combinación del Servidor de mediación con su grupo de servidores front-end puede administrar la carga. Si el entorno no cumple estos requisitos, deberá implementar un Grupo de servidores de mediación independiente.

## Consideraciones del sitio central y las sucursales

Los Servidores de mediación del sitio central se pueden usar para enrutar llamadas a puertas de enlace RTC o IP-PBX en las sucursales. Sin embargo, si implementa troncos SIP, deberá implementar un Servidor de mediación en el sitio donde termina cada tronco. Para que un Servidor de mediación del sitio central enrute las llamadas a una puerta de enlace RTC o IP-PBX en una sucursal, no es necesario usar desvío de medios. Sin embargo, si puede habilitar el desvío de medios y lo hace, se reducirá la latencia de la ruta de acceso a los medios y, por ello, mejorará la calidad de los medios, porque la ruta de acceso a los medios ya no estará obligada a seguir la ruta de acceso de señalización. El desvío de medios disminuirá también la carga de procesamiento del grupo de servidores.


> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con los IP-PBX de Cisco. La omisión de medios solo se permite con los productos y las versiones listados en Ingeniería completa para Microsoft Lync, en <A href="http://go.microsoft.com/fwlink/?linkid=268730%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268730&amp;clcid=0xC0A</A>.



Si se necesita resistencia en la sucursal, se debe implementar un Aplicación de sucursal con funciones de supervivencia o una combinación de Servidor front-end, Servidor de mediación y puerta de enlace en la sucursal. (Con la resistencia de las sucursales, se presupone que la presencia y las conferencias no son resistentes en el sitio). Para saber cómo planear la voz en las sucursales, consulte [Planificar la resistencia de voz en sitios de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

En las interacciones con un IP-PBX, si el IP-PBX no admite correctamente las interacciones iniciales de medios con las interacciones RFC 3960 y varios diálogos iniciales, puede recortarse el primer saludo de las llamadas entrantes del IP-PBX en los extremos de Lync. Este comportamiento puede agravarse si un Servidor de mediación del sitio central enruta llamadas a un IP-PBX en el que la ruta termina en una sucursal, porque se necesita más tiempo para que la señalización finalice. Si esto ocurre, la única forma de reducir el recorte de las primeras palabras es implementar un Servidor de mediación en la sucursal.

Por último, si el sitio central tiene un PBX TDM, o si el IP-PBX no evita la necesidad de una puerta de enlace RTC, deberá implementar una puerta de enlace en la ruta de la llamada para conectar el Servidor de mediación y el PBX.


> [!NOTE]
> Para mejorar el rendimiento de medios del Servidor de mediación independiente, deberá poder habilitar la Escalabilidad de tráfico de entrada (RSS) en los adaptadores de red en estos servidores. La RSS permite que los paquetes entrantes estén administrados por varios procesadores en el servidor. Para obtener detalles, vea "Mejoras en la escalabilidad de tráfico de entrada en Windows Server" en <A href="http://go.microsoft.com/fwlink/?linkid=268731%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=268731&amp;clcid=0xC0A</A>. Para obtener información detallada sobre cómo habilitar RSS, vea la documentación de su adaptador de red.


