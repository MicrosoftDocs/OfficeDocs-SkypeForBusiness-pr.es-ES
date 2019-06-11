---
title: 'Lync Server 2013: Directivas de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1e72a1b62a224898d98aec7fcef9bc62ddf8bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a>Directivas de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

*Las directivas de voz* de Lync Server definen lo siguiente para cada usuario, sitio u organización a la que se asigna la Directiva:

  - Un conjunto de características de llamadas que se pueden habilitar o deshabilitar para determinar la funcionalidad de telefonía IP empresarial disponible para los usuarios.

  - Un conjunto de registros de uso de la red telefónica conmutada (RTC) que definen qué tipo de llamadas están autorizadas.

<div>

## <a name="planning-for-voice-policies"></a>Planificación de directivas de voz

Los pasos siguientes le ayudarán a planear las directivas de voz que necesitará para su implementación de telefonía IP empresarial:

  - Determina cómo configurarás la directiva de voz global (la directiva de voz predeterminada que se instala con el producto). Esta Directiva se aplicará a todos los usuarios de telefonía de telefonía empresarial a los que no se les haya asignado explícitamente una directiva de sitio o usuario.

  - Identifica cualquier directiva de voz de sitio que puedas necesitar.

  - Identifica cualquier directiva de voz de usuario que puedas necesitar.

  - Decide qué características de llamada deseas habilitar para cada directiva de voz.

  - Determina qué registros de uso de RTC deseas configurar para cada directiva de voz.

<div>

## <a name="voice-policy-scope"></a>Ámbito de directiva de voz

El *ámbito de directiva de voz* determina el nivel jerárquico en el que se puede aplicar la directiva. En Lync Server, puede configurar directivas de voz con los siguientes niveles de ámbito (enumerados de la más específica a la más general).

  - La **directiva de voz de usuario** se puede asignar a usuarios, grupos u objetos de contacto individuales. Es la directiva de nivel más bajo. Las directivas de voz de usuario se pueden implementar para habilitar características para usuarios y grupos determinados en un sitio, pero no para otros en el mismo sitio. Por ejemplo, puedes deshabilitar las llamadas de larga distancia para algunos empleados. Con el fin de asignar una directiva de voz, un objeto de contacto se considera un usuario individual.
    
    <div>
    

    > [!NOTE]  
    > Le recomendamos que implemente una directiva de voz de usuario para los usuarios de la empresa de voz de un sitio de sucursal que estén registrados en la implementación de sitio central o los usuarios que estén registrados en un dispositivo de sucursal con la supervivencia.

    
    </div>

  - La **directiva de voz de sitio** se aplica a todo un sitio, excepto para los usuarios, grupos u objetos de contacto a los que se ha asignado una directiva de voz de usuario. Para definir una directiva de voz de sitio, necesitas especificar el sitio al que se aplica la directiva. Si no se asignó una directiva de voz de usuario, se usa la directiva de voz de sitio.

  - La **directiva de voz global** es la directiva de voz predeterminada que se instala con el producto. Puedes editar la directiva de voz global para cumplir las necesidades específicas de tu organización, pero no puedes cambiar su nombre ni eliminarla. Esta directiva de voz se aplica a todos los usuarios, grupos y objetos de contacto de Enterprise Voice de su implementación, a menos que configure y asigne una directiva de voz con un ámbito más específico. Si deseas deshabilitar esta directiva en su totalidad, asegúrate de que todos los sitios y todos los usuarios tengan asignadas directivas personalizadas.

</div>

<div>

## <a name="call-features"></a>Características de llamada

Puedes habilitar o deshabilitar las siguientes características de llamada para cada directiva de voz:

  - El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Está habilitado de forma predeterminada.

  - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. Está habilitada de forma predeterminada.

  - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está habilitada de forma predeterminada.

  - El **estacionamiento de llamadas** permite a los usuarios estacionar llamadas y atenderlas en otro teléfono o cliente. Está deshabilitado de forma predeterminada.

  - La característica de **llamadas simultáneas** permite que las llamadas entrantes suenen en un teléfono adicional (por ejemplo, un móvil) u otros dispositivos de extremo. Está habilitada de forma predeterminada.

  - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Está habilitada de forma predeterminada.

  - El **desvío de RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan desviar en la red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Está habilitado de forma predeterminada.

  - El **reemplazo de directiva de ancho de banda** permite a los administradores cambiar las decisiones de la directiva del servicio de control de admisión de llamadas para un usuario en concreto. Está deshabilitado de forma predeterminada.

  - El **seguimiento de llamadas** malintencionadas permite a los usuarios denunciar llamadas malintencionadas mediante el cliente de Lync y, a continuación, marca dichas llamadas en los registros de detalles de llamadas. Está deshabilitado de forma predeterminada.

  - El **escape en correo de voz** impide que las llamadas se redirijan de inmediato al sistema de correo de voz del teléfono móvil del usuario cuando se configura la característica de llamadas simultáneas y el teléfono está apagado, sin batería o fuera del alcance, y se basa en un valor del temporizador. Esta configuración habilita y deshabilita el temporizador, y establece su valor. Solo se puede configurar mediante el shell de administración de Lync Server. Está deshabilitado de forma predeterminada.

  - El **desvío de llamadas y los usos de RTC** de llamadas simultáneas permite a los administradores especificar el mismo uso de la RTC que la Directiva de voz para el desvío de llamadas y las llamadas simultáneas, restringir el desvío de llamadas y las llamadas simultáneas solo a usuarios internos de Lync. o especifique un uso de RTC personalizado que sea diferente del uso de RTC de la Directiva de voz. La opción predeterminada es usar el mismo uso de RTC que la directiva de voz para el desvío de llamadas y las llamadas simultáneas.

</div>

<div>

## <a name="pstn-usage-records"></a>Registros de uso de RTC

Cada directiva de voz necesita tener uno o más registros de uso de RTC asociados. Los usos de RTC se pueden asociar a una directiva de voz únicamente para las llamadas simultáneas y el desvío de llamadas. Para obtener más información sobre la planificación de registros de uso de RTC, consulte [registros de uso de RTC en Lync Server 2013](lync-server-2013-pstn-usage-records.md).

<div>


> [!NOTE]  
> El orden de los usos de RTC es fundamental ya que, al asociar usuarios a rutas, la función de enrutamiento saliente compara los usos de RTC desde el principio hasta el final. Si el primer uso coincide con la ruta de la llamada, se usa la ruta. En caso contrario, la función de enrutamiento saliente pasa al siguiente uso de RTC de la lista y sigue así hasta que encuentra alguna coincidencia. De hecho, los usos de RTC siguientes se usan a modo de copia de seguridad si el primero de la lista no está disponible.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

