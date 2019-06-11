---
title: Usar los paquetes de administración de Lync Server 2010 en un escenario de coexistencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Usar los paquetes de administración de Lync Server 2010 en un escenario de coexistencia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Muchos clientes adoptan un programa de implementación dentro de sus empresas en el que los usuarios se migran progresivamente desde Microsoft Lync Server 2010 a Lync Server 2013. Los administradores de estas empresas se interesan en la supervisión de ambas versiones de Lync Server para garantizar que todos los usuarios finales obtengan la mejor experiencia de comunicación posible. Para este escenario, el paquete de administración de Lync Server 2013 admite una ruta de migración en paralelo con el módulo de administración de Lync Server 2010.

En Lync Server 2010, los equipos de Lync Server se detectaron a través del documento de topología almacenado con el almacén central de administración. En esta configuración, un único equipo notificaría la existencia de todos los demás equipos de Lync Server.

Los módulos de administración para Lync Server 2013 ahora usan la detección a nivel de equipo en lugar del mecanismo de detección central que se usó en Lync Server 2010. Esto significa que cada agente de System Center se descubre por sí mismo e informa de su existencia en System Center Operations Manager. El uso de detección en el nivel de equipo simplifica la administración de la infraestructura de System Center y también permite diferentes versiones de los paquetes de administración de Lync Server (por ejemplo, módulos de administración para Lync Server 2010 y paquetes de administración para Lync Server 2013) coexistir más fácilmente.

Para admitir esta migración, primero deberá actualizar la supervisión de Lync Server 2010 existente para evitar lagunas en la cobertura. Para ello, elija un equipo de Lync Server 2010 existente para que sea servicio del script de detección central de Lync Server 2010 antes de actualizar su almacén de administración central a Lync Server 2013. Este es un proceso de cuatro pasos:

1.  Actualice los paquetes de administración de Lync Server 2010 a la actualización acumulativa 7.

2.  Indique a un equipo de Lync Server 2010 que ejecute el script de detección central.

3.  Invalide el candidato de detección central en el módulo de administración de Microsoft Lync Server 2010.

4.  Compruebe que se ha descubierto el nuevo candidato de detección central.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Instrucciones para que un equipo de Lync Server 2010 ejecute el script de detección central

Para designar un equipo de almacenamiento de administración no central (por ejemplo, un servidor front-end de Lync Server) para controlar la detección centralizada, tendrá que crear la siguiente clave de registro en el servidor de almacenamiento de administración no central:

Software\\\\HKLM CentralDiscoveryCandidate\\de salud\\de las\\comunicaciones en tiempo real de Microsoft

Puede crear esta clave del registro completando el procedimiento siguiente:

1.  Haga clic en **Inicio** y, después, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar** , **** escriba regedit y, a continuación, presione Entrar.

3.  En el editor del registro, expanda el **\_equipo local\_HKEY**, expanda **software**, expanda **Microsoft**y, a continuación, expanda **comunicaciones en tiempo real**.

4.  Haga clic con el botón derecho en **mantenimiento**, seleccione **nuevo**y, a continuación, haga clic en **clave**. Si la clave de **Estado** no existe, haga clic con el botón secundario en **comunicaciones en tiempo real**, seleccione **nuevo**y, a continuación, haga clic en **clave**. Cuando se cree la nueva clave, escriba Health y, a continuación, presione Entrar.
    
    Una vez creada la nueva clave, escriba **CentralDiscoveryCandidate** y, a continuación, presione Entrar para cambiar el nombre de la clave.

Es posible que tarde el equipo varias horas en detectar este cambio. Para que el cambio surta efecto inmediatamente, detenga y reinicie el servicio de agente de estado. Para reiniciar el servicio agente de estado, complete el procedimiento siguiente en el equipo con Lync Server 2010:

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, haga clic con el botón derecho en **símbolo del sistema**y, a continuación, haga clic en **Ejecutar como administrador**.

2.  En la ventana de consola, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
        Net stop HealthService

3.  Verá un mensaje que indica "el servicio de administración de System Center se está deteniendo" seguido de un segundo mensaje que le indica que el servicio se ha detenido. Una vez que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando entrar:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Reemplazar el candidato de detección central en el módulo de administración de Lync Server 2010

Después de indicar a un equipo de Lync Server 2010 que informe sobre los equipos de Lync Server 2010, tendrá que informar también al módulo de administración de Lync Server 2010. Para ello, tendrá que crear un reemplazo en el módulo de administración. Esto se puede realizar mediante el siguiente procedimiento:

1.  En la consola de Operations Manager, haga clic en **creación**.

2.  En la pestaña creación, expanda **objetos del módulo de administración**, haga clic en descubrimientos de **objetos**y, a continuación, haga clic en **ámbito**.

3.  En el cuadro de diálogo **objetos del módulo de administración del ámbito** , seleccione el elemento con el candidato de detección de **LS** de destino y haga clic en **Aceptar**. Tenga en cuenta que el candidato de detección de LS solo aparecerá si ha instalado el módulo de administración de Lync Server 2010.

4.  En la consola de Operations Manager, haga clic con el botón secundario del **** mouse en la **detección de LS**, seleccione reemplazos, seleccione **invalidar la detección de objetos**y, a continuación, haga clic en **para todos los objetos de clase: candidato de detección de LS**.

5.  En el cuadro de diálogo **reemplazar propiedades** , seleccione **** la casilla invalidar situada junto al parámetro de **descubrimiento central WatcherNode FQDN**. Escriba el nombre de dominio completo del equipo de Lync Server 2010 en los cuadros **valor de reemplazo** y **valor efectivo** . Seleccione la **** casilla exigido y haga clic en **Aceptar**.

Una vez que haya creado el reemplazo, debe reiniciar el servicio de mantenimiento en el servidor de administración raíz. Para reiniciar el servicio de mantenimiento, complete el procedimiento siguiente en el servidor de administración raíz:

1.  Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, haga clic con el botón derecho en **símbolo del sistema**y, a continuación, haga clic en **Ejecutar como administrador**.

2.  En la ventana de consola, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
        Net stop HealthService

3.  Verá un mensaje en el que se indica que "el servicio de administración de System Center se está deteniendo" seguido de un segundo mensaje que le indica que el servicio se ha detenido. Después de que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando entrar:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Comprobar que se detectó el nuevo candidato de detección central

El paso final antes de actualizar el almacén de administración central es asegurarse de que el nuevo candidato de detección central fue descubierto por el módulo de administración de Lync Server 2010. Para ello, abra la consola de Operations Manager y, a continuación, haga clic en supervisión. En la pestaña supervisión, expanda **estado 2010 de Microsoft Lync Server**, expanda **descubrimiento de topología**y, a continuación, haga clic en **vista estado de detección**. Compruebe que una fila de la pantalla tiene una **ruta de acceso** que indica el nombre de dominio completo del candidato de detección central. También debe verificar que el estado del equipo sea **correcto**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

