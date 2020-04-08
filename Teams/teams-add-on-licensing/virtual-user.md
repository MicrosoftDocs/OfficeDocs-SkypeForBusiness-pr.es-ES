---
title: Sistema telefónico de Microsoft 365-licencias de usuario virtual
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
description: Obtenga más información sobre las licencias de usuario virtual gratuitas.
ms.openlocfilehash: f2ecaddc6fd1dcc4bbb179fde3f495a0eea29353
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190812"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Sistema telefónico Microsoft 365-licencia de usuario virtual 

Las organizaciones con licencias de usuario de sistema telefónico pueden asignar una licencia de usuario de sistema telefónico gratuita de Microsoft 365, o una licencia de usuario de sistema telefónico de pagar a cuentas de recursos. No se requiere un plan de llamadas. Todos los operadores automáticos o las colas de llamadas requieren una cuenta de recursos asociada. Las cuentas de recursos que requieren un número de teléfono necesitan un sistema telefónico Microsoft 365, una licencia de usuario virtual o una licencia de usuario de sistema telefónico de pagos antes de que se pueda aplicar un número de teléfono a la cuenta de recursos.

> [!TIP]
> No se necesita ninguna licencia para cuentas de recursos que se usarán con operadores automáticos anidados o colas de llamadas que no tengan un número de teléfono asignado. Vea el siguiente diagrama de referencia: 

![Licencias de usuario virtual](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Asignación de licencia de usuario virtual

Su organización está asignada a Microsoft 365 Phone System: licencias de usuario virtual según su tamaño global. Cualquier organización que tenga al menos una licencia que incluya el sistema telefónico o tenga un sistema telefónico agregado tiene 25 licencias de usuario virtual disponibles sin costo alguno. Al agregar las licencias de usuario de un sistema de 10 teléfonos a su organización, se ofrece una licencia de usuario virtual de Microsoft 365 Phone System:

> [!NOTE]
> Sistema telefónico es una licencia de complemento disponible con Office 365 E1 y E3. El sistema telefónico también se incluye como parte de las licencias de Office 365 E5 y Microsoft 365 Business Voice.

Si su organización usa el sistema telefónico gratuito Microsoft 365: licencias de usuario virtual en la creación de nodos de cola de llamadas o de operadores automáticos, aún puede usar las licencias de sistema telefónico de pagos con una cuenta de recursos. La mayoría de las organizaciones tendrá suficientes licencias de usuario virtual basadas en el plan de escala. 

### <a name="license-allocation-example"></a>Ejemplo de asignación de licencias

Contoso, Inc. compró licencias 600 que incluían el sistema telefónico (una por empleado). Contoso tiene asignado un sistema de telefonía inicial de 25 más 60 Microsoft 365: licencias de usuario virtual, 85 en total. Su organización tiene 90 colas de llamadas y operadores automáticos que tienen números de teléfono. Necesitan asignar todas las licencias de usuario virtual de Microsoft 365 Phone System y obtener cinco licencias de sistema telefónicas a precios regulares. 

Contoso debe considerar rediseñar el operador automático y el sistema de la cola de llamadas. Si usan menos números de teléfono y más nodos anidados que no necesitan un número de teléfono, simplifican la implementación y reducen los costos. 

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Cómo comprar Microsoft 365 Phone System-licencias de usuario virtual 

1. Inicie sesión en el Centro de administración de Microsoft 365.
2. Ir a los**Complementos de** **servicios** > de compra de **facturación** > 
3. Desplácese hasta el final para buscar **Microsoft 365 Phone System-virtual User** License. Seleccione **comprar ahora**.

> [!NOTE]
> Tenga en cuenta que aún debe **comprar** la licencia aunque tenga un costo de cero. 

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Cambiar una cuenta de recursos existente para usar un sistema telefónico de Microsoft 365-licencia de usuario virtual

Si decide cambiar la licencia de la cuenta de recursos de una licencia de sistema telefónico a un sistema telefónico de Microsoft 365, una licencia de usuario virtual: 

1. Obtenga la nueva licencia de usuario virtual de Microsoft 365 Phone System: 
2. Siga los pasos vinculados en el centro de administración de Microsoft 365 para [mover usuarios a un plan diferente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Elimine siempre una licencia de sistema telefónico completo y asigne la licencia de usuario virtual de Microsoft 365 Phone System en la misma actividad de licencia. Si quita la licencia anterior, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para el sistema telefónico Microsoft 365: licencia de usuario virtual y quite la cuenta de recursos dañados. 

## <a name="related-information"></a>Información relacionada

[Actualización de servicio de las colas de llamadas y operadores automáticos](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Administrar cuentas de recursos en Microsoft Teams](../manage-resource-accounts.md)
