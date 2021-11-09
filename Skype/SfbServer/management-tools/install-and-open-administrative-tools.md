---
title: Instalar y abrir herramientas administrativas
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: En este tema se describe cómo instalar y abrir las herramientas administrativas que necesita para implementar y administrar Skype Empresarial.
ms.openlocfilehash: 21fc33f5e095100f9634695925e1000172742695
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848423"
---
# <a name="install-and-open-administrative-tools"></a>Instalar y abrir herramientas administrativas

En este tema se describe cómo instalar las herramientas administrativas que necesita para implementar y administrar Skype Empresarial Server. Las herramientas administrativas se instalan de forma predeterminada en cada servidor que ejecuta Skype Empresarial Server. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Le recomendamos encarecidamente que instale las herramientas administrativas en un equipo que se encuentra en el mismo dominio o bosque que la implementación de Skype Empresarial Server que está creando, para asegurarse de que los pasos de preparación de Servicios de dominio de Active Directory ya están completados, lo que le permite usar las herramientas administrativas en ese equipo más adelante para publicar la topología. Asegúrese también de revisar los requisitos necesarios antes de instalar o usar las Skype Empresarial Server administrativas. Vea la documentación de requisitos [Skype Empresarial Server 2019](../../SfBServer2019/plan/system-requirements.md) [o Skype Empresarial Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Si su organización requiere localizar Internet Information Services (IIS) y todos los servicios web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de ubicación de instalación de los archivos Skype Empresarial Server en el cuadro de diálogo Instalación. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos Skype Empresarial Server se implementarán también en esta unidad. 

## <a name="to-install-the-administrative-tools"></a>Para instalar las herramientas administrativas

1. Inicie sesión como administrador local (requisito mínimo) en el equipo donde desee instalar las herramientas administrativas. Si ha iniciado sesión como usuario estándar en Windows y el control de cuentas de usuario (UAC) está habilitado, se le pedirá el administrador local o un nombre de usuario y contraseña equivalentes al dominio.
2. Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \Setup\amd64\Setup.exe.
3. Si se le pide que instale el Microsoft Visual C++ distribuible, haga clic en **Sí**.
4. En la página Ubicación de instalación, haga clic en **Aceptar**. Cambie esta ruta de acceso a otra ubicación o unidad si necesita que los archivos se instalen en una ubicación diferente.

    > [!Important]
    > Si su organización requiere localizar Internet Information Services (IIS) y todos los servicios web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de ubicación de instalación de los archivos Skype Empresarial Server en el cuadro de diálogo Instalación. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos Skype Empresarial Server se implementarán también en esta unidad. 

5. En la página Contrato de licencia para el usuario final, revise los términos de la licencia, haga clic en **Acepto** y, a continuación, haga clic en **Aceptar**. Este paso es necesario para poder continuar
6. En la página Asistente para implementación, haga clic **en Instalar herramientas de administrador**. 
7. Cuando finalice la instalación correctamente, haga clic en **Salir**.

Use los siguientes procedimientos para abrir herramientas administrativas para implementar, configurar o solucionar problemas de Skype Empresarial Server topología.

- [Asistente para implementación](#deployment-wizard)
- [Topology Builder](#topology-builder) 
- [Panel de control de Skype Empresarial Server](#skype-for-business-server-control-panel)
- [Shell de administración de Skype Empresarial Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Asistente para implementación

Use el siguiente procedimiento para iniciar el Asistente para implementación localmente para agregar o quitar archivos de componentes.

**Para iniciar el Asistente Skype Empresarial Server implementación**

1. Inicie sesión en el equipo en el que el Asistente para la implementación de Skype Empresarial Server está instalado como miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins.
2. Haga **clic en** Inicio , en **Todos** los programas, **en Skype Empresarial Server** y, a continuación, en Skype Empresarial Server Asistente **para implementación**.


## <a name="topology-builder"></a>Topology Builder 

Use el siguiente procedimiento para abrir el Generador de topologías para definir los servidores que desea implementar en la Skype Empresarial Server topología.

**Para abrir el generador Skype Empresarial Server topología para diseñar la topología**

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Puede definir una topología mediante una cuenta que sea miembro del grupo usuarios local, pero para leer, publicar o habilitar una topología, que es necesaria para instalar Skype Empresarial Server en un servidor, debe usar una cuenta que sea miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins,  y que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que va a usar para el almacén de archivos de archivado para que el Generador de topologías pueda configurar la lista de control de acceso discrecional (DACL) necesaria o una cuenta con derechos de usuario equivalentes.
 
2. Iniciar generador de topologías: haga clic **en Inicio**, todos los **programas,** haga clic **en Skype Empresarial Server** y, a continuación, haga clic Skype Empresarial Server Generador **de topologías**.

## <a name="skype-for-business-server-control-panel"></a>Panel de control de Skype Empresarial Server 

Use uno de los siguientes procedimientos para abrir el Panel de control de Skype Empresarial Server para administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el Panel de control Skype Empresarial Server usuario. Puede usar otros roles para iniciar sesión en el Panel de control de Skype Empresarial Server para realizar tareas de administración específicas, según la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para administrar el archivado en el Panel Skype Empresarial Server control. Para obtener más información acerca de los roles, vea [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Para obtener información sobre las funciones que puede usar para realizar una tarea específica, consulte la documentación de la tarea. 

**Para abrir el panel Skype Empresarial Server control desde cualquier equipo dentro del firewall de la organización**

1. Desde una cuenta de usuario asignada al rol CsAdministrator u otro rol que tenga los derechos y permisos de usuario adecuados para realizar la tarea, inicie sesión en cualquier equipo de la implementación interna con una resolución de pantalla mínima de 1024 x 768.

    > [!IMPORTANT]
    > Si ha configurado un localizador uniforme de recursos (URL) simple de administración, puede acceder al Panel de control de Skype Empresarial Server desde un explorador de Internet que se ejecuta en cualquier equipo dentro del firewall de su organización. Para obtener más información sobre cómo configurar la dirección URL sencilla de administración, vea [Planning for simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) y [Edit or configure simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls). 

2. Abra una ventana del explorador y escriba la dirección URL de administración configurada para la organización.

**Para abrir el Panel Skype Empresarial Server control en un equipo que ejecute Skype Empresarial Server**

1. Desde una cuenta de usuario que sea miembro del rol CsAdministrator u otro rol que tenga los derechos y permisos de usuario adecuados para realizar la tarea, inicie sesión en un equipo en el que haya instalado Skype Empresarial Server o, como mínimo, las herramientas administrativas de Skype Empresarial Server. Para configurar la configuración, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.
2. Inicio Skype Empresarial Server Panel de control: haga clic en Inicio **,** haga clic en Todos los programas **,** elija Herramientas administrativas **,** elija Skype Empresarial Server **y,** a continuación, haga clic Skype Empresarial Server **Panel de control**.

## <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server 

Use el siguiente procedimiento para abrir el Shell de administración Skype Empresarial Server administrar servidores, usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el Shell Skype Empresarial Server administración. Puede iniciar sesión con otras funciones para realizar tareas específicas de administración, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con las administración de archivado. Para obtener más información acerca de los roles, vea [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Para obtener información sobre las funciones que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.<br/><br/>También puede ejecutar ciertos cmdlets mediante una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, o RTCUniversalReadOnlyAdmins, según el cmdlet. 

**Para abrir Skype Empresarial Server Shell de administración**

Si abre una ventana Windows PowerShell en lugar del Shell de administración de Skype Empresarial Server, de forma predeterminada no puede ejecutar los cmdlets Skype Empresarial Server. Para ejecutar los cmdlets Skype Empresarial Server desde dentro de Windows PowerShell, escriba lo siguiente en el símbolo del sistema Windows PowerShell comandos:

`Import-Module Lync`

Inicie el Shell Skype Empresarial Server de administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial Server** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.