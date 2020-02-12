---
title: Administrar servicios en Skype empresarial Server
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
description: Obtenga información sobre cómo ver el estado del servicio, iniciar y detener servicios, y evitar las sesiones de servicios.
ms.openlocfilehash: da617e386f30469c1b787522f8472d822d02b1e5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888449"
---
# <a name="manage-services-in-skype-for-business-server"></a>Administrar servicios en Skype empresarial Server

Puede usar el panel de control de Skype empresarial Server para ver una lista de todos los equipos que ejecutan Skype empresarial Server en su topología, ver el estado de los servicios, iniciar o detener servicios e impedir sesiones de servicios.

- [Ver una lista de equipos con Skype empresarial Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Ver el estado de los servicios que se ejecutan en un equipo en Skype empresarial](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Iniciar o detener servicios de Skype empresarial](#start-or-stop-skype-for-business-services)
- [Impedir sesiones para servicios](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Ver una lista de equipos con Skype empresarial Server

Use el panel de control de Skype empresarial Server para ver una lista de todos los equipos que están ejecutando Skype empresarial en su topología y ver el estado del servicio de cada uno de ellos. Puede ordenar la lista por equipo, grupo o sitio. 

1. Desde una cuenta de usuario asignada a cualquiera de las funciones administrativas predefinidas para Skype empresarial Server, inicie sesión en cualquier equipo de su implementación interna. Para obtener más información, consulte [control de acceso basado en roles (RBAC) para Skype empresarial Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. En la página Estado, realice una de las siguientes acciones según sea necesario:
    - Ordene la lista haciendo clic en el encabezado de la columna **equipo**, **Grupo**de servidores o **sitio** y, a continuación, haga clic en la flecha arriba o la flecha abajo.
    - Haga clic en **Actualizar** para ver la lista más actualizada.
    - Busque un equipo específico escribiendo el nombre del equipo en el campo de búsqueda.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Ver el estado de los servicios que se ejecutan en un equipo en Skype empresarial

Use el panel de control de Skype empresarial Server para ver todos los servicios que se están ejecutando en un equipo específico de su topología de Skype empresarial Server y ver el estado de cada servicio.

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **topología**.
4. En la página Estado, ordene o busque la lista, según sea necesario, para buscar el equipo que le interesa y, a continuación, haga clic en el nombre del equipo.
5. Realice una de las siguientes acciones:
    - Para ver el estado más reciente de los servicios que se ejecutan en el equipo, haga clic en **obtener estado del servicio**.
    - Para ver una lista de los servicios específicos que se ejecutan en el equipo y el estado de cada servicio, haga clic en **propiedades**y, a continuación, haga clic en **cerrar** para volver a la lista.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Ver el estado del servicio con cmdlets de Windows PowerShell

También puede ver el estado del servicio con Windows PowerShell y el cmdlet Get-CsWindowsService. Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información, consulte [Shell de administración de Skype empresarial Server](../management-shell.md).

**Para ver el estado del servicio**

Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Este comando devolverá información similar a la siguiente:

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

Para obtener más información, vea [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Iniciar o detener servicios de Skype empresarial

Use el panel de control de Skype empresarial Server para iniciar o detener todos los servicios de Skype empresarial Server que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Iniciar o detener todos los servicios de Skype empresarial Server en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. . Puede determinar si se le ha asignado el rol de CsServerAdministrator o el rol de RBAC de CsAdministrator ejecutando un comando similar al siguiente:

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. En la página Estado, ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **acción**.
6. Haga clic en **iniciar todos los servicios** o en **detener todos los servicios**.

### <a name="start-or-stop-a-specific-service"></a>Iniciar o detener un servicio específico

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. En la página Estado, ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **propiedades**.
6. Ordene la lista de servicios, si es necesario, y haga clic en el servicio que desea iniciar o detener.
7. Haga clic en **acción**.
8. Haga clic en **Iniciar servicio** o **Detener servicio**.
9. Haga clic en **Cerrar**.


## <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios

Use el panel de control de Skype para empresas para evitar nuevas sesiones para todos los servicios de Skype empresarial Server que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio específico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Evitar nuevas sesiones para todos los servicios de Skype empresarial Server en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.
4. En la página Estado, ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios para los que desea evitar nuevas sesiones y, a continuación, haga clic en ella.
5. Haga clic en **acción**.
6. Haga clic en **evitar nuevas sesiones para todos los servicios**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Evitar nuevas sesiones para un servicio específico

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [instalar y abrir herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. Haga clic en **propiedades**.
5. Si es necesario, ordene la lista de servicios y haga clic en el servicio para el que desea evitar nuevas sesiones.
6. Haga clic en **acción**.
7. Haga clic en **evitar nuevas sesiones para el servicio**.
8. Haga clic en **Cerrar**.
