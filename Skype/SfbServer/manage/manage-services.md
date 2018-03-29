---
title: Administrar los servicios de Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Este artículo describe cómo administrar los servicios que se ejecutan en un Skype para Business Server 2015 topología.
ms.openlocfilehash: f8406d473b1d2ae644ac56d071313d2b488169fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-services-for-skype-for-business-server-2015"></a>Administrar los servicios de Skype para Business Server 2015

Este artículo describe cómo administrar los servicios que se ejecutan en un Skype para Business Server 2015 topología.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server-2015"></a>Ver una lista de equipos que ejecutan Skype para Business Server 2015
<a name="view_list"> </a>

Puede utilizar Skype para Business Server Control Panel para ver una lista de todos los equipos que ejecutan Skype para 2015 de servidor empresarial en su topología y ver el estado de servicio de cada uno. Puede ordenar la lista por equipo, grupo o sitio. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Para ver una lista de equipos que ejecutan Skype para Business Server

1. Desde una cuenta de usuario que se asigna a cualquiera de las funciones administrativas predefinidas para Skype para Business Server 2015, iniciar sesión en cualquier equipo en la implementación interna. Para obtener más información acerca de las funciones administrativas predefinidas disponibles en Skype para Business Server 2015, vea **Planear Role-Based Access Control**.   
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.   
3. En la barra de navegación de la izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.   
4. En la página de **estado** , realice una de las siguientes opciones según sea necesario:
   - Ordenar la lista haciendo clic en el **equipo**, **grupo**o encabezado de columna de **sitio** y, a continuación, la flecha arriba o flecha abajo. 
   - Haga clic en **Actualizar** para ver la lista más actualizada.  
   - Búsqueda de un equipo específico, escriba el nombre del equipo en el campo de búsqueda.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-2015-server"></a>Ver el estado de los servicios que se ejecutan en un Skype para servidor de negocios 2015
<a name="view-status"> </a>

Puede utilizar Skype para Business Server Control Panel para ver todos los servicios que se ejecutan en un equipo específico en su Skype para la topología de servidores de la empresa y ver el estado de cada servicio.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para ver el estado de los servicios que se ejecutan en un equipo

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
3. En la barra de navegación de la izquierda, haga clic en **topología**. 
4. En la página de **estado** , ordenar o buscar en la lista, según sea necesario, para buscar el equipo que le interesa y, a continuación, haga clic en el nombre del equipo.
5. Siga uno de estos pasos:
   - Para ver el estado más reciente de los servicios que se ejecutan en el equipo, haga clic en **obtener el estado del servicio**.
   - Para ver una lista de servicios específicos que se ejecutan en el equipo y el estado de cada servicio, haga clic en **Propiedades**y, a continuación, haga clic en **Cerrar** para volver a la lista.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Ver el estado de servicio con los cmdlets de Windows Powershell

También puede ver el estado del servicio mediante Windows PowerShell y el cmdlet **Get-CsWindowsService** . Puede ejecutar este cmdlet desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-view-service-status"></a>Para ver el estado del servicio

Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el Skype para negocios de Shell de administración de servidor y, a continuación, presione ENTRAR:
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Este comando devolverá información similar a la siguiente:
  
|**Nombre de rol**|**Estado**|
|:-----|:-----|
|{W3SVC}  <br/> |Ejecuta  <br/> |
|{CentralManagement}  <br/> | Ejecuta <br/> |
|{ClsAgent}  <br/> |Ejecuta  <br/> |
|{Registrador, USESERVER, EdgeServer}  <br/> |Ejecuta  <br/> |
|{ApplicationServer}  <br/> |Ejecuta  <br/> |
|{ConferencingServer}  <br/> |Ejecuta  <br/> |
|{MediationServer}  <br/> |Ejecuta  <br/> |
   
Para obtener más información, consulte [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Ver detalles acerca de un servicio
<a name="view_details"> </a>

Puede utilizar Skype para Business Server Control Panel para ver detalles acerca de cada servicio que se ejecuta en un equipo específico en la topología. Puede ver el estado de cada servicio y detalles como las bases de datos asociadas, puertos y servicios dependientes.
  
### <a name="to-view-details-for-a-service"></a>Para ver los detalles de un servicio

1. Desde una cuenta de usuario que se asigna a cualquiera de las funciones administrativas predefinidas para Skype para Business Server 2015, iniciar sesión en cualquier equipo en la implementación interna. Para obtener más información acerca de las funciones administrativas predefinidas disponibles en Skype para Business Server 2015, vea **Planear Role-Based Access Control**.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
3. En la barra de navegación de la izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página **estado** , ordenar o buscar en la lista y, a continuación, haga clic en el equipo que desea ver.
5. Haga clic en **Propiedades**.
6. En la ventana **Ver detalle del equipo** , ordenar la lista de servicios, si es necesario y haga clic en el servicio que desea ver.
7. Realice una de las siguientes opciones según sea necesario:
   - Para ver el estado más reciente de dicho servicio específico, haga clic en **obtener el estado del servicio**.
   - Para ver los detalles de ese servicio en concreto, haga clic en **Propiedades** y, a continuación, haga clic en **Cerrar**.
   - Para volver a la lista de todos los equipos de la topología, haga clic en **Cerrar**.
    
## <a name="start-or-stop-skype-for-business-server-2015-services"></a>Iniciar o detener Skype para servicios de Business Server 2015
<a name="StartStop"> </a>

Puede utilizar Skype para Panel de Control de servidor de negocios para iniciar o detener todo el Skype para Business Server 2015 servicios que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Para iniciar o detener todos Skype para Business services en un equipo

1. Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015. Puede determinar si se le ha asignado el CsServerAdministrator o la función RBAC CsAdministrator ejecutando un comando similar al siguiente:
    
  ```
  Get-CsAdminRoleAssignment -Identity "kenmyer"

  ```

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
3. En la barra de navegación de la izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página de **estado** , el orden o la búsqueda a través de la lista según sea necesario para buscar el equipo que está ejecutando los servicios que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **acción**.
6. Haga clic en **iniciar todos los servicios** o **Detener todos los servicios**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Para iniciar o detener un servicio específico

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
3. En la barra de navegación de la izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página de **estado** , el orden o la búsqueda a través de la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él.
5. Haga clic en **Propiedades**.
6. Ordenar la lista de servicios, si es necesario y haga clic en el servicio que desea iniciar o detener.
7. Haga clic en **acción**.
8. Haga clic en **Iniciar servicio** o **Detener el servicio**.
9. Haga clic en **Cerrar**.
    
## <a name="prevent-sessions-for-services"></a>Evitar las sesiones de servicios
<a name="prevent_session"> </a>

Puede utilizar Skype para Panel de Control de servidor empresarial para prevenir nuevas sesiones para todo el Skype para Business Server 2015 servicios que se ejecutan en un equipo específico o para evitar nuevas sesiones para un específico Skype para el servicio de servidor de negocios 2015.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Para evitar nuevas sesiones de Skype todos los servicios de negocios en un equipo

1. Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
3. En la barra de navegación de la izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página de **estado** , ordenar o buscar a través de la lista como sea necesario para buscar el equipo que está ejecutando los servicios para los cuales desea evitar nuevas sesiones y, a continuación, haga clic en.
5. Haga clic en **acción**.
6. Haga clic en **prevenir nuevas sesiones para todos los servicios**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para evitar nuevas sesiones para un servicio específico

1. Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
3. En la barra de navegación de la izquierda, haga clic en **topología** y, a continuación, haga clic en **estado**.
4. En la página de **estado** , el orden o la búsqueda a través de la lista según sea necesario para buscar el equipo que está ejecutando el servicio que desea iniciar o detener y, a continuación, haga clic en él. 
5. Haga clic en **Propiedades**.
6. Ordenar la lista de servicios, si es necesario y haga clic en el servicio para el que desea evitar nuevas sesiones.
7. Haga clic en **acción**.
8. Haga clic en **prevenir nuevas sesiones para el servicio**.
9. Haga clic en **Cerrar**.
    

