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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Este artículo describe cómo administrar los servicios que se ejecutan en un Skype de topología de servidores de negocio.
ms.openlocfilehash: d2068f5b485e4beb76016c9cad4388f157fdae97
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898304"
---
# <a name="manage-services-for-skype-for-business-server"></a>Administrar los servicios de Skype para Business Server

Este artículo describe cómo administrar los servicios que se ejecutan en un Skype de topología de servidores de negocio.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Ver una lista de los equipos que ejecutan Skype para Business Server
<a name="view_list"> </a>

Puede usar Skype para el Panel de Control de servidor empresarial para ver una lista de todos los equipos que ejecutan Skype para Business Server en su topología y ver el estado de servicio de cada uno. Puede ordenar la lista por equipo, grupo o sitio. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Para ver una lista de los equipos que ejecutan Skype para Business Server

1. Desde una cuenta de usuario que se asigna a cualquiera de las funciones administrativas predefinidas para Skype para Business Server, inicie sesión en cualquier equipo en la implementación interna. Para obtener información detallada acerca de las funciones administrativas predefinidas disponibles en Skype para Business Server, consulte **Planning for Role-Based Access Control**.   
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.   
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.   
4. En la página **estado** , realice una de las siguientes opciones según sea necesario:
   - Ordene la lista haciendo clic en el **equipo**, el **grupo de servidores**o el encabezado de columna de **sitio** y, a continuación, al hacer clic en la flecha arriba o flecha abajo. 
   - Haga clic en **Actualizar** para ver la lista más actualizada.  
   - Búsqueda de un equipo específico, escriba el nombre del equipo en el campo de búsqueda.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Ver el estado de los servicios que se ejecutan en un Skype para Business server
<a name="view-status"> </a>

Puede usar Skype para el Panel de Control de servidor empresarial para ver todos los servicios que se ejecutan en un equipo específico en su Skype de topología de servidores de negocio y ver el estado de cada servicio.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para ver el estado de los servicios que se ejecutan en un equipo

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3. En la barra de navegación izquierda, haga clic en **topología**. 
4. En la página **estado** , ordenar o buscar en la lista, según sea necesario, para encontrar el equipo que le interesa y, a continuación, haga clic en el nombre del equipo.
5. Siga uno de estos pasos:
   - Para ver el estado más reciente de servicios que se ejecutan en el equipo, haga clic en **obtener estado del servicio**.
   - Para ver una lista de servicios específicos que se ejecutan en el equipo y el estado de cada servicio, haga clic en **Propiedades**y, a continuación, haga clic en **Cerrar** para volver a la lista.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Ver el estado de servicio con los cmdlets de Windows Powershell

También puede ver el estado de los servicios mediante el uso de Windows PowerShell y el cmdlet **Get-CsWindowsService** . Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-view-service-status"></a>Para ver el estado de servicio

Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Este comando devolverá información similar a la siguiente:
  
|**Nombre de rol**|**Estado**|
|:-----|:-----|
|{W3SVC}  <br/> |Ejecuta  <br/> |
|{CentralManagement}  <br/> | Ejecuta <br/> |
|Con {ClsAgent}  <br/> |Ejecuta  <br/> |
|{Registrador, UserServer, EdgeServer}  <br/> |Ejecuta  <br/> |
|{ApplicationServer}  <br/> |Ejecuta  <br/> |
|{ConferencingServer}  <br/> |Ejecuta  <br/> |
|{MediationServer}  <br/> |Ejecuta  <br/> |
   
Para obtener información detallada, vea [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Ver detalles acerca de un servicio
<a name="view_details"> </a>

Puede usar Skype para el Panel de Control de servidor empresarial para ver detalles acerca de cada servicio que se ejecuta en un equipo específico en su topología. Puede ver el estado de cada servicio y obtener información detallada, como las bases de datos asociadas, puertos y servicios dependientes.
  
### <a name="to-view-details-for-a-service"></a>Para ver los detalles para un servicio

1. Desde una cuenta de usuario que se asigna a cualquiera de las funciones administrativas predefinidas para Skype para Business Server, inicie sesión en cualquier equipo en la implementación interna. Para obtener información detallada acerca de las funciones administrativas predefinidas disponibles en Skype para Business Server, consulte **Planning for Role-Based Access Control**.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página **estado** , ordenar o a través de la lista de búsqueda y, a continuación, haga clic en el equipo que desea ver.
5. Haga clic en **Propiedades**.
6. En la ventana **Ver detalles de equipo** , clasifique la lista de servicios, si fuera necesario y haga clic en el servicio que desea ver.
7. Realice una de las siguientes opciones según sea necesario:
   - Para ver el estado más reciente de este servicio en particular, haga clic en **obtener estado del servicio**.
   - Para ver los detalles de este servicio en particular, haga clic en **Propiedades** y, a continuación, haga clic en **Cerrar**.
   - Para volver a la lista de todos los equipos de la topología, haga clic en **Cerrar**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Inicio o detención de Skype para servicios de Business Server
<a name="StartStop"> </a>

Puede usar Skype para el Panel de Control de servidor empresarial para iniciar o detener todos los Skype para servicios de Business Server que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Para iniciar o detener todos los Skype para servicios de negocios en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server . Puede determinar si se le ha asignado el CsServerAdministrator o un rol RBAC CsAdministrator mediante la ejecución de un comando similar al siguiente:
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página de **estado** , la ordenación o la búsqueda a través de la lista según sea necesario para encontrar el equipo que ejecuta los servicios que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **acción**.
6. Haga clic en **iniciar todos los servicios** o **Detener todos los servicios**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Para iniciar o detener un servicio específico

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página de **estado** , la ordenación o la búsqueda a través de la lista según sea necesario para encontrar el equipo que ejecuta el servicio que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **Propiedades**.
6. Ordenar la lista de servicios, si es necesario y haga clic en el servicio que desea iniciar o detener.
7. Haga clic en **acción**.
8. Haga clic en **Iniciar servicio** o **Detener el servicio**.
9. Haga clic en **Cerrar**.
    
## <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios
<a name="prevent_session"> </a>

Puede usar Skype para el Panel de Control de servidor empresarial para evitar sesiones nuevas para todas las Skype para servicios de Business Server que se ejecutan en un equipo específico o para evitar sesiones nuevas para un Skype específico para el servicio de Business Server.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Para evitar que las sesiones de nuevo para todos los Skype para servicios de negocios en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página **estado** , ordenación o búsqueda a través de la lista como sea necesario para encontrar el equipo que ejecuta los servicios para la que desea impedir nuevas sesiones y, a continuación, haga clic en él.
5. Haga clic en **acción**.
6. Haga clic en **evitar sesiones nuevas en todos los servicios**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para evitar que las sesiones nuevas para un servicio específico

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
3. En la barra de navegación izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página de **estado** , la ordenación o la búsqueda a través de la lista según sea necesario para encontrar el equipo que ejecuta el servicio que desea iniciar o detener y, a continuación, haga clic en él. 
5. Haga clic en **Propiedades**.
6. Ordenar la lista de servicios, si es necesario y haga clic en el servicio para la que desea impedir nuevas sesiones.
7. Haga clic en **acción**.
8. Haga clic en **evitar sesiones nuevas para el servicio**.
9. Haga clic en **Cerrar**.
    

