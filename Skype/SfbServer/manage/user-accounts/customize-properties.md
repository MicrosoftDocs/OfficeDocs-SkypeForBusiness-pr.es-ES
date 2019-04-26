---
title: Personalizar propiedades de la cuenta de usuario de Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede usar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.
ms.openlocfilehash: 5162cb187538b5288f13f25beae96f3775faa594
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214838"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizar propiedades de la cuenta de usuario de Skype para Business Server
 
Puede usar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.
  
Hay dos operaciones básicas que pueden llevarse a cabo en el nivel de usuario individual:
  
- [Configurar las opciones de telefonía para una cuenta de usuario específica](customize-properties.md#Tel_Op)
    
- [Mover usuarios a otro grupo de servidores](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar las opciones de telefonía para una cuenta de usuario específica
<a name="Tel_Op"> </a>

Puede personalizar la configuración de telefonía para un usuario específico (siempre que se ha habilitado para el usuario individual de Skype para Business Server y la organización admite la telefonía).
  
Skype para las opciones de telefonía de usuario de Business Server incluyen lo siguiente:
  
- **Deshabilita el audio y vídeo** El usuario no puede realizar llamadas con audio y vídeo.
    
- **De PC a PC sólo** El usuario puede realizar solo de PC a PC audio o vídeos las llamadas.
    
- **Enterprise Voice** El usuario puede utilizar el Skype para infraestructura de Business Server para enrutar todas las llamadas entrantes y salientes. El usuario también puede realizar llamadas de PC a PC.
    
- **Control remoto de llamadas** El usuario puede usar Skype para Business Server para controlar el teléfono de escritorio y también puede realizar llamadas de PC a PC.
    
Para obtener información detallada sobre la configuración de telefonía para una organización, vea [Implementar Enterprise Voice en Skype para Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) y [permiten a los usuarios para Enterprise Voice en Skype para Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) en la documentación de implementación.
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en Buscar ** **.
    
5. En la tabla, haga clic en la cuenta de usuario que desea modificar.
    
6. En el menú **Edición** , haga clic en **Modificar**.
    
7. En **telefonía**, realice lo siguiente:
    
   - Para deshabilitar las llamadas de audioconferencias y vídeo para el usuario, haga clic en **Audio y vídeo deshabilitados**.
    
   - Para habilitar las comunicaciones de audio de PC a PC para el usuario, pero el control no remoto de llamadas o la telefonía IP empresarial, haga clic en **PC a PC sólo**. Especifique un valor para el **URI de línea** para el teléfono que el usuario se utiliza para las comunicaciones de audio de PC a PC.
    
   - Para enrutar las llamadas de teléfono del usuario mediante el uso de la Skype para infraestructura empresarial con arreglo a la clase de directiva de servicios, incluida la comunicación de audio de PC a PC, haga clic en **Enterprise Voice**. En **URI de línea**, especifique el número de teléfono para Enterprise Voice. En **Directiva de plan de marcado** y la **Directiva de voz**, especifique las directivas apropiadas para el usuario. Para especificar las reglas de normalización de la traducción de los números de teléfono marcados por el usuario para el formato E.164, seleccione el perfil de ubicación apropiada en la **Directiva de ubicación**.
    
   - Para habilitar la llamada remota control, que permite a los usuarios controlar su línea de teléfono de escritorio de Skype para Business Server realizar llamadas de PC a PC y llamadas de PC a teléfono, haga clic en **el control remoto de llamadas**. En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas. El usuario debe tener un teléfono de escritorio y conexión de central de conmutación (PBX) de exchange para el enrutamiento de llamadas.
    
## <a name="move-users-to-another-pool"></a>Mover usuarios a otro grupo de servidores
<a name="Move_Users"> </a>

Puede usar Skype para el Panel de Control de servidor empresarial para asignar a usuarios a un servidor específico o grupo de servidores.
  
> [!TIP]
> Mover todos los usuarios existentes de un grupo de servidores de origen que ejecuta Lync Server 2010 o anterior a un Skype para el grupo de servidores de destino de Business Server en un entorno complejo de Active Directory puede dar lugar a que la replicación de Active Directory más lenta. Para evitar este problema, puede usar filtros de búsqueda para mover usuarios de los grupos de servidores que ejecutan Lync Server 2010 o anteriormente por separado, o puede usar Skype para Shell de administración de servidor empresarial para mover usuarios con los cmdlets. Además, la funcionalidad de filtro funciona con Skype para los usuarios de Business Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover los usuarios seleccionados a otro servidor o grupo de servidores

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en Buscar ** **. 
    
5. En la tabla, seleccione un usuario o usuarios específicos en la lista. 
    
6. En el menú **acción** , haga clic en **mover usuarios seleccionados al grupo de servidores**.
    
7. En **Mover usuarios**, seleccione el grupo que desea trasladar los usuarios en el **grupo de registrador de destino**.
    
8. (Opcional) Si el servidor de destino o grupo de servidores no está disponible, active la casilla de verificación **Force** .
    
    > [!CAUTION]
    > Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminarán los datos de usuario asociado (por ejemplo, las conferencias que ha programado el usuario). Si no se selecciona, la cuenta y los datos asociados se mueven. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el menú **acción** , haga clic en **mover todos los usuarios al grupo de servidores**.
    
5. En **Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en **grupo de registradores de origen**.
    
6. En el **grupo de registrador de destino**, seleccione el grupo que desea trasladar los usuarios.
    
7. (Opcional) Si el servidor de destino o grupo de servidores no está disponible, active la casilla de verificación **Force** .
    
    > [!CAUTION]
    > Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminarán los datos de usuario asociado (por ejemplo, las conferencias que ha programado el usuario). Si no se selecciona, la cuenta y los datos asociados se mueven. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover usuarios de un grupo de servidores a otro grupo diferente mediante un filtro

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En la **Búsqueda de usuarios**, haga clic en **Buscar**y, a continuación, haga clic en **Agregar filtro**.
    
5. En los criterios de búsqueda, seleccione **Grupo de registrador**, seleccione es **igual a**, seleccione el **FQDN del grupo actual**y, a continuación, haga clic en **Buscar**.
    
6. En el menú **acción** , haga clic en **mover todos los usuarios al grupo de servidores**.
    
    > [!NOTE]
    > Cuando se aplica un filtro a un conjunto existente de usuarios, la opción **mover todos los usuarios al grupo de servidores** está en el contexto del filtrado subconjunto de usuarios, no **todos los** usuarios posibles.
  
7. En **Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en **grupo de registradores de origen**.
    
8. En **grupo de registrador de destino**, seleccione el grupo de servidores donde desea mover los usuarios.
    
9. (Opcional) Si el servidor de destino o grupo de servidores no está disponible, active la casilla de verificación **Force** .
    
    > [!CAUTION]
    > Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminarán los datos de usuario asociado (por ejemplo, las conferencias que ha programado el usuario y contactos). Si no se selecciona, la cuenta y los datos asociados se mueven. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuarios de un grupo de servidores a otro mediante cmdlets de Windows Powershell

1. En función de cómo ejecutar comandos de Windows PowerShell (es decir, local o remotamente), deberá iniciar sesión como un miembro de la correcta Skype para funciones administrativas Business Server como sigue:
    
   a. Si está ejecutando los comandos en la máquina local (por ejemplo, inicia sesión directamente en un servidor Front-End): inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con la necesaria derechos de usuario como se describe en **Delegar permisos de instalación**.
    
   b. Si está ejecutando los comandos de forma remota en otro equipo (por ejemplo, inicie sesión en su equipo y ejecuta los comandos de forma remota en una edición estándar servidor Front-End): desde una cuenta de usuario que se asigna al rol CsUserAdministrator o la CsAdministrator función, inicie sesión en cualquier equipo en la implementación interna.
    
2. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
3. Para mover usuarios individuales, use el cmdlet Move-CsUser de la siguiente forma:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Donde el usuario que se moverá es el usuario Pilar Ackerman y el usuario se moverá de su grupo de servidores principal actualmente asignado al grupo pool01.contoso.net
    
4. Para mover un gran número de usuarios, utilice filtros con el cmdlet **Get-CsUser** y pase el conjunto resultante de los usuarios a **Move-CsUser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Los comandos combinados de **Get-CsUser** y **Move-CsUser** es posible que el resultado siguiente:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


