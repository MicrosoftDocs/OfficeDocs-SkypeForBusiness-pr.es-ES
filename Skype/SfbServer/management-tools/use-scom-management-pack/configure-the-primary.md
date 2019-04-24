---
title: Configurar el servidor de administración principal
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Resumen: Configurar el servidor de administración principal, instalar a System Center Operations Manager e Importar módulos de administración para Skype para Business Server 2015.'
ms.openlocfilehash: 06dbf8161e2b241bb527c0ca02c9e8210055d409
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197944"
---
# <a name="configure-the-primary-management-server"></a>Configurar el servidor de administración principal

**Resumen:** Configurar el servidor de administración principal, instalar a System Center Operations Manager e Importar módulos de administración para Skype para Business Server 2015.

Para aprovechar al máximo la nueva de supervisión de mantenimiento funcionalidades incluidas en Skype para Business Server 2015, primero debe designar un equipo para que actúe como el servidor de administración principal. A continuación, debe instalar System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 en dicho equipo. Además, primero debe instalar una versión compatible de SQL Server para funcionar como la base de datos de back-end de Operations Manager.

Al instalar System Center Operations Manager, debe instalar todos los componentes de ese producto, incluidos:

- Base de datos operativa

- Servidor

- Consola

- Cmdlets de Windows PowerShell

- Consola web

- Informes

- Almacén de datos

> [!IMPORTANT]
> El "[Paquete redistribuible de Microsoft informe Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" debe instalarse antes de instalar System Center Operations Manager 2012.

Para obtener más información sobre estos productos y su instalación, consulte los siguientes vínculos:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Tenga en cuenta que puede tener un solo servidor de administración raíz por Skype para la implementación de Business Server.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importación de los paquetes de administración de Skype Empresarial Server 2015

Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de paquetes de administración: software que puede supervisar indica qué elementos de System Center Operations Manager, cómo deben supervisarse esos elementos y cómo se deben desencadenar alertas y notifiquen. Skype para Business Server 2015 incluye dos paquetes de administración de System Center Operations Manager que proporcionan las siguientes capacidades:

- **El componente y el módulo de administración de usuario** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) realiza un seguimiento de Skype para Business Server problemas registrados en los registros de eventos, registrado por los contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o las bases de datos de calidad de la experiencia (QoE). Para problemas críticos, System Center Operations Manager puede configurarse para notificar inmediatamente a los administradores a través de correo electrónico, mensaje instantáneo o SMS de mensajería. (SMS o servicio de mensajes cortos, es la tecnología que se utiliza para enviar mensajes de texto desde un dispositivo móvil a otro).

    > [!NOTE]
    >  Para obtener información detallada sobre la configuración de notificación de Operations Manager, vea [Configuración de las notificaciones](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **El módulo de administración de supervisión activa** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactivamente pruebas clave Skype para los componentes de servidor empresarial, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono que se encuentra en la red telefónica conmutada (RTC ). Estas pruebas se llevan a cabo mediante el uso de la Skype para cmdlets de transacciones sintéticas Business Server. Por ejemplo, se usa el cmdlet **Test-CsIM** para simular una conversación entre un par de usuarios de prueba de mensajería instantánea. Si se produce un error en esta conversación simulada, se genera una alerta.

Importar los paquetes de administración es un paso fundamental. Si los módulos de administración no se importan, no podrá usar Operations Manager para supervisar los eventos de Skype Empresarial Server ni para ejecutar transacciones sintéticas de Skype Empresarial Server.

El módulo de componentes y administración de usuario se usa solo para supervisar Skype Empresarial Server 2015. Si se encuentra en un escenario de coexistencia en el se ha instalado Skype Empresarial Server 2015 y Lync Server 2013, debe continuar usando los paquetes de administración de Lync Server 2013 para sus equipos Lync Server 2013.

> [!NOTE]
> Los módulos de administración de Skype Empresarial Server 2015 incluyen el módulo de componentes y administración de usuarios y el módulo de administración de supervisión activa.

Puede usar una de las siguientes herramientas para importar los paquetes de administración:

- **System Center Operations Manager** Con este método, se utiliza el Administrador de operaciones para agregar supervisión para Skype para Business Server.

- **Shell de Operations Manager** Puede usar el Shell de Operations Manager para importar directamente o a solucionar los problemas que surgen al importar módulos de administración mediante el uso de la consola de System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importación de los módulos de administración mediante System Center Operations Manager

1. Descargue SkypeForBusiness2015ManagementPacks.msi desde la web de descargas de Microsoft e instala el archivo msi.

2. En System Center Operations Manager, haga clic en **administración**.

3. En el panel de administración, haga clic en **Los paquetes de administración**y, a continuación, haga clic en **Importar módulos de administración**.

4. En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.

5. En el cuadro de diálogo **Conexión del catálogo en línea**, haga clic en **No**.

6. En el cuadro de diálogo **Seleccionar módulos de administración a importar**, localice y seleccione los archivos Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2015.Monitoring.ComponentAndUser.mp y, a continuación, haga clic en **Abrir**. Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo, mantenga presionada la tecla Ctrl y haga clic en el segundo archivo.

7. En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede realizar la instalación, generalmente significa que los archivos del módulo de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. En este caso, copie los archivos en otra carpeta y luego reinicie el proceso de importación e instalación.

8. En el cuadro de diálogo **Seleccionar módulos de administración**, haga clic en **Cerrar**. Tenga en cuenta que el proceso de instalación e importación puede requerir algunos minutos para completarse.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importación de los módulos de administración mediante el Shell de Operations Manager

En general, es más fácil importar los módulos de administración con la consola de Operations Manager. Sin embargo, si se produce un error y no es posible llevar a cabo la importación, la consola no siempre proporciona informes de errores adecuados. El Shell de Operations Manager, en cambio, proporciona información detallada. Si está usando Operations Manager y tiene problemas al importar un módulo de administración, importe el módulo con el Shell de Operations Manager. La información que proporciona el Shell de Operations Manager puede ayudarle a determinar el motivo del error de importación.

1. Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft System Center 2012**, **Operations Manager** y **Shell de Operations Manager**.

2. En Shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta de acceso real a su copia del archivo Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. Después de haber importado el primer módulo de administración, repita el proceso usando la ruta a su copia del archivo Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
