---
title: 'Lync Server 2013: pautas de implementación para el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400f8cceeb86d407297b3f564c01266a477ca0ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Instrucciones de implementación para el servidor de mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-12_

En este tema se describen las directrices de planeación para la implementación de Media Server. Después de revisar estas instrucciones, le recomendamos que use la herramienta de planeación para crear y ver posibles topologías alternativas, que pueden servir como modelos para el aspecto de la topología final personalizada que decida implementar.

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediación colocada o independiente?

De forma predeterminada, el servidor de mediación se encuentra en el servidor Standard Edition o en el servidor front-end de un grupo front-end en los sitios centrales. La cantidad de llamadas por la red telefónica conmutada (RTC) que se pueden gestionar y la cantidad de equipos necesarios en el grupo dependerán de los siguientes factores:

  - El número de puertas de enlace o gateways controladas por el grupo de servidores de mediación

  - Los períodos de gran tráfico de esas puertas de enlace

  - El porcentaje de llamadas que son llamadas cuyos medios omiten el servidor de mediación

Al planificar, asegúrate de tener en cuenta los requisitos de procesamiento de medios para las llamadas RTC y las conferencias de A/V no configuradas para la omisión de medios, además del procesamiento necesario para gestionar las interacciones de señalización para la cantidad de llamadas que es necesario admitir en las horas de más actividad. Si no hay suficiente CPU, debe implementar un grupo independiente de servidores de mediación; y las puertas de enlace RTC, IP-PBX y SBCs deberán dividirse en subconjuntos que se controlan mediante servidores de mediación en un mismo grupo y los servidores de mediación independientes en uno o más grupos de servidores independientes.

Si ha implementado puertas de enlace RTC, IP-PBX o controladores de borde de sesión (SBCs) que no son compatibles con las funciones correctas para interactuar con un grupo de servidores de mediación, entre los que se incluyen los siguientes, deberán asociarse con un conjunto independiente que contenga de un solo servidor de mediación:

  - Realizar el equilibrio de carga del sistema de nombres de dominio (DNS) de nivel de red en los servidores de mediación de un grupo (o bien enrutar el tráfico uniformemente a todos los servidores de mediación de un grupo)

  - Aceptar el tráfico de cualquier servidor de mediación de un grupo

Puede usar la herramienta de planeación de Microsoft Lync Server 2013, para evaluar si collocating el servidor de mediación con el grupo de servidores front-end puede controlar la carga. Si su entorno no puede cumplir estos requisitos, debe implementar un grupo de servidores de mediación independiente.

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>Consideraciones del sitio central y del sitio de sucursal

Los servidores de mediación del sitio central se pueden usar para enrutar llamadas para IP-PBX o puertas de enlace RTC en sitios de sucursales. Sin embargo, si implementas los troncos SIP, debes implementar un servidor de mediación en el sitio en el que termina cada tronco. Tener un servidor de mediación en el sitio central las llamadas a una puerta de enlace IP o RTC en un sitio de sucursal no requieren el uso de la omisión de medios. Sin embargo, si puede habilitar la omisión de medios, esta acción reducirá la latencia de la ruta multimedia y, por consiguiente, dará como resultado una mejor calidad de contenido multimedia porque la ruta multimedia ya no es necesaria para seguir la ruta de señalización. La omisión de medios también reducirá la carga de procesamiento del grupo.

<div>


> [!NOTE]  
> La omisión de medios no interactuará con todas las puertas de enlace RTC, las IP-PBX y los SBC. Microsoft ha probado una serie de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con las IP-PBX de Cisco. La omisión de elementos multimedia solo se admite con productos y versiones que se incluyen en el programa de interoperabilidad abierto de comunicaciones unificadas: Lync Server en <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>.



</div>

Si se requiere resistencia al sitio de la sucursal, se debe implementar en el sitio de la sucursal un dispositivo de aplicación de media o una combinación de un servidor front-end, un servidor de mediación y una combinación. (La hipótesis con la resistencia de los sitios de las sucursales es que la presencia y las conferencias no son resistentes en el sitio). Para obtener instrucciones sobre el planeamiento de sitios de sucursal para voz, vea [planear la resistencia de voz de un sitio de sucursal en Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

En el caso de interacciones con un IP-PBX, si el IP-PBX no es compatible con las interacciones de medios iniciales con varios cuadros de diálogo y interacciones de RFC 3960, puede recortar las primeras palabras del saludo para las llamadas entrantes desde el IP-PBX a los puntos de conexión de Lync. Este comportamiento puede ser más grave si un servidor de mediación de un sitio central está enrutando las llamadas a un IP-PBX donde la ruta termina en un sitio de sucursal, porque se necesita más tiempo para que se complete la señalización. Si experimenta este comportamiento, implementar un servidor de mediación en el sitio de la sucursal es la única forma de reducir el recorte de las primeras palabras.

Por último, si su sitio central tiene un sistema PBX con TDM, o si su IP-PBX no elimina la necesidad de una puerta de enlace RTC, debe implementar una puerta de enlace en la ruta de llamada y en el servidor PBX.

<div>


> [!NOTE]  
> Para mejorar el rendimiento de medios del servidor de mediación independiente, es necesario habilitar el ajuste de escala en lado de recepción (RSS) en los adaptadores de red de estos servidores. RSS permite que los paquetes entrantes se administren en paralelo por varios procesadores en el servidor. Para obtener más información, vea "mejoras en la escala de recepción en Windows Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>" en. Para más información sobre cómo habilitar RSS, vea la documentación de su adaptador de red.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

