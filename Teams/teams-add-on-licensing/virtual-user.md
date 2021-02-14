---
title: 'Sistema telefónico de Microsoft 365: licencias de usuario virtual'
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
description: Obtenga información sobre cómo asignar una licencia gratuita de Sistema telefónico- Usuario virtual o una licencia de usuario de sistema telefónico de pago a cuentas de recursos de su organización.
ms.openlocfilehash: 00c3463aa933b4d91308fee85d362c4c4807cf69
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868657"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Sistema telefónico de Microsoft 365: licencia de usuario virtual

Las organizaciones con usuarios con licencia de Sistema telefónico pueden asignar una licencia gratuita de Sistema telefónico de Microsoft 365: licencia de usuario virtual o una licencia de usuario de Sistema telefónico de pago a cuentas de recursos. No se requiere un plan de llamadas. Todos los operadores automáticos o colas de llamadas requieren una cuenta de recursos asociada. Las cuentas de recursos que requieren un número de teléfono necesitan una licencia gratuita de Sistema telefónico de Microsoft 365: licencia de usuario virtual o una licencia de usuario de sistema telefónico de pago para poder aplicar un número de teléfono a la cuenta del recurso.

> [!TIP]
> No se necesita ninguna licencia para las cuentas de recursos que se usarán con operadores automáticos anidados o colas de llamadas que no tengan asignado un número de teléfono. Vea el siguiente diagrama como referencia: 

![Licencias de usuario virtual](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Asignación de licencias de usuario virtual

A su organización se le asigna Microsoft 365 Phone System: licencias de usuario virtual en función de su tamaño total. Cualquier organización que tenga al menos una licencia, incluido Sistema telefónico o que tenga Sistema telefónico agregado, tiene 25 licencias de Usuario virtual disponibles sin costo. Al agregar 10 licencias de usuario de Sistema telefónico en su organización, una más de Sistema telefónico de Microsoft 365: la licencia de usuario virtual pasa a estar disponible.

> [!NOTE]
> Sistema telefónico es una licencia de complemento disponible con Microsoft 365 y Office 365 E1 y E3. Phone System también se incluye como parte de las licencias de Microsoft 365 E5, Office 365 E5 y Microsoft 365 Business Voice.

Si su organización utiliza el sistema telefónico de Microsoft 365 gratuito disponible: licencias de usuario virtual para crear operadores automáticos o nodos de la cola de llamadas, todavía puede usar las licencias de pago del sistema telefónico con una cuenta de recursos. La mayoría de las organizaciones tendrán suficientes licencias de usuario virtual basadas en el plan de escalado. 

### <a name="license-allocation-example"></a>Ejemplo de asignación de licencias

Contoso, Inc. ha comprado 600 licencias que incluían Sistema telefónico (una para cada empleado). A Contoso se le asigna una cantidad inicial de 25 más 60 licencias de Microsoft 365 Phone System: licencias de usuario virtual, 85 en total. Su organización tiene 90 colas de llamadas y operadores automáticos que tienen números de teléfono. Tienen que asignar todas las licencias de Sistema telefónico de Microsoft 365: licencias de Usuario virtual y obtener cinco licencias de Sistema telefónico de precio normal.

Contoso debería considerar la posibilidad de rediseñar el operador automático y el sistema de la cola de llamadas. Si usan menos números de teléfono y más nodos anidados que no necesitan un número de teléfono, simplifican la implementación y reducen los costes.

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Cómo comprar Sistema telefónico de Microsoft 365: licencias de usuario virtual

1. Inicie sesión en el Centro de administración de Microsoft 365.
2. Ir a **Complementos de servicios** de  >  **compra** de  >  **facturación**
3. Desplácese hasta el final para encontrar el Sistema telefónico de **Microsoft 365: licencia de usuario** virtual. Seleccione **Comprar ahora.**

> [!NOTE]
> Tenga en cuenta que debe  **comprar la** licencia aunque tenga un coste de cero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Cambiar una cuenta de recurso existente para usar un sistema telefónico de Microsoft 365: licencia de usuario virtual

Si decide cambiar la licencia de su cuenta de recursos de una licencia de Sistema telefónico a una licencia de Sistema telefónico de Microsoft 365- Licencia de usuario virtual:

1. Obtenga la nueva licencia de Microsoft 365 Phone System - Usuario virtual.
2. Siga los pasos vinculados en el Centro de administración de Microsoft 365 para [mover usuarios a una suscripción diferente.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> Quite siempre una licencia completa de Sistema telefónico y asigne la licencia de Sistema telefónico de Microsoft 365: licencia de usuario virtual en la misma actividad de licencia. Si quita la licencia anterior, guarda los cambios en la cuenta, agrega la nueva licencia y, a continuación, guarda de nuevo la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione como se espera. Si esto sucede, le recomendamos que cree una nueva cuenta de recurso para Microsoft 365 Phone System: licencia de usuario virtual y quite la cuenta de recursos rota. 

## <a name="related-information"></a>Información relacionada

[Operador automático del servicio de colas de llamadas y de llamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Administrar cuentas de recursos en Microsoft Teams](../manage-resource-accounts.md)
