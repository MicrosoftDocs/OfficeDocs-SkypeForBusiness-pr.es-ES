---
title: 'Lync Server 2013: importación de los módulos de administración de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adaf9fe1c6d5d4cc0769810aece05bcb46681e79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importación de los paquetes de administración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de los paquetes de administración (software que determina qué elementos puede supervisar System Center Operations Manager) y cómo se deben supervisar esos elementos y cómo se deben desencadenar alertas y Enviado. Lync Server 2013 incluye dos paquetes de administración de System Center Operations Manager que proporcionan las siguientes capacidades:

  - El componente y el módulo de administración de usuarios (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en los registros de eventos, registrados por los contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o la calidad de la experiencia (QoE). bases. Para los problemas críticos, System Center Operations Manager se puede configurar para que notifique inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o servicio de mensajes cortos (SMS). SMS es la tecnología usada para enviar mensajes de texto desde un dispositivo móvil a otro).
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre cómo configurar la notificación de Operations Manager, vea la notificación <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>de configuración en la biblioteca de TechNet en.

    
    </div>

  - El módulo de administración de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) comprueba proactivamente los componentes clave de Lync Server, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en el conmutador público red telefónica (RTC). Estas pruebas se llevan a cabo con los cmdlets de transacciones sintéticas de Lync Server. Por ejemplo, puede usar el cmdlet **Test-CsIM** para simular una conversación por mensaje instantáneo (IM) entre un par de usuarios de prueba. Si esta conversación de mensajes simulados falla, se genera una alerta.

Debe importar los paquetes de administración. Si no importa los paquetes de administración, no puede usar Operations Manager para supervisar los eventos de Lync Server ni ejecutar transacciones sintéticas de Lync Server.

El módulo de administración de componentes y usuarios solo se usa para supervisar Lync Server 2013. Si está en un escenario de coexistencia, donde tiene instalados tanto Lync Server 2013 como Lync Server 2010, debe seguir usando los paquetes de administración de Lync Server 2010 para los equipos con Lync Server 2010.

<div>


> [!NOTE]  
> Los módulos de administración para Lync Server 2010 incluyen el módulo de administración de supervisión de Lync Server 2010 y el módulo de administración de supervisión de chat de grupo de Lync Server 2010.



</div>

Puede usar una de las siguientes herramientas para importar los paquetes de administración:

  - **System Center Operations Manager**   con este método, se usa Operations Manager para agregar supervisión para Lync Server.

  - **Shell de Operations Manager**   puede usar el shell de Operations Manager para importar directamente o para solucionar los problemas que se encuentren al importar módulos de administración mediante la consola de System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importación de los paquetes de administración mediante System Center Operations Manager

1.  Descargue los archivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  En System Center Operations Manager, haga clic en **Administración**.

3.  En el panel **Administración**, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.

4.  En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.

5.  En el cuadro de diálogo **conexión al catálogo en línea** , haga clic en **Cancelar** para evitar que Operations Manager se conecte para ver si existe alguna dependencia para los paquetes de administración de Lync Server. Si usa System Center Operations Manager 2012, haga clic en **no**.

6.  En el cuadro de diálogo **Seleccionar paquetes de administración a importar**, encuentre y seleccione los archivos **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** y **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** y luego haga clic en **Abrir**. para seleccionar varios archivos en el cuadro de diálogo haga clic en el primer archivo, mantenga presionada la tecla Ctrl y haga clic en el segundo archivo.

7.  En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. Si esto sucede, copie los archivos a una carpeta diferente y luego reinicie el proceso de importación e instalación.

8.  En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**. Tenga en cuenta que el proceso de instalación e importación puede requerir algunos minutos para completarse.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importación de paquetes de administración mediante el shell de Operations Manager

En general, es más fácil importar los paquetes de administración mediante Operations Manager. sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona los informes de error adecuados. Por comparación, el shell de Operations Manager proporciona información detallada. Si está usando Operations Manager y tiene problemas para importar un módulo de administración, importe el paquete mediante el shell de Operations Manager. El shell de Operations Manager proporciona más información que puede ayudarle a determinar por qué se produjo un error en la importación.

Si usa System Center Operations Manager 2007 R2, complete el siguiente procedimiento:

1.  Haga clic en **Inicio**, en **todos los programas**, haga clic en **System Center Operations Manager 2007 R2**y, a continuación, haga clic en **Shell de Operations Manager**.

2.  En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, con la ruta de acceso real a su copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Después de importar el primer paquete de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Cierre el shell de Operations Manager.

Si usa System Center Operations Manager 2012, complete este procedimiento en su lugar:

1.  Haga clic en **Inicio**, en **todos los programas**, en **Microsoft System Center 2012**, haga clic en **Operations Manager**y, a continuación, haga clic en **Shell de Operations Manager**.

2.  En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, con la ruta de acceso real a su copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Después de haber importado el primer paquete de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

