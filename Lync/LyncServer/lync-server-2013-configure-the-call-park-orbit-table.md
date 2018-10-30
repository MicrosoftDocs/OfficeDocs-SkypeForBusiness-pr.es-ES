---
title: 'Lync Server 2013: Configurar la tabla de órbitas de estacionamiento de llamadas'
TOCTitle: Configurar la tabla de órbitas de estacionamiento de llamadas
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48277003
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la tabla de órbitas de estacionamiento de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-10_

El Estacionamiento de llamadas usa órbitas para estacionar las llamadas. Para que los usuarios puedan estacionar y recuperar llamadas, debe configurar la tabla de órbitas del Estacionamiento de llamadas. Deberá especificar los intervalos de números de extensión (órbitas) que la organización reservará para estacionar llamadas y definir el enrutamiento para dichos intervalos especificando qué grupo de servidores del Estacionamiento de llamadas administra cada intervalo. A la hora de definir intervalos de órbitas, el objetivo es tener una cantidad suficiente de órbitas, de modo que ninguna de las órbitas vuelva a usarse en seguida, pero tampoco se deben tener demasiadas órbitas porque esto limitaría el número de extensiones disponibles para los usuarios u otros servicios. Puede crear varios intervalos de órbitas del Estacionamiento de llamadas para cada grupo de servidores de Lync Server donde se implemente el Aplicación de estacionamiento de llamadas. Cada intervalo de órbitas del Estacionamiento de llamadas debe tener un nombre único de forma global, además de un conjunto de extensiones único.

> [!IMPORTANT]  
> Un intervalo de órbitas suele estar formado por 100 órbitas o menos, pero puede ser mucho mayor, siempre que tenga menos de 10.000 órbitas (número máximo) por intervalo y que usted tenga menos de 50.000 órbitas por grupo de servidores. Si un intervalo es demasiado pequeño, las órbitas se volverán a usar con mayor rapidez.



Use bloques de extensiones virtuales (extensiones que no tengan asignado ningún usuario ni teléfono) para los intervalos de órbitas.


> [!NOTE]
> En la tabla de órbitas de Estacionamiento de llamadas no se pueden asignar números de llamada directa a la extensión (DID) como números de órbita.



## En esta sección

[Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

