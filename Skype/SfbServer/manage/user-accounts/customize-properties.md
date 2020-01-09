---
title: Personalizar las propiedades de la cuenta de usuario para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede usar los procedimientos de esta sección para modificar las propiedades de una cuenta de usuario individual.
ms.openlocfilehash: eca88717d0b81ddd7c27fc140df9bdbf7590c5c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991435"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizar las propiedades de la cuenta de usuario para Skype empresarial Server
 
Puede usar los procedimientos de esta sección para modificar las propiedades de una cuenta de usuario individual.
  
Existen dos operaciones básicas que se pueden realizar en el nivel de usuario individual:
  
- [Configurar opciones de telefonía para una cuenta de usuario específica](customize-properties.md#Tel_Op)
    
- [Mover usuarios a otro grupo](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar opciones de telefonía para una cuenta de usuario específica
<a name="Tel_Op"> </a>

Puede personalizar la configuración de telefonía de un usuario específico (siempre y cuando el usuario individual se haya habilitado en Skype empresarial Server y la organización admita telefonía).
  
Entre las opciones de telefonía de usuario de Skype empresarial Server se incluyen las siguientes:
  
- **Audio/vídeo deshabilitado** El usuario no puede hacer llamadas con audio y vídeo.
    
- **Solo de PC a PC** El usuario solo puede hacer videollamadas o videollamadas de PC a PC.
    
- **Telefonía IP empresarial** El usuario puede usar la infraestructura de Skype empresarial Server para enrutar todas las llamadas entrantes y salientes. El usuario también puede hacer llamadas de PC a PC.
    
- **Control remoto de llamadas** El usuario puede usar Skype empresarial Server para controlar el teléfono de escritorio y también puede hacer llamadas entre equipos.
    
Para obtener detalles sobre la configuración de telefonía para una organización, vea [Habilitar usuarios de telefonía IP empresarial en Skype empresarial Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e implementar la telefonía [IP empresarial en Skype empresarial Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) en la documentación de implementación.
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desea modificar.
    
6. En el menú **Editar** , haga clic en **modificar**.
    
7. En **telefonía**, haga lo siguiente:
    
   - Para deshabilitar las llamadas de audio y vídeo para el usuario, haga clic en **audio/vídeo deshabilitado**.
    
   - Para habilitar las comunicaciones de audio de PC a PC para el usuario, pero no para el control remoto de llamadas ni para la telefonía IP empresarial, haga clic en **solo de PC a PC**. Especifique un valor para el **URI de línea** del teléfono que usa el usuario para las comunicaciones de audio de PC a PC.
    
   - Para enrutar las llamadas telefónicas del usuario mediante la infraestructura de Skype empresarial según la política de clase de servicio, incluidas las comunicaciones de audio de PC a PC, haga clic en **telefonía IP empresarial**. En **URI de línea**, especifique el número de teléfono de la telefonía IP empresarial. En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas apropiadas para el usuario. Para especificar las reglas de normalización para traducir números de teléfono marcados por el usuario al formato E. 164, seleccione el perfil de ubicación adecuado en la **política de ubicación**.
    
   - Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea telefónica de escritorio desde Skype empresarial Server para realizar llamadas de PC a PC y llamadas de PC a teléfono, haga clic en **control remoto de llamadas**. En **URI de línea**, especifique el número de teléfono para el control de llamada remota. El usuario debe tener una conexión de teléfono de escritorio y de central de conmutación (PBX) para el enrutamiento de llamadas.
    
## <a name="move-users-to-another-pool"></a>Mover usuarios a otro grupo
<a name="Move_Users"> </a>

Puede usar el panel de control de Skype empresarial Server para asignar usuarios a un servidor o grupo de servidores específico.
  
> [!TIP]
> El traslado de todos los usuarios existentes de un grupo de origen que ejecuta Lync Server 2010 o una versión anterior a un grupo de destino de Skype empresarial Server en un entorno complejo de Active Directory puede ralentizar la replicación de Active Directory. Para evitar esto, puede usar filtros de búsqueda para mover los usuarios de los grupos que ejecutan Lync Server 2010 o una versión anterior por separado, o bien puede usar el shell de administración de Skype empresarial Server para mover usuarios con cmdlets. Además, la funcionalidad de filtro funciona con usuarios de Skype empresarial Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover los usuarios seleccionados a otro servidor o grupo de servidores

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**. 
    
5. En la tabla, seleccione un usuario o usuarios específicos de la lista. 
    
6. En el menú **acción** , haga clic en **mover los usuarios seleccionados al grupo**.
    
7. En **mover usuarios**, seleccione el grupo al que desea mover los usuarios en el **grupo de registrador de destinos**.
    
8. Faculta Si el servidor de destino o el grupo de servidores no están disponibles, active la casilla **forzar** .
    
    > [!CAUTION]
    > Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminan los datos de los usuarios asociados (por ejemplo, las conferencias que el usuario ha programado). Si no la selecciona, tanto la cuenta como los datos asociados se mueven. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.
    
5. En **mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registrador de origen**.
    
6. En **grupo de registradores de destino**, seleccione el grupo al que desea mover a los usuarios.
    
7. Faculta Si el servidor de destino o el grupo de servidores no están disponibles, active la casilla **forzar** .
    
    > [!CAUTION]
    > Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminan los datos de los usuarios asociados (por ejemplo, las conferencias que el usuario ha programado). Si no la selecciona, tanto la cuenta como los datos asociados se mueven. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover los usuarios de un grupo a otro mediante un filtro

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En **búsqueda de usuario**, haga clic en **Buscar**y, a continuación, haga clic en **Agregar filtro**.
    
5. En los criterios de búsqueda, seleccione **registrar grupo**, seleccione **igual a**, seleccione **FQDN del grupo actual**y, a continuación, haga clic en **Buscar**.
    
6. En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.
    
    > [!NOTE]
    > Cuando se aplica un filtro a un conjunto de usuarios existente, la opción **mover todos los usuarios al grupo** se encuentra en el contexto del subconjunto filtrado de usuarios, no de **todos** los usuarios posibles.
  
7. En **mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registrador de origen**.
    
8. En **grupo de registradores de destino**, seleccione el grupo al que desea mover los usuarios.
    
9. Faculta Si el servidor de destino o el grupo de servidores no están disponibles, active la casilla **forzar** .
    
    > [!CAUTION]
    > Si selecciona **fuerza**, se mueve la cuenta de usuario, pero se eliminan los datos de los usuarios asociados (por ejemplo, las conferencias que el usuario ha programado y a las que los contactos han programado). Si no la selecciona, tanto la cuenta como los datos asociados se mueven. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuarios de un grupo a otro mediante cmdlets de Windows PowerShell

1. En función de cómo ejecute los comandos de Windows PowerShell (es decir, de forma local o remota), debe iniciar sesión como miembro de las funciones administrativas del servidor de Skype empresarial correctas de la siguiente manera:
    
   a. Si está ejecutando los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor de aplicaciones para el usuario): inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en **permisos de configuración de delegado**.
    
   b. Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator rol, inicie sesión en cualquier equipo de su implementación interna.
    
2. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.
    
3. Para mover usuarios individuales, use el cmdlet Move-CsUser de la siguiente manera:
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Donde el usuario debe mover es el usuario Pilar Ackerman, y el usuario se moverá de su grupo local asignado a la agrupación pool01.contoso.net
    
4. Para mover un gran número de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto de usuarios resultante a **Move-CsUser**:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Los comandos combinados de **Get-CsUser** y **Move-CsUser** pueden dar lugar a esto:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


