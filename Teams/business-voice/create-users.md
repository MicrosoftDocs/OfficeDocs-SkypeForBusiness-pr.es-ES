---
title: Crear usuarios de Microsoft 365, agregar licencias de Microsoft 365 Business Voice y asignar números de teléfono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd00c4baf7958926c2e27e8141630444e7df637c
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972081"
---
# <a name="create-and-license-users-and-assign-phone-numbers-to-them"></a>Cree y asigne licencias a los usuarios y asígneles números de teléfono

Para usar Microsoft 365 Business Voice, un usuario necesita una cuenta de Microsoft 365 con Microsoft 365 Business Voice con una licencia SMS. Una vez que se ha creado una cuenta con una licencia de Microsoft 365 Business Voice con SMS, puede asignarle un número de teléfono.

## <a name="create-and-license-users"></a>Crear y asignar licencias a los usuarios

1. Siga los pasos descritos en [Agregar usuarios individualmente o de forma masiva a Office 365](https://docs.microsoft.com/office365/admin/add-users/add-users) para agregar uno o más usuarios.
2. En el panel **Asignar licencias de producto**, asegúrese de seleccionar **Microsoft 365 Business Voice con SMS**.

## <a name="assign-phone-numbers-to-users"></a>Asignar números de teléfono a los usuarios

Una vez que los usuarios hayan sido creados y asignados a una licencia de Microsoft 365 Business Voice con SMS, puede asignarle un número de teléfono. Debe tener un número de teléfono sin asignar para cada usuario que necesite uno. Si no tiene suficientes números de teléfono sin asignar, consulte [Obtener más números de teléfono](#get-more-phone-numbers) más adelante en este artículo.

1. Vaya a https://admin.teams.microsoft.com
2. Escriba un nombre y una descripción para la solicitud del número de teléfono.
3. Seleccione **Voz** > **Números de teléfono**
4. Seleccione el número de teléfono que quiera asignar a un usuario y, después, seleccione **Editar**
5. En el panel **Editar**, escriba el nombre del usuario al que quiere asignar el número en **Asignar a** y seleccione **Asignar**
6. En **Ubicación de emergencia**, escriba la ubicación en la que se encuentra el usuario y, después, seleccione **Aplicar**


## <a name="get-more-phone-numbers"></a>Obtener más números de teléfono

Si no dispone de números de teléfono suficientes para asignarlos a los nuevos usuarios, puede obtener más. Una vez que haya realizado la solicitud, puede tardar hasta 24 horas en que los números estén disponibles.

1. Vaya a https://admin.teams.microsoft.com
2. Escriba un nombre y una descripción para la solicitud del número de teléfono.
3. Seleccione **Voz** > **Números de teléfono**, y después **Agregar**
4. Elija el país o la región donde se debe crear el número de teléfono.
5. En **Tipo de número**, seleccione **Usuario (suscriptor)**
6. En **Ubicación**, encuentre la ubicación del usuario y selecciónela. Si necesita agregar una nueva ubicación, seleccione **Agregar una ubicación**
7. Elija un código de área, escriba el número de números de teléfono que se va a obtener y, a continuación, haga clic en **Siguiente**
8. Espere a que se reserve el número de teléfono, revise los números seleccionados y, si todo es correcto, seleccione **Realizar pedido** y, a continuación, **Finalizar**.

