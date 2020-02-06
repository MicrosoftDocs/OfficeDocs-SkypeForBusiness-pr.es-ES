---
title: Instalar y abrir herramientas administrativas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En este tema se describe cómo instalar y abrir las herramientas administrativas necesarias para implementar y administrar Skype empresarial.
ms.openlocfilehash: c720aba3998df8742406f4c9954f523b20e9af5f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816559"
---
# <a name="install-and-open-administrative-tools"></a>Instalar y abrir herramientas administrativas

En este tema se describe cómo instalar las herramientas administrativas necesarias para implementar y administrar Skype empresarial Server. Las herramientas administrativas se instalan de forma predeterminada en todos los servidores que ejecuten Skype empresarial Server. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Le recomendamos encarecidamente que instale las herramientas administrativas en un equipo del mismo dominio o bosque que la implementación de Skype empresarial Server que está creando para asegurarse de que los pasos de preparación de los servicios de dominio de Active Directory ya están completados. que le permite usar las herramientas administrativas en ese equipo más adelante para publicar su topología. Además, asegúrese de revisar los requisitos necesarios antes de instalar o usar las herramientas administrativas de Skype empresarial Server. Consulte la documentación de los requisitos en [Skype empresarial server 2019](../../SfBServer2019/plan/system-requirements.md) o [skype empresarial Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Si su organización requiere que encuentre Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Skype empresarial Server en el cuadro de diálogo Configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Skype empresarial Server también se implementarán en esta unidad. 

## <a name="to-install-the-administrative-tools"></a>Para instalar las herramientas administrativas

1. Inicie sesión como administrador local (requisito mínimo) en el equipo en el que desea instalar las herramientas administrativas. Si ha iniciado sesión como un usuario estándar en Windows y el control de cuentas de usuario (UAC) está habilitado, se le solicitará el administrador local o un nombre de usuario y una contraseña de dominio equivalente.
2. Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \Setup\amd64\Setup.exe.
3. Si se le pide que instale el distribuible de Microsoft Visual C++, haga clic en **sí**.
4. En la página Ubicación de la instalación, haga clic en **Aceptar**. Cambie esta ruta de acceso a otra ubicación o unidad si necesita tener los archivos instalados en otra ubicación.

    > [!Important]
    > Si su organización requiere que encuentre Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Skype empresarial Server en el cuadro de diálogo Configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Skype empresarial Server también se implementarán en esta unidad. 

5. En la página contrato de licencia para el usuario final, revise los términos de licencia **, haga clic en Acepto y**, después, haga clic en **Aceptar**. Este paso es necesario para poder continuar.
6. En la página Asistente para la implementación, haga clic en **instalar herramientas de administrador**. 
7. Cuando la instalación finalice correctamente, haga clic en **salir**.

Use los procedimientos siguientes para abrir herramientas administrativas para implementar, configurar o solucionar problemas de la topología de Skype empresarial Server.

- [Asistente para la implementación](#deployment-wizard)
- [Generador de topologías](#topology-builder) 
- [Panel de control de Skype Empresarial Server](#skype-for-business-server-control-panel)
- [Shell de administración de Skype Empresarial Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Asistente para la implementación

Use el siguiente procedimiento para iniciar el Asistente para la implementación de forma local y agregar o quitar archivos de componentes.

**Para iniciar el Asistente para la implementación de Skype empresarial Server**

1. Inicie sesión en el equipo donde está instalado el Asistente para la implementación de Skype empresarial Server como miembro del grupo administradores de dominio y el grupo RTCUniversalServerAdmins.
2. Haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, a continuación, haga clic en Asistente para la **implementación de Skype empresarial Server**.


## <a name="topology-builder"></a>Generador de topologías 

Use el siguiente procedimiento para abrir el generador de topologías y definir los servidores que desea implementar en la topología de servidor de Skype empresarial.

**Para abrir el generador de topologías de Skype empresarial Server para diseñar la topología**

1. Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para leer, publicar o habilitar una topología, lo cual es necesario para instalar Skype empresarial Server en un servidor, debe usar una cuenta que sea miembro del grupo de administradores de dominio y de TH RTCUniversalServerAdmins Group, y que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que va a usar para el almacén de archivos de almacenamiento para que Topology Builder pueda configurar la lista de control de acceso discrecional requerida ( DACL) o una cuenta con derechos de usuario equivalentes.
 
2. Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Skype empresarial Server**y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.

## <a name="skype-for-business-server-control-panel"></a>Panel de control de Skype Empresarial Server 

Use uno de los procedimientos siguientes para abrir el panel de control de Skype empresarial Server para administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el panel de control de Skype empresarial Server. Puede usar otros roles para iniciar sesión en el panel de control de Skype empresarial Server y realizar tareas de administración específicas, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para administrar el archivado en el panel de control de Skype empresarial Server. Para obtener más información sobre los roles, consulte [planificación de control de acceso basado en roles](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obtener más información sobre los roles que puede usar para realizar una tarea específica, consulte la documentación de la tarea. 

**Para abrir el panel de control de Skype empresarial Server desde cualquier equipo del firewall de su organización**

1. Desde una cuenta de usuario que tenga asignada la función CsAdministrator u otro rol que tenga los permisos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en cualquier equipo de la implementación interna con una resolución de pantalla mínima de 1024 x 768.

    > [!IMPORTANT]
    > Si ha configurado un localizador de recursos uniforme (URL) de administración, puede acceder al panel de control de Skype empresarial Server desde un explorador de Internet que se esté ejecutando en cualquier equipo del firewall de su organización. Para obtener detalles sobre la configuración de la dirección URL simple de administración, consulte [planificación de direcciones URL simples](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) y [edición o configuración de direcciones URL simples](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administrador configurada para su organización.

**Para abrir el panel de control de Skype empresarial Server en un equipo con Skype empresarial Server**

1. Desde una cuenta de usuario que sea miembro de la función CsAdministrator u otro rol que tenga los derechos de usuario y permisos adecuados para la tarea que se va a realizar, inicie sesión en un equipo en el que tenga instalado Skype empresarial Server o, como mínimo, , las herramientas administrativas de Skype empresarial Server. Para configurar las opciones, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.
2. Inicie el panel de control de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, seleccione **herramientas administrativas**, seleccione **Skype empresarial Server**y, a continuación, haga clic en **Panel de control de Skype empresarial Server**.

## <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server 

Use el siguiente procedimiento para abrir el shell de administración de Skype empresarial para administrar servidores, usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el shell de administración de Skype empresarial Server. Puede iniciar sesión con otros roles para realizar tareas de administración específicas, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con la administración de archivado. Para obtener más información sobre los roles, consulte [planificación de control de acceso basado en roles](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obtener más información sobre los roles que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.<br/><br/>También puede ejecutar determinados cmdlets usando una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins o RTCUniversalReadOnlyAdmins, según el cmdlet. 

**Para abrir el shell de administración de Skype empresarial Server**

Si abre una ventana de Windows PowerShell en lugar del shell de administración de Skype empresarial Server, de forma predeterminada, no podrá ejecutar los cmdlets de Skype empresarial Server. Para ejecutar los cmdlets de Skype empresarial Server desde Windows PowerShell, escriba lo siguiente en el símbolo del sistema de Windows PowerShell:

`Import-Module Lync`

Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, por último, en **consola de administración de Skype empresarial Server**.
