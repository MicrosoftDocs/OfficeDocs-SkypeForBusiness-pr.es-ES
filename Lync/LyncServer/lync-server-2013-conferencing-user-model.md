---
title: El modelo de usuario de conferencias
TOCTitle: El modelo de usuario de conferencias
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48276492
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# El modelo de usuario de conferencias

 

_**Última modificación del tema:** 2012-10-22_

Una parte esencial del modelo de usuario de conferencia de Lync Server es el tamaño de las reuniones. Después de recopilar datos de varios puntos de datos (conforme a lo descrito en la sección anterior), se puede determinar lo siguiente:

  - La mayoría de las reuniones son reuniones de colaboración pequeñas, con una media de cuatro a seis participantes.

  - Aproximadamente, el 80 % de las reuniones tienen menos de 20 participantes.

  - El 99,98 % de las reuniones tienen menos de 100 participantes.

Además del tamaño de la reunión, el modelo de usuario de conferencia también tiene en cuenta otros factores, como:

  - **Reuniones simultáneas**   ¿Cuántos usuarios se prevé que asistirán simultáneamente a la reunión?

  - **Combinación de medios**   ¿Qué tipos de medios se encuentran disponibles y se espera que usen los usuarios en la reuniones?

  - **Tipos de usuarios**   ¿Se trata de usuarios internos, remotos, federados o anónimos?

  - **Tiempo de incorporación a la reunión**   ¿Cuánto tiempo necesitan todos los usuarios de una reunión para unirse a la misma?

Para más información sobre el modelo de usuario, consulte [Modelos de usuario en Lync Server 2013](lync-server-2013-user-models.md).

Para determinar el número de reuniones y usuarios que debían usarse en la prueba, hicimos lo siguiente:

  - Tomamos el número total de usuarios de una organización (por ejemplo 80.000 usuarios) y lo multiplicamos por el índice de simultaneidad de reuniones (por ejemplo, el 5 % de todos los usuarios) para determinar el número total de usuarios previstos en las reuniones de forma simultánea (en este ejemplo, 4.000 usuarios).

  - Dividimos el número total de usuarios entre el número de Lync Server 2013, Servidores front-end en la implementación (por ejemplo, 8 servidores), para determinar el número estimado de participantes en las reuniones por Servidor front-end (en este ejemplo, 500 usuarios por Servidor front-end).

  - Dividimos el número de usuarios por Servidor front-end entre el tamaño medio de reunión (por ejemplo, 4 usuarios) para determinar la media estimada de reuniones por Servidor front-end (en este ejemplo, 125 reuniones por Servidor front-end).

  - Para obtener la carga media en cada Servidor front-end, calculamos la combinación de medios. Por ejemplo, suponiendo que el 75 % de las reuniones requieren más que la simple compatibilidad con audio, y que el 50 % de estas reuniones requieren el uso compartido de aplicaciones, una media de 47 reuniones y 188 usuarios se conectarían simultáneamente a cada Servidor front-end para realizar un uso compartido de las aplicaciones.

  - Probamos diversos tamaños de reunión (sobre la base de nuestro modelo de usuario, de hasta 250 usuarios en un grupo compartido) para asegurar la escalabilidad de los servidores.

