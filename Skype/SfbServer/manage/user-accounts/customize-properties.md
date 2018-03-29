---
title: Personalizar propiedades de la cuenta de usuario de Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede utilizar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a>Personalizar propiedades de la cuenta de usuario de Skype para Business Server 2015
 
Puede utilizar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.
  
Hay dos operaciones básicas que pueden realizarse en el nivel de usuario individual:
  
- [Configurar las opciones de telefonía de una cuenta de usuario específica](customize-properties.md#Tel_Op)
    
- [Mover usuarios a otro grupo](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar las opciones de telefonía de una cuenta de usuario específica
<a name="Tel_Op"> </a>

Puede personalizar la configuración de telefonía para un usuario específico (siempre que el usuario se ha habilitado para Skype para Business Server 2015 y admite la telefonía de la organización).
  
Skype para las opciones de telefonía de usuario Business Server incluyen lo siguiente:
  
- **Deshabilita el audio y vídeo** El usuario no puede realizar llamadas con vídeo y audio.
    
- **PC-PC sólo** El usuario puede realizar sólo PC a PC audio o vídeo llamadas.
    
- **Telefonía IP empresarial** El usuario puede utilizar el Skype para la infraestructura de servidor de negocios 2015 para enrutar todas las llamadas entrantes y salientes. El usuario también puede realizar llamadas de PC a PC.
    
- **Control remoto de llamada** El usuario puede utilizar Skype para Business Server 2015 para controlar el teléfono de escritorio y también puede realizar llamadas de PC a PC.
    
Para obtener más información acerca de la configuración de telefonía de una organización, vea [Implementación de Telefonía IP empresarial en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) y [Permitir que los usuarios de Telefonía IP empresarial en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) en la documentación de implementación.
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar **.
    
5. En la tabla, haga clic en la cuenta de usuario que desea modificar.
    
6. En el menú **Edición** , haga clic en **Modificar**.
    
7. En **telefonía**, realice lo siguiente:
    
   - Para deshabilitar las llamadas de audio y vídeo para el usuario, haga clic en **deshabilitado de Audio y vídeo**.
    
   - Para habilitar las comunicaciones de audio de PC a PC del usuario, pero el control de llamadas remotas no o la Telefonía IP empresarial, haga clic en **PC a PC sólo**. Especifique un valor para el **URI de la línea** de teléfono que el usuario que se utiliza para las comunicaciones de audio de PC a PC.
    
   - Para enrutar las llamadas de teléfono del usuario utilizando el Skype para infraestructura empresarial con arreglo a la clase de directiva de servicios, incluida la comunicación de audio de PC a PC, haga clic en **Telefonía IP empresarial**. En **URI de línea**, especifique el número de teléfono para Telefonía IP empresarial. En **política de voz**y **políticas del plan de marcado** , especifique las políticas adecuadas para el usuario. Para especificar las reglas de normalización para convertir números de teléfono marcados por el usuario en el formato E.164, seleccione el perfil de ubicación adecuada en la **política de ubicación**.
    
   - Para habilitar la llamada remota de control, que permite a los usuarios controlar su línea de teléfono de escritorio de Skype para Business Server 2015 realizar llamadas de PC a PC y llamadas de PC a teléfono, haga clic en **control de llamada remota**. En **URI de línea**, especifique el número de teléfono para el control de llamadas remotas. El usuario debe tener un teléfono de escritorio y conexión de private branch exchange (PBX) para el enrutamiento de llamadas.
    
## <a name="move-users-to-another-pool"></a>Mover usuarios a otro grupo
<a name="Move_Users"> </a>

Puede utilizar Skype para Panel de Control de servidor empresarial para asignar a usuarios a un servidor específico o grupo.
  
> [!TIP]
> Mover todos los usuarios de un grupo de origen que se está ejecutando Lync Server 2010 o anterior a un Skype para Business Server 2015 grupo de destino en un entorno de Active Directory complejo puede provocar una replicación de Active Directory más lenta. Para evitar esto, puede utilizar filtros de búsqueda para mover usuarios desde grupos que ejecutan Lync Server 2010 o anteriormente por separado, o puede utilizar Skype para negocios de Shell de administración de servidor para mover usuarios con cmdlets. Además, la funcionalidad de filtro funciona con Skype para los usuarios de Business Server 2015. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover los usuarios seleccionados a otro servidor o grupo de

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar **. 
    
5. En la tabla, seleccione un usuario específico o los usuarios de la lista. 
    
6. En el menú **acción** , haga clic en **mover los usuarios seleccionados al grupo**.
    
7. **Mover usuarios**, seleccione el grupo que desea mover los usuarios en el **grupo de registro de destino**.
    
8. (Opcional) Si el servidor de destino o grupo de servidores no está disponible, seleccione la casilla de verificación **Forzar** .
    
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario, pero se eliminará cualquier dato de usuario asociado (por ejemplo, conferencias a las que el usuario haya programado). Si no se selecciona, se mueven la cuenta y los datos asociados. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.
    
5. **Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registro de origen**.
    
6. En el **grupo de registro de destino**, seleccione el grupo que desea mover los usuarios.
    
7. (Opcional) Si el servidor de destino o grupo de servidores no está disponible, seleccione la casilla de verificación **Forzar** .
    
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario, pero se eliminará cualquier dato de usuario asociado (por ejemplo, conferencias a las que el usuario haya programado). Si no se selecciona, se mueven la cuenta y los datos asociados. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover usuarios de un grupo a una agrupación diferente utilizando un filtro

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En **La búsqueda de usuario**, haga clic en **Buscar**y, a continuación, haga clic en **Agregar filtro**.
    
5. En los criterios de búsqueda, seleccione **Registrar el fondo**, seleccione **igual a**, seleccione **Actual FQDN del grupo de servidores**y, a continuación, haga clic en **Buscar**.
    
6. En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.
    
    > [!NOTE]
    > Cuando se aplica un filtro a un conjunto existente de los usuarios, la opción **mover todos los usuarios al grupo** es en el contexto del subconjunto filtrado de usuarios, no **todos los** posibles usuarios.
  
7. **Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registro de origen**.
    
8. En el **grupo de registro de destino**, seleccione el grupo donde desea mover los usuarios.
    
9. (Opcional) Si el servidor de destino o grupo de servidores no está disponible, seleccione la casilla de verificación **Forzar** .
    
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario, pero se eliminará cualquier dato de usuario asociado (por ejemplo, conferencias a las que el usuario haya programado y contactos). Si no se selecciona, se mueven la cuenta y los datos asociados. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover los usuarios de un grupo a otro mediante cmdlets de Windows Powershell

1. Dependiendo de cómo ejecute comandos de Windows PowerShell (es decir, local o remota), debe iniciar sesión como un miembro de la correcta Skype para funciones administrativas Business Server 2015 como sigue:
    
   a. Si está ejecutando los comandos en el equipo local (por ejemplo, iniciar la sesión directamente a un servidor Front-End): inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con la necesaria derechos de usuario como se describe en **Configuración de permisos de delegado**.
    
   b. Si está ejecutando los comandos de forma remota en otro equipo (por ejemplo, inicie sesión en el equipo y ejecutar los comandos de forma remota en un servidor estándar de edición Front-End): desde una cuenta de usuario que se asigna a la función CsUserAdministrator o la CsAdministrator función, inicie sesión en cualquier equipo en la implementación interna.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Para mover los usuarios individuales, utilice el cmdlet Move-CsUser como sigue:
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Donde el usuario mover es el Pilar Ackerman del usuario y el usuario se moverá de su grupo doméstico asignada actualmente a la pool01.contoso.net de grupo
    
4. Para mover un gran número de usuarios, utilice filtros con el cmdlet **Get-CsUser** y pasar el conjunto resultante de los usuarios a **Mover CsUser**:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Los comandos del **Movimiento Csusuario** y **Get-Csusuario** combinados pueden dar lugar a esto:
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


