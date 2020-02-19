---
title: 'Lync Server 2013: rutas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c328cc674461dae0fdce7833d7bef43c1f95dd8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42120083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a>Rutas de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes realizadas por los usuarios de telefonía IP empresarial. Cuando un usuario marca un número, el servidor front-end normaliza la cadena de marcado al formato E. 164, si es necesario, e intenta establecer una coincidencia con un URI de SIP. Si el servidor no puede realizar la coincidencia, aplica la lógica de enrutamiento de llamadas salientes en función del número. El último paso para definir la lógica es crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino que se enumeran en cada plan de marcado.

Antes de definir las rutas de llamadas salientes, debe completar los siguientes pasos:

  - Implementar uno o más troncos.

  - Crear planes de marcado según sea necesario para los sitios, los individuos y los objetos de contacto.

  - Crear registros de uso de la red telefónica conmutada (RTC).

Además, para habilitar el enrutamiento de llamadas salientes, debe crear y asignar una o más directivas de voz. Puede hacer esto ya sea antes o después de definir las rutas de llamadas salientes.

Para cada ruta, debe especificar:

  - Nombre por el que se puede identificar fácilmente la ruta.

  - Una descripción opcional en los casos en los que el nombre solo puede no ser suficiente para describir la ruta.

  - El patrón de coincidencia de expresión regular que identifica los números de teléfono de destino a los que se aplica la ruta, junto con las excepciones a las que no se aplica el patrón de coincidencia.

  - Uno o más troncos que desea asignar a la ruta.

  - Los registros de uso de RTC que los usuarios deben tener para llamar a los números que coinciden con la expresión regular del número de teléfono de destino.

Puede especificar rutas de llamadas en el panel de control de Lync Server. Estas rutas de llamadas rellenan la tabla de enrutamiento del servidor, que Lync Server usa para enrutar las llamadas dirigidas a la RTC.

<div>

## <a name="mn-trunk-support"></a>Compatibilidad con troncos M:N

Lync Server proporciona flexibilidad en la forma en que las llamadas se enrutan a la RTC. Una ruta de voz especifica un conjunto de troncos a la RTC que se pueden usar para una llamada de voz en particular. Un tronco asocia un servidor de mediación y un número de puerto con una puerta de enlace RTC y un número de puerto de escucha. Esta asociación lógica permite asociar un servidor de mediación con varias puertas de enlace y tener varias conexiones a la misma puerta de enlace. Al definir una ruta de llamada, se especifican los troncos asociados con dicha ruta, pero no se especifica qué servidores de mediación están asociados a la ruta. Para crear troncos mediante la definición de las relaciones entre los servidores de mediación y las puertas de enlace RTC, las IP-PBX y los controladores de borde de sesión (SBC), use el generador de topologías.

</div>

<div>

## <a name="least-cost-routing"></a>Enrutamiento de menor costo

La capacidad de especificar los troncos a los que se redirigen varios números le permite determinar qué rutas incurren en el menor costo y las implementan en consecuencia. La regla general en la selección de troncos es elegir el tronco con la puerta de enlace más cercana a la ubicación del número de destino con el fin de minimizar los gastos de larga distancia. Por ejemplo, si se encuentran en Nueva York y se llama a un número en Roma, se llevará a cabo la llamada a través de la red IP al tronco con la puerta de enlace en la oficina de la Roma, por lo que incurre en una carga solo para una llamada local.

Para obtener un ejemplo de cómo se puede usar el enrutamiento menos costoso, tenga en cuenta lo siguiente: fabrikam decide habilitar a los usuarios alemanes para marcar números de Estados Unidos mediante el tronco de Estados Unidos. Fabrikam también desea configurar el sistema para que todas las llamadas de los usuarios de Lync Server de Estados Unidos a Alemania y países o regiones adyacentes terminen en el tronco con la puerta de enlace en Alemania. Este enrutamiento ahorrará dinero, ya que una llamada de Alemania a Austria, por ejemplo, es menos costosa que una llamada de Estados Unidos a Austria.

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>Traducción de las cadenas de marcado salientes

Lync Server 2013, al igual que sus predecesoras inmediatas, requiere que todas las cadenas de marcado se puedan normalizar al formato E. 164 con el propósito de realizar la búsqueda inversa de números (RNL). Para los troncos con puertas de enlace o centrales de conmutación (PBX) que requieran números traducidos en formatos de marcado locales, Lync Server 2013 permite crear una o más reglas que ayuden a manipular el número llamado (es decir, el URI de solicitud) antes de enrutarlo al tronco. Por ejemplo, podría escribir una regla para quitar + 44 del encabezado de una cadena de marcado y reemplazarla por 0144.

Con Lync Server 2013, es posible crear una o más reglas que ayuden a manipular el número de llamada antes de enrutarlo al tronco.

En la planeación de los troncos que asocian puertas de enlace: pares de puertos con servidor de mediación: pares de puertos, puede ser útil agrupar los troncos con requisitos de marcado local similares y, por tanto, reducir el número de reglas de conversión necesarias y el tiempo que se tarda en escribirlas.

</div>

<div>

## <a name="configuring-caller-id"></a>Configuración del identificador de llamada

Lync Server proporciona una forma de manipular el identificador de llamada para las llamadas salientes. Por ejemplo, si una organización desea enmascarar las extensiones de marcado directo de los empleados y reemplazarlas por el número genérico Corporate o departamental, un administrador puede hacerlo mediante el panel de control de Lync Server para suprimir el identificador de llamada y reemplazarlo por un IDENTIFICADOR de llamada alternativo especificado. En planear la lógica de enrutamiento, tenga en cuenta qué individuos, grupos y sitios desea que tenga esta opción (quizá, incluso, para todos los empleados).

<div>


> [!NOTE]  
> Para las llamadas que se redirigen a través de la RTC, se presentará el identificador de llamada genérico en lugar del identificador de llamada original. Esto puede hacer que la llamada para omitir no moleste o la configuración de privacidad que el destinatario de la llamada haya configurado.



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>Lógica de enrutamiento adicional

Al crear rutas de llamadas salientes, debe tener en cuenta los siguientes factores que pueden afectar a la lógica de enrutamiento:

  - Cuando se establece una llamada a través de un límite federado, la parte de dominio del URI se usa para enrutar la llamada a la empresa que es responsable de aplicar la lógica de enrutamiento de salida.

  - Si la parte de dominio del URI de la solicitud no contiene un dominio compatible para la empresa, el componente de enrutamiento de salida en el servidor no procesa la llamada.

  - Si un usuario no está habilitado para telefonía IP empresarial, el servidor aplicará otra lógica de enrutamiento, según corresponda.

  - Si una llamada se redirige a una puerta de enlace que está completamente ocupada (todas las líneas troncales están ocupadas), la puerta de enlace rechaza la llamada y la lógica de enrutamiento de salida redirige la llamada a la siguiente-menos costosa ruta. Preste especial atención, ya que el tamaño de una puerta de enlace para una oficina pequeña del extranjero (por ejemplo, Zurich) puede llevar una cantidad importante de tráfico no local para las llamadas internacionales a Suiza. Si la puerta de enlace no tiene el tamaño correcto para este tráfico adicional, las llamadas a Suiza pueden enrutarse a través de una puerta de enlace en Alemania, lo que da como resultado mayores gastos de llamadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

