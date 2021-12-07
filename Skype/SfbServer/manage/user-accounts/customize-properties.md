---
title: Personalizar las propiedades de cuenta de usuario para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mathavale
author: v-mathavale
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede utilizar los procedimientos que se describen en esta sección para modificar las propiedades de cuenta de usuario individuales.
ms.openlocfilehash: f80847b57122539654541a444f427f4031ee6197
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314208"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Personalizar las propiedades de cuenta de usuario para Skype Empresarial Server
 
Puede utilizar los procedimientos que se describen en esta sección para modificar las propiedades de cuenta de usuario individuales.
 
Hay dos operaciones básicas que se pueden realizar en el nivel de usuario individual:
 
- [Configurar opciones de telefonía para una cuenta de usuario específica](#configure-telephony-options-for-a-specific-user-account)

- [Mover usuarios a otro grupo](#move-users-to-another-pool)
 
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Configurar opciones de telefonía para una cuenta de usuario específica

Puede personalizar la configuración de telefonía para un usuario específico (siempre que el usuario individual se haya habilitado para Skype Empresarial Server y la organización admita telefonía).
 
Skype Empresarial Server opciones de telefonía del usuario son las siguientes:
 
|Opciones de telefonía  |Descripción  |
|---------|---------|
|**Audio y vídeo deshabilitados**|El usuario no puede realizar llamadas con audio y vídeo.|
|**Solo de equipo a equipo** | El usuario solo puede realizar llamadas de audio o vídeo de un equipo a otro.|
|**Telefonía IP empresarial** | El usuario puede usar la infraestructura Skype Empresarial Server para enrutar todas las llamadas entrantes y salientes. También puede realizar llamadas de equipo a equipo.|
|**Control remoto de llamadas**   | El usuario puede usar Skype Empresarial Server para controlar el teléfono de escritorio y también puede realizar llamadas de EQUIPO a EQUIPO.|
 
Para obtener más información sobre cómo [](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) configurar la telefonía para una organización, vea Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server e Implementar Telefonía IP empresarial en [Skype Empresarial Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) en el Documentación de implementación.
 
### <a name="configure-telephony-options-for-specific-users-using-new-control-panel"></a>Configurar opciones de telefonía para usuarios específicos mediante el nuevo Panel de control 
 
1. Abra una ventana del explorador y escriba la dirección URL de administración para abrir el panel Skype Empresarial Server control.
 
2. Inicie sesión con una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator.
 
3. En el panel izquierdo, seleccione **Usuarios**.
 
4. En el **cuadro Buscar,** escriba todo o la primera parte del nombre para mostrar y haga clic en **Buscar**.
 
5. En la tabla, haga doble clic en la cuenta de usuario que desea modificar.
 
6. En el panel que aparece, haga clic en el icono de lápiz situado junto a **Directivas asignadas**.
 
7. En **Telefonía**, siga este procedimiento:
 
    1. Para deshabilitar las llamadas de audio y vídeo para el usuario, seleccione **Audio y vídeo deshabilitados** en la lista desplegable.
 
    2. Para habilitar las comunicaciones de audio de EQUIPO a EQUIPO para el usuario, pero no para el control remoto de llamadas o Telefonía IP empresarial, seleccione PC a **PC** solo en la lista desplegable. Especifique un valor para **URI de línea** para el teléfono que usa el usuario para comunicaciones de audio de equipo a equipo.
 
    3. Para enrutar las llamadas de teléfono del usuario mediante la infraestructura de Skype Empresarial de acuerdo con la clase de directiva de servicio, incluida la comunicación de audio de EQUIPO a **EQUIPO,** seleccione Telefonía IP empresarial en la lista desplegable. En **URI de línea**, especifique el número de teléfono para la Telefonía IP empresarial. En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas adecuadas para el usuario. Para especificar las reglas de normalización para traducir los números de teléfono marcados por el usuario al formato E.164, seleccione el perfil de ubicación adecuado en la lista desplegable Directiva **de** ubicación.
 
    4. Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea de teléfono de escritorio desde Skype Empresarial Server para realizar llamadas de EQUIPO a EQUIPO y llamadas de equipo a teléfono, seleccione **Control** remoto de llamadas en la lista desplegable. En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas. El usuario debe tener un teléfono de escritorio y una conexión de central de conmutación (PBX) para el enrutamiento de llamadas.

> [!NOTE]
> El nuevo Panel de control no está disponible para Skype Empresarial Server 2015.

### <a name="configure-telephony-options-for-specific-users-using-legacy-control-panel"></a>Configurar opciones de telefonía para usuarios específicos mediante el Panel de control heredado
 
1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
 
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
 
3. En el panel izquierdo, seleccione **Usuarios**.
 
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.
 
5. En la tabla, seleccione la cuenta de usuario que desea modificar.
 
6. En el menú **Edición**, seleccione **Modificar**.
 
7. En **Telefonía**, siga este procedimiento:
 
    1. Para deshabilitar las llamadas de audio y vídeo para el usuario, **seleccione Audio/vídeo deshabilitado.**
 
    2. Para habilitar las comunicaciones de audio de PC a PC para el usuario, pero no para el control remoto de llamadas o Telefonía IP empresarial, seleccione **solo PC a PC**. Especifique un valor para **URI de línea** para el teléfono que usa el usuario para comunicaciones de audio de equipo a equipo.
 
    3. Para enrutar las llamadas telefónicas del usuario mediante la infraestructura Skype Empresarial de acuerdo con la clase de directiva de servicio, incluida la comunicación de audio de EQUIPO a **PC,** seleccione Telefonía IP empresarial . En **URI de línea**, especifique el número de teléfono para la Telefonía IP empresarial. En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas adecuadas para el usuario. Para especificar las reglas de normalización para convertir los números de teléfono que marque el usuario a formato E.164, seleccione el perfil de ubicación apropiado en **Directiva de ubicación**.
 
    4. Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea de teléfono de escritorio desde Skype Empresarial Server para realizar llamadas de equipo a equipo y de equipo a teléfono, seleccione Control remoto de **llamadas**. En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas. El usuario debe tener un teléfono de escritorio y una conexión de central de conmutación (PBX) para el enrutamiento de llamadas.

## <a name="move-users-to-another-pool"></a>Mover usuarios a otro grupo

Puede usar el Panel Skype Empresarial Server control para asignar usuarios a un servidor o grupo específico.
 
> [!TIP]
> Mover todos los usuarios existentes de un grupo de servidores de origen que ejecuta Lync Server 2010 o versiones anteriores a un grupo de destino de Skype Empresarial Server en un entorno complejo de Active Directory puede provocar una replicación de Active Directory más lenta. Para evitar esto, puede usar filtros de búsqueda para mover usuarios de grupos que ejecutan Lync Server 2010 o versiones anteriores por separado, o puede usar el Shell de administración de Skype Empresarial Server para mover usuarios con cmdlets. Además, la funcionalidad de filtro funciona con Skype Empresarial Server usuarios. 
 
### <a name="move-selected-users-to-a-different-server-or-pool-using-new-control-panel"></a>Mover usuarios seleccionados a otro servidor o grupo de servidores mediante el nuevo Panel de control

1. Abra una ventana del explorador y escriba la dirección URL de administración para abrir el panel Skype Empresarial Server control.
 
2. Inicie sesión con una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator. 
 
3. En el panel izquierdo, seleccione **Usuarios**.
 
4. En el **cuadro Buscar,** escriba todo o la primera parte del nombre para mostrar y haga clic en **Buscar**.
 
5. En la tabla, haga doble clic para seleccionar un usuario o usuarios específicos en la lista. 

6. En el panel que aparece, haga clic en el icono de lápiz situado junto a **Grupo de registradores**.
 
7. En **Mover usuarios**, seleccione el grupo al que desea mover los usuarios en la lista desplegable.
 
8. (Opcional) Si el servidor o grupo de destino no está disponible, active la **casilla Forzar.**
 
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados. 

> [!NOTE]
> El nuevo Panel de control no está disponible para Skype Empresarial Server 2015.

### <a name="move-selected-users-to-a-different-server-or-pool-using-legacy-control-panel"></a>Mover usuarios seleccionados a otro servidor o grupo de servidores mediante el Panel de control heredado

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
 
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
 
3. En el panel izquierdo, seleccione **Usuarios**.
 
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**. 
 
5. En la tabla, seleccione uno o varios usuarios de la lista. 
 
6. En el menú  **Acción**, haga clic en  **Mover usuarios seleccionados a un grupo de servidores**.
 
7. En **Mover usuarios**, seleccione el grupo de servidores al que desea trasladar los usuarios en **Grupo de registrador de destino**.
 
8. (Opcional) Si el servidor o grupo de destino no está disponible, active la **casilla Forzar.**
 
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados. 
 
### <a name="move-users-from-one-pool-to-a-different-pool-by-using-a-filter-using-legacy-control-panel"></a>Mover usuarios de un grupo de servidores a otro mediante un filtro mediante el Panel de control heredado 

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
 
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control. 
 
3. En el panel izquierdo, seleccione **Usuarios**.
 
4. En **Búsqueda de usuario,** **seleccione Buscar** y, a continuación, haga clic en **Agregar filtro**.
 
5. En los Criterios de búsqueda, seleccione **Grupo de registradores**, **Igual que**, **FQDN del grupo actual** y, a continuación, haga clic en **Buscar**.
 
6. En el **menú Acción,** seleccione **Mover todos los usuarios al grupo**.
 
    > [!NOTE]
    > Cuando se aplica un filtro a un conjunto de usuarios existente, la opción **Mover todos los usuarios al grupo** se refiere al subconjunto de usuarios filtrados, no a **todos** los usuarios posibles.
 
7. En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registradores de origen**.
 
8. En **Grupo de registradores de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.
 
9. (Opcional) Si el servidor o grupo de destino no está disponible, active la **casilla Forzar.**
 
    > [!CAUTION]
    > Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado y contactos). Si no se selecciona, se mueven la cuenta y los datos asociados. 
 
### <a name="move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Mover usuarios de un grupo a otro mediante Windows PowerShell cmdlets

1. En función de cómo ejecute Windows PowerShell comandos (es decir, local o remotamente), debe iniciar sesión como miembro de los roles Skype Empresarial Server administrativos correctos de la siguiente manera:
 
    1. Si ejecuta los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor front-end): inicie sesión en el equipo donde se instala el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en **Delegate Setup Permissions**.
 
    2. Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end de Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator, inicie sesión en cualquier equipo de la implementación interna.
 
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** en Todos los **programas,** haga clic en **Skype Empresarial** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.
 
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


