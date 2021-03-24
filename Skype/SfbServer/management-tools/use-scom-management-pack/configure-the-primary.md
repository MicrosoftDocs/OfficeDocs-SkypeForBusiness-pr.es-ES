---
title: Configurar el servidor de administración principal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Summary: Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.'
ms.openlocfilehash: ace25e1b4971c561dc1544290b04f481f36c9676
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111646"
---
# <a name="configure-the-primary-management-server"></a>Configurar el servidor de administración principal

**Resumen:** Configure el servidor de administración principal, instale System Center Operations Manager e importe paquetes de administración para Skype Empresarial Server 2015.

Para aprovechar al máximo las nuevas funcionalidades de supervisión de estado incluidas en Skype Empresarial Server 2015, primero debe designar un equipo para que actúe como el servidor de administración principal. A continuación, debe instalar System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 en ese equipo. Además, primero debe instalar una versión compatible de SQL Server para funcionar como la base de datos back-end de Operations Manager.

Al instalar System Center Operations Manager, deberá instalar todos los componentes de ese producto, incluidos:

- Base de datos operativa

- Servidor

- Consola

- Cmdlets de Windows PowerShell

- Consola web

- Reporting

- Almacén de datos

> [!IMPORTANT]
> El " Paquete redistribuible de[Microsoft Report Viewer 2010](https://www.microsoft.com/download/details.aspx?id=6442)" debe instalarse antes de instalar System Center Operations Manager 2012.

Para obtener más información sobre estos productos y su instalación, consulte los siguientes vínculos:

- [System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tenga en cuenta que solo puede tener un servidor de administración raíz por implementación de Skype Empresarial Server.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importar los módulos de administración de Skype Empresarial Server 2015

Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de módulos de administración, software que determina qué elementos puede supervisar System Center Operations Manager, cómo deben supervisarse esos elementos y cómo se deben activar e informar las alertas. Skype Empresarial Server 2015 incluye dos módulos de administración de System Center Operations Manager que proporcionan las siguientes funcionalidades:

- El **módulo** de administración de componentes y usuarios (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) realiza un seguimiento de los problemas de Skype Empresarial Server registrados en registros de eventos, registrados por contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o las bases de datos de calidad de la experiencia (QoE). Para problemas críticos, System Center Operations Manager se puede configurar para notificar inmediatamente a los administradores a través del correo electrónico, el mensaje instantáneo o la mensajería SMS. (SMS, o servicio de mensajes cortos, es la tecnología que se usa para enviar mensajes de texto de un dispositivo móvil a otro).

    > [!NOTE]
    >  Para obtener más información sobre cómo configurar la notificación de Operations Manager, vea [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).

- Active **Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) prueba proactivamente los componentes clave de Skype Empresarial Server, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC). Estas pruebas se llevan a cabo mediante los cmdlets de transacciones sintéticas de Skype Empresarial Server. Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba. Si se produce un error en esta conversación simulada, se genera una alerta.

La importación de los módulos de administración es un paso fundamental. Si los módulos de administración no se importan, no podrá usar Operations Manager para supervisar eventos de Skype Empresarial Server ni ejecutar transacciones sintéticas de Skype Empresarial Server.

El módulo de administración de componentes y usuarios se usa para supervisar solo Skype Empresarial Server 2015. Si se encuentra en un escenario de coexistencia en el que están instalados Skype Empresarial Server 2015 y Lync Server 2013, debe seguir usando los módulos de administración de Lync Server 2013 para sus equipos de Lync Server 2013.

> [!NOTE]
> Los módulos de administración de Skype Empresarial Server 2015 incluyen el Módulo de administración de usuarios y componentes de Skype Empresarial Server 2015 y el Módulo de administración de supervisión activa de Skype Empresarial Server 2015.

Puede usar una de las siguientes herramientas para importar los paquetes de administración:

- **System Center Operations Manager** Con este método, se usa Operations Manager para agregar supervisión para Skype Empresarial Server.

- **Shell de Operations Manager** Puede usar el Shell de Operations Manager para importar directamente o para solucionar cualquier problema que se encuentre al importar módulos de administración mediante la consola de System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importar los módulos de administración mediante System Center Operations Manager

1. Descargue el SkypeForBusiness2015ManagementPacks.msi de las descargas web de Microsoft e instale el msi.

2. En System Center Operations Manager, haga clic en **Administración**.

3. En el panel Administración, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.

4. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.

5. En el cuadro **de diálogo Conexión** de catálogo en línea, haga clic en **No**.

6. En el cuadro de diálogo Seleccionar **módulos** de administración para importar, busque y seleccione los archivos Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2015.Monitoring.ComponentAndUser.mp y, a continuación, haga clic en **Abrir**. Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo y, a continuación, mantenga presionada la tecla Ctrl y haga clic en los archivos siguientes.

7. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. Si esto ocurre, copie los archivos en una carpeta diferente y, a continuación, reinicie el proceso de importación e instalación.

8. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**. El proceso de importación e instalación puede requerir varios minutos para completarse.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importar los módulos de administración mediante el Shell de Operations Manager

En general, es más fácil importar los módulos de administración mediante la consola de Operations Manager. Sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona informes de error adecuados. En comparación, el Shell de Operations Manager proporciona información detallada. Si usa Operations Manager y encuentra problemas al importar un módulo de administración, importe el paquete mediante el Shell de Operations Manager. La información proporcionada por el Shell de Operations Manager puede ayudarle a determinar por qué se ha fallado la importación.

1. Haga **clic en** Inicio , en Todos **los** programas, en **Microsoft System Center 2012,** en **Operations Manager** y, a continuación, en Shell de **Operations Manager**.

2. En shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta de acceso real a la copia del archivo Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. Después de importar el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```