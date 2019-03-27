---
title: Migrar grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de que los usuarios se mueven a Skype para grupos de negocio Server 2019, puede migrar los grupos de respuesta. Respuesta migrar grupos incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada a la Skype para el grupo de servidores de Business Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta son resueltos por la aplicación de grupo de respuesta en el Skype para el grupo de servidores de Business Server 2019. Las llamadas a grupos de respuesta ya no se controlan mediante el grupo heredado.
ms.openlocfilehash: 17ba19be3b574436f3a175457264654d8c28ebd0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876316"
---
# <a name="migrate-response-groups"></a>Migrar grupos de respuesta

Después de que los usuarios se mueven a Skype para grupos de negocio Server 2019, puede migrar los grupos de respuesta. Respuesta migrar grupos incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada a la Skype para el grupo de servidores de Business Server 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta son resueltos por la aplicación de grupo de respuesta en el Skype para el grupo de servidores de Business Server 2019. Las llamadas a grupos de respuesta ya no se controlan mediante el grupo heredado.
  
> [!NOTE]
> Aunque puede migrar grupos de respuesta antes de mover todos los usuarios a la Skype para Business Server 2019 grupo de servidores, se recomienda que mueva todos los usuarios en primer lugar. En particular, los usuarios que sean los agentes del grupo de respuesta no tendrán una funcionalidad completa de las nuevas características hasta que se mueven a la Skype para el grupo de servidores de Business Server 2019. 
  
Antes de migrar grupos de respuesta, debe haber implementado un Skype para Business Server 2019 del grupo que incluye la aplicación de grupo de respuesta. La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar Enterprise Voice. Asegúrese de que está instalada la aplicación de grupo de respuesta ejecutando el cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Puede crear nuevas Skype Business Server 2019 grupos de respuesta en el Skype para el grupo de servidores de Business Server 2019 antes de migrar los grupos de respuesta heredados. 
  
Para migrar grupos de respuesta de un grupo de servidores heredado a la Skype para Business Server 2019, ejecute el cmdlet **Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> El cmdlet de migración de grupo de respuesta mueve a la configuración de grupo de respuesta para todo el grupo. No puede seleccionar grupos específicos, colas o flujos de trabajo para migrar. 
  
Después de migrar los grupos de respuesta, debe usar Skype para el Panel de Control de servidor empresarial o Skype para los cmdlets del Shell de administración de servidor empresarial para comprobar que todos los grupos de agentes, colas y flujos de trabajo se hayan migrado correctamente. 
  
Cuando se migran grupos de respuesta, no se quitan los grupos de respuesta heredados. Al administrar grupos de respuesta después de la migración mediante el uso de ambos Skype para el Panel de Control de servidor empresarial o Skype de consola de administración de servidor empresarial, puede ver los grupos de respuesta heredados y la Skype Business Server 2019 grupos de respuesta. Se deben aplicar las actualizaciones sólo a la Skype Business Server 2019 grupos de respuesta. Los grupos de respuesta heredados se conservan únicamente con fines de reversión. 
  
> [!CAUTION]
> Después de la migración se ha completado y se han creado los nuevos grupos de respuesta, el Skype para el Panel de Control de servidor empresarial y la Skype para Shell de administración de Business Server mostrará el heredado y Skype para Business Server 2019 versiones de cada respuesta grupo. No use Skype para Panel de Control de servidor empresarial o Skype para Business Server Management Shell para quitar los grupos de respuesta heredados. Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar. Los grupos de respuesta heredados se quitan cuando se dé de baja el grupo heredado. 
  
> [!IMPORTANT]
> Se recomienda que no quite los datos de la implementación anterior hasta que se dé de baja el grupo de servidores. Además, se recomienda exportar grupos de respuesta inmediatamente después de migrar. Si debe obtener quitar un grupo de respuesta heredados, a continuación, puede restaurar los grupos de respuesta desde la copia de seguridad para obtener Skype para volver a ejecutar los grupos de respuesta Business Server 2019. 
  
Skype para Business Server 2019 presenta una nueva característica de grupo de respuesta denominada **Tipo de flujo de trabajo**. **Tipo de flujo de trabajo** puede ser **administrado** o **no administrado**. Todos los grupos de respuesta se migran con el **Tipo de flujo de trabajo** establecido como **no administrados** y con una lista vacía en Administrador. 
  
Cuando se ejecuta el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, colas, flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión. Sin embargo, si es necesario revertir al grupo de servidores heredado, necesario ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover objetos de contacto de vuelta al grupo de servidores heredado. 
  
El siguiente procedimiento para migrar las configuraciones de grupo de respuesta se da por supuesto que tiene una relación de uno a uno entre los grupos heredados y la Skype para grupos de negocio Server 2019. Si tiene previsto consolidar o dividir los grupos de servidores durante la migración y la implementación, debe plan qué grupo heredado que se asigna a qué Skype para el grupo de servidores de Business Server 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Para migrar las configuraciones de grupo de respuesta

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga permisos y derechos de administrador equivalentes.
    
2. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
3. Ejecute:
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por ejemplo:
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Después de migrar los grupos de respuesta y los agentes a la Skype para el grupo de servidores de Business Server 2019, la dirección URL que los agentes que se utilizan para iniciar y cerrar la sesión es un Skype para Business Server 2019 URL y está disponible en el menú **Herramientas** . Recuerde a los agentes para actualizar las referencias, como marcadores, a la nueva dirección URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para comprobar la migración de grupo de respuesta mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o, como mínimo, es un miembro del rol CsViewOnlyAdministrator.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. Para obtener información detallada sobre los distintos métodos que puede usar para iniciar Skype para el Panel de Control de servidor empresarial, vea [Open Skype para las herramientas administrativas de Business Server 2019](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.
    
4. En la ficha **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno heredado se encuentran en la lista. 
    
5. Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno heredado se encuentran en la lista. 
    
6. Haga clic en la ficha de **grupo** y compruebe que todos los grupos de agentes del entorno heredado se encuentran en la lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para comprobar la migración de grupo de respuesta mediante el uso de Skype para Shell de administración de servidor empresarial

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalReadOnlyAdmins o, como mínimo, es un miembro del rol CsViewOnlyAdministrator.
    
2. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
    Para obtener información detallada sobre los siguientes cmdlets, ejecute:
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. Ejecute:
    
   ```
   Get-CsRgsAgentGroup
   ```

4. Compruebe que todos los grupos de agentes del entorno heredado se encuentran en la lista.
    
5. Ejecute:
    
   ```
   Get-CsRgsQueue
   ```

6. Compruebe que todas las colas del entorno heredado se encuentran en la lista.
    
7. Ejecute:
    
   ```
   Get-CsRgsWorkflow
   ```

8. Compruebe que todos los flujos de trabajo del entorno heredado se encuentran en la lista.
    

