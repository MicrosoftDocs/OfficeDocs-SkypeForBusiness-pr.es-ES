---
title: Configurar Operator Connect
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Obtenga más información sobre cómo configurar Operator Connect.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947582"
---
# <a name="configure-operator-connect"></a>Configurar Operator Connect

>[!NOTE]
>Operator Connect solo está disponible actualmente en **versión preliminar pública.** La vista previa pública le permite probar las próximas características y proporcionar comentarios. Es posible que las características incluidas en la versión preliminar pública no estén completas, que puedan sufrir cambios y que no sean compatibles con las nubes de Office 365 Government.

En este artículo se describe cómo configurar Operator Connect. Antes de configurar Operator Connect, asegúrese de leer [Plan para Conexión de](operator-connect-plan.md) operadores para obtener información sobre los requisitos previos y las licencias.

## <a name="enable-an-operator"></a>Habilitar un operador

Puede habilitar, editar y quitar operadores en el Centro de administración de Teams. En el panel de navegación izquierdo, vaya **a Operadores de > voz.**

Para habilitar un operador:

1. **Elija un operador.** En la **pestaña Todos los** operadores, filtre los operadores disponibles por región o servicio para buscar el operador adecuado para sus necesidades de voz. A continuación, seleccione el operador que desea habilitar.  

2. **Seleccione países.** En **Configuración del operador,** seleccione los países que desea habilitar con el operador seleccionado.

3. **Proporcionar información de contacto (opcional).** Si desea que los operadores se pondrán en contacto con usted con información adicional sobre Conexión del operador, active la casilla y proporcione su información de contacto.  

4. **Aceptar el aviso de transferencia de datos.**

5. **Agregue el operador.** Seleccione **Agregar como mi operador** para guardar.

## <a name="set-up-phone-numbers"></a>Configurar números de teléfono

La forma de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo números existentes desde Planes de llamadas de Microsoft o Enrutamiento directo.

- Si necesita adquirir números de teléfono para nuevos usuarios, vea [Adquirir números para nuevos usuarios de Teams.](#acquire-numbers-for-new-teams-users)

- Si desea mover números existentes de Planes de llamadas a Conexión de operadores, vea Mover números de planes [de llamadas a Conexión de operador.](#move-numbers-from-calling-plans-to-operator-connect)

- Si desea mover números existentes de Enrutamiento directo a Conexión del operador, vea Mover números de [Enrutamiento directo a Conexión del operador.](#move-numbers-from-direct-routing-to-operator-connect)

>[!IMPORTANT]
>**Direcciones de emergencia:** El operador administra los números de teléfono asociados con las direcciones de emergencia. Una vez que cree direcciones de emergencia en el Centro de administración de Teams, el operador asignará números de teléfono a esas direcciones de emergencia. Para realizar cambios en las direcciones de emergencia y sus números de teléfono asignados, póngase en contacto con su operador.

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para nuevos usuarios de Teams

Para adquirir números para nuevos usuarios de Teams, siga estos pasos:

1. **Asignar una licencia de Sistema telefónico.** Puede asignar una licencia de Sistema telefónico a los usuarios desde el Centro de administración de Microsoft 365 o mediante PowerShell. Para obtener más información, vea [Asignar licencias de complementos de Teams a los usuarios.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. **Asegúrese de que solo está en modo Teams.** Para comprobar si su organización solo está en modo Teams, en el Centro de administración de Teams, vaya a Configuración de toda la **organización > actualización de Teams.** Para comprobar si un usuario solo está en modo Teams, vaya a **Usuarios** y seleccione una cuenta de usuario. En la **pestaña Cuenta,** en **Actualización de Teams, compruebe** que el modo de coexistencia está establecido en "Solo Teams".

3. **Crear y validar direcciones de emergencia.** En el Centro de administración de Teams, vaya a **Ubicaciones > direcciones de emergencia para** configurar las direcciones de emergencia. Para obtener más información, vea [Agregar, cambiar o quitar una ubicación de emergencia para su organización.](add-change-remove-emergency-location-organization.md)

4. **Adquirir números.** Vaya al sitio web de su operador para solicitar y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators) Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, vea Buscar su id. de inquilino de [Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.

5. **Asignar números.** Una vez que el operador complete el pedido, cargarán números a su inquilino. Puede ver los números y el proveedor en el Centro de administración de Teams yendo a Números **de > de teléfono.** Asigne números a los usuarios mediante el Centro de administración de Teams o mediante PowerShell. Para obtener más información, vea [Asignar números.](#assign-numbers)
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de planes de llamadas a Operador Connect

1. Póngase en contacto con su operador para portabilidad de los números a Operador Connect. Consulte [Operadores](#operators) para buscar el sitio web del operador.

2. Después de que el operador complete el pedido de porte, puede quitar los números de teléfono del Plan de llamadas de los usuarios y quitar la licencia del plan de llamadas. A continuación, el operador puede cargar los números en el espacio empresarial.

3. Asignar números de Conexión de operador a los usuarios mediante el Centro de administración de Teams o mediante PowerShell. Para obtener más información, vea [Asignar números.](#assign-numbers)

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Mover números de Enrutamiento directo a Conexión del operador

1. Quite el número de teléfono existente del usuario de la siguiente manera:  

   Obtenga el URI de línea predefinida existente ejecutando el siguiente comando de PowerShell:

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   Para quitar el URI de línea predefinida, ejecute el siguiente comando de PowerShell:  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. Quite cualquier RTC asociado a los usuarios, de lo contrario, las llamadas se enrutarán a la puerta de enlace especificada en el uso de RTC. Para obtener información sobre cómo quitar el uso de RTC, vea [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).

3. Vaya al sitio web de su operador para solicitar y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators) Tendrá que proporcionar su id. de inquilino. Si no conoce su id. de inquilino, vea Buscar su id. de inquilino de [Microsoft 365](/onedrive/find-your-office-365-tenant-id) para obtener más información.

4. Una vez que el operador complete el pedido, cargarán números a su inquilino. Puede ver los números y el proveedor en el Centro de administración de Teams yendo a Números **de > de teléfono.** Asignar números de Conexión de operador a los usuarios mediante el Centro de administración de Teams o mediante PowerShell. Para obtener más información, vea [Asignar números.](#assign-numbers)

   

### <a name="assign-numbers"></a>Asignar números

Tanto si va a agregar nuevos usuarios de Teams como si mueve usuarios existentes a Operator Connect, los pasos para asignar números son los siguientes:

Para asignar números mediante el Centro de administración de Teams, vaya a **Números de teléfono.** Los pasos son los mismos que asignar números para planes de llamadas. Para obtener más información, vea [Asignar un número de teléfono a un usuario.](assign-change-or-remove-a-phone-number-for-a-user.md)

Para asignar números mediante PowerShell, use el cmdlet Set-CsOnlineVoiceUser siguiente:

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

Por ejemplo:

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

Para obtener más información sobre cómo asignar números de teléfono a los usuarios, vea Asignar, cambiar o quitar un número de teléfono [para un usuario.](assign-change-or-remove-a-phone-number-for-a-user.md)



## <a name="manage-your-operators"></a>Administrar los operadores

Desde la pestaña Mis operadores, puede ver los operadores y su estado y realizar los siguientes cambios en las selecciones:  

- Administrar servicios de operadores por país
- Suspender un operador
- Quitar un operador

> [!NOTE]
> Antes de quitar un operador de su organización o de un país, debe quitar todos los números de teléfono asignados a los usuarios de la organización o el país y ponerse en contacto con el operador para liberar los números.

## <a name="operators"></a>Operadores

Puede adquirir números de teléfono de los siguientes operadores yendo a los sitios web vinculados aquí:


|Operador  |Sitio web del operador  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
