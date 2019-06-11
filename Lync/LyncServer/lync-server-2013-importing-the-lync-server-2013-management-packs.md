---
title: 'Lync Server 2013: importación de los módulos de administración de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importar los módulos de administración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración, es decir, el software que determina qué elementos puede supervisar System Center Operations Manager y cómo se deben supervisar esos elementos y cómo se deben desencadenar alertas y registrados. Lync Server 2013 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes características:

  - El componente y el paquete de administración de usuario (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Lync Server registrados en registros de eventos, registrados por contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o la calidad de la experiencia (QoE). bases. En el caso de problemas críticos, System Center Operations Manager se puede configurar para que notifiquen inmediatamente a los administradores a través de mensajes de correo electrónico, mensajes instantáneos o mensajes SMS. SMS es la tecnología que se usa para enviar mensajes de texto desde un dispositivo móvil a otro.)
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre cómo configurar las notificaciones de Operations Manager, consulte la <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>notificación de configuración en la biblioteca de TechNet en.

    
    </div>

  - El módulo de administración de supervisión activa (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) prueba de forma proactiva componentes de Lync Server clave como iniciar sesión en el sistema, intercambiar mensajes instantáneos o hacer llamadas a un teléfono que se encuentra en la conmutación pública red telefónica (RTC). Estas pruebas se realizan mediante los cmdlets de transacciones sintéticas de Lync Server. Por ejemplo, puede usar el cmdlet **Test-CsIM** para simular una conversación de mensajería instantánea (mi) entre dos usuarios de prueba. Si se produce un error en esta conversación de mensajería simulada, se genera una alerta.

Debe importar los paquetes de administración. Si no importa los paquetes de administración, no puede usar Operations Manager para supervisar los eventos de Lync Server o ejecutar transacciones sintéticas de Lync Server.

El paquete de administración de componentes y usuarios solo se usa para supervisar Lync Server 2013. Si se encuentran en un escenario de coexistencia, donde tiene instalado Lync Server 2013 y Lync Server 2010, debe seguir usando los paquetes de administración de Lync Server 2010 para sus equipos de Lync Server 2010.

<div>


> [!NOTE]  
> Los módulos de administración para Lync Server 2010 incluyen el módulo de administración de supervisión de Lync Server 2010 y el módulo de administración de supervisión de chat de Lync Server 2010.



</div>

Puede usar una de las siguientes herramientas para importar los paquetes de administración:

  - **System Center Operations Manager**   con este método, se usa el Operations Manager para agregar la supervisión de Lync Server.

  - **Shell de Operations Manager**   puede usar el shell de Operations Manager para importar directamente o para solucionar cualquier problema que encuentre al importar paquetes de administración mediante la consola de System Center Operations Manager.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importación de los módulos de administración mediante System Center Operations Manager

1.  Descargue los archivos Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.

2.  En System Center Operations Manager, haga clic en **Administración**.

3.  En el panel **Administración** , haga clic con el botón secundario en **módulos**de administración y luego haga clic en **importar módulos de administración**.

4.  En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.

5.  En el cuadro de diálogo **conexión al catálogo en línea** , haga clic en **Cancelar** para evitar que Operations Manager se conecte para ver si hay alguna dependencia para los paquetes de administración de Lync Server. Si está usando System Center Operations Manager 2012, haga clic en **no**.

6.  En el cuadro de diálogo **seleccionar módulos de administración para importar** , busque y seleccione los archivos **Microsoft.LS.2013.Monitoring.ActiveMonitoring.MP** y **Microsoft.LS.2013.Monitoring.ComponentAndUser.MP** y, a continuación, haga clic en **abrir**. Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo, mantenga presionada la tecla Ctrl y, a continuación, haga clic en el segundo archivo.

7.  En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede realizar la instalación, generalmente significa que los archivos del módulo de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. Si esto sucede, copie los archivos en una carpeta diferente y, a continuación, reinicie el proceso de importación e instalación.

8.  En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Cerrar**. Tenga en cuenta que el proceso de importación e instalación puede tardar varios minutos en completarse.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importar paquetes de administración mediante el shell de Operations Manager

En general, es más fácil importar los paquetes de administración mediante Operations Manager. sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona los informes de errores adecuados. En comparación, el shell de Operations Manager proporciona información detallada. Si está usando Operations Manager y tiene problemas para importar un paquete de administración, importe el paquete mediante el shell de Operations Manager. El shell de Operations Manager proporciona más información que puede ayudarle a determinar por qué se produjo un error en la importación.

Si está usando System Center Operations Manager 2007 R2, complete el siguiente procedimiento:

1.  Haga clic en **Inicio**, en **todos los programas**, en **System Center Operations Manager 2007 R2**y, a continuación, en **Operations Manager Shell**.

2.  En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, utilizando la ruta de acceso real a la copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Después de importar el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Cierre el shell de Operations Manager.

Si está usando System Center Operations Manager 2012, realice este procedimiento en su lugar:

1.  Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft System Center 2012**, **Operations Manager** y **Shell de Operations Manager**.

2.  En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, utilizando la ruta de acceso real a la copia del archivo Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Una vez que haya importado el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

