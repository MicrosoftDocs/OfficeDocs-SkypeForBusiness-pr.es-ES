---
title: Administrar cuentas de recursos en Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: En este artículo, aprenderá a crear, editar y administrar cuentas de recursos en Microsoft Teams.
ms.openlocfilehash: 3ac03e8531457d21d2988db0a86ca8bdca367f0a
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392210"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Administrar cuentas de recursos en Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Pasos siguientes

Una vez que haya completado la configuración de la cuenta de recursos y asignado un número de teléfono si es necesario, está listo para usar la cuenta de recursos con un operador automático o una cola de llamadas.

Vea las siguientes referencias para obtener más información:

- [Operador automático en la nube](create-a-phone-system-auto-attendant.md)
- [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)

Puede editar la cuenta de recursos **Nombre para mostrar** y el tipo **de cuenta de recurso** con la opción **Editar** . Selecciona **Guardar** cuando hayas terminado.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Cambiar una cuenta de recursos existente para usar una licencia de cuenta de recursos de Teléfono Microsoft Teams

Para cambiar las licencias de su cuenta de recursos existente de una licencia **de Teléfono Teams Estándar** a una licencia de cuenta de recursos **de Teléfono Microsoft Teams**, tendrá que adquirir la licencia de cuenta de recursos **de Teléfono Microsoft Teams** y, a continuación, seguir los pasos de la Centro de administración de Microsoft 365 mover [usuarios a una suscripción diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Quite siempre una licencia **de Teléfono Teams Estándar** y asigne la licencia **Teléfono Microsoft Teams cuenta de** recursos en la misma actividad de licencia. Si quita la licencia antigua, guarda los cambios en la cuenta, agrega la nueva licencia y, a continuación, guarda de nuevo la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto ocurre, le recomendamos que cree una nueva cuenta de recursos para la licencia **de cuenta de recursos de Teléfono Microsoft Teams** y quite la cuenta de recursos rota.

## <a name="skype-for-business-server-2019"></a>Skype Empresarial Server 2019

Para las cuentas de recursos alojados en Skype Empresarial Server 2019 que se pueden usar con colas de llamadas en la nube y operadores automáticos en la nube, consulte [Planear colas de llamadas](/SkypeforBusiness/hybrid/plan-call-queue) en la nube o [Planear operadores automáticos de la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Las implementaciones híbridas (números alojados en Direct Routing) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) en un servidor local de Skype Empresarial Server 2019.

Los identificadores de aplicación que necesita usar al crear las instancias de la aplicación son:

- **Operador automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Cola de llamadas:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Si quiere que los usuarios de Skype Empresarial Server 2019 puedan buscar la cola de llamadas o el operador automático, debe crear sus cuentas de recursos en Skype Empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory. Cuando los registros SRV de DNS para sipfederationtls se resuelvan en Skype Empresarial Server 2019, las cuentas de recursos **deben** crearse en Skype Empresarial Server 2019 con el shell de administración de SfB y sincronizarse con Azure AD.

Para implementaciones híbridas con Skype Empresarial Server:

   [Planear los operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Planear las colas de llamadas en la nube](/SkypeforBusiness/hybrid/plan-call-queue)

   [Configurar cuentas de recursos locales](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Eliminar una cuenta de recursos

Asegúrese de disociar el número de teléfono de la cuenta de recursos antes de eliminarla, para evitar que su número de teléfono se quede atascado en el modo pendiente.

Después de hacerlo, puede eliminar la cuenta de recursos en la Centro de administración de Microsoft 365, en la pestaña **Usuarios**.

Para desasociar un número de teléfono de Enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
