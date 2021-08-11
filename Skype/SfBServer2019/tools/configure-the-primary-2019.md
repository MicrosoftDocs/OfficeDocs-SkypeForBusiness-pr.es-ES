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
description: 'Summary: Configure your primary management server, install System Center Operations Manager, and import management packs for Skype Empresarial Server 2019.'
ms.openlocfilehash: 2606c87d5874bdec4e6dded494b024bc7810de70db000c2c65892e0d80e5a6d1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277535"
---
# <a name="configure-the-primary-management-server"></a>Configurar el servidor de administración principal

**Resumen:** Configure el servidor de administración principal, instale System Center Operations Manager e importe paquetes de administración para Skype Empresarial Server 2019.

Para aprovechar al máximo las nuevas funcionalidades de supervisión de estado incluidas en Skype Empresarial Server 2019, primero debe designar un equipo para que actúe como servidor de administración principal. A continuación, debe instalar System Center Operations Manager 2012 SP1 o R2 o System Center Operations Manager 2007 R2 en ese equipo. Además, primero debe instalar una versión compatible de SQL Server para funcionar como la base de datos back-end de Operations Manager.

Al instalar System Center Operations Manager, deberá instalar todos los componentes de ese producto, incluidos:

- Base de datos operativa

- Servidor

- Consola

- Cmdlets de Windows PowerShell

- Consola web

- Generación de informes

- Almacén de datos

> [!IMPORTANT]
> El "[Microsoft Report Viewer paquete redistribuible de 2010](https://www.microsoft.com/download/details.aspx?id=6442)" debe instalarse antes de instalar System Center Operations Manager 2012.

Para obtener más información sobre estos productos y su instalación, consulte los siguientes vínculos:

- [System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tenga en cuenta que solo puede tener un servidor de administración raíz por Skype Empresarial Server implementación.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importar los módulos Skype Empresarial Server administración de 2019

Puede ampliar las capacidades de System Center Operations Manager mediante la instalación de módulos de administración, software que determina qué elementos System Center Operations Manager puede supervisar, cómo deben supervisarse esos elementos y cómo deben activarse e informarse las alertas. Skype Empresarial Server 2019 incluye dos System Center de administración de Operations Manager que proporcionan las siguientes funcionalidades:

- El **módulo** de administración de componentes y usuarios (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) realiza un seguimiento de Skype Empresarial Server problemas registrados en registros de eventos, registrados por contadores de rendimiento o registrados en los registros de detalles de llamadas (CDR) o las bases de datos de calidad de la experiencia (QoE). Para problemas críticos, System Center Operations Manager se puede configurar para notificar inmediatamente a los administradores a través de correo electrónico, mensaje instantáneo o mensajería SMS. (SMS, o servicio de mensajes cortos, es la tecnología que se usa para enviar mensajes de texto de un dispositivo móvil a otro).

    > [!NOTE]
    >  Para obtener más información sobre cómo configurar la notificación de Operations Manager, vea [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).

- Active **Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) prueba proactivamente componentes clave de Skype Empresarial Server, como iniciar sesión en el sistema, intercambiar mensajes instantáneos o realizar llamadas a un teléfono ubicado en la red telefónica conmutada (RTC). Estas pruebas se realizan mediante el uso de los cmdlets Skype Empresarial Server transacciones sintéticas. Por ejemplo, el cmdlet **Test-CsIM** se usa para simular una conversación de mensajería instantánea entre dos usuarios de prueba. Si se produce un error en esta conversación simulada, se genera una alerta.

La importación de los módulos de administración es un paso fundamental. Si los módulos de administración no se importan, no podrá usar Operations Manager para supervisar los eventos Skype Empresarial Server o ejecutar Skype Empresarial Server transacciones sintéticas.

El módulo de administración de componentes y usuarios se usa para supervisar solo Skype Empresarial Server 2019. Si se encuentra en un escenario de coexistencia en el que están instalados Skype Empresarial Server 2019 y Skype Empresarial Server 2015, debe seguir usando los módulos de administración de Skype Empresarial Server 2015 para los equipos de Skype Empresarial Server 2015.

> [!NOTE]
> Los módulos de administración de Skype Empresarial Server 2019 incluyen el módulo de administración de usuarios y componentes de Skype Empresarial Server 2019 y el módulo de administración de supervisión activa de Skype Empresarial Server 2019.

Puede usar una de las siguientes herramientas para importar los paquetes de administración:

- **System Center Operations Manager** Con este método, se usa Operations Manager para agregar supervisión para Skype Empresarial Server.

- **shell de Operations Manager** Puede usar el shell de Operations Manager importar directamente o para solucionar los problemas que se encuentren al importar módulos de administración mediante la consola de System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importar los módulos de administración mediante System Center Operations Manager

1. Descargue el SkypeForBusiness2019ManagementPacks.msi de las descargas web de Microsoft e instale el msi.

2. En System Center Operations Manager, haga clic en **Administración**.

3. En el panel Administración, haga clic con el botón secundario en **Paquetes de administración** y luego haga clic en **Importar paquetes de administración**.

4. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Agregar** y luego en **Agregar desde el disco**.

5. En el cuadro **de diálogo Conexión** de catálogo en línea, haga clic en **No**.

6. En el cuadro de diálogo Seleccionar **módulos** de administración para importar, busque y seleccione los archivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp y Microsoft.LS.2019.Monitoring.ComponentAndUser.mp y, a continuación, haga clic en **Abrir**. Para seleccionar varios archivos en el cuadro de diálogo, haga clic en el primer archivo y, a continuación, mantenga presionada la tecla Ctrl y haga clic en los archivos siguientes.

7. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Instalar**. Si obtiene un mensaje de error y no se puede producir la instalación, que generalmente significa que los archivos del paquete de administración se encuentran en una carpeta protegida por el control de cuentas de usuario de Windows. Si esto ocurre, copie los archivos en una carpeta diferente y, a continuación, reinicie el proceso de importación e instalación.

8. En el cuadro de diálogo **Seleccionar paquetes de administración**, haga clic en **Cerrar**. El proceso de importación e instalación puede requerir varios minutos para completarse.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importar los módulos de administración mediante el shell de Operations Manager

En general, es más fácil importar los módulos de administración mediante la consola de Operations Manager. Sin embargo, si se produce un error y se produce un error en la importación, la consola no siempre proporciona informes de error adecuados. En comparación, el shell de Operations Manager proporciona información detallada. Si usa Operations Manager y encuentra problemas al importar un módulo de administración, importe el paquete mediante el shell de Operations Manager. La información proporcionada por shell de Operations Manager puede ayudarle a determinar por qué se ha fallado la importación.

1. Haga **clic en** Inicio , en **Todos** los programas, en Microsoft System Center **2012**, en **Operations Manager** y, a continuación, en **shell de Operations Manager**.

2. En shell de Operations Manager, escriba el siguiente comando en el símbolo del sistema, usando la ruta de acceso real a la copia del archivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp y, a continuación, presione ENTRAR:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Después de importar el primer módulo de administración, repita el proceso con la ruta de acceso a la copia del archivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```