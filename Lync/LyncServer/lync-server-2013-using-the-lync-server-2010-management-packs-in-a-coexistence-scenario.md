---
title: Uso de los paquetes de administración de Lync Server 2010 en un escenario de coexistencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc2aed62b9ad26fd1498787ecd3d58144a005b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Uso de los paquetes de administración de Lync Server 2010 en un escenario de coexistencia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Muchos clientes adoptan un programa de implementación dentro de sus empresas en el que los usuarios se migran progresivamente desde Microsoft Lync Server 2010 a Lync Server 2013. Los administradores de estas empresas le interesarán la supervisión de ambas versiones de Lync Server para ayudar a garantizar que todos sus usuarios finales obtengan la mejor experiencia de comunicación posible. Para este escenario, el módulo de administración de Lync Server 2013 admite una ruta de migración en paralelo con el módulo de administración de Lync Server 2010.

En Lync Server 2010, los equipos con Lync Server se detectaron a través del documento de topología almacenado con el almacén de administración central. En esta configuración, un único equipo notificaría la existencia de todos los demás equipos de Lync Server.

Los paquetes de administración de Lync Server 2013 ahora usan la detección en el nivel de equipo en lugar del mecanismo de detección central que se usó en Lync Server 2010. Por ello, cada agente de System Center, básicamente, se detecta a sí mismo e informa de su existencia a System Center Operations Manager. El uso de la detección en el nivel de máquina simplifica la administración de la infraestructura de System Center y también habilita distintas versiones de los paquetes de administración de Lync Server (por ejemplo, módulos de administración para Lync Server 2010 y paquetes de administración para Lync Server 2013) coexistir más fácilmente.

Para admitir esta migración, primero tendrá que actualizar la supervisión de Lync Server 2010 existente para evitar brechas en la cobertura. Para ello, elija un equipo de Lync Server 2010 existente para que servicio el script de detección central de Lync Server 2010 antes de actualizar el almacén de administración central a Lync Server 2013. Este proceso tiene cuatro pasos:

1.  Actualice los paquetes de administración de Lync Server 2010 a la actualización acumulativa 7.

2.  Indique a un equipo de Lync Server 2010 que ejecute el script de detección central.

3.  Invalide el candidato de detección central en el módulo de administración de Microsoft Lync Server 2010.

4.  Compruebe que se ha detectado el nuevo candidato de detección central.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Ordenar a un equipo de Lync Server 2010 que ejecute el script de detección central

Para designar un equipo que no sea el almacén de administración central (por ejemplo, un servidor front-end de Lync Server) que controle la detección central, deberá crear la siguiente clave del registro en el servidor no central de almacenamiento de administración:

Software\\\\HKLM CentralDiscoveryCandidate\\de estado\\de comunicaciones\\en tiempo real de Microsoft

Puede crear esta clave del Registro llevando a cabo el siguiente procedimiento:

1.  Haga clic en **Inicio** y, a continuación, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.

3.  En el editor del registro, expanda el **\_equipo local\_HKEY**, expanda **software**, expanda **Microsoft**y, a continuación, expanda **comunicaciones en tiempo real**.

4.  Haga clic con el botón secundario en **Health**, haga clic en **Nuevo** y, después, haga clic en **Clave**. Si no existe la clave **Health**, haga clic con el botón secundario en **Real-Time Communications**, elija **Nuevo** y, luego, haga clic en **Clave**. Cuando se haya creado la nueva clave, escriba Health y presione ENTRAR.
    
    Después de que se haya creado la nueva clave, escriba **CentralDiscoveryCandidate** y presione ENTRAR para cambiar el nombre de la clave.

El equipo puede tardar varias horas en adoptar este cambio. Para que el cambio se aplique de inmediato, detenga el servicio Agente de mantenimiento y reinícielo. Para reiniciar el servicio de agente de mantenimiento, complete el siguiente procedimiento en el equipo con Lync Server 2010:

1.  Haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.

2.  En la ventana de la consola, escriba el siguiente comando y presione ENTRAR:
    
        Net stop HealthService

3.  Verá el siguiente mensaje: "El servicio de administración de System Center se está deteniendo", seguido de un segundo mensaje para informarle de que el servicio se ha detenido. Después de que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando ENTRAR:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Invalidación del candidato de detección central del módulo de administración de Lync Server 2010

Después de indicar a un equipo de Lync Server 2010 que informe sobre los equipos de Lync Server 2010, deberá informar también al módulo de administración de Lync Server 2010 sobre este cambio. Para ello, tendrá que crear una invalidación en el módulo de administración. Se puede hacer siguiendo este procedimiento:

1.  En la consola de Operations Manager, haga clic en **Creación**.

2.  En la pestaña Creación, expanda **Objetos del módulo de administración**, haga clic en **Detecciones de objetos** y, después, haga clic en **Ámbito**.

3.  En el cuadro de diálogo **Objetos de módulo de administración de ámbito**, seleccione el elemento que tenga el **candidato de detección de LS** de destino y, a continuación, haga clic en **Aceptar**. Tenga en cuenta que LS Discovery Candidate solo aparecerá si ha instalado el módulo de administración de Lync Server 2010.

4.  En la consola de Operations Manager, haga clic con el botón secundario en **Candidato de detección de LS**, elija **Invalidaciones**, elija **Invalidar la detección de objetos** y, luego, haga clic en **Para todos los objetos de la clase: candidato de detección de LS**.

5.  En el cuadro de diálogo **Propiedades de invalidación**, active la casilla **Invalidar** que hay junto al parámetro **Fqdn de WatcherNode de detección central**. Escriba el nombre de dominio completo del equipo de Lync Server 2010 en los cuadros **valor de reemplazo** y **valor efectivo** . Active la casilla **Aplicado** y haga clic en **Aceptar**.

Una vez haya creado la invalidación, debe reiniciar el servicio de mantenimiento del Servidor de administración raíz. Para reiniciar el servicio de mantenimiento, lleve a cabo el siguiente procedimiento en el Servidor de administración raíz:

1.  Haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.

2.  En la ventana de la consola, escriba el siguiente comando y presione ENTRAR:
    
        Net stop HealthService

3.  Verá el siguiente mensaje: "El servicio de administración de System Center se está deteniendo", seguido de un segundo mensaje para informarle de que el servicio se ha detenido. Después de que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando ENTRAR:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Comprobar que se detectó el nuevo candidato de detección central

El último paso antes de actualizar el almacén de administración central es asegurarse de que el módulo de administración de Lync Server 2010 detectó el nuevo candidato de detección central. Para ello, abra la consola de Operations Manager y haga clic en Supervisión. En la pestaña Supervisión, expanda **Mantenimiento de Microsoft Lync Server 2010**, expanda **Detección de topologías** y, a continuación, haga clic en **Vista de estado de detección**. Compruebe que una fila de la pantalla tiene una **Ruta** con el nombre de dominio completo del candidato de detección central. También debe comprobar que el estado del equipo es **Correcto**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

