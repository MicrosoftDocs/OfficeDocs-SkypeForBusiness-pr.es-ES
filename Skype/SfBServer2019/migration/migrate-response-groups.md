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
description: Una vez que los usuarios se han movido a los grupos de servidores de Skype empresarial Server 2019, puede migrar los grupos de respuesta. Migrar grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de Skype empresarial Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación grupo de respuesta en el grupo de servidores de Skype empresarial 2019. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752682"
---
# <a name="migrate-response-groups"></a>Migrar los grupos de respuesta

Una vez que los usuarios se han movido a los grupos de servidores de Skype empresarial Server 2019, puede migrar los grupos de respuesta. Migrar grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de Skype empresarial Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación grupo de respuesta en el grupo de servidores de Skype empresarial 2019. El grupo heredado ya no maneja las llamadas a los grupos de respuesta.
  
> [!NOTE]
> Aunque puede migrar los grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Skype empresarial Server 2019, le recomendamos que mueva todos los usuarios en primer lugar. En concreto, los usuarios que son agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de Skype empresarial Server 2019. 
  
Antes de migrar los grupos de respuesta, debe haber implementado un grupo de servidores de Skype empresarial 2019 que incluya la aplicación de grupo de respuesta. La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial. Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Puede crear nuevos grupos de respuesta 2019 de Skype empresarial Server en el grupo de Skype empresarial Server 2019 antes de migrar los grupos de respuesta heredados. 
  
Para migrar grupos de respuesta de un grupo heredado a la versión 2019 de Skype empresarial Server, ejecute el cmdlet **Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> El cmdlet de migración del grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo. No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración. 
  
Después de migrar los grupos de respuesta, debe usar el panel de control de Skype empresarial Server o los cmdlets del shell de administración de Skype empresarial Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se movieron correctamente. 
  
Al migrar grupos de respuesta, los grupos de respuesta heredados no se quitan. Cuando administre grupos de respuesta después de la migración mediante el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial Server, puede ver tanto los grupos de respuesta heredados como los grupos de respuesta de Skype empresarial Server 2019. Solo debe aplicar actualizaciones a los grupos de respuesta de Skype empresarial Server 2019. Los grupos de respuesta heredados se conservan solo por motivos de reversión. 
  
> [!CAUTION]
> Una vez que se haya completado la migración y se hayan creado los nuevos grupos de respuesta, el panel de control de Skype empresarial Server y el shell de administración de Skype empresarial Server mostrarán las versiones heredada y de Skype empresarial Server 2019 de cada grupo de respuesta. No use el panel de control de Skype empresarial Server ni el shell de administración de Skype empresarial Server para quitar los grupos de respuesta heredados. Si quita una, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar. Los grupos de respuesta heredados se quitarán cuando retire el grupo de servidores heredado. 
  
> [!IMPORTANT]
> Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores. También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración. Si un grupo de respuesta heredado debe quitarse, puede restaurar los grupos de respuesta a partir de la copia de seguridad para que los grupos de respuesta de Skype empresarial Server 2019 se ejecuten de nuevo. 
  
Skype empresarial Server 2019 presenta una nueva característica de grupo de respuesta llamada **tipo de flujo de trabajo**. El **tipo de flujo de trabajo** puede ser **administrado** o **no administrado**. Todos los grupos de respuesta son migrados con el **tipo de flujo de trabajo** configurado en **No administrado** y con la lista del Administrador vacía. 
  
Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión. Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado. 
  
El siguiente procedimiento para migrar configuraciones de grupo de respuesta presupone que tiene una relación de uno a uno entre los grupos de servidores heredados y los grupos de servidores de 2019 de Skype empresarial. Si planea consolidar o dividir grupos durante la migración y la implementación, debe planear el grupo de servidores heredado asignado al grupo de Skype empresarial Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Para migrar configuraciones de grupo de respuesta

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
3. Realizar
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por ejemplo:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Después de migrar los grupos de respuesta y los agentes al grupo de Skype empresarial Server 2019, la dirección URL que los agentes usan para iniciar y cerrar sesión es una dirección URL de Skype empresarial Server 2019 y está disponible en el menú **herramientas** . Recuerde a los agentes que actualicen las referencias, como los marcadores, a la nueva dirección URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para comprobar la migración del grupo de respuesta mediante el panel de control de Skype empresarial Server

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [Open Skype for Business server 2019 Administrative Tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.
    
4. En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno heredado se incluyan en la lista. 
    
5. Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno heredado están incluidas en la lista. 
    
6. Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno heredado están incluidos en la lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para comprobar la migración del grupo de respuesta mediante el shell de administración de Skype empresarial Server

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o que como mínimo sea miembro del rol CsViewOnlyAdministrator.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.
    
    Para obtener más información sobre los siguientes cmdlets, ejecute:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Realizar
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Compruebe que todos los grupos de agentes del entorno heredado están incluidos en la lista.
    
5. Realizar
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Compruebe que todas las colas del entorno heredado están incluidas en la lista.
    
7. Realizar
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Compruebe que todos los flujos de trabajo del entorno heredado están incluidos en la lista.
    

