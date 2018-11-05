---
title: 'Lync Server 2013: Directivas de voz'
TOCTitle: Directivas de voz
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48276458
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Directivas de voz en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

Las *directivas de voz* de Lync Server definen los siguientes elementos para cada usuario, sitio u organización a los que se asigna la directiva:

  - Un conjunto de características de llamada que se pueden habilitar o deshabilitar para determinar las funciones de Telefonía IP empresarial disponibles para los usuarios.

  - Un conjunto de registros de uso de la red telefónica conmutada (RTC) que definen qué tipo de llamadas están autorizadas.

## Planeación de directivas de voz

Los pasos siguientes lo ayudarán a planear las directivas de voz que necesitará para la implementación de Telefonía IP empresarial:

  - Determine cómo configurará la directiva de voz global (la directiva de voz predeterminada que se instala con el producto). Esta directiva se aplicará a todos los usuarios de Telefonía IP empresarial a los que no se ha asignado explícitamente una directiva de nivel de sitio o por usuario.

  - Identifique cualquier directiva de voz de nivel de sitio que pueda necesitar.

  - Identifique cualquier directiva de voz por usuario que pueda necesitar.

  - Decida qué características de llamada desea habilitar para cada directiva de voz.

  - Determine qué registros de uso de RTC desea configurar para cada directiva de voz.

## Ámbito de directiva de voz

El *ámbito de directiva de voz* determina el nivel jerárquico en el que se puede aplicar la directiva. En Lync Server, puede configurar directivas de voz con los niveles de ámbito siguientes (ordenados del más específico al más general).

  - La **directiva de voz de usuario** se puede asignar a usuarios, grupos u objetos de contacto individuales. Es la directiva de nivel más bajo. Las directivas de voz de usuario se pueden implementar para habilitar características para usuarios y grupos determinados en un sitio, pero no para otros en el mismo sitio. Por ejemplo, puede deshabilitar las llamadas de larga distancia para algunos empleados. Con el fin de asignar una directiva de voz, un objeto de contacto se considera un usuario individual.
    

    > [!NOTE]
    > Recomendamos implementar una directiva de voz de usuario para los usuarios de Telefonía IP empresarial de sitios de sucursal que estén registrados con la implementación del sitio central o para los usuarios que estén registrados en una aplicación de sucursal con funciones de supervivencia.



  - La **directiva de voz de sitio** se aplica a todo un sitio, excepto para los usuarios, grupos u objetos de contacto a los que se ha asignado una directiva de voz de usuario. Para definir una directiva de voz de sitio, debe especificar el sitio al que se aplica la directiva. Si no se asignó una directiva de voz de usuario, se usa la directiva de voz de sitio.

  - La **directiva de voz global** es la directiva de voz predeterminada que se instala con el producto. Puede modificar la directiva de voz global para cumplir las necesidades específicas de su organización, pero no puede cambiar su nombre ni eliminarla. Esta directiva de voz se aplica a todos los usuarios, grupos y objetos de contacto de Telefonía IP empresarial de la implementación, a menos que configure y asigne una directiva de voz con un ámbito más específico. Si desea deshabilitar esta directiva en su totalidad, compruebe que todos los sitios y usuarios tengan asignadas directivas personalizadas.

## Características de llamada

Puede habilitar o deshabilitar las siguientes características de llamada para cada directiva de voz:

  - El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente. Habilitado de forma predeterminada.

  - La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre. Habilitada de forma predeterminada.

  - La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Opción habilitada habitualmente.

  - El **estacionamiento de llamadas** permite a los usuarios estacionar llamadas y atenderlas en otro teléfono o cliente. Deshabilitado de forma predeterminada.

  - La característica de **llamadas simultáneas** permite que las llamadas entrantes suenen en un teléfono adicional (por ejemplo, un móvil) u otros dispositivos de extremo. Habilitada de forma predeterminada.

  - La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo. Opción habilitada habitualmente.

  - El **nuevo enrutamiento RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a enrutar en la red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Habilitado de forma predeterminada.

  - El **reemplazo de directiva de ancho de banda** permite a los administradores reemplazar las decisiones de la directiva de control de admisión de llamadas para un usuario concreto. Opción deshabilitada habitualmente.

  - El **seguimiento de llamadas malintencionadas** permite a los usuarios notificar las llamadas malintencionadas con el cliente de Lync y marca este tipo de llamadas en el registro detallado de llamadas. Deshabilitado de forma predeterminada.

  - El **escape de correo de voz** impide que las llamadas se enruten de inmediato al sistema de correo de voz del teléfono móvil del usuario cuando se configura la característica de llamadas simultáneas y el teléfono está apagado, sin batería o fuera del alcance, y se basa en un valor del temporizador. Esta opción habilita y deshabilita el temporizador, y establece su valor. Se puede configurar solamente con el Shell de administración de Lync Server. Deshabilitado de forma predeterminada.

  - La característica de **usos de RTC para desvío de llamadas y llamadas simultáneas** permite a los administradores especificar el mismo uso de RTC que la directiva de voz para el desvío de llamadas y las llamadas simultáneas, limitar el desvío de llamadas y las llamadas simultáneas a los usuarios internos de Lync únicamente o especificar un uso de RTC personalizado que sea diferente al uso de RTC de la directiva de voz. La opción predeterminada es usar el mismo uso de RTC que la directiva de voz para el desvío de llamadas y las llamadas simultáneas.

## Registros de uso de RTC

Cada directiva de voz debe tener uno o más registros de uso de RTC asociados. Los usos de RTC se pueden asociar a una directiva de voz únicamente para las llamadas simultáneas y el desvío de llamadas. Para más información sobre la planeación de registros de uso de RTC, vea [Registros de uso de RTC en Lync Server 2013](lync-server-2013-pstn-usage-records.md).


> [!NOTE]
> El orden de los usos de RTC es fundamental ya que, al asociar usuarios a rutas, la función de enrutamiento saliente compara los usos de RTC desde el principio hasta el final. Si el primer uso coincide con la ruta de la llamada, se usa la ruta. En caso contrario, la función de enrutamiento saliente pasa al siguiente uso de RTC de la lista y sigue así hasta que encuentra alguna coincidencia. De hecho, los usos de RTC siguientes se usan a modo de reserva si el primero de la lista no está disponible.


