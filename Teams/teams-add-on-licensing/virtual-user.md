---
title: 'Microsoft 365 Phone System: licencias de usuario virtual'
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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Obtenga información sobre cómo asignar una licencia de usuario virtual o de sistema telefónico gratuito a cuentas de recursos de su organización.
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116928"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Phone System: licencia de usuario virtual

Las organizaciones con usuarios con licencia de Sistema telefónico pueden asignar una licencia gratuita de Microsoft 365 Phone System : usuario virtual o una licencia de usuario de sistema telefónico de pago a cuentas de recursos. No se requiere un plan de llamadas. Todos los operadores automáticos o las colas de llamadas requieren una cuenta de recursos asociada. Las cuentas de recursos que requieren un número de teléfono necesitan un sistema telefónico gratuito de Microsoft 365: una licencia de usuario virtual o una licencia de usuario del sistema telefónico de pago antes de que se pueda aplicar un número de teléfono a la cuenta de recursos.

> [!TIP]
> No se necesita ninguna licencia para las cuentas de recursos que se usarán con operadores automáticos anidados o colas de llamadas que no tengan asignado un número de teléfono. Vea el siguiente diagrama para obtener referencia: 

![Licencias de usuario virtual](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Asignación de licencias de usuario virtual

Su organización se asigna a Microsoft 365 Phone System: licencias de usuario virtual en función de su tamaño general. Cualquier organización que tenga al menos una licencia, incluido Sistema telefónico o tenga sistema telefónico agregado, tiene 25 licencias de usuario virtual disponibles sin costo. Al agregar 10 licencias de usuario de Sistema telefónico en su organización, una licencia más de Microsoft 365 Phone System: la licencia de usuario virtual estará disponible.

> [!NOTE]
> Phone System es una licencia de complemento disponible con Microsoft 365 y Office 365 E1 y E3. Phone System también se incluye como parte de las licencias de Microsoft 365 E5, Office 365 E5 y Microsoft 365 Business Voice.

Si su organización usa el sistema telefónico gratuito de Microsoft 365: licencias de usuario virtual para crear nodos de operador automático o cola de llamadas, puede seguir utilizando las licencias del sistema telefónico de pago con una cuenta de recursos. La mayoría de las organizaciones tendrán suficientes licencias de usuario virtual en función del plan de escalado. 

### <a name="license-allocation-example"></a>Ejemplo de asignación de licencias

Contoso, Inc. compró 600 licencias que incluían Sistema telefónico (una para cada empleado). Contoso tiene asignado un 25 inicial más 60 Microsoft 365 Phone System: licencias de usuario virtual, 85 en total. Su organización tiene 90 colas de llamadas y operadores automáticos que tienen números de teléfono. Deben asignar todas las licencias del Sistema telefónico de Microsoft 365: licencias de usuario virtual y obtener cinco licencias de sistema telefónico de precio normal.

Contoso debería considerar la posibilidad de rediseñar el operador automático y el sistema de cola de llamadas. Si usan menos números de teléfono y más nodos anidados que no necesitan un número de teléfono, simplifican la implementación y reducen los costos.

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Cómo comprar Microsoft 365 Phone System: licencias de usuario virtual

1. Inicie sesión en el Centro de administración de Microsoft 365.
2. Ir a **Complementos de servicios** de  >  **compra**  >  **de facturación**
3. Desplácese hasta el final para buscar la **licencia microsoft 365 Phone System : usuario** virtual. Selecciona **Comprar ahora**.

> [!NOTE]
> Tenga en cuenta que aún debe  **comprar** la licencia aunque tenga un costo de cero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Cambiar una cuenta de recurso existente para usar un sistema telefónico de Microsoft 365: licencia de usuario virtual

Si decide cambiar la licencia de su cuenta de recursos de una licencia de Sistema telefónico a un sistema telefónico de Microsoft 365: licencia de usuario virtual:

1. Obtenga la nueva licencia de Usuario virtual de Microsoft 365 Phone System.
2. Siga los pasos vinculados del Centro de administración de Microsoft 365 para [mover usuarios a una suscripción diferente.](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Quite siempre una licencia completa del sistema telefónico y asigne la licencia sistema telefónico de Microsoft 365: licencia de usuario virtual en la misma actividad de licencia. Si quita la licencia antigua, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para microsoft 365 Phone System: licencia de usuario virtual y quite la cuenta de recursos rota. 

## <a name="related-information"></a>Información relacionada

[Operador automático servicio de colas de llamadas y llamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Administrar cuentas de recursos en Microsoft Teams](../manage-resource-accounts.md)