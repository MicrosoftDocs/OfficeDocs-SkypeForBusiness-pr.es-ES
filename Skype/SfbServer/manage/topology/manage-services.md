---
title: Administrar los servicios de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Obtenga información sobre cómo ver el estado de los servicios, iniciar y detener los servicios e impedir sesiones para servicios.
ms.openlocfilehash: 78d8b2a16204585a0ff403867617ff709666c4f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911969"
---
# <a name="manage-services-in-skype-for-business-server"></a>Administrar los servicios de Skype para Business Server

Puede usar el Skype para el Panel de Control de servidor empresarial para ver una lista de todos los equipos que ejecutan Skype para Business Server en la topología, ver el estado de los servicios, iniciar o detener servicios e impedir sesiones para servicios.

- [Ver una lista de los equipos que ejecutan Skype para Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Ver el estado de los servicios que se ejecutan en un equipo de Skype para la empresa](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Inicio o detención de Skype para servicios de negocios](#start-or-stop-skype-for-business-services)
- [Impedir sesiones para servicios](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Ver una lista de los equipos que ejecutan Skype para Business Server

Use el Skype para el Panel de Control de servidor empresarial para ver una lista de todos los equipos que ejecutan Skype para la empresa en su topología y ver el estado de servicio de cada uno. Puede ordenar la lista por equipo, grupo o sitio. 

1. Desde una cuenta de usuario que se asigna a cualquiera de las funciones administrativas predefinidas para Skype para Business Server, inicie sesión en cualquier equipo en la implementación interna. Para obtener más información, vea [control de acceso basado en roles (RBAC) para Skype para Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control de servidor empresarial, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. En la página Estado, realice una de las siguientes opciones según sea necesario:
    - Ordene la lista haciendo clic en el **equipo**, el **grupo de servidores**o el encabezado de columna de **sitio** y, a continuación, al hacer clic en la flecha arriba o flecha abajo.
    - Haga clic en **Actualizar** para ver la lista más actualizada.
    - Búsqueda de un equipo específico, escriba el nombre del equipo en el campo de búsqueda.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Ver el estado de los servicios que se ejecutan en un equipo de Skype para la empresa

Use el Skype para el Panel de Control de servidor empresarial para ver todos los servicios que se ejecutan en un equipo específico en su Skype de topología de servidores de negocio y ver el estado de cada servicio.

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control de servidor empresarial, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **topología**.
4. En la página Estado, ordenar o buscar en la lista, según sea necesario, para encontrar el equipo que le interesa, y, a continuación, haga clic en el nombre del equipo.
5. Realice una de las siguientes opciones:
    - Para ver el estado más reciente de servicios que se ejecutan en el equipo, haga clic en **obtener estado del servicio**.
    - Para ver una lista de servicios específicos que se ejecutan en el equipo y el estado de cada servicio, haga clic en **Propiedades**y, a continuación, haga clic en **Cerrar** para volver a la lista.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Visualización del estado de servicio mediante el uso de Cmdlets de Windows PowerShell

También puede ver el estado de los servicios mediante el uso de Windows PowerShell y el cmdlet Get-CsWindowsService. Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información, vea [Skype para Shell de administración de servidor empresarial](../management-shell.md).

**Para ver el estado de servicio**

Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

Este comando devolverá información similar a la siguiente:

```
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

Para obtener información detallada, vea [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Inicio o detención de Skype para servicios de negocios

Use el Skype para el Panel de Control de servidor empresarial para iniciar o detener todos los Skype para servicios de Business Server que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Iniciar o detener todos los Skype para servicios de Business Server en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server . Puede determinar si se le ha asignado el CsServerAdministrator o un rol RBAC CsAdministrator mediante la ejecución de un comando similar al siguiente:

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control de servidor empresarial, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. En la página Estado, ordenación o búsqueda a través de la lista según sea necesario para encontrar el equipo que ejecuta los servicios que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **acción**.
6. Haga clic en **iniciar todos los servicios** o **Detener todos los servicios**.

### <a name="start-or-stop-a-specific-service"></a>Iniciar o detener un servicio específico

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control de servidor empresarial, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. En la página, ordenación o búsqueda a través de la lista según sea necesario para encontrar el equipo que ejecuta el servicio de estado que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **Propiedades**.
6. Ordenar la lista de servicios, si es necesario y haga clic en el servicio que desea iniciar o detener.
7. Haga clic en **acción**.
8. Haga clic en **Iniciar servicio** o **Detener el servicio**.
9. Haga clic en **Cerrar**.


## <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios

Use el Skype para el Panel de Control para evitar sesiones nuevas para todas la Skype para servicios de Business Server que se ejecutan en un equipo específico o para evitar que las sesiones nuevas para un servicio específico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Evitar sesiones nuevas para todos los Skype para servicios de Business Server en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control de servidor empresarial, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página Estado, ordenación o búsqueda a través de la lista como sea necesario para encontrar el equipo que ejecuta los servicios para la que desea impedir nuevas sesiones y, a continuación, haga clic en él.
5. Haga clic en **acción**.
6. Haga clic en **evitar sesiones nuevas en todos los servicios**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Impedir sesiones nuevas para un servicio específico

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de Control. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar el Skype para el Panel de Control de servidor empresarial, consulte [Install and open herramientas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. En la barra de navegación izquierda, haga clic en **Topología ** y, a continuación, en **Estado **. 
4. Haga clic en **Propiedades**.
5. Ordenar la lista de servicios, si es necesario y haga clic en el servicio para la que desea impedir nuevas sesiones.
6. Haga clic en **acción**.
7. Haga clic en **evitar sesiones nuevas para el servicio**.
8. Haga clic en **Cerrar**.
