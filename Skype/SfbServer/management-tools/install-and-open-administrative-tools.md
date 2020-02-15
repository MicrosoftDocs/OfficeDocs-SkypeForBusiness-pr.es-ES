---
title: Instalación y apertura de herramientas administrativas
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
ms.openlocfilehash: b2d06d14263174229d35ff2e5108574296bb5034
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031074"
---
# <a name="install-and-open-administrative-tools"></a>Instalación y apertura de herramientas administrativas

En este tema se describe cómo instalar las herramientas administrativas necesarias para implementar y administrar Skype empresarial Server. Las herramientas administrativas se instalan de forma predeterminada en cada servidor que ejecuta Skype empresarial Server. Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas. Se recomienda instalar las herramientas administrativas en un equipo que se encuentre en el mismo dominio o bosque que la implementación de Skype empresarial Server que está creando para garantizar que los pasos de preparación de los servicios de dominio de Active Directory ya se hayan completado. lo que le permite usar las herramientas administrativas en ese equipo más adelante para publicar la topología. Además, asegúrese de revisar los requisitos necesarios antes de instalar o usar las herramientas administrativas de Skype empresarial Server. Consulte la documentación de requisitos en [Skype empresarial server 2019](../../SfBServer2019/plan/system-requirements.md) o [skype empresarial Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Si su organización requiere Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Skype empresarial Server en el cuadro de diálogo de configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Skype empresarial Server también se implementarán en esta unidad. 

## <a name="to-install-the-administrative-tools"></a>Para instalar las herramientas administrativas

1. Inicie sesión como administrador local (requisito mínimo) en el equipo donde desee instalar las herramientas administrativas. Si ha iniciado sesión como usuario estándar en Windows y el control de cuentas de usuario (UAC) está habilitado, se le pedirá que indique el administrador local o un nombre de usuario y una contraseña equivalentes a los dominios.
2. Busque los medios de instalación en el equipo y, a continuación, haga doble clic en \Setup\amd64\Setup.exe.
3. Si se le pide que instale el paquete distribuible de Microsoft Visual C++, haga clic en **sí**.
4. En la página ubicación de instalación, haga clic en **Aceptar**. Cambie esta ruta de acceso a otra ubicación o unidad si necesita que los archivos se instalen en una ubicación diferente.

    > [!Important]
    > Si su organización requiere Internet Information Services (IIS) y todos los servicios web en una unidad distinta de la unidad del sistema, puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Skype empresarial Server en el cuadro de diálogo de configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Skype empresarial Server se implementarán también en esta unidad. 

5. En la página Contrato de licencia para el usuario final, revise los términos de la licencia, haga clic en **Acepto** y, a continuación, haga clic en **Aceptar**. Este paso es necesario para poder continuar
6. En la página Asistente para la implementación, haga clic en **instalar herramientas de administrador**. 
7. Cuando finalice la instalación correctamente, haga clic en **Salir**.

Use los siguientes procedimientos para abrir las herramientas administrativas para implementar, configurar o solucionar problemas de la topología de Skype empresarial Server.

- [Asistente para implementación](#deployment-wizard)
- [Topology Builder](#topology-builder) 
- [Panel de control de Skype Empresarial Server](#skype-for-business-server-control-panel)
- [Shell de administración de Skype Empresarial Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Asistente para implementación

Use el siguiente procedimiento para iniciar el Asistente para la implementación de forma local a fin de agregar o quitar archivos de componentes.

**Para iniciar el Asistente para la implementación de Skype empresarial Server**

1. Inicie sesión en el equipo en el que está instalado el Asistente para la implementación de Skype empresarial Server como miembro del grupo administradores del dominio y el grupo RTCUniversalServerAdmins.
2. Haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server**y, a continuación, haga clic en **Asistente para la implementación de Skype empresarial Server**.


## <a name="topology-builder"></a>Topology Builder 

Use el siguiente procedimiento para abrir el generador de topologías y definir los servidores que desea implementar en su topología de Skype empresarial Server.

**Para abrir el generador de topologías de Skype empresarial Server para diseñar la topología**

1. Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para leer, publicar o habilitar una topología, lo cual es necesario para instalar Skype empresarial Server en un servidor, debe usar una cuenta que sea miembro del grupo administradores de dominio y de un TH RTCUniversalServerAdmins grupo y que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que se va a usar para el almacén de archivos de archivado, de modo que el generador de topologías pueda configurar la lista de control de acceso discrecional requerida ( DACL) o una cuenta con derechos de usuario equivalentes.
 
2. Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Skype empresarial Server**y, a continuación, haga clic en **generador de topologías de Skype empresarial Server**.

## <a name="skype-for-business-server-control-panel"></a>Panel de control de Skype Empresarial Server 

Use uno de los siguientes procedimientos para abrir el panel de control de Skype empresarial Server para administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el panel de control de Skype empresarial Server. Puede usar otros roles para iniciar sesión en el panel de control de Skype empresarial Server y realizar tareas de administración específicas, en función de la tarea que necesite realizar. Por ejemplo, puede usar rol csarchivingadministrator para administrar el archivado en el panel de control de Skype empresarial Server. Para obtener más información sobre los roles, consulte [Planning for role-based access control](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Para obtener información sobre las funciones que puede usar para realizar una tarea específica, consulte la documentación de la tarea. 

**Para abrir el panel de control de Skype empresarial Server desde cualquier equipo dentro del firewall de la organización**

1. Desde una cuenta de usuario asignada al rol CsAdministrator o a otro rol que tenga los derechos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en cualquier equipo en la implementación interna con una resolución de pantalla mínima de 1024 x 768.

    > [!IMPORTANT]
    > Si ha configurado una dirección URL sencilla de administración, puede tener acceso al panel de control de Skype empresarial Server desde un explorador de Internet que se ejecute en cualquier equipo del firewall de la organización. Para obtener más información sobre cómo configurar la dirección URL sencilla de administración, consulte [Planning for simple URL](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) y [Edit or configure simple URL](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx). 

2. Abra una ventana del explorador y escriba la dirección URL de administración configurada para la organización.

**Para abrir el panel de control de Skype empresarial Server en un equipo que ejecuta Skype empresarial Server**

1. Desde una cuenta de usuario que sea miembro de la función CsAdministrator o de otro rol que tenga los derechos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en un equipo en el que haya instalado Skype empresarial Server o, como mínimo, , las herramientas administrativas de Skype empresarial Server. Para configurar las opciones, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.
2. Inicie el panel de control de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, seleccione **herramientas administrativas**, seleccione **Skype empresarial Server**y, a continuación, haga clic en **Panel de control de Skype empresarial Server**.

## <a name="skype-for-business-server-management-shell"></a>Shell de administración de Skype Empresarial Server 

Use el siguiente procedimiento para abrir el shell de administración de Skype empresarial Server para administrar servidores, usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.

> [!NOTE]
> Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el shell de administración de Skype empresarial Server. Puede iniciar sesión con otras funciones para realizar tareas específicas de administración, en función de la tarea que necesite realizar. Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con las administración de archivado. Para obtener más información sobre los roles, consulte [Planning for role-based access control](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx). Para obtener información sobre las funciones que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.<br/><br/>También puede ejecutar ciertos cmdlets mediante una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, o RTCUniversalReadOnlyAdmins, según el cmdlet. 

**Para abrir el shell de administración de Skype empresarial Server**

Si abre una ventana de Windows PowerShell en lugar del shell de administración de Skype empresarial Server, de forma predeterminada, no podrá ejecutar los cmdlets de Skype empresarial Server. Para ejecutar los cmdlets de Skype empresarial Server desde dentro de Windows PowerShell, escriba lo siguiente en el símbolo del sistema de Windows PowerShell:

`Import-Module Lync`

Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial Server**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
