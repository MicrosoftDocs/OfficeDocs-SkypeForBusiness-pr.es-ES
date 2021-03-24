---
title: Administrar servicios en Skype Empresarial Server
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
description: Obtenga información sobre cómo ver el estado del servicio, iniciar y detener servicios e impedir sesiones para los servicios.
ms.openlocfilehash: 34228a7e1b8cf9ef044d2f1f15c4b1219f795d79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103186"
---
# <a name="manage-services-in-skype-for-business-server"></a>Administrar servicios en Skype Empresarial Server

Puede usar el Panel de control de Skype Empresarial Server para ver una lista de todos los equipos que ejecutan Skype Empresarial Server en la topología, ver el estado de los servicios, iniciar o detener servicios y evitar sesiones para los servicios.

- [Ver una lista de equipos que ejecutan Skype Empresarial Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Ver el estado de los servicios que se ejecutan en un equipo en Skype Empresarial](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Iniciar o detener servicios de Skype Empresarial](#start-or-stop-skype-for-business-services)
- [Impedir sesiones para servicios](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Ver una lista de equipos que ejecutan Skype Empresarial Server

Use el Panel de control de Skype Empresarial Server para ver una lista de todos los equipos que ejecutan Skype Empresarial en la topología y ver el estado del servicio de cada uno. Puede ordenar la lista por PC, grupo de servidores o sitio. 

1. Desde una cuenta de usuario asignada a cualquiera de los roles administrativos predefinidos para Skype Empresarial Server, inicie sesión en cualquier equipo de la implementación interna. Para obtener más información, vea Control de acceso basado en [roles (RBAC) para Skype Empresarial Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
4. En la página Estado, realice una de las siguientes acciones según sea necesario:
    - Ordene la lista haciendo clic en el encabezado de columna **Equipo**, **Grupo de servidores** o **Sitio** y después haga clic en la flecha arriba o en la flecha abajo.
    - Haga clic en **Actualizar** para ver la lista más actualizada.
    - Para buscar un equipo específico, escriba el nombre del equipo en el campo de búsqueda.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Ver el estado de los servicios que se ejecutan en un equipo en Skype Empresarial

Use el Panel de control de Skype Empresarial Server para ver todos los servicios que se ejecutan en un equipo específico de la topología de Skype Empresarial Server y ver el estado de cada servicio.

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología**.
4. En la página Estado, ordena o busca en la lista, según sea necesario, para buscar el equipo que te interesa y, a continuación, haz clic en el nombre del equipo.
5. Realice una de las siguientes acciones:
    - Para ver el estado más reciente de los servicios que se ejecutan en el equipo, haga clic en **Obtener estado del servicio**.
    - Para ver una lista de servicios específicos que se ejecutan en el  equipo y el estado de cada servicio, haga clic en Propiedades **y,** a continuación, haga clic en Cerrar para volver a la lista.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Visualización del estado del servicio mediante Windows PowerShell cmdlets

También puede ver el estado del servicio mediante Windows PowerShell y el cmdlet Get-CsWindowsService. Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información, vea [Shell de administración de Skype Empresarial Server](../management-shell.md).

**Para ver el estado del servicio**

Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:

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

Para obtener más información, [vea Get-CsWindowsService](/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Iniciar o detener servicios de Skype Empresarial

Use el Panel de control de Skype Empresarial Server para iniciar o detener todos los servicios de Skype Empresarial Server que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Iniciar o detener todos los servicios de Skype Empresarial Server en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server. Puede determinar si se le ha asignado el rol RBAC CsServerAdministrator o CsAdministrator ejecutando un comando similar al siguiente:

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
4. En la página Estado, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta los servicios que desea iniciar o detener, y haga clic en él.
5. Haga clic en **Acción**.
6. Haga clic en **Iniciar todos los servicios** o **Detener todos los servicios**.

### <a name="start-or-stop-a-specific-service"></a>Iniciar o detener un servicio específico

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
4. En la página Estado, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.
5. Haga clic en **Propiedades**.
6. Ordene la lista de servicios si es necesario y haga clic en el servicio que desea iniciar o detener.
7. Haga clic en **Acción**.
8. Haga clic en **Iniciar servicio** o **Detener servicio**.
9. Haga clic en **Cerrar**.


## <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios

Use el Panel de control de Skype Empresarial para evitar nuevas sesiones para todos los servicios de Skype Empresarial Server que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio específico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Impedir sesiones nuevas para todos los servicios de Skype Empresarial Server en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología** y después en **Estado**.
4. En la página Estado , clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.
5. Haga clic en **Acción**.
6. Haga clic en **Evitar sesiones nuevas en todos los servicios**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Impedir nuevas sesiones para un servicio específico

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control. Para obtener información detallada sobre los diferentes métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, vea [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
4. Haga clic en **Propiedades**.
5. Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.
6. Haga clic en **Acción**.
7. Haga clic en **Evitar sesiones nuevas en el servicio**.
8. Haga clic en **Cerrar**.