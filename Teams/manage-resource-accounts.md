---
title: Administrar cuentas de recursos en Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: En este artículo, aprenderá a crear, editar y administrar cuentas de recursos en Microsoft Teams.
ms.openlocfilehash: 7ccc7a26c83357d68147381101ef8a97184f03f4
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993526"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Administrar cuentas de recursos en Microsoft Teams

Una cuenta de recursos es un objeto de usuario deshabilitado en Azure AD y se puede usar para representar recursos en general. Por ejemplo, una cuenta de recursos puede usarse en Exchange para representar salas de conferencias y permitirles tener un número de teléfono y un calendario. Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.

En Microsoft Teams, es necesario disponer de una cuenta de recursos para cada operador automático o cola de llamadas. A las cuentas de recursos también se les puede asignar números de teléfono de servicio. Así es como asigna números de teléfono a los operadores automáticos y las colas de llamadas, lo que permite que los autores de llamadas de equipos externos puedan comunicarse con el operador automático o la cola de llamadas.

En este artículo se explica cómo crear cuentas de recursos y prepararlas para usarlas con los operadores automáticos y las colas de llamadas.

Antes de iniciar los procedimientos de este artículo, asegúrese de que ha hecho lo siguiente:

- [Obtener licencias de usuario virtual](#obtain-virtual-user-licenses)
- [Obtener números de servicio](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Obtener licencias de usuario virtual

Cada cuenta de recursos requiere una licencia para poder trabajar con los operadores automáticos y las colas de llamadas. Puede usar una licencia gratuita *de usuario virtual de Microsoft 365 Phone System* . Para obtener estas licencias, consulte [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md).

Más adelante en este artículo, se explica cómo asignar la licencia a una cuenta de recursos.

Para obtener la licencia de usuario virtual, en el centro de administración de Microsoft 365 **Billing** , vaya a  >  **Purchase services**  >  **suscripciones del complemento** de servicios de compra de facturación y desplácese hasta el final: verá la licencia *de usuario virtual del sistema telefónico* . Seleccione **comprar ahora**. Hay un costo cero, pero sigue siendo necesario seguir estos pasos para adquirir la licencia.

### <a name="obtain-service-numbers"></a>Obtener números de servicio

Los números de servicio son opcionales para los operadores automáticos y las colas de llamadas, pero necesitará al menos un número de servicio para que las personas que llamen puedan comunicarse con el operador automático y la configuración de la cola de llamadas. Para cualquier operador automático o cola de llamadas a los que desee ser alcanzable directamente por un número de servicio, debe tener una cuenta de recursos con un número de servicio asociado.

Las cuentas de recursos pueden usar números de servicio de pago o gratuitos. Puedes solicitar números nuevos o portar números existentes de otro transportista.

Para obtener nuevos números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md).

Para trasladar un número de otro proveedor, consulte [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Puede crear una cuenta de recursos en el centro de administración de Teams.

![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](media/resource-account-add.png)

1. En el centro de administración de Teams, expanda **configuración de toda la organización** y, a continuación, haga clic en **cuentas de recursos**.

2. Haga clic en **Agregar**.

3. En el panel **Agregar cuenta de recursos** , rellene el campo **nombre para mostrar** , nombre de **usuario** y el **tipo de cuenta recurso**. El tipo de cuenta de recurso puede ser **operador automático** o **cola de llamadas** , en función de cómo desee usar esta cuenta de recurso.

4. Haga clic en **Guardar**.

![Captura de pantalla de una lista de cuentas de recursos](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Asignar una licencia

Para cada cuenta de recursos, debe asignar una licencia *de sistema telefónico o licencia* *de usuario Virtual de Microsoft 365* .

![Captura de pantalla de la interfaz de usuario de asignación de licencias en el centro de administración de Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. En el centro de administración de Microsoft 365, haga clic en la cuenta de recursos a la que desea asignar una licencia.

2. En la pestaña **licencias y aplicaciones** , en **licencias** , seleccione **Microsoft 365 Phone System-virtual User**.

3. Haga clic en **Guardar cambios**.

## <a name="assign-a-service-number"></a>Asignar un número de servicio

Si está planeando usar la cuenta de recursos con un operador automático o una cola de llamadas que requiera un número de servicio, asigne un número a la cuenta de recursos.

![Captura de pantalla de la interfaz de usuario de asignación de número de servicio](media/resource-account-assign-phone-number.png)

1. En el centro de administración de Teams, en la página **cuentas de recursos** , seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en **asignar o quitar asignación**.

2. En la lista desplegable **tipo de número de teléfono** , elija el tipo de número que desea usar.

3. En el cuadro **número de teléfono asignado** , busque el número que desea usar y haga clic en **Agregar**.

4. Haga clic en **Guardar**.


Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, necesita usar PowerShell:

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Siguientes pasos

Una vez que haya completado la configuración de la cuenta de recursos y la asignación de un número de servicio si es necesario, estará listo para usar la cuenta de recursos con un operador automático o una cola de llamadas.

Vea las referencias siguientes:

 - [Operador automático de la nube](create-a-phone-system-auto-attendant.md)

 - [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)

Puede editar el **nombre para mostrar** de la cuenta de recursos y el tipo de **cuenta de recursos** con la opción **Editar** . Haga clic en **Guardar** cuando haya terminado.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Cambiar una cuenta de recursos existente para usar una licencia de usuario virtual

Si decide cambiar las licencias de la cuenta de recursos existente de una licencia de **sistema telefónico** a una licencia de usuario virtual, tendrá que adquirir la licencia de usuario virtual gratuita y, a continuación, seguir los pasos que se indican en el centro de administración de Microsoft 365 para [mover usuarios a una suscripción diferente](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Quitar siempre una licencia de sistema telefónico completo y asignar la licencia de usuario virtual en la misma actividad de licencia. Si quita la licencia anterior, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para la licencia de usuario virtual y quite la cuenta de recursos dañados.

## <a name="skype-for-business-server-2019"></a>Skype empresarial Server 2019

Cuentas de recursos alojados en Skype empresarial Server 2019 que se pueden usar con las colas de llamadas en la nube y los operadores automáticos de la nube, consulte [planear colas de llamadas en la](/SkypeforBusiness/hybrid/plan-call-queue) nube o [planear operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Las implementaciones híbridas (números alojados en enrutamiento directo) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) en un servidor local de Skype empresarial Server 2019.

Los identificadores de la aplicación que necesita usar durante la creación de las instancias de la aplicación son:

- **Operador automático:** ce933385-9390-45D1-9512-c8d228074e07
- **Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07

> [!NOTE]
> Si desea que los usuarios de Skype empresarial Server 2019 puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos en Skype empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory. Cuando los registros SRV de DNS para sipfederationtls se resuelven en Skype empresarial Server 2019, las cuentas de recursos **deben** crearse en Skype empresarial Server 2019 con el shell de administración de SfB y sincronizado con Azure ad.

Para las implementaciones híbridas con Skype empresarial Server:

   [Planear los operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planear las colas de llamadas en la nube](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurar cuentas de recursos locales](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Eliminar una cuenta de recursos

Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente.

Después de hacerlo, puede eliminar la cuenta de recursos en el centro de administración de Microsoft 365, en la pestaña usuarios.

Para desvincular un número de teléfono de enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
