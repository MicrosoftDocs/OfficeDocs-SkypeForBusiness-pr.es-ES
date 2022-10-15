---
title: Configurar Teams Phone Mobile
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
description: Obtenga más información sobre cómo configurar Teams Phone Mobile.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0ffdc63200289f6f77dccb5214e8b2e3c3b344f
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576606"
---
# <a name="configure-teams-phone-mobile"></a>Configurar Teams Phone Mobile

Para obtener una lista de los operadores que participan en el programa Teléfono Microsoft Teams Mobile y los países o regiones donde su servicio está disponible, consulte [Teléfono móvil de Microsoft 365 Teams](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/teams-phone-mobile).

En este artículo se describe cómo configurar Teams Phone Mobile. Antes de configurar Teams Phone Mobile, asegúrese de leer [Plan para Teams Phone Mobile](operator-connect-mobile-plan.md) para obtener información sobre ventajas, requisitos previos y licencias.

## <a name="enable-an-operator"></a>Habilitar un operador

Puede habilitar, editar y quitar operadores en el Centro de administración de Teams. En el panel de navegación izquierdo, vaya a **Operadores de > de voz**.

Para habilitar un operador:

1. Elija un operador compatible con Teams Phone Mobile. En la pestaña **Todos los operadores** , filtre los operadores disponibles por región o servicio para encontrar el operador adecuado compatible con Teams Phone Mobile. A continuación, selecciona el operador que quieras habilitar.

2. En **Configuración del operador**, selecciona los países que quieras habilitar con el operador seleccionado.

3. **Proporcionar información de contacto.** Tu información de contacto, incluyendo tu nombre completo y dirección de correo electrónico, se compartirá automáticamente con tu operador. Puede cambiar esta información más adelante. Además, tendrás que proporcionar el tamaño de la empresa y tendrás la opción de proporcionar tu número de teléfono. Los operadores usarán esta información para ponerse en contacto con usted con más detalles sobre Teams Phone Mobile.

4. Acepta el aviso de transferencia de datos.

5. Selecciona **Agregar como mi operador** para guardar.

## <a name="set-up-phone-numbers"></a>Configurar números de teléfono

Si desea agregar los números de teléfono de pago habilitados para SIM de su empresa a Teams, póngase en contacto con su operador para asegurarse de que tiene la suscripción válida de Teams Phone Mobile y que pueden cargar sus números en Teams. Una vez que el operador complete el pedido, puede asignar esos números a los usuarios. 

Para buscar el sitio web de su operador, consulte el [directorio móvil de Microsoft 365 Teams Phone](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, consulte [Buscar su id. de inquilino de Microsoft 365](/onedrive/find-your-office-365-tenant-id.md). Puede que esté realizando la portabilidad de un número de teléfono de escritorio o un número de línea de cable existente a una suscripción de voz inalámbrica si es compatible con su región y con su operador. 

La manera de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo los números existentes de los planes de llamadas de Microsoft, Conexión de operadores o enrutamiento directo.

- [Adquirir números para nuevos usuarios de Teams](#acquire-numbers-for-new-teams-users).  

- [Mueva los números de Planes de llamadas a Teams Phone Mobile](#move-numbers-from-calling-plans-to-teams-phone-mobile).  

- [Mueva los números de Operador Conectar a Teams Phone Mobile](#move-numbers-from-operator-connect-to-teams-phone-mobile).  

- [Mueva los números de Enrutamiento directo a Teams Phone Mobile](#move-numbers-from-direct-routing-to-teams-phone-mobile).  


### <a name="assign-numbers-to-emergency-addresses"></a>Asignar números a direcciones de emergencia

La dirección de emergencia es una ubicación estática asociada a un número cuando es accesible a través de clientes o extremos de Microsoft Teams. Una vez creadas las direcciones de emergencia en el Centro de administración de Teams, la forma de asignarlas o cambiarlas más adelante dependerá de su operador.

Para asignar números a las direcciones de emergencia que usan los puntos de conexión de Microsoft Teams, su operador implementará uno de los tres escenarios siguientes:

- El operador asigna direcciones de emergencia a los números de teléfono y le permite cambiarlas más adelante en el Centro de administración de Teams.

- El operador no asigna direcciones y le permite asignar direcciones de emergencia a los números de teléfono del centro de administración de Teams.

- El operador asigna direcciones de emergencia a los números de teléfono y no le permite cambiarlas. En este escenario, deberá ponerse en contacto con su operador para realizar cambios en los números de teléfono y su dirección de emergencia asignada.

Cuando las llamadas se realizan a través del marcador nativo del smartphone habilitado para SIM, el operador puede usar las coordenadas geográficas o la torre de telefonía móvil que gestiona la llamada a una ubicación aproximada de emergencia para obtener asistencia.

Para obtener más información sobre las llamadas de emergencia, consulte [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md) y [Planear y configurar llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md).

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para nuevos usuarios de Teams

Para adquirir números para nuevos usuarios de Teams, siga estos pasos:

1. **Asigne una licencia de Sistema telefónico y una licencia del complemento Teams Phone Mobile.** Puede asignar una licencia de Sistema telefónico y una licencia de complemento de Teams Phone Mobile a los usuarios desde la Centro de administración de Microsoft 365 o mediante PowerShell. Para obtener más información, consulte [Asignar licencias de complementos de Teams a usuarios](teams-add-on-licensing/assign-teams-add-on-licenses.md).

2. **Los usuarios a los que se les asignarán números de teléfono adquiridos con Teams Phone Mobile deben estar en el modo TeamsOnly.** Si su organización está en modo TeamsOnly, todos los usuarios se encuentran en el modo TeamsOnly. 

   Para comprobarlo, en el Centro de administración de Teams, vaya a **Teams > configuración de actualización de Teams**. Si su organización está en modo Islas, compruebe si determinados usuarios están en modo TeamsOnly. Vaya a **Usuarios** y seleccione una cuenta de usuario. En la pestaña **Cuenta** , en **Actualización de Teams,** el modo de coexistencia debe establecerse en TeamsOnly.

3. **Adquirir números.** Ve al sitio web de tu operador o ponte en contacto con él para pedir y adquirir números de teléfono móviles habilitados para SIM con el servicio Teams Phone Mobile habilitado. 

   Una vez que el operador complete el pedido, cargará los números de teléfono móviles habilitados para SIM en tu inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de teléfono de voz >**. 

4. **Asignar números.** Puede asignar números a los usuarios desde el Centro de administración de Teams o mediante PowerShell. Para obtener más información, vea [Asignar números](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-calling-plans-to-teams-phone-mobile"></a>Mover números de Planes de llamadas a Teams Phone Mobile

1. Asegúrese de que tiene suscripciones válidas de Microsoft 365 para Teams Phone Mobile y la licencia del complemento Teléfono móvil de Teams. Debe [quitar el número de teléfono que se va a mover para los usuarios respectivos](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). 

2. Ponte en contacto con tu operador para transferir tus números a Teams Phone Mobile en un plan de voz inalámbrica apto habilitado para SIM. 

3. Una vez que el operador complete la solicitud de portabilidad, el operador cargará los números en su inquilino.  Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de teléfono de voz >**. 

4. Puede asignar números a los usuarios mediante el Centro de administración de Teams o powerShell. Para obtener más información, vea [Asignar números](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-operator-connect-to-teams-phone-mobile"></a>Mover números de Operador Conectar a Teams Phone Mobile

1. Asegúrese de que tiene suscripciones válidas de Microsoft 365 para Teams Phone Mobile y la licencia del complemento Teléfono móvil de Teams. Debe [quitar el número de teléfono que se va a mover para los usuarios respectivos](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user). Ponte en contacto con el proveedor Operator Connect existente para quitar los números de teléfono de tu inquilino.

2. Ponte en contacto con tu operador para transferir tus números a Teams Phone Mobile en un plan de voz inalámbrica apto habilitado para SIM. 

3. Una vez que el operador complete la solicitud de portabilidad, el operador cargará los números en su inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de teléfono de voz >**. 

4. Puede asignar números a los usuarios mediante el Centro de administración de Teams o powerShell. Para obtener más información, vea [Asignar números](assign-change-or-remove-a-phone-number-for-a-user.md).

### <a name="move-numbers-from-direct-routing-to-teams-phone-mobile"></a>Mover números de Enrutamiento directo a Teams Phone Mobile   

Para mover números de Enrutamiento directo a Teams Phone Mobile, deberá completar los pasos siguientes:

1. [Determine si los números de enrutamiento directo existentes se asignan en línea o de forma local](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises).

2. [Migre los números de Enrutamiento directo a Teams Phone Mobile](#migrate-the-numbers-from-direct-routing-to-teams-phone-mobile).

2. [Quite la directiva de enrutamiento de voz en línea asociada con el usuario](#remove-the-online-voice-routing-policy-associated-with-your-user).

3. [Adquirir números de teléfono](#acquire-phone-numbers).

4. [Asignar números de teléfono](#assign-phone-numbers).

Estos pasos se describen con mayor detalle en las secciones siguientes.

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>Determine si los números de enrutamiento directo existentes se asignan en línea o de forma local.

La forma de quitar los números de enrutamiento directo existentes depende de si el número está asignado de forma local o en línea.

1. En primer lugar, compruebe que el usuario tiene asignado un número de enrutamiento directo ejecutando el siguiente comando de PowerShell de Teams. NumberType debe ser DirectRouting:

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. Determine si el número está asignado en línea o local ejecutando el siguiente comando de PowerShell de Teams:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   Si OnPremLineUri se rellena con un número de teléfono E.164, el número de teléfono se asignó de forma local y se sincronizó con Microsoft 365.

#### <a name="migrate-the-numbers-from-direct-routing-to-teams-phone-mobile"></a>Migrar los números de Enrutamiento directo a Teams Phone Mobile

Para migrar números, siga los pasos que se indican a continuación.  

> [!Important]
> Durante la migración, el número de teléfono estará fuera de servicio. Coordine con su operador de Teams Phone Mobile antes de comenzar la migración.

- **Para migrar los números de enrutamiento directo existentes asignados en línea a Teams Phone Mobile**, póngase en contacto con su operador. Para buscar el sitio web de su operador, consulte [Directorio móvil de Microsoft 365 Teams Phone](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory). En la fecha y hora acordadas, su operador migrará los números de Enrutamiento directo a Teams Phone Mobile. Esto puede implicar la eliminación del número de teléfono que se migra de su inquilino y agregarlo de nuevo como un nuevo número de teléfono asociado con Teams Phone Mobile.

- **Para migrar números de enrutamiento directo asignados localmente a Teams Phone Mobile**, ejecute el siguiente comando Skype Empresarial Server PowerShell:

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  Para comprobar si se quitó el número local y los cambios se han sincronizado desde local a Microsoft 365, ejecute el siguiente comando de PowerShell de Teams:

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

Después de que los cambios se hayan sincronizado con el directorio en línea de Microsoft 365, el resultado esperado es:

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

Para comprobar si se ha quitado el número de teléfono, ejecute el siguiente comando de PowerShell de Teams:

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> La cantidad de tiempo que tarda en surtir efecto la eliminación depende de la configuración. Quitar el número de teléfono puede tardar hasta 10 minutos, en raras ocasiones, puede tardar hasta 24 horas. 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>Quitar la directiva de enrutamiento de voz en línea asociada con el usuario

Una vez que el número esté sin asignar, quite la directiva de enrutamiento de voz en línea asociada con el usuario ejecutando el siguiente comando de PowerShell de Teams:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>Adquiera los números de teléfono

Ponte en contacto con tu operador para transferir tus números a Teams Phone Mobile en un plan de voz inalámbrica apto habilitado para SIM.

Una vez que tu operador complete el pedido, cargará los números en el inquilino. Para ver los números y el proveedor en el centro de administración de Teams, vaya a **Números de teléfono de voz >**. 

#### <a name="assign-phone-numbers"></a>Asignar números de teléfono

Puede asignar números de Teléfono móvil de Teams a los usuarios mediante el Centro de administración de Teams o powerShell. Para obtener más información, vea [Asignar números](assign-change-or-remove-a-phone-number-for-a-user.md).


## <a name="manage-your-operators"></a>Administrar los operadores

En la pestaña **Mis operadores** , puede ver sus operadores y su estado, y realizar los siguientes cambios en las selecciones:  

- Administrar los servicios del operador por país
- Suspender un operador
- Quitar un operador

> [!NOTE]
> Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios de la organización o del país y ponerse en contacto con el operador para liberar los números.

## <a name="release-numbers"></a>Números de versión

Para liberar números de teléfono desde el Centro de administración de Teams, vaya a la página **Números** de teléfono y seleccione un número.

- Si el número de teléfono no está asignado a un usuario, seleccione **Liberar**.

- Si el número de teléfono está asignado a un usuario, tendrá que anular la asignación del número. Seleccione **Editar** y, después, **Quitar usuario**. Después de guardar los cambios, selecciona **Liberar**.

## <a name="manage-user-incoming-calling-policies"></a>Administrar directivas de llamadas entrantes de usuario

Puede administrar las directivas de llamadas entrantes de un usuario mediante el Centro de administración de Teams o PowerShell. De forma predeterminada, las llamadas entrantes para los usuarios de Teams Phone Mobile llamarán primero a la aplicación Teams en el dispositivo móvil habilitado para SIM del usuario. 

- Si la preferencia de llamadas entrantes de un usuario se establece en la aplicación Teams, todas las llamadas entrantes sonarán simultáneamente a la aplicación Teams en el smartphone habilitado para SIM y en cualquier otro punto de conexión de Teams en otros dispositivos. 

- Si la preferencia de llamadas entrantes de un usuario se establece en el marcador nativo, todas las llamadas entrantes suenan en el smartphone habilitado para SIM y suenan simultáneamente en todos los demás puntos de conexión de Teams en otros dispositivos. 

### <a name="use-the-teams-admin-center"></a>Usar el Centro de administración de Teams

Para administrar las directivas de llamadas entrantes de un usuario mediante el Centro de administración de Teams:

1. En la pestaña voz, seleccione **Directivas de movilidad**. 

2. Para agregar una nueva directiva móvil, haga clic en **Agregar**.

3. Seleccione un nombre, agregue una descripción de la directiva y elija una de las siguientes opciones en la opción desplegable **Seleccionar un marcador móvil** :

   -  **Microsoft Teams** para llamar primero a la aplicación Teams en el smartphone habilitado para SIM. 

   - **Marcador nativo** para hacer sonar el marcador nativo en el smartphone habilitado para SIM en primer lugar.

4. Asigne las directivas a los usuarios. Vea [Asignar directivas](assign-policies-users-and-groups.md).


### <a name="use-powershell"></a>Usar PowerShell

1. Conéctese a su inquilino: Connect-MicrosoftTeams.
 
2. Cree directivas para que las llamadas entrantes llamen primero al marcador nativo o a la aplicación de Teams. (Puede elegir el nombre de la directiva; en este ejemplo se usa TeamsFirst y NativeFirst). 

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. Conceder directivas a los usuarios: 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. Comprobar directivas de usuario: 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. Compruebe todas las opciones de directiva de movilidad: 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








