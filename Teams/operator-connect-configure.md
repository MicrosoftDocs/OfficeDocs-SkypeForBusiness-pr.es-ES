---
title: Configurar operador Conectar
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
description: Obtenga más información sobre cómo configurar operador Conectar.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb6ceacb6e7a2cc4d458c86edda96511e5230ace
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717861"
---
# <a name="configure-operator-connect"></a>Configurar operador Conectar

>[!NOTE]
>El Conectar operador solo está disponible actualmente en **la vista previa pública.** La vista previa pública le permite probar las próximas características y proporcionar comentarios. Es posible que las características incluidas en la vista previa pública no se completen, que se someten a cambios y que no se admiten en Office 365 Administración Pública nubes.

En este artículo se describe cómo configurar operador Conectar. Antes de configurar Conectar operador, asegúrese de leer Plan para operadores [Conectar](operator-connect-plan.md) información sobre requisitos previos y licencias.

## <a name="enable-an-operator"></a>Habilitar un operador

Puede habilitar, editar y quitar operadores en el Centro Teams administración. En el panel de navegación izquierdo, vaya **a Operadores de > voz.**

Para habilitar un operador:

1. **Elija un operador.** En la **pestaña Todos los** operadores, filtre los operadores disponibles por región o servicio para buscar el operador adecuado para sus necesidades de voz. A continuación, seleccione el operador que desea habilitar.  

2. **Seleccione países.** En **Configuración del operador,** seleccione los países que desea habilitar con el operador seleccionado.

3. **Proporcionar información de contacto (opcional).** Si desea que los operadores se pondrán en contacto con usted con información adicional sobre Conectar operador, active la casilla y proporcione su información de contacto.  

4. **Aceptar el aviso de transferencia de datos.**

5. **Agregue el operador.** Seleccione **Agregar como mi operador** para guardar.

## <a name="set-up-phone-numbers"></a>Configurar números de teléfono

La forma de configurar los números de teléfono depende de si está configurando números para nuevos usuarios o moviendo números existentes desde Planes de llamadas de Microsoft o Enrutamiento directo.

- Si necesita adquirir números de teléfono para nuevos usuarios, vea Adquirir números para nuevos [Teams usuarios.](#acquire-numbers-for-new-teams-users)

- Si desea mover números existentes de planes de llamadas a Conectar, vea Mover números de planes de llamadas a [operador Conectar](#move-numbers-from-calling-plans-to-operator-connect).

- Si desea mover números existentes de Enrutamiento directo a Operador Conectar, vea Mover números de enrutamiento directo a [operador Conectar](#move-numbers-from-direct-routing-to-operator-connect).

>[!IMPORTANT]
>**Direcciones de emergencia:** Las direcciones de emergencia asociadas a un número adquirido del operador se administran directamente con el operador. Póngase en contacto con el operador para realizar cualquier cambio.

### <a name="acquire-numbers-for-new-teams-users"></a>Adquirir números para nuevos Teams usuarios

Para adquirir números para nuevos Teams usuarios, siga estos pasos:

1. **Asigne una Sistema telefónico licencia.** Puede asignar una licencia de Sistema telefónico a los usuarios desde el centro de administración de Microsoft 365 o mediante PowerShell. Para obtener más información, vea [Asignar Teams de complementos a los usuarios.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

2. **Asegúrese de que está en modo TeamsOnly.** Para comprobarlo, en el Teams de administración, vaya a Configuración de toda **la organización > Teams actualización.** El modo de coexistencia debe establecerse en Teams solo.

3. **Crear y validar direcciones de emergencia.** En el Teams de administración, vaya a Ubicaciones **> de** emergencia para configurar direcciones de emergencia. Para obtener más información, vea [Agregar, cambiar o quitar una ubicación de emergencia para su organización.](add-change-remove-emergency-location-organization.md)

4. **Adquirir números.** Vaya al sitio web de su operador para solicitar y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators) Tendrá que proporcionar su id. de inquilino. Si no conoce su identificador de inquilino, vea Buscar su Microsoft 365 [inquilino para](/onedrive/find-your-office-365-tenant-id) obtener más información.

5. **Asignar números.** Una vez que el operador complete el pedido, cargarán números a su inquilino. Puede ver los números y el proveedor en el centro Teams de administración yendo a Números **> Teléfono voz.** Asigne números a los usuarios mediante el centro Teams de administración o mediante PowerShell. Para obtener más información, vea [Asignar números.](#assign-numbers)
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>Mover números de planes de llamadas a operador Conectar

1. Póngase en contacto con su operador para portabilidad de los números a Operador Conectar. Consulte [Operadores](#operators) para buscar el sitio web del operador.

2. Después de que el operador complete el pedido de porte, puede quitar los números de teléfono del Plan de llamadas de los usuarios y quitar la licencia del plan de llamadas. A continuación, el operador puede cargar los números en el espacio empresarial.

3. Asigne números Conectar operador a los usuarios mediante el centro Teams administrador o mediante PowerShell. Para obtener más información, vea [Asignar números.](#assign-numbers)

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>Mover números de Enrutamiento directo a Operador Conectar

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

3. Vaya al sitio web de su operador para solicitar y adquirir números de teléfono. Para obtener una lista de sitios web de operadores, vea [Operadores.](#operators) Tendrá que proporcionar su id. de inquilino. Si no conoce su identificador de inquilino, vea Buscar su Microsoft 365 [inquilino para](/onedrive/find-your-office-365-tenant-id) obtener más información.

4. Una vez que el operador complete el pedido, cargarán números a su inquilino. Puede ver los números y el proveedor en el centro Teams de administración yendo a Números **> Teléfono voz.** Asigne números Conectar operador a los usuarios mediante el centro Teams administrador o mediante PowerShell. Para obtener más información, vea [Asignar números.](#assign-numbers)

   

### <a name="assign-numbers"></a>Asignar números

Tanto si va a agregar nuevos Teams usuarios o mover usuarios existentes a Operador Conectar, los pasos para asignar números son los siguientes:

Para asignar números mediante el centro Teams administración, vaya a **Teléfono números.** Los pasos son los mismos que asignar números para planes de llamadas. Para obtener más información, vea [Asignar un número de teléfono a un usuario.](assign-change-or-remove-a-phone-number-for-a-user.md)

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
