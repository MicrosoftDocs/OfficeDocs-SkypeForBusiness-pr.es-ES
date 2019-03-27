---
title: Instalar y abrir herramientas administrativas
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema se describe cómo instalar y abrir las herramientas administrativas que necesita para implementar y administrar Skype para la empresa.
ms.openlocfilehash: 260d84f071558ff54511b8650868db3ebb56abcb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899480"
---
# <a name="install-and-open-administrative-tools"></a>Instalar y abrir herramientas administrativas

En este tema se describe cómo instalar las herramientas administrativas que necesita para implementar y administrar Skype para Business Server. Las herramientas administrativas se instalan de forma predeterminada en cada servidor que ejecuta Skype para Business Server. Además, puede instalar las herramientas administrativas en otros equipos, como dedicadas consolas administrativas. Se recomienda encarecidamente que instalar las herramientas administrativas en un equipo que se encuentra en el mismo dominio o bosque como el Skype para la implementación de Business Server que va a crear, para asegurarse de que la preparación de los servicios de dominio de Active Directory ya están completas, pasos que le permite usar las herramientas administrativas en el equipo más adelante para publicar su topología. Además, asegúrese de revisar los requisitos necesarios antes de instalar o usar el Skype para herramientas administrativas de Business Server. Consulte la documentación de los requisitos de [Skype para Business Server 2019](../../SfBServer2019/plan/system-requirements.md) o [Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Si la organización requiere que busque Internet Information Services (IIS) y todos los servicios Web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de acceso de ubicación de instalación para el Skype para los archivos del servidor de negocio en el cuadro de diálogo del programa de instalación. Si instala los archivos del programa de instalación para esta ruta de acceso, incluidos OCSCore.msi, se implementará el resto de la Skype para los archivos del servidor empresarial a esta unidad también. 

## <a name="to-install-the-administrative-tools"></a>Para instalar las herramientas administrativas

1. Inicie sesión como administrador local (como mínimo) en el equipo donde desea instalar las herramientas administrativas. Si ha iniciado sesión como un usuario estándar de Windows y Control de cuentas de usuario (UAC) está habilitados, se le pedirá para el administrador local o un nombre de usuario equivalentes de dominio y una contraseña.
2. Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \Setup\amd64\Setup.exe.
3. Si le pide que instale Microsoft Visual C++ distribuible, haga clic en **Sí**.
4. En la página Ubicación de la instalación, haga clic en **Aceptar**. Si necesita tener los archivos instalados a otra ubicación, cambie esta ruta de acceso a otra ubicación o unidad.

    > [!Important]
    > Si la organización requiere que busque Internet Information Services (IIS) y todos los servicios Web en una unidad que no sea la unidad del sistema, puede cambiar la ruta de acceso de ubicación de instalación para el Skype para los archivos del servidor de negocio en el cuadro de diálogo del programa de instalación. Si instala los archivos del programa de instalación para esta ruta de acceso, incluidos OCSCore.msi, el resto de la Skype para los archivos del servidor empresarial se implementarán en esta unidad demasiado. 

5. En la página Contrato de licencia de usuario final, revise los términos de licencia, haga clic en **acepto**y, a continuación, haga clic en **Aceptar**. Este paso es necesario para poder continuar.
6. En la página Asistente para la implementación, haga clic en **Instalar herramientas de administrador**. 
7. Cuando la instalación finalice correctamente, haga clic en **Salir**.

Use los procedimientos siguientes para abrir las herramientas administrativas para implementar, configurar o solucionar problemas de su Skype de topología de servidores de negocio.

- [Asistente para la implementación](#deployment-wizard)
- [Generador de topologías](#topology-builder) 
- [Panel de control de Skype Empresarial Server](#skype-for-business-server-control-panel)
- [Shell de administración de Skype Empresarial Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Asistente para la implementación

Use el procedimiento siguiente para iniciar el Asistente para implementación localmente y agregar o quitar archivos de componentes.

**Para iniciar el Skype para el Asistente para la implementación de servidor de negocio**

1. Inicie sesión en el equipo donde está instalado el Skype para el Asistente para la implementación de Business Server como miembro del grupo Administradores del dominio y del grupo RTCUniversalServerAdmins.
2. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para el Asistente para la implementación de servidor de negocio**.


## <a name="topology-builder"></a>Generador de topologías 

Use el procedimiento siguiente para abrir el generador de topología para definir los servidores que desea implementar en su Skype de topología de servidores de negocio.

**Para abrir el Skype para Business Server Topology Builder diseñar la topología**

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Puede definir una topología mediante una cuenta que sea miembro del grupo de usuarios locales, pero para leer, publicar o habilitar una topología, que es necesario para instalar Skype para Business Server en un servidor, debe usar una cuenta que sea miembro del grupo Administradores de dominio y ésimo grupo de RTCUniversalServerAdmins e y que tiene permisos de control total (es decir, leer, escribir y modificar) en el recurso compartido de archivos que se va a usar para el almacén de archivos de archivado para que el generador de topología pueda configurar la lista de control de acceso discrecional requerido ( Las DACL), o una cuenta con derechos de usuario equivalentes.
 
2. Inicie el generador: Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Business Server Topology Builder**.

## <a name="skype-for-business-server-control-panel"></a>Panel de control de Skype Empresarial Server 

Use uno de los procedimientos siguientes para abrir el Skype para el Panel de Control de servidor empresarial para administrar la configuración de servidores, los usuarios, clientes y dispositivos en su entorno.

> [!NOTE]
> Puede usar una cuenta de usuario que se asigna al rol CsAdministrator para llevar a cabo cualquier tarea en el Skype para el Panel de Control de servidor empresarial. Puede usar otros roles para iniciar sesión en el Skype para el Panel de Control de servidor empresarial para llevar a cabo tareas de administración específicas, dependen de la tarea que necesita realizar. Por ejemplo, puede usar CSArchivingAdministrator para administrar el archivado en el Skype para el Panel de Control de servidor empresarial. Para obtener información detallada acerca de las funciones, consulte [Planning for control de acceso basado en roles](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obtener información detallada acerca de las funciones que puede usar para realizar una tarea específica, consulte la documentación de la tarea. 

**Para abrir el Skype para el Panel de Control de Business Server desde cualquier equipo dentro de la organización del firewall**

1. Desde una cuenta de usuario que se asigna al rol CsAdministrator o de otro rol que tiene derechos de usuario adecuados y los permisos para la tarea que se debe realizar, inicie sesión en cualquier equipo en la implementación interna con una resolución de pantalla mínima de 1024 x 768.

    > [!IMPORTANT]
    > Si ha configurado un localizador de administración simple identificador uniforme de recursos (URL), puede obtener acceso a la Skype para Panel de Control de servidor empresarial desde un explorador de Internet que se ejecuta en cualquier equipo dentro del firewall de la organización. Para obtener información detallada acerca de cómo configurar la dirección URL de administración sencilla, consulte [Planning for simple URLs](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) y [Editar o configurar direcciones URL sencillas](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración de su organización.

**Para abrir el Skype para el Panel de Control de Business Server en un equipo que ejecuta Skype para Business Server**

1. Desde una cuenta de usuario que sea miembro del rol CsAdministrator o de otro rol que tiene derechos de usuario adecuados y los permisos para la tarea que se debe realizar, inicie sesión en un equipo en el que ha instalado Skype para Business Server o, como mínimo , el Skype para herramientas administrativas de Business Server. Para establecer la configuración, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.
2. Iniciar Skype para el Panel de Control de Business Server: haga clic en **Inicio**, haga clic en **Todos los programas**, elija **Herramientas administrativas**, elija **Skype para Business Server**y, a continuación, haga clic en **Skype para el Panel de Control de servidor empresarial**.

## <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server 

Use el procedimiento siguiente para abrir la Skype para Shell de administración de servidor empresarial para administrar los servidores, los usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.

> [!NOTE]
> Puede usar una cuenta de usuario que se asigna al rol CsAdministrator para realizar cualquier tarea en el Skype de Shell de administración de servidor empresarial. Puede iniciar sesión con otras funciones para realizar tareas de administración específicas, según la tarea que necesita realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar los cmdlets relacionados con la administración de archivado. Para obtener información detallada acerca de las funciones, consulte [Planning for control de acceso basado en roles](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obtener información detallada acerca de las funciones que puede usar para ejecutar un cmdlet específico, consulte la documentación para el cmdlet.<br/><br/>También puede ejecutar ciertos cmdlets mediante una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, según el cmdlet. 

**Para abrir Skype para Shell de administración de servidor empresarial**

Si abre una ventana de Windows PowerShell en lugar de la Skype para Shell de administración de servidor empresarial, de forma predeterminada no se puede ejecutar el Skype para cmdlets de Business Server. Para ejecutar la Skype para Business Server cmdlets de Windows PowerShell, escriba lo siguiente en el símbolo del sistema de Windows PowerShell:

`Import-Module Lync`

Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
