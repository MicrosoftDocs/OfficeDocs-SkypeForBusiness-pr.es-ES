---
title: Personalizar las propiedades de la cuenta de usuario para Skype Empresarial Server
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
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede utilizar los procedimientos que se describen en esta sección para modificar las propiedades de cuenta de usuario individuales.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826270"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizar las propiedades de la cuenta de usuario para Skype Empresarial Server
 
Puede utilizar los procedimientos que se describen en esta sección para modificar las propiedades de cuenta de usuario individuales.
  
Hay dos operaciones básicas que se pueden realizar en el nivel de usuario individual:
  
- [Configurar opciones de telefonía para una cuenta de usuario específica](customize-properties.md#Tel_Op)
    
- [Mover usuarios a otro grupo](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar opciones de telefonía para una cuenta de usuario específica
<a name="Tel_Op"> </a>

Puede personalizar la configuración de telefonía para un usuario específico (siempre que el usuario individual se haya habilitado para Skype Empresarial Server y la organización admita telefonía).
  
Entre las opciones de telefonía de usuario de Skype Empresarial Server se incluyen las siguientes:
  
- **Audio/vídeo deshabilitado** El usuario no puede realizar llamadas con audio y vídeo.
    
- **Solo de equipo a equipo** El usuario solo puede realizar llamadas de audio o vídeo de un equipo a otro.
    
- **Telefonía IP empresarial** El usuario puede usar la infraestructura de Skype Empresarial Server para enrutar todas las llamadas entrantes y salientes. También puede realizar llamadas de equipo a equipo.
    
- **Control remoto de llamadas** El usuario puede usar Skype Empresarial Server para controlar el teléfono de escritorio y también puede realizar llamadas de equipo a equipo.
    
Para obtener más información sobre cómo configurar la telefonía para una organización, consulte Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial [Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e Implementar Telefonía IP empresarial en Skype Empresarial [Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) en la documentación sobre implementación.
  
1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario que desee modificar.
    
6. En el menú **Editar**, haga clic en **Modificar**.
    
7. En **Telefonía**, siga este procedimiento:
    
   - Para deshabilitar las llamadas de audio y vídeo del usuario, haga clic en **Audio y vídeo deshabilitados**.
    
   - Para habilitar las comunicaciones de audio de equipo a equipo para el usuario, pero no el control remoto de llamadas ni la Telefonía IP empresarial, haga clic en **Solo de equipo a equipo**. Especifique un valor para **URI de línea** para el teléfono que usa el usuario para comunicaciones de audio de equipo a equipo.
    
   - Para enrutar las llamadas telefónicas del usuario mediante la infraestructura de Skype Empresarial de acuerdo con la clase de directiva de servicio, incluida la comunicación de audio de equipo a **equipo,** haga clic en Telefonía IP empresarial . En **URI de línea**, especifique el número de teléfono para la Telefonía IP empresarial. En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas adecuadas para el usuario. Para especificar las reglas de normalización para convertir los números de teléfono que marque el usuario a formato E.164, seleccione el perfil de ubicación apropiado en **Directiva de ubicación**.
    
   - Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea de teléfono de escritorio desde Skype Empresarial Server para realizar llamadas de equipo a equipo y de equipo a teléfono, haga clic en **Control** remoto de llamadas. En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas. El usuario debe tener un teléfono de escritorio y una conexión de central de conmutación (PBX) para el enrutamiento de llamadas.
    
## <a name="move-users-to-another-pool"></a>Mover usuarios a otro grupo
<a name="Move_Users"> </a>

Puede usar el Panel de control de Skype Empresarial Server para asignar usuarios a un servidor o grupo específico.
  
> [!TIP]
> Mover todos los usuarios existentes de un grupo de servidores de origen que ejecuta Lync Server 2010 o versiones anteriores a un grupo de destino de Skype Empresarial Server en un entorno complejo de Active Directory puede producir una replicación de Active Directory más lenta. Para evitar esto, puede usar filtros de búsqueda para mover usuarios de grupos que ejecutan Lync Server 2010 o versiones anteriores por separado, o puede usar el Shell de administración de Skype Empresarial Server para mover usuarios con cmdlets. Además, la funcionalidad de filtro funciona con usuarios de Skype Empresarial Server. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover determinados usuarios a otro servidor o grupo de servidores

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**. 
    
5. En la tabla, seleccione uno o varios usuarios de la lista. 
    
6. En el menú **Acción**, haga clic en **Mover usuarios seleccionados a un grupo de servidores**.
    
7. En **Mover usuarios**, seleccione el grupo de servidores al que desea trasladar los usuarios en **Grupo de registrador de destino**.
    
8. (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.
    
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el menú **Acción**, haga clic en **Mover todos los usuarios a un grupo de servidores**.
    
5. En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registrador de origen**.
    
6. En **Grupo de registrador de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.
    
7. (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.
    
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover usuarios de un grupo a otro grupo diferente mediante un filtro

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En **Búsqueda de usuarios,** haga **clic en** Buscar y, a continuación, haga clic en **Agregar filtro.**
    
5. En los Criterios de búsqueda, seleccione **Grupo de registradores**, **Igual que**, **FQDN del grupo actual** y, a continuación, haga clic en **Buscar**.
    
6. En el menú **Acción**, haga clic en **Mover todos los usuarios al grupo**.
    
    > [!NOTE]
    > Cuando se aplica un filtro a un conjunto de usuarios existente, la opción **Mover todos los usuarios al grupo** se refiere al subconjunto de usuarios filtrados, no a **todos** los usuarios posibles.
  
7. En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registradores de origen**.
    
8. En **Grupo de registradores de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.
    
9. (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Forzar**.
    
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado y contactos). Si no se selecciona, se mueven la cuenta y los datos asociados. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuarios de un grupo a otro mediante cmdlets de Windows PowerShell

1. Dependiendo de cómo ejecute Windows PowerShell comandos (es decir, de forma local o remota), debe iniciar sesión como miembro de los roles administrativos correctos de Skype Empresarial Server de la siguiente manera:
    
   a. Si ejecuta los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor front-end): inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en Permisos de configuración **delegados.**
    
   b. Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator, inicie sesión en cualquier equipo de la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
3. Para mover usuarios únicos, use el cmdlet Move-CsUser de la siguiente forma:
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Donde el usuario que se moverá es Pilar Ackerman, y el usuario se moverá de su grupo de servidores principales actualmente asignado al grupo pool01.contoso.net
    
4. Para mover una cantidad grande de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto resultante de usuarios a **Move-CsUser**:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Los comandos combinados de los cmdlets **Get-CsUser** y **Move-CsUser** podrían dar el resultado siguiente:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


