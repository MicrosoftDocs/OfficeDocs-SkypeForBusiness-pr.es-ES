---
title: Administrar servicios para Skype Empresarial Server
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: En este artículo se describe cómo administrar los servicios que se ejecutan en una topología de Skype Empresarial Server.
ms.openlocfilehash: 05bf37248e710424b7540fe0dbcc10338bd1f4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816600"
---
# <a name="manage-services-for-skype-for-business-server"></a>Administrar servicios para Skype Empresarial Server

En este artículo se describe cómo administrar los servicios que se ejecutan en una topología de Skype Empresarial Server.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Ver una lista de equipos que ejecutan Skype Empresarial Server
<a name="view_list"> </a>

Puede usar el Panel de control de Skype Empresarial Server para ver una lista de todos los equipos que ejecutan Skype Empresarial Server en su topología y ver el estado del servicio de cada uno. Puede ordenar la lista por PC, grupo de servidores o sitio. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Para ver una lista de equipos que ejecutan Skype Empresarial Server

1. Desde una cuenta de usuario asignada a cualquiera de los roles administrativos predefinidos para Skype Empresarial Server, inicie sesión en cualquier equipo de la implementación interna. Para obtener más información sobre los roles administrativos predefinidos disponibles en Skype Empresarial Server, **consulte Planeación de** Role-Based Access Control .   
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.   
3. En la barra de navegación izquierda, haga clic en **Topología** y después en **Estado**.   
4. En la página **Estado**, realice alguna de las operaciones siguientes:
   - Ordene la lista haciendo clic en el encabezado de columna **Equipo**, **Grupo de servidores** o **Sitio** y después haga clic en la flecha arriba o en la flecha abajo. 
   - Haga clic en **Actualizar** para ver la lista más actualizada.  
   - Para buscar un equipo específico, escriba el nombre del equipo en el campo de búsqueda.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Ver el estado de los servicios que se ejecutan en un servidor de Skype Empresarial
<a name="view-status"> </a>

Puede usar el Panel de control de Skype Empresarial Server para ver todos los servicios que se ejecutan en un equipo específico de la topología de Skype Empresarial Server y ver el estado de cada servicio.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para ver el estado de los servicios que se ejecutan en un equipo

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **Topología**. 
4. En la **página** Estado, ordene o busque la lista, según sea necesario, para encontrar el equipo que le interesa y, a continuación, haga clic en el nombre del equipo.
5. Siga uno de estos procedimientos:
   - Para ver el estado más reciente de los servicios que se ejecutan en el equipo, haga clic en **Obtener estado del servicio.**
   - Para ver una lista de servicios específicos que se ejecutan en el  equipo y el estado de cada servicio, haga clic en Propiedades y, a continuación, haga clic en Cerrar para volver a la lista.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Visualización del estado del servicio con cmdlets de Windows PowerShell

También puede ver el estado del servicio mediante Windows PowerShell y el cmdlet **Get-CsWindowsService.** Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-view-service-status"></a>Para ver el estado del servicio

Para ver el estado del servicio en un equipo, escriba un comando similar al siguiente en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Este comando devolverá información similar a la siguiente:
  
|**RoleName**|**Estado**|
|:-----|:-----|
|{W3SVC}  <br/> |En funcionamiento  <br/> |
|{CentralManagement}  <br/> | En funcionamiento <br/> |
|{ClsAgent}  <br/> |En funcionamiento  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |En funcionamiento  <br/> |
|{ApplicationServer}  <br/> |En funcionamiento  <br/> |
|{ConferencingServer}  <br/> |En funcionamiento  <br/> |
|{MediationServer}  <br/> |En funcionamiento  <br/> |
   
Para obtener más información, [vea Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Ver detalles sobre un servicio
<a name="view_details"> </a>

Puede usar el Panel de control de Skype Empresarial Server para ver detalles sobre cada servicio que se ejecuta en un equipo específico de la topología. Puede ver el estado de cada servicio y los detalles, como por ejemplo, las bases de datos asociadas, puertos y servicios dependientes.
  
### <a name="to-view-details-for-a-service"></a>Para ver los detalles de un servicio

1. Desde una cuenta de usuario asignada a cualquiera de los roles administrativos predefinidos para Skype Empresarial Server, inicie sesión en cualquier equipo de la implementación interna. Para obtener más información sobre los roles administrativos predefinidos disponibles en Skype Empresarial Server, **consulte Planeación de** Role-Based Access Control .
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
4. En la página **Estado**, clasifique o busque en la lista y, a continuación, haga clic en el equipo que desee ver.
5. Haga clic en **Propiedades**.
6. En la ventana **Ver detalles de equipo**, clasifique la lista de servicios, si fuera necesario, y haga clic en el servicio de desee ver.
7. Siga uno de estos procedimientos, según sea necesario:
   - Para ver el último estado de este servicio en particular, haga clic en **Obtener estado del servicio**.
   - Para ver los detalles de este servicio en particular, haga clic en **Propiedades** y, a continuación, en **Cerrar**.
   - Para volver a la lista de todos los equipos en la topología, haga clic en **Cerrar**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Iniciar o detener los servicios de Skype Empresarial Server
<a name="StartStop"> </a>

Puede usar el Panel de control de Skype Empresarial Server para iniciar o detener todos los servicios de Skype Empresarial Server que se ejecutan en un equipo específico o para iniciar o detener un servicio específico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Para iniciar o detener todos los servicios de Skype Empresarial en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server. Puede determinar si se le ha asignado el rol RBAC CsServerAdministrator o CsAdministrator ejecutando un comando similar al siguiente:
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.
4. En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta los servicios que desea iniciar o detener, y haga clic en él.
5. Haga clic en **Acción**.
6. Haga clic en **Iniciar todos los servicios** o **Detener todos los servicios**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Para iniciar o detener un servicio específico:

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.
4. En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él.
5. Haga clic en **Propiedades**.
6. Ordene la lista de servicios si es necesario y haga clic en el servicio que desea iniciar o detener.
7. Haga clic en **Acción**.
8. Haga clic en **Iniciar servicio** o **Detener servicio**.
9. Haga clic en **Cerrar**.
    
## <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios
<a name="prevent_session"> </a>

Puede usar el Panel de control de Skype Empresarial Server para evitar nuevas sesiones para todos los servicios de Skype Empresarial Server que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio específico de Skype Empresarial Server.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Para evitar nuevas sesiones para todos los servicios de Skype Empresarial en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
4. En la página **Estado**, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él.
5. Haga clic en **Acción**.
6. Haga clic en **Evitar sesiones nuevas en todos los servicios**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para impedir que se creen sesiones nuevas para un servicio específico

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
3. En la barra de navegación izquierda, haga clic en **Topología** y en **Estado**.
4. En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él. 
5. Haga clic en **Propiedades**.
6. Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.
7. Haga clic en **Acción**.
8. Haga clic en **Evitar sesiones nuevas en el servicio**.
9. Haga clic en **Cerrar**.
    

