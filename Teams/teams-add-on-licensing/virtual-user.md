---
title: Teléfono Microsoft Teams licencias de cuenta de recursos
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- admindeeplinkMAC
description: Obtenga información sobre cómo asignar licencias de Teléfono Microsoft Teams cuenta de recursos a cuentas de recursos para operadores automáticos y colas de llamadas de su organización.
ms.openlocfilehash: 56b461c2de32f32dd51d72c5468e31f51b107310
ms.sourcegitcommit: 09b77e83bc41914007606468e322d4ea47e2e8a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "67630430"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Teléfono Microsoft Teams licencias de cuenta de recursos

En Microsoft Teams, todos los operadores automáticos y las colas de llamadas requieren una cuenta de recursos asociada. Cada cuenta de recursos debe tener asignada una licencia **de Teléfono Microsoft Teams cuenta** de recursos para asegurarse de que el sistema las identifica correctamente y funcionan correctamente, *independientemente de si se asignará un número de teléfono a la cuenta de recursos*. A las organizaciones con una suscripción que incluya Teams Phone se les asigna automáticamente una determinada cantidad de licencias de cuenta de recursos de **Teams Phone** sin ningún costo adicional.  No es necesario un plan de llamadas de Microsoft a menos que quiera llamar con esa cuenta de recursos. Para obtener más información, vea [Planear el operador automático y las colas de llamadas de Teams](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> Anteriormente, una licencia de cuenta de recursos de **teléfono de Teams** (una vez conocida como licencia de **usuario virtual** ) solo era necesaria al asignar un número de teléfono a una cuenta de recursos. Ahora, todas las cuentas de recursos deben tener asignada una licencia de **cuenta de recursos de teléfono de Teams** , independientemente de si se les asignará un número de teléfono o no. Además, no asigne una licencia **de Teléfono Teams Estándar** a una cuenta de recursos. Si actualmente tiene cuentas de recursos configuradas con licencias **de Teléfono Teams Estándar**, debe cambiar a una licencia de cuenta de recursos de **Teléfono de Teams** como se describe a continuación.
 

## <a name="resource-account-license-allocation"></a>Asignación de licencias de cuenta de recursos

A su organización se le asignan licencias de **la cuenta de recursos telefónicos de Teams** en función de su tamaño general. A cualquier organización que tenga una suscripción con características del sistema telefónico, como **Teléfono Teams Estándar** y **Teams Phone con** licencias de plan de llamadas, se le asignan 25 licencias de cuenta de recursos **telefónicos de Teams** disponibles sin costo alguno. 

Por cada 10 licencias de usuario de **Teléfono Teams Estándar** o **Teléfono de Teams con plan de llamadas** en su organización, está disponible una licencia más de **cuenta de recursos de Teléfono de Teams**.  La mayoría de las organizaciones tendrán suficientes licencias de **la cuenta de recursos de Teléfono de Teams** en función de este plan de escalado. En caso de que se requieran más licencias de **la cuenta de recursos de teléfono de Teams** , puede comprar más licencias de cuenta de recursos de Teléfono de **Teams** más allá de la asignación estándar a través de su representante de cuenta de Microsoft.

### <a name="license-allocation-example"></a>Ejemplo de asignación de licencias

Contoso, Inc. compró 600 licencias que incluyen Phone System (una para cada empleado). Contoso tiene asignadas 25 licencias iniciales más 60 licencias de cuenta de recursos **de teléfono de Teams** , 85 en total. Su organización tiene 90 colas de llamadas y operadores automáticos. Deben asignar todas las licencias de la **cuenta de recursos de Teléfono de Teams** y comprar cinco licencias de **cuenta de recursos de teléfono de Teams** adicionales. 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Cómo obtener licencias de Teléfono Microsoft Teams cuenta de recursos

1. Inicia sesión en la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Ve a **Complementos** de [**servicios**](https://go.microsoft.com/fwlink/p/?linkid=868433) >  de compra de **facturación** > .
3. Desplácese para buscar la licencia **de cuenta de recursos Teléfono Microsoft Teams**. Selecciona **Comprar ahora**.

   > [!NOTE]
   > Tenga en cuenta que, aunque esté dentro de su asignación, debe **comprar** la licencia aunque tenga un coste cero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Cambiar una cuenta de recursos existente para usar una licencia de cuenta de recursos de Teléfono Microsoft Teams

Si tiene cuentas de recursos existentes con una licencia **de Teléfono Teams Estándar**, debe cambiar a usar una licencia de cuenta de recursos de **Teléfono de Teams**:

1. Obtenga la nueva licencia **de la cuenta de recursos de Teléfono de Teams** .
2. Siga los pasos vinculados de la Centro de administración de Microsoft 365 mover [usuarios a una suscripción diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Quite siempre una licencia **de Teléfono Teams Estándar** y asigne la licencia **de la cuenta de recursos de Teléfono de Teams** en la misma actividad de licencia. Si quita la licencia antigua, guarda los cambios de cuenta, agrega la nueva licencia y guarda de nuevo la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado, como los operadores automáticos y las colas de llamadas de su organización ya no funcionan.
>
> Si esto ocurre, le recomendamos que cree una nueva cuenta de recursos con la licencia **de cuenta** de recursos de Teléfono de Teams y quite la cuenta de recursos rota.

## <a name="related-information"></a>Información relacionada

[Actualización del servicio de operador automático y colas de llamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Administrar cuentas de recursos en Microsoft Teams](../manage-resource-accounts.md)
