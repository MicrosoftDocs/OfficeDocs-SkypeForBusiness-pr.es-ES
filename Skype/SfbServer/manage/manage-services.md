---
title: Administrar servicios para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: En este artículo se describe cómo administrar los servicios que se ejecutan en una topología de servidor de Skype empresarial.
ms.openlocfilehash: 76628840c37bdb0eb85d58887d8bfdcedd20f27c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991675"
---
# <a name="manage-services-for-skype-for-business-server"></a>Administrar servicios para Skype empresarial Server

En este artículo se describe cómo administrar los servicios que se ejecutan en una topología de servidor de Skype empresarial.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Ver una lista de equipos con Skype empresarial Server
<a name="view_list"> </a>

Puede usar el panel de control de Skype empresarial Server para ver una lista de todos los equipos que ejecutan Skype empresarial Server en su topología y ver el estado del servicio de cada uno. Puede ordenar la lista por equipo, grupo o sitio. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Para ver una lista de equipos con Skype empresarial Server

1. Desde una cuenta de usuario asignada a cualquiera de las funciones administrativas predefinidas para Skype empresarial Server, inicie sesión en cualquier equipo de su implementación interna. Para más información sobre los roles administrativos predefinidos disponibles en Skype empresarial Server, consulte **planificación de control de acceso basado en roles**.   
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.   
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.   
4. En la página **Estado** , realice una de las siguientes acciones según sea necesario:
   - Ordene la lista haciendo clic en el encabezado de la columna **equipo**, **Grupo**de servidores o **sitio** y, a continuación, haga clic en la flecha arriba o la flecha abajo. 
   - Haga clic en **Actualizar** para ver la lista más actualizada.  
   - Busque un equipo específico escribiendo el nombre del equipo en el campo de búsqueda.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Ver el estado de los servicios que se ejecutan en un servidor de Skype empresarial
<a name="view-status"> </a>

Puede usar el panel de control de Skype empresarial Server para ver todos los servicios que se ejecutan en un equipo específico de su topología de servidor de Skype empresarial y ver el estado de cada servicio.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para ver el estado de los servicios que se ejecutan en un equipo

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **topología**. 
4. En la página **Estado** , ordene o busque la lista, según sea necesario, para buscar el equipo que le interesa y, a continuación, haga clic en el nombre del equipo.
5. Siga uno de estos pasos:
   - Para ver el estado más reciente de los servicios que se ejecutan en el equipo, haga clic en **obtener estado del servicio**.
   - Para ver una lista de los servicios específicos que se ejecutan en el equipo y el estado de cada servicio, haga clic en **propiedades**y, a continuación, haga clic en **cerrar** para volver a la lista.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Ver el estado del servicio con cmdlets de Windows PowerShell

También puede ver el estado del servicio con Windows PowerShell y el cmdlet **Get-CsWindowsService** . Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.
  
### <a name="to-view-service-status"></a>Para ver el estado del servicio

Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Este comando devolverá información similar a la siguiente:
  
|**RoleName**|**Statu**|
|:-----|:-----|
|W3SVC  <br/> |Utilicen  <br/> |
|{CentralManagement}  <br/> | Utilicen <br/> |
|{ClsAgent}  <br/> |Utilicen  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |Utilicen  <br/> |
|{ApplicationServer}  <br/> |Utilicen  <br/> |
|{ConferencingServer}  <br/> |Utilicen  <br/> |
|{MediationServer}  <br/> |Utilicen  <br/> |
   
Para obtener más información, vea [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Ver los detalles de un servicio
<a name="view_details"> </a>

Puede usar el panel de control de Skype empresarial Server para ver los detalles de cada servicio que se ejecuta en un equipo específico de su topología. Puede ver el estado de cada servicio y los detalles como las bases de datos, los puertos y los servicios dependientes asociados.
  
### <a name="to-view-details-for-a-service"></a>Para ver los detalles de un servicio

1. Desde una cuenta de usuario asignada a cualquiera de las funciones administrativas predefinidas para Skype empresarial Server, inicie sesión en cualquier equipo de su implementación interna. Para más información sobre los roles administrativos predefinidos disponibles en Skype empresarial Server, consulte **planificación de control de acceso basado en roles**.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.
4. En la página **Estado** , ordene o busque en la lista y, a continuación, haga clic en el equipo que desea ver.
5. Haga clic en **propiedades**.
6. En la ventana **Ver detalles del equipo** , ordene la lista de servicios, si es necesario, y haga clic en el servicio que desea ver.
7. Realice una de las siguientes acciones según sea necesario:
   - Para ver el estado más reciente de ese servicio específico, haga clic en **obtener estado del servicio**.
   - Para ver los detalles de ese servicio específico, haga clic en **propiedades** y, a continuación, en **cerrar**.
   - Para volver a la lista de todos los equipos de su topología, haga clic en **cerrar**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Iniciar o detener los servicios de Skype empresarial
<a name="StartStop"> </a>

Puede usar el panel de control de Skype empresarial Server para iniciar o detener todos los servicios de Skype empresarial Server que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Para iniciar o detener todos los servicios de Skype empresarial en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. . Puede determinar si se le ha asignado el rol de CsServerAdministrator o el rol de RBAC de CsAdministrator ejecutando un comando similar al siguiente:
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.
4. En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **acción**.
6. Haga clic en **iniciar todos los servicios** o en **detener todos los servicios**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Para iniciar o detener un servicio específico

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.
4. En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **propiedades**.
6. Ordene la lista de servicios, si es necesario, y haga clic en el servicio que desea iniciar o detener.
7. Haga clic en **acción**.
8. Haga clic en **Iniciar servicio** o **Detener servicio**.
9. Haga clic en **Cerrar**.
    
## <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios
<a name="prevent_session"> </a>

Puede usar el panel de control de Skype empresarial Server para evitar nuevas sesiones para todos los servicios de Skype empresarial Server que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio específico de Skype empresarial Server.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Para evitar nuevas sesiones para todos los servicios de Skype empresarial en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.
4. En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que ejecuta los servicios para los que desea evitar nuevas sesiones y, a continuación, haga clic en ella.
5. Haga clic en **acción**.
6. Haga clic en **evitar nuevas sesiones para todos los servicios**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para evitar nuevas sesiones para un servicio específico

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, en **Estado**.
4. En la página **Estado** , ordene o busque en la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él. 
5. Haga clic en **propiedades**.
6. Si es necesario, ordene la lista de servicios y haga clic en el servicio para el que desea evitar nuevas sesiones.
7. Haga clic en **acción**.
8. Haga clic en **evitar nuevas sesiones para el servicio**.
9. Haga clic en **Cerrar**.
    

