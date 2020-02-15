---
title: 'Lync Server 2013: directrices de implementación para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0404590ab5b3208de989093df7ede55a3aee2f54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Instrucciones de implementación para el servidor de mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-12_

En este tema se describen las directrices de planeación para la implementación del servidor de mediación. Después de revisar estas instrucciones, le recomendamos que use la herramienta de planeación para crear y ver posibles topologías alternativas, que pueden servir como modelos para determinar el aspecto de la topología adaptada final que decida implementar.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediación combinado o independiente

El servidor de mediación se combina de forma predeterminada en el servidor Standard Edition o en el servidor front-end de un grupo de servidores front-end en los sitios centrales. El número de llamadas de red telefónica conmutada (RTC) que se pueden administrar y el número de máquinas necesarias en el grupo dependerá de lo siguiente:

  - El número de puertas de enlace del mismo nivel que controla el grupo de servidores de mediación

  - Los períodos de tráfico de gran volumen a través de estas puertas de enlace

  - El porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación

Al planear, asegúrese de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y las conferencias de A/V que no están configuradas para el desvío de medios, así como el procesamiento necesario para controlar las interacciones de señalización para el número de llamadas de horas no disponibles que deben admitirse. Si no hay suficiente CPU, debe implementar un grupo independiente de servidores de mediación; Además, las puertas de enlace RTC, las IP-PBX y los SBC deberán dividirse en subconjuntos controlados por los servidores de mediación combinados en un grupo y los servidores de mediación independientes en uno o más grupos de servidores independientes.

Si ha implementado puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBC) que no son compatibles con las funciones correctas para interactuar con un grupo de servidores de mediación, incluidos los siguientes, se deben asociar a un grupo independiente que consista de un servidor de mediación único:

  - Realizar el equilibrio de carga del sistema de nombres de dominio (DNS) de la capa de red en los servidores de mediación de un grupo (o enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo)

  - Aceptar tráfico de cualquier servidor de mediación de un grupo de servidores

Puede usar la herramienta de planeación 2013 de Microsoft Lync Server para evaluar si combinar el servidor de mediación con el grupo de servidores front-end puede controlar la carga. Si el entorno no cumple estos requisitos, deberá implementar un grupo de servidores de mediación independiente.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y las sucursales

Los servidores de mediación del sitio central se pueden usar para enrutar llamadas a puertas de enlace RTC o IP-PBX en las sucursales. Sin embargo, si implementa troncos SIP, deberá implementar un servidor de mediación en el sitio donde termina cada tronco. Para que un servidor de mediación del sitio central enrute las llamadas a una puerta de enlace RTC o IP-PBX en una sucursal, no es necesario usar desvío de medios. Sin embargo, si puede habilitar el desvío de medios y lo hace, se reducirá la latencia de la ruta de acceso a los medios y, por ello, mejorará la calidad de los medios, porque la ruta de acceso a los medios ya no estará obligada a seguir la ruta de acceso de señalización. El desvío de medios disminuirá también la carga de procesamiento del grupo de servidores.

<div>


> [!NOTE]  
> El desvío de medios no interactuará con todas las puertas de enlace RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierto de comunicaciones unificadas – Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.



</div>

Si se necesita resistencia en la sucursal, se debe implementar una aplicación de sucursal con funciones de supervivencia o una combinación de servidor front-end, servidor de mediación y puerta de enlace en la sucursal. (La hipótesis con resistencia de sitios de sucursal es que la presencia y la Conferencia no son resistentes en el sitio). Para obtener instrucciones sobre la planeación de sitios de sucursal para voz, vea [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

En el caso de las interacciones con un IP-PBX, si la IP-PBX no es compatible correctamente con interacciones de medios iniciales con varios cuadros de diálogo de RFC 3960 y con interacciones de RFC, puede haber un recorte de las primeras palabras del saludo para las llamadas entrantes desde los puntos de conexión de IP-PBX a Lync. Este suceso puede agravarse si un servidor de mediación del sitio central enruta llamadas a un IP-PBX en el que la ruta termina en una sucursal, porque se necesita más tiempo para que la señalización finalice. Si experimenta este comportamiento, la única forma de reducir el recorte de las primeras palabras es implementar un servidor de mediación en el sitio de sucursal.

Por último, si el sitio central tiene un PBX TDM, o si el IP-PBX no evita la necesidad de una puerta de enlace RTC, deberá implementar una puerta de enlace en la ruta de la llamada para conectar el servidor de mediación y el PBX.

<div>


> [!NOTE]  
> Para mejorar el rendimiento de medios de un servidor de mediación independiente, debe habilitar el ajuste de escala en el lado de recepción (RSS) en los adaptadores de red de estos servidores. El RSS permite administrar los paquetes entrantes en paralelo con varios procesadores del servidor. Para obtener más información, vea "mejoras en el ajuste de escala en lado de <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>recepción en Windows Server" en. Para obtener más información sobre cómo habilitar RSS, consulte la documentación de su adaptador de red.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

