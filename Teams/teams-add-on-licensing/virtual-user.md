---
title: 'Microsoft Teams Teléfono estándar: licencias de usuario virtual'
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
- seo-marvel-apr2020
description: 'Obtenga información sobre cómo asignar licencias de usuario Teams Teléfono: licencias de usuario virtual o de pago Teams Teléfono de usuario estándar a cuentas de recursos de su organización.'
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435734"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams Teléfono estándar: licencias de usuario virtual

Las organizaciones con Teams Teléfono estándar o Teams Teléfono con usuarios con licencia del Plan de llamadas pueden asignar una licencia gratuita *Microsoft Teams Teléfono Estándar*: usuario virtual o un Teams Teléfono *estándar de pago*  licencia de usuario para cuentas de recursos. No siempre es necesario un plan de llamadas de Microsoft (consulte Planear para Teams operador automático y colas de llamadas para [requisitos](../plan-auto-attendant-call-queue.md#prerequisites) previos al transferir llamadas a un número de teléfono externo).

Todos los operadores automáticos y las colas de llamadas requieren una cuenta de recursos asociada. Las cuentas de recursos que requieren un número de teléfono necesitan una licencia *gratuita Microsoft Teams Teléfono Estándar*: usuario virtual o una licencia de usuario estándar de Teams Teléfono de pago antes de que se pueda aplicar un número de teléfono *a* la cuenta de recursos.

> [!TIP]
> No se necesita ninguna licencia para las cuentas de recursos que se usarán con operadores automáticos anidados o colas de llamadas que no tengan asignado un número de teléfono. Vea el siguiente diagrama para obtener referencia.

:::image type="content" alt-text="Licencias de usuario virtual." source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>Asignación de licencias de usuario virtual

Su organización se asigna Microsoft Teams Teléfono *estándar: licencias de usuario virtual* en función de su tamaño general. Cualquier organización que tenga al menos una licencia con Teams Sistema telefónico, incluidos Teams Teléfono Standard y Teams Teléfono con licencias del Plan de llamadas, tiene 25 licencias de usuario virtual disponibles sin costo. Al agregar 10 Teams Teléfono estándar o Teams Teléfono con licencias de usuario del Plan de llamadas en su organización, una licencia más Microsoft Teams Teléfono *estándar:* la licencia de usuario virtual estará disponible.

> [!NOTE]
> Teams Teléfono estándar y Teams Teléfono con plan de llamadas son licencias de complementos disponibles para todos los Microsoft 365 suscriptores. Teams Teléfono licencias estándar también se incluyen como parte de Microsoft 365 E5 planes.

Si su organización usa el Microsoft Teams Teléfono *Estándar gratuito:* licencias de usuario virtual para crear nodos de operador automático o cola de llamadas, puede seguir utilizando las licencias Teams Teléfono *Standard* de pago con una cuenta de recursos. La mayoría de las organizaciones tendrán suficientes licencias de usuario virtual en función del plan de escalado.

### <a name="license-allocation-example"></a>Ejemplo de asignación de licencias

Contoso, Inc. compró 600 licencias que incluyen Sistema telefónico (una para cada empleado). Contoso se asigna una inicial de 25 más 60 *Microsoft Teams Teléfono:* licencias de usuario virtual, 85 en total. Su organización tiene 90 colas de llamadas y operadores automáticos que tienen números de teléfono. Deben asignar todas las licencias *estándar Microsoft Teams Teléfono : usuario virtual* y obtener cinco licencias estándar de Teams Teléfono *precio* normal.

Contoso debería considerar la posibilidad de rediseñar el operador automático y el sistema de cola de llamadas. Si usan menos números de teléfono y más nodos anidados que no necesitan un número de teléfono, simplifican la implementación y reducen los costos.

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>Cómo comprar Microsoft Teams Teléfono estándar: licencias de usuario virtual

1. Inicie sesión en el Centro de administración de Microsoft 365.
2. Vaya a **BillingPurchase** >  **servicesAdd-ons** > .
3. Desplácese hasta el final para buscar **la Microsoft Teams Teléfono estándar : licencia de usuario** virtual. Selecciona **Comprar ahora**.

   > [!NOTE]
   > Tenga en cuenta que aún debe **comprar** la licencia aunque tenga un costo de cero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>Cambiar una cuenta de recurso existente para usar una Microsoft Teams Teléfono estándar: licencia de usuario virtual

Si decide cambiar la licencia de su cuenta de recursos de una licencia *estándar* Teams Teléfono a una licencia estándar Microsoft Teams Teléfono *: licencia de usuario virtual*:

1. Obtenga la nueva Microsoft Teams Teléfono estándar: licencia de usuario virtual.
2. Siga los pasos vinculados del centro de Administración de Microsoft 365 para [mover usuarios a una suscripción diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Quite siempre una licencia *Teams Teléfono estándar* y asigne la Microsoft Teams Teléfono *estándar: licencia* de usuario virtual en la misma actividad de licencia. Si quita la licencia antigua, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para la licencia *estándar Microsoft Teams Teléfono: usuario virtual* y quite la cuenta de recursos rota.

## <a name="related-information"></a>Información relacionada

[Operador automático servicio de colas de llamadas y llamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Administrar cuentas de recursos en Microsoft Teams](../manage-resource-accounts.md)
