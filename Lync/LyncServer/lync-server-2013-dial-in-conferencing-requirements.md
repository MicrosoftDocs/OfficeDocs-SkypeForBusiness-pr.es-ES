---
title: Requisitos de conferencia de acceso telefónico local de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Requisitos de las conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Antes de iniciar el proceso de implementación de Lync Server 2013, necesitará planear lo siguiente:

  - La configuración que se usa para conectarse a la red de telefonía pública conmutada (RTC)

  - Su estrategia para asignar regiones de conferencia de acceso telefónico local a los números de acceso telefónico local

  - Su estrategia para crear directorios de conferencia

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Planificación de la conectividad RTC de acceso telefónico local

Las conferencias de acceso telefónico local requieren al menos un servidor de mediación y una puerta de enlace PSTN como mínimo.

Puede implementar un servidor de mediación en un sitio central o en un sitio de sucursal. En un sitio central, puede instalar un servidor de mediación en un grupo de servidores front-end o en un servidor Standard Edition, o bien puede implementarlo en un servidor o en un grupo de servidores independiente. En un sitio de sucursal, puede implementar un servidor de mediación en un servidor independiente o como componente de la aplicación de sucursal con funciones de supervivencia.

Puede implementar una puerta de enlace RTC en un sitio central o en un sitio de sucursal. En un sitio de sucursal, la puerta de enlace RTC puede ser independiente o un componente de la aplicación de sucursal con funciones de supervivencia.

<div>


> [!NOTE]  
> Las conferencias de acceso telefónico local no usan la omisión de medios porque el servidor de conferencia A/V no admite la omisión de medios.



</div>

Para obtener detalles sobre el planeamiento de la configuración del servidor de mediación y de las puertas de enlace RTC para conferencias de acceso telefónico local, vea [componentes y topologías de servidor de mediación en Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación de planeación.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Planificación de regiones de conferencia de acceso telefónico local

Durante la configuración de acceso telefónico, puede crear planes de marcado y números de acceso a la Conferencia de acceso telefónico local. Los planes de marcado son conjuntos de reglas de normalización que especifican el número y el patrón de dígitos en un número de teléfono y traducen el número de teléfono en el formato estándar E. 164 para el enrutamiento de llamadas. Los números de acceso a conferencias de acceso telefónico local son números a los que pueden llamar los usuarios para participar en una conferencia.

Cada número de acceso a conferencias de acceso telefónico local necesita estar asociado por lo menos con un plan de marcado. Las regiones de conferencias de acceso telefónico local asocian un número de acceso de conferencia de acceso telefónico local a sus planes de marcado. Al configurar un plan de marcado, se especifica la región de conferencia de acceso telefónico local que se aplica al plan de marcado. Cuando crea el número de acceso telefónico local, selecciona las regiones que asocian el número de acceso con los planes de marcado pertinentes.

Al crear un plan de marcado, debe especificar el ámbito del plan de marcado: ámbito de usuario, ámbito del grupo o ámbito del sitio. A cada usuario se le asigna el plan de marcado correspondiente al ámbito más limitado que se aplica al usuario. Por ejemplo, se asigna a un usuario un plan de marcado de nivel de usuario, si procede. Si no tiene aplicado ningún plan de marcado de nivel de usuario, se le asignará un plan de marcado de nivel de grupo de servidores. Si no tiene aplicado ningún plan de marcado de nivel de grupo de servidores, se le asignará un plan de marcado de nivel de sitio. Si no tiene aplicado ningún plan de marcado de nivel de sitio, se le asignará el plan de marcado global.

Antes de configurar los planes de marcado, es importante planear qué nombres desea aplicar a las regiones y cómo desea usarlas. Las consideraciones siguientes necesitan aplicarse a las regiones de conferencia de acceso telefónico local:

  - Una región es, por lo general, un área geográfica asociada con una oficina o con un grupo de oficinas.

  - Los números de acceso telefónico local están asociados a idiomas. Si admite áreas geográficas con varios idiomas, tendrá que decidir cómo desea definir las regiones para que admitan los diferentes idiomas. Por ejemplo, puede definir varias regiones según una combinación de zona geográfica e idioma, o bien puede definir una única región según la zona geográfica y tener números de acceso telefónico local distintos para cada idioma.

  - Cuando un usuario programa una reunión, de forma predeterminada la reunión usa la región especificada por el plan de marcado del usuario.

  - De forma predeterminada, todos los números de acceso telefónico local de la región están incluidos en la invitación a la reunión.

  - Es importante asignar un nombre a las regiones de modo que puedan reconocerse claramente. El usuario puede usar los nombres de las regiones para cambiar una región de una reunión de modo que los distintos números de acceso se incluyan en la invitación. (Cuando los usuarios usan Outlook para programar una reunión, el usuario usa el complemento de reunión en línea para Lync 2013 para cambiar la región).

  - Las regiones necesitan asignarse de tal modo que cualquier invitado que quiera obtener acceso a una conferencia pueda ver un número de acceso local en la invitación a la misma.

  - Puede configurar el orden en el que aparecen los números de acceso dentro de una región en la página Configuración de conferencia de acceso telefónico local (y, por tanto, el orden en el que aparecen en la invitación a la Conferencia) mediante los cmdlets del shell de administración de Lync Server.

  - Cualquier usuario puede llamar al número de acceso telefónico local que desee para unirse a una conferencia desde cualquier ubicación.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Planificación de directorios de conferencia

Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia al usar Lync 2013 y el identificador de conferencia de acceso telefónico local que usa un participante de conferencia de acceso telefónico local para unirse a la Conferencia. El formato del identificador de conferencia es el siguiente:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Con esta pauta, los identificadores de conferencia generalmente se mantienen reducidos. Ahora bien, una vez que entre los diferentes grupos de servidores haya más de 9 directorios de conferencia, el número de Id. de conferencia crecerá para facilitar la creación de nuevas conferencias.

</div>

<div>

## <a name="see-also"></a>Vea también


[Componente de servidor de mediación de Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

