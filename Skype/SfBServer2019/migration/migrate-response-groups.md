---
title: Migrar grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de mover los usuarios a los grupos de servidores de Skype empresarial 2019, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada al grupo de servidores de Skype empresarial 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Skype empresarial 2019. Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.
ms.openlocfilehash: 148fbe2ca547c3bd7e3d240e687b37c94d10270b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991115"
---
# <a name="migrate-response-groups"></a>Migrar grupos de respuesta

Después de mover los usuarios a los grupos de servidores de Skype empresarial 2019, puede migrar los grupos de respuesta. La migración de grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo, archivos de audio y mover los objetos de contacto del grupo de respuesta de la implementación heredada al grupo de servidores de Skype empresarial 2019. Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación de grupo de respuesta en el grupo de servidores de Skype empresarial 2019. Las llamadas a grupos de respuesta ya no son controladas por el grupo heredado.
  
> [!NOTE]
> Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Skype empresarial 2019, le recomendamos que mueva todos los usuarios en primer lugar. En particular, los usuarios que sean agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Skype empresarial 2019. 
  
Antes de migrar grupos de respuesta, debe haber implementado un grupo de servidores de Skype empresarial 2019 que incluya la aplicación de grupo de respuesta. La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial. Para asegurarse de que la aplicación de grupo de respuesta se instala, ejecute el cmdlet **Get-CsService-ApplicationServer** . 
  
> [!NOTE]
> Puede crear nuevos grupos de respuesta de Skype empresarial 2019 en el grupo de Skype empresarial 2019 antes de migrar los grupos de respuesta heredados. 
  
Para migrar grupos de respuesta de un grupo heredado a la 2019 de Skype empresarial Server, ejecute el cmdlet **Move-CsRgsConfiguration** . 
  
> [!IMPORTANT]
> El cmdlet de migración de grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo. No puede seleccionar grupos, colas o flujos de trabajo específicos para migrar. 
  
Después de migrar los grupos de respuesta, debe usar el panel de control de Skype empresarial Server o los cmdlets del shell de administración de Skype empresarial para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se han movido correctamente. 
  
Al migrar grupos de respuesta, los grupos de respuesta heredados no se quitan. Al administrar grupos de respuesta después de la migración mediante el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial, puede ver los grupos de respuesta heredados y los grupos de respuesta de Skype empresarial Server 2019. Solo debe aplicar actualizaciones a los grupos de respuesta 2019 de Skype empresarial Server. Los grupos de respuesta heredados solo se conservan con fines de desinstalación. 
  
> [!CAUTION]
> Una vez que se haya completado la migración y se hayan creado los nuevos grupos de respuesta, el panel de control de Skype empresarial Server y el shell de administración de Skype empresarial Server mostrarán las versiones del servidor de Skype heredado y de Skype empresarial 2019 de cada respuesta mesa. No use el panel de control de Skype empresarial Server ni el shell de administración de Skype empresarial para quitar los grupos de respuesta heredados. Si quita uno, el grupo de respuesta correspondiente que se creó durante la migración dejará de funcionar. Los grupos de respuesta heredados se quitarán al retirar el grupo heredado. 
  
> [!IMPORTANT]
> Le recomendamos que no elimine ningún dato de la implementación anterior hasta que no represente el grupo. Además, le recomendamos encarecidamente que exporte los grupos de respuesta inmediatamente después de la migración. Si un grupo de respuesta heredado debe quitarse, puede restaurar los grupos de respuesta de la copia de seguridad para que los grupos de respuesta de Skype empresarial Server 2019 vuelvan a ejecutarse. 
  
Skype empresarial Server 2019 presenta una nueva característica de grupo de respuesta llamada **tipo de flujo de trabajo**. El **tipo de flujo de trabajo** se puede administrar o **no administrar**. **** Todos los grupos de respuesta se migran con el **tipo de flujo de trabajo** establecido en **no administrado** y con una lista vacía de administrador. 
  
Al ejecutar el cmdlet **Move-CsRgsConfiguration** , los grupos de agentes, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para fines de desinstalación. Sin embargo, si necesita volver al grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para mover los objetos de contacto de nuevo al grupo heredado. 
  
El siguiente procedimiento para migrar la configuración de un grupo de respuesta supone que tiene una relación uno a uno entre los grupos heredados y los grupos de 2019 de Skype empresarial Server. Si tiene previsto consolidar o dividir las agrupaciones durante la migración y la implementación, debe planear los mapas de agrupaciones heredados en los que el grupo de servidores de Skype empresarial 2019.
  
## <a name="to-migrate-response-group-configurations"></a>Para migrar las configuraciones de grupos de respuesta

1. Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.
    
3. Ejecute:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    Por ejemplo:
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. Después de migrar grupos de respuesta y agentes al grupo de servidores de Skype empresarial 2019, la dirección URL que los agentes usan para iniciar y cerrar sesión es una URL de Skype empresarial Server 2019 y está disponible en el menú **herramientas** . Recuerde a los agentes que actualicen cualquier referencia, como marcadores, a la nueva dirección URL. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>Para comprobar la migración de grupos de respuesta con el panel de control de Skype empresarial Server

1. Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Skype empresarial Server, consulte [abrir las herramientas administrativas 2019 de Skype empresarial Server](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx). 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. En el panel de navegación izquierdo, haga clic en **grupos de respuesta**.
    
4. En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo de su entorno heredado estén incluidos en la lista. 
    
5. Haga clic en la pestaña **cola** y compruebe que todas las colas de su entorno heredado estén incluidas en la lista. 
    
6. Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes de su entorno heredado estén incluidos en la lista. 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>Para comprobar la migración de grupos de respuesta con el shell de administración de Skype empresarial Server

1. Inicie sesión en el equipo con una cuenta que sea miembro de RTCUniversalReadOnlyAdmins grupo o que sea, al menos, miembro de la función CsViewOnlyAdministrator.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.
    
    Para obtener más información sobre los siguientes cmdlets, ejecute:
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. Ejecute:
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. Verifique que todos los grupos de agentes de su entorno heredado estén incluidos en la lista.
    
5. Ejecute:
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. Verifique que todas las colas de su entorno heredado estén incluidas en la lista.
    
7. Ejecute:
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. Verifique que todos los flujos de trabajo de su entorno heredado estén incluidos en la lista.
    

