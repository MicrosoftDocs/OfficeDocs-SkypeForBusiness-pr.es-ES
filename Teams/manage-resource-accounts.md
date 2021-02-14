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
- m365initiative-voice
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
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031026"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Administrar cuentas de recursos en Microsoft Teams

Una cuenta de recursos es un objeto de usuario deshabilitado en Azure AD y se puede usar para representar recursos en general. Por ejemplo, una cuenta de recursos se puede usar en Exchange para representar salas de conferencias y permitirles tener un número de teléfono y un calendario. Una cuenta de recursos puede estar en Microsoft 365 o en local con Skype Empresarial Server 2019.

En Microsoft Teams, se requiere una cuenta de recursos para cada operador automático o cola de llamadas. Las cuentas de recursos también pueden tener asignados números de teléfono de servicio. Así se asignan números de teléfono a operadores automáticos y colas de llamadas que permiten a los autores de llamadas externos a Teams llegar al operador automático o a la cola de llamadas.

Este artículo trata sobre cómo crear cuentas de recursos y listas para su uso con operadores automáticos y colas de llamadas.

Antes de comenzar los procedimientos de este artículo, asegúrese de que ha hecho lo siguiente:

- [Obtener licencias de usuario virtual](#obtain-virtual-user-licenses)
- [Obtener números de servicio](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>Obtener licencias de usuario virtual

Cada cuenta de recurso necesita una licencia para trabajar con operadores automáticos y colas de llamadas. Puede usar una licencia gratuita *de Microsoft 365 Phone System - Virtual User.* Para obtener estas licencias, consulte [Licencia de usuario virtual.](teams-add-on-licensing/virtual-user.md)

En este artículo explicamos cómo asignar la licencia a una cuenta de recursos.

Para obtener la licencia de Usuario virtual, en el Centro de administración de Microsoft 365, vaya al complemento de servicios de compra de facturación y desplácese hasta el final ( verá Sistema telefónico - Licencia de usuario  >    >   *virtual).* Seleccione **Comprar ahora.** El costo es cero, pero debe seguir estos pasos para adquirir la licencia.

### <a name="obtain-service-numbers"></a>Obtener números de servicio

Los números de servicio son opcionales para los operadores automáticos y las colas de llamadas, pero necesitará al menos un número de servicio para que los autores de llamadas lleguen a su operador automático y a la configuración de la cola de llamadas. Para cualquier operador automático o cola de llamadas al que desee que se le pueda obtener acceso directamente mediante un número de servicio, debe tener una cuenta de recurso con un número de servicio asociado.

Las cuentas de recursos pueden usar números de servicio de pago o gratuitos. Puede solicitar números nuevos o realizar la portabilidad de números existentes de otro operador.

Para obtener nuevos números de servicio, vea [Obtener números de teléfono de servicio.](getting-service-phone-numbers.md)

Para transferir un número de otro operador, consulte [Transferir números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="create-a-resource-account"></a>Crear una cuenta de recurso

Puede crear una cuenta de recurso en el Centro de administración de Teams.

![Captura de pantalla de la interfaz de usuario para agregar una cuenta de recurso](media/resource-account-add.png)

1. En el Centro de administración de Teams, expanda **la configuración de toda la** organización y, a continuación, haga clic en Cuentas de **recursos.**

2. Haga clic en **Agregar**.

3. En el **panel Agregar cuenta de** recurso, rellene **Nombre** para mostrar, **Nombre** de usuario y el tipo de cuenta **de recurso.** El tipo de cuenta de recurso puede ser un operador **automático** o una cola **de** llamadas, dependiendo de cómo pretende usar esta cuenta de recursos.

4. Haga clic en **Guardar**.

![Captura de pantalla de una lista de cuentas de recursos](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Asignar una licencia

Para cada cuenta de recurso, debe asignar una licencia de Sistema telefónico de *Microsoft 365:* licencia de Usuario virtual o *de Sistema* telefónico.

![Captura de pantalla de la interfaz de usuario de asignación de licencias en el Centro de administración de Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. En el Centro de administración de Microsoft 365, haga clic en la cuenta de recursos a la que desea asignar una licencia.

2. En la **pestaña Licencias y aplicaciones,** en **Licencias,** seleccione Sistema telefónico de **Microsoft 365 - Usuario virtual.**

3. Haga clic **en Guardar cambios.**

## <a name="assign-a-service-number"></a>Asignar un número de servicio

Si está pensando en usar la cuenta de recursos con un operador automático o una cola de llamadas que requiere un número de servicio, asigne un número a la cuenta de recursos.

![Captura de pantalla de la interfaz de usuario asignar número de servicio](media/resource-account-assign-phone-number.png)

1. En el Centro de  administración de Teams, en la página Cuentas de recursos, seleccione la cuenta de recursos a la que desea asignar un número de servicio y, a continuación, haga clic en Asignar **o desasignir.**

2. En la **lista desplegable Tipo de** número de teléfono, elija el tipo de número que desea usar.

3. En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.**

4. Haga clic en **Guardar**.


Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, debe usar PowerShell:

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>Pasos siguientes

Una vez que haya completado la configuración de la cuenta de recursos y asigne un número de servicio si es necesario, estará listo para usar la cuenta de recursos con un operador automático o una cola de llamadas.

Vea las siguientes referencias:

 - [Operador automático en la nube](create-a-phone-system-auto-attendant.md)

 - [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)

Puede editar el nombre para mostrar de la cuenta del recurso **y** el **tipo de** cuenta de recurso con la **opción** Editar. Haga **clic en** Guardar cuando haya terminado.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Cambiar una cuenta de recurso existente para usar una licencia de usuario virtual

Si decide cambiar las licencias de su cuenta  de recursos existente de una licencia de Sistema telefónico a una licencia de Usuario virtual, tendrá que adquirir la licencia gratuita De Usuario virtual y, a continuación, siga los pasos del Centro de administración de Microsoft 365 para mover usuarios [a](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)una suscripción diferente.

> [!WARNING]
> Quite siempre una licencia completa de Sistema telefónico y asigne la licencia de Usuario virtual en la misma actividad de licencia. Si quita la licencia anterior, guarda los cambios en la cuenta, agrega la nueva licencia y, a continuación, guarda de nuevo la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione como se espera. Si esto ocurre, le recomendamos que cree una nueva cuenta de recurso para la licencia de usuario virtual y quite la cuenta de recursos rota.

## <a name="skype-for-business-server-2019"></a>Skype Empresarial Server 2019

Para las cuentas de recursos hogar en Skype Empresarial Server 2019 que se pueden usar con colas de llamadas en la nube y operadores automáticos en la nube, consulte [Planear](/SkypeforBusiness/hybrid/plan-call-queue) colas de llamadas en la nube o Planear operadores automáticos en la [nube.](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant) Las implementaciones híbridas (números que se encuentran en enrutamiento directo) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) en un servidor local de Skype Empresarial Server 2019.

Los iD de aplicación que necesita usar al crear las instancias de la aplicación son:

- **Operador automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Cola de llamadas:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Si desea que los usuarios de Skype Empresarial Server 2019 puedan buscar en la cola de llamadas o el operador automático, debe crear sus cuentas de recursos en Skype Empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory. Cuando los registros SRV de DNS para sipfederationtls se resuelven  en Skype Empresarial Server 2019, es necesario crear cuentas de recursos en Skype Empresarial Server 2019 con el shell de administración de SfB y sincronizarse con Azure AD.

Para implementaciones híbridas con Skype Empresarial Server:

   [Planear los operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planear las colas de llamadas en la nube](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurar cuentas de recursos locales](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>Eliminar una cuenta de recurso

Asegúrese de desvincular el número de teléfono de la cuenta del recurso antes de eliminarlo, para evitar que el número de servicio se atasca en el modo pendiente.

Después de hacerlo, puede eliminar la cuenta del recurso en el Centro de administración de Microsoft 365, en la pestaña Usuarios.

Para desasociar un número de teléfono de enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
