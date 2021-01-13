---
title: Instalar y abrir herramientas administrativas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este tema se describe cómo instalar y abrir las herramientas administrativas que necesita para implementar y administrar Skype Empresarial.
ms.openlocfilehash: d31fe784b62a5d709049dc5061e323034065df37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835100"
---
# <a name="install-and-open-administrative-tools"></a>Instalar y abrir herramientas administrativas

En este tema se describe cómo instalar las herramientas administrativas necesarias para implementar y administrar Skype Empresarial Server. Las herramientas administrativas se instalan de forma predeterminada en cada servidor que ejecuta Skype Empresarial Server. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Le recomendamos encarecidamente que instale las herramientas administrativas en un equipo que se encuentra en el mismo dominio o bosque que la implementación de Skype Empresarial Server que está creando, para asegurarse de que los pasos de preparación de los Servicios de dominio de Active Directory ya están completos, lo que le permite usar las herramientas administrativas en ese equipo más adelante para publicar la topología. Asegúrese también de revisar los requisitos necesarios antes de instalar o usar las herramientas administrativas de Skype Empresarial Server. Consulte la documentación de [requisitos en Skype Empresarial Server 2019](../../SfBServer2019/plan/system-requirements.md) o [Skype Empresarial Server 2015.](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)
 
> [!Important]
> Si su organización requiere que localice Internet Information Services (IIS) y todos los servicios web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de acceso de ubicación de instalación de los archivos de Skype Empresarial Server en el cuadro de diálogo de instalación. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos de Skype Empresarial Server también se implementarán en esta unidad. 

## <a name="to-install-the-administrative-tools"></a>Para instalar las herramientas administrativas

1. Inicie sesión como administrador local (requisito mínimo) en el equipo donde desee instalar las herramientas administrativas. Si ha iniciado sesión como usuario estándar en Windows y el Control de cuentas de usuario (UAC) está habilitado, se le pedirá el administrador local o un nombre de usuario y contraseña equivalentes a un dominio.
2. Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \Setup\amd64\Setup.exe.
3. Si se te pide que instales microsoft Visual C++ distribuible, haz clic en **Sí.**
4. En la página Ubicación de instalación, haga clic en **Aceptar.** Cambie esta ruta de acceso a otra ubicación o unidad si necesita que los archivos se instalen en una ubicación diferente.

    > [!Important]
    > Si su organización requiere que localice Internet Information Services (IIS) y todos los servicios web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de acceso de ubicación de instalación de los archivos de Skype Empresarial Server en el cuadro de diálogo de instalación. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos de Skype Empresarial Server también se implementarán en esta unidad. 

5. En la página Contrato de licencia para el usuario final, revise los términos de la licencia, haga clic en **Acepto** y, a continuación, haga clic en **Aceptar**. Este paso es necesario para poder continuar
6. En la página Asistente para la implementación, haga **clic en Instalar herramientas de administrador.** 
7. Cuando finalice la instalación correctamente, haga clic en **Salir**.

Use los siguientes procedimientos para abrir herramientas administrativas para implementar, configurar o solucionar problemas de la topología de Skype Empresarial Server.

- [Asistente para implementación](#deployment-wizard)
- [Topology Builder](#topology-builder) 
- [Panel de control de Skype Empresarial Server](#skype-for-business-server-control-panel)
- [Shell de administración de Skype Empresarial Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Asistente para implementación

Use el siguiente procedimiento para iniciar el Asistente para la implementación localmente para agregar o quitar archivos de componentes.

**Para iniciar el Asistente para la implementación de Skype Empresarial Server**

1. Inicie sesión en el equipo donde está instalado el Asistente para la implementación de Skype Empresarial Server como miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins.
2. Haga **clic en Inicio,** **en Todos** los programas, en Skype Empresarial **Server** y, a continuación, en Asistente para la implementación de Skype **Empresarial Server.**


## <a name="topology-builder"></a>Topology Builder 

Use el siguiente procedimiento para abrir el Generador de topologías para definir los servidores que desea implementar en la topología de Skype Empresarial Server.

**Para abrir el Generador de topologías de Skype Empresarial Server para diseñar la topología**

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para leer, publicar o habilitar una topología, que es necesaria para instalar Skype Empresarial Server en un servidor, debe usar una cuenta que sea miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (es decir, , leer, escribir y modificar) en el recurso compartido de archivos que va a usar para el almacén de archivos de archivado para que Topology Builder pueda configurar la lista de control de acceso discrecional (DACL) necesaria o una cuenta con derechos de usuario equivalentes.
 
2. Inicie el Generador de topologías: **Haga** clic en Inicio, Todos los **programas,** Skype Empresarial **Server** y, a continuación, haga clic en Generador de topologías de Skype Empresarial **Server.**

## <a name="skype-for-business-server-control-panel"></a>Panel de control de Skype Empresarial Server 

Use uno de los siguientes procedimientos para abrir el Panel de control de Skype Empresarial Server para administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el Panel de control de Skype Empresarial Server. Puede usar otros roles para iniciar sesión en el Panel de control de Skype Empresarial Server para realizar tareas de administración específicas, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para administrar el archivado en el Panel de control de Skype Empresarial Server. Para obtener más información acerca de los roles, vea [Planeación del control de acceso basado en roles.](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx) Para obtener información sobre las funciones que puede usar para realizar una tarea específica, consulte la documentación de la tarea. 

**Para abrir el Panel de control de Skype Empresarial Server desde cualquier equipo dentro del firewall de su organización**

1. Desde una cuenta de usuario asignada al rol CsAdministrator u otro rol que tenga los permisos y derechos de usuario adecuados para la tarea que se va a realizar, inicie sesión en cualquier equipo de la implementación interna con una resolución de pantalla mínima de 1024 x 768.

    > [!IMPORTANT]
    > Si ha configurado un localizador uniforme de recursos (URL) simple de administración, puede obtener acceso al Panel de control de Skype Empresarial Server desde un explorador de Internet que se ejecute en cualquier equipo dentro del firewall de su organización. Para obtener más información sobre cómo configurar la dirección URL sencilla de administración, vea [Planeación](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) de direcciones URL sencillas y [Editar o configurar direcciones URL sencillas.](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx) 

2. Abra una ventana del explorador y escriba la dirección URL de administración configurada para la organización.

**Para abrir el Panel de control de Skype Empresarial Server en un equipo que ejecute Skype Empresarial Server**

1. Desde una cuenta de usuario que sea miembro del rol CsAdministrator u otro rol que tenga los permisos y derechos de usuario adecuados para la tarea que se va a realizar, inicie sesión en un equipo en el que haya instalado Skype Empresarial Server o, como mínimo, las herramientas administrativas de Skype Empresarial Server. Para configurar las opciones, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.
2. Inicie el Panel de control de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** seleccione Herramientas **administrativas,** Skype Empresarial **Server** y, a continuación, haga clic en Panel de control de Skype Empresarial **Server.**

## <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server 

Use el siguiente procedimiento para abrir el Shell de administración de Skype Empresarial Server para administrar servidores, usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el Shell de administración de Skype Empresarial Server. Puede iniciar sesión con otras funciones para realizar tareas específicas de administración, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con las administración de archivado. Para obtener más información acerca de los roles, vea [Planeación del control de acceso basado en roles.](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx) Para obtener información sobre las funciones que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.<br/><br/>También puede ejecutar ciertos cmdlets mediante una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, o RTCUniversalReadOnlyAdmins, según el cmdlet. 

**Para abrir el Shell de administración de Skype Empresarial Server**

Si abre una ventana Windows PowerShell en lugar del Shell de administración de Skype Empresarial Server, de forma predeterminada no puede ejecutar los cmdlets de Skype Empresarial Server. Para ejecutar los cmdlets de Skype Empresarial Server desde dentro Windows PowerShell, escriba lo siguiente en el símbolo Windows PowerShell comando:

`Import-Module Lync`

Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **Server** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
