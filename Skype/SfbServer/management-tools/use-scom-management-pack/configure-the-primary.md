---
title: Configurar el servidor de administración principal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Resumen: configure el servidor de administración principal, instale System Center Operations Manager e importe los paquetes de administración de Skype empresarial Server 2015.'
ms.openlocfilehash: 08c1967965248d26844433030e4bf77501882cd8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005965"
---
# <a name="configure-the-primary-management-server"></a>Configurar el servidor de administración principal

**Resumen:** Configure el servidor de administración principal, instale System Center Operations Manager e importe los paquetes de administración de Skype empresarial Server 2015.

Para aprovechar todas las ventajas de las nuevas funciones de supervisión de estado incluidas en Skype empresarial Server 2015, primero debe designar un equipo para que actúe como servidor de administración principal. A continuación, debe instalar System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 en ese equipo. Además, debe instalar primero una versión compatible de SQL Server para que funcione como su base de datos back-end de Operations Manager.

Al instalar System Center Operations Manager, tendrá que instalar todos los componentes de ese producto, incluidos:

- Base de datos operativa

- Servidor

- Consola

- Cmdlets de Windows PowerShell

- Consola web

- Reporting

- Almacén de datos

> [!IMPORTANT]
> Es necesario instalar el "[paquete redistribuible de Microsoft Report Viewer 2010](https://www.microsoft.com/download/details.aspx?id=6442)" antes de instalar System Center Operations Manager 2012.

Para obtener más información sobre estos productos y su instalación, consulte los siguientes vínculos:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tenga en cuenta que solo puede tener un servidor de administración raíz por cada implementación de Skype empresarial Server.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importación de los paquetes de administración de Skype empresarial Server 2015

Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración: software que determina qué elementos puede supervisar System Center Operations Manager, cómo se deben supervisar esos elementos y cómo se deben desencadenar alertas y Enviado. Skype empresarial Server 2015 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes capacidades:

- **El componente y el módulo de administración de usuarios** (Microsoft.LS.2015.Monitoring.ComponentAndUser.MP) realiza un seguimiento de los problemas de Skype empresarial Server registrados en los registros de eventos, registrados por los contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o las bases de datos de calidad de la experiencia (QoE). Para los problemas críticos, System Center Operations Manager se puede configurar para que notifique a los administradores de forma inmediata a través del correo electrónico, los mensajes instantáneos o los mensajes SMS. (SMS, o servicio de mensajes cortos, es la tecnología que se usa para enviar mensajes de texto desde un dispositivo móvil a otro).

    > [!NOTE]
    >  Para obtener más información sobre cómo configurar la notificación de Operations Manager, consulte Configuración de la [notificación](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **El módulo de administración de supervisión activa** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.MP) comprueba de forma proactiva los componentes clave de Skype empresarial Server, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC). Estas pruebas se llevan a cabo mediante los cmdlets de transacciones sintéticas de Skype empresarial Server. Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba. Si se produce un error en esta conversación simulada, se genera una alerta.

La importación de los paquetes de administración es un paso crucial. Si no se importan los paquetes de administración, no podrá usar Operations Manager para supervisar los eventos de Skype empresarial Server ni ejecutar transacciones sintéticas de Skype empresarial Server.

El módulo de componentes y administración de usuarios solo se usa para supervisar Skype empresarial Server 2015. Si está en un escenario de coexistencia donde están instalados tanto Skype empresarial Server 2015 como Lync Server 2013, debe seguir usando los paquetes de administración de Lync Server 2013 para los equipos con Lync Server 2013.

> [!NOTE]
> Los módulos de administración de Skype empresarial Server 2015 incluyen el componente de Skype empresarial Server 2015 y el módulo de administración de usuario y el módulo de administración de supervisión activa de Skype empresarial Server 2015.

Puede usar una de las siguientes herramientas para importar los paquetes de administración:

- **System Center Operations Manager** Con este método, se usa Operations Manager para agregar supervisión de Skype empresarial Server.

- **Shell de Operations Manager** Puede usar el shell de Operations Manager para importar directamente o para solucionar cualquier problema que encuentre al importar paquetes de administración mediante la consola de System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importación de los paquetes de administración mediante System Center Operations Manager

1. Descargue SkypeForBusiness2015ManagementPacks. msi de las descargas del Web de Microsoft e instale el msi.

2. En System Center Operations Manager, haga clic en **Administración**.

3. En el panel Administración, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.

4. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.

5. En el cuadro de diálogo **conexión al catálogo en línea** , haga clic en **no**.

6. En el cuadro de diálogo **seleccionar módulos de administración para importar** , busque y seleccione los archivos Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2015.Monitoring.ComponentAndUser.MP y, a continuación, haga clic en **abrir**. Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo y, a continuación, mantenga presionada la tecla Ctrl y haga clic en los archivos subsiguientes.

7. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. Si esto ocurre, copie los archivos en una carpeta diferente y, a continuación, reinicie el proceso de importación e instalación.

8. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**. El proceso de importación e instalación puede tardar varios minutos en completarse.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importación de los paquetes de administración mediante el shell de Operations Manager

En general, es más fácil importar los paquetes de administración mediante la consola de Operations Manager. Sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona los informes de error adecuados. Por comparación, el shell de Operations Manager proporciona información detallada. Si usa Operations Manager y surgen problemas al importar un módulo de administración, importe el paquete mediante el shell de Operations Manager. La información que proporciona el shell de Operations Manager puede ayudarle a determinar por qué se produjo un error en la importación.

1. Haga clic en **Inicio**, en **todos los programas**, en **Microsoft System Center 2012**, haga clic en **Operations Manager**y, a continuación, haga clic en **Shell de Operations Manager**.

2. En el shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta de acceso real a su copia del archivo Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. Una vez que haya importado el primer módulo de administración, repita el proceso usando la ruta de acceso a su copia del archivo Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
