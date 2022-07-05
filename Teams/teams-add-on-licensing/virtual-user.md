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
- seo-marvel-apr2020
description: Obtenga información sobre cómo asignar licencias de cuenta de recursos de Teams Phone gratuitas o licencias de usuario de Teléfono Teams Estándar de pago a cuentas de recursos de su organización.
ms.openlocfilehash: 07b47b2ec5b24b1edbfb599dc5a61e96169a02a2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615406"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Teléfono Microsoft Teams licencias de cuenta de recursos

Las organizaciones con Teléfono Teams Estándar o Teams Phone con plan de llamadas con licencia pueden asignar una licencia gratuita *de cuenta de recursos de Teléfono Microsoft Teams* o una licencia de usuario *de pago Teléfono Teams Estándar* a cuentas de recursos. No siempre es necesario un plan de llamadas de Microsoft (consulte [Planear el operador automático de Teams y las colas de llamadas](../plan-auto-attendant-call-queue.md#prerequisites) para conocer los requisitos previos al transferir llamadas a un número de teléfono externo).

Todos los operadores automáticos y las colas de llamadas requieren una cuenta de recursos asociada. Las cuentas de recursos que requieren un número de teléfono necesitan una licencia gratuita *Teléfono Microsoft Teams cuenta* de recursos o una licencia de usuario *de Teléfono Teams Estándar* de pago antes de que se pueda aplicar un número de teléfono a la cuenta de recursos.

> [!TIP]
> No se necesita ninguna licencia para las cuentas de recursos que se usarán con operadores automáticos anidados o colas de llamadas que no tengan asignado un número de teléfono. Consulte el siguiente diagrama para obtener referencia.

## <a name="resource-account-license-allocation"></a>Asignación de licencias de cuenta de recursos

Su organización se asigna Teléfono Microsoft Teams licencias de *cuenta de* recursos en función de su tamaño general. Cualquier organización que tenga al menos una licencia con las características de Teams Phone System, incluidos Teléfono Teams Estándar y Teams Phone con licencias de plan de llamadas, tiene 25 licencias de cuenta de recursos disponibles sin costo alguno. Cuando agregue 10 licencias de usuario de Teléfono Teams Estándar o Teams Phone con plan de llamadas en su organización, estará disponible una licencia más *Teléfono Microsoft Teams cuenta de* recursos.

> [!NOTE]
> Teléfono Teams Estándar y Teams Phone con plan de llamadas son licencias complementarias disponibles para todos los suscriptores de Microsoft 365. Teléfono Teams Estándar licencias también se incluyen como parte de los planes de Microsoft 365 E5.

Si su organización usa las licencias gratuitas *Teléfono Microsoft Teams cuenta de* recursos para crear nodos de operador automático o cola de llamadas, puede seguir usando las licencias *de Teléfono Teams Estándar* de pago con una cuenta de recursos. La mayoría de las organizaciones tendrán suficientes licencias de cuenta de recursos en función del plan de escalado.

### <a name="license-allocation-example"></a>Ejemplo de asignación de licencias

Contoso, Inc. compró 600 licencias que incluyen Phone System (una para cada empleado). Contoso tiene asignadas 25 licencias iniciales más 60 *Teléfono Microsoft Teams cuenta de* recursos, 85 en total. Su organización tiene 90 colas de llamadas y operadores automáticos que tienen números de teléfono. Deben asignar todas las licencias de *cuenta de recursos de Teléfono Microsoft Teams* y obtener cinco licencias *de Teléfono Teams Estándar* de precio normal.

Contoso debería considerar la posibilidad de rediseñar el operador automático y el sistema de cola de llamadas. Si usan menos números de teléfono y más nodos anidados que no necesitan un número de teléfono, simplifican la implementación y reducen los costos.

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>Cómo comprar licencias de Teléfono Microsoft Teams cuenta de recursos

1. Inicie sesión en el Centro de administración de Microsoft 365.
2. Ve a **Complementos** de **servicios** >  de compra de **facturación** > .
3. Desplácese para buscar la licencia **de cuenta de recursos Teléfono Microsoft Teams**. Selecciona **Comprar ahora**.

   > [!NOTE]
   > Tenga en cuenta **que debe comprar** la licencia aunque tenga un coste cero.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Cambiar una cuenta de recursos existente para usar una licencia de cuenta de recursos de Teléfono Microsoft Teams

Si decide cambiar la licencia de su cuenta de recursos de una licencia *de Teléfono Teams Estándar* a una licencia de *cuenta de recursos de Teléfono Microsoft Teams*:

1. Obtenga la nueva licencia *de cuenta de recursos de Teléfono Microsoft Teams*.
2. Siga los pasos vinculados de la Centro de administración de Microsoft 365 mover [usuarios a una suscripción diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Quite siempre una licencia *de Teléfono Teams Estándar* completa y asigne la licencia *Teléfono Microsoft Teams cuenta de* recursos en la misma actividad de licencia. Si quita la licencia antigua, guarda los cambios en la cuenta, agrega la nueva licencia y, a continuación, guarda de nuevo la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto ocurre, le recomendamos que cree una nueva cuenta de recursos para la licencia *de cuenta de recursos de Teléfono Microsoft Teams* y quite la cuenta de recursos rota.

## <a name="related-information"></a>Información relacionada

[Actualización del servicio de operador automático y colas de llamadas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Administrar cuentas de recursos en Microsoft Teams](../manage-resource-accounts.md)
