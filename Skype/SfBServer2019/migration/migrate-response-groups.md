---
title: Migrar los grupos de respuesta
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de mover los usuarios a los grupos de Skype Empresarial Server 2019, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de Skype Empresarial Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación Grupo de respuesta en el grupo de Skype Empresarial Server 2019. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752682"
---
# <a name="migrate-response-groups"></a>Migrar los grupos de respuesta

Después de mover los usuarios a los grupos de Skype Empresarial Server 2019, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de Skype Empresarial Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación Grupo de respuesta en el grupo de Skype Empresarial Server 2019. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.
  
> [!NOTE]
> Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de Skype Empresarial Server 2019, se recomienda mover primero todos los usuarios. En particular, los usuarios que son agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se trasladen al grupo de Skype Empresarial Server 2019. 
  
Antes de migrar grupos de respuesta, debe haber implementado un grupo de Skype Empresarial Server 2019 que incluya la aplicación Grupo de respuesta. La aplicación Grupo de respuesta se instala y activa de forma predeterminada al implementar Telefonía IP empresarial. Puede asegurarse de que la aplicación Grupo de respuesta está instalada ejecutando el cmdlet **Get-CsService -ApplicationServer.** 
  
> [!NOTE]
> Puede crear nuevos grupos de respuesta de Skype Empresarial Server 2019 en el grupo de Skype Empresarial Server 2019 antes de migrar los grupos de respuesta heredados. 
  
Para migrar grupos de respuesta de un grupo heredado a Skype Empresarial Server 2019, ejecute el cmdlet **Move-CsRgsConfiguration.** 
  
> [!IMPORTANT]
> El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo. No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración. 
  
Después de migrar los grupos de respuesta, debe usar el Panel de control de Skype Empresarial Server o los cmdlets del Shell de administración de Skype Empresarial Server para comprobar que todos los grupos de agentes, colas y flujos de trabajo se movieron correctamente. 
  
Al migrar grupos de respuesta, no se quitan los grupos de respuesta heredados. Cuando administra grupos de respuesta después de la migración mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server, puede ver tanto los grupos de respuesta heredados como los grupos de respuesta de Skype Empresarial Server 2019. Solo debe aplicar actualizaciones a los grupos de respuesta de Skype Empresarial Server 2019. Los grupos de respuesta heredados se conservan solo con fines de reversión. 
  
> [!CAUTION]
> Una vez completada la migración y creados los nuevos grupos de respuesta, el Panel de control de Skype Empresarial Server y el Shell de administración de Skype Empresarial Server mostrarán las versiones heredadas y de Skype Empresarial Server 2019 de cada grupo de respuesta. No use el Panel de control de Skype Empresarial Server ni el Shell de administración de Skype Empresarial Server para quitar los grupos de respuesta heredados. Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar. Los grupos de respuesta heredados se quitarán al retirar el grupo heredado. 
  
> [!IMPORTANT]
> Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores. También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración. Si se debe quitar un grupo de respuesta heredado, puede restaurar los grupos de respuesta de la copia de seguridad para que los grupos de respuesta de Skype Empresarial Server 2019 vuelvan a ejecutarse. 
  
Skype Empresarial Server 2019 presenta una nueva característica de grupo de respuesta denominada **Tipo de flujo de trabajo.** El **tipo de flujo de trabajo** puede ser **administrado** o **no administrado**. Todos los grupos de respuesta son migrados con el **tipo de flujo de trabajo** configurado en **No administrado** y con la lista del Administrador vacía. 
  
Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión. Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado. 
  
El siguiente procedimiento para migrar configuraciones de grupo de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de Skype Empresarial Server 2019. Si planea consolidar o dividir grupos durante la migración y la implementación, debe planear qué grupo heredado se asigna a qué grupo de servidores de Skype Empresarial Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Para migrar configuraciones de grupo de respuesta

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. Ejecute:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por ejemplo:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Después de migrar los grupos de respuesta y los agentes al grupo de Skype Empresarial Server 2019, la dirección URL que usan  los agentes para iniciar y cerrar sesión es una dirección URL de Skype Empresarial Server 2019 y está disponible en el menú Herramientas. Recuerde a los agentes que actualicen las referencias, como los marcadores, a la nueva dirección URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para comprobar la migración del grupo de respuesta mediante el Panel de control de Skype Empresarial Server

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. Para obtener más información sobre los distintos métodos que puede usar para iniciar el Panel de control de Skype Empresarial Server, consulte Herramientas administrativas de Skype Empresarial [Server 2019.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx) 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.
    
4. En la **pestaña Flujo de** trabajo, compruebe que todos los flujos de trabajo del entorno heredado estén incluidos en la lista. 
    
5. Haga clic **en la** pestaña Cola y compruebe que todas las colas del entorno heredado estén incluidas en la lista. 
    
6. Haga clic **en la pestaña** Grupo y compruebe que todos los grupos de agentes del entorno heredado estén incluidos en la lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para comprobar la migración del grupo de respuesta mediante el Shell de administración de Skype Empresarial Server

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
    Para obtener más información sobre los siguientes cmdlets, ejecute:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Ejecute:
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Compruebe que todos los grupos de agentes del entorno heredado estén incluidos en la lista.
    
5. Ejecute:
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Compruebe que todas las colas del entorno heredado estén incluidas en la lista.
    
7. Ejecute:
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Compruebe que todos los flujos de trabajo del entorno heredado estén incluidos en la lista.
    

