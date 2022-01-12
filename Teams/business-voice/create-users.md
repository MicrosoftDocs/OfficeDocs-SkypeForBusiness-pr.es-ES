---
title: Crear Microsoft 365 usuarios, agregar Teams Teléfono con licencias del Plan de llamadas y asignar números de teléfono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00eb2842b063399f69563571180197de0238588e
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766193"
---
# <a name="create-and-license-teams-phone-with-calling-plan-users-and-assign-them-phone-numbers"></a>Crear y licenciar Teams Teléfono usuarios del Plan de llamadas y asignarles números de teléfono

Para usar :::no-loc text="Microsoft 365 Teams Phone with Calling Plan":::, necesita una cuenta de :::no-loc text="Microsoft 365"::: que tenga una licencia de :::no-loc text="Microsoft 365 Teams Phone with Calling Plan":::. Cuando tenga una cuenta y una licencia, puede asignarle un número de teléfono.

## <a name="create-and-license-users"></a>Crear y asignar licencias a los usuarios

Siga los pasos en [Agregar usuarios individualmente o en bloque](/microsoft-365/admin/add-users/add-users)y [Asignar licencias a los usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> En el panel **Asignar licencias de producto**, seleccione **:::no-loc text="Microsoft 365 Teams Phone with Calling Plan":::**.

## <a name="assign-phone-numbers-to-users"></a>Asignar números de teléfono a los usuarios

Después de crear los usuarios y asignarles una licencia de:::no-loc text="Microsoft 365 Teams Phone with Calling Plan":::, también puede asignarles números de teléfono. Debe tener un número de teléfono sin asignar para cada usuario que necesite realizar o recibir llamadas hacia o desde números de teléfono externos. Si no tiene suficientes números de teléfono sin asignar, consulte [Obtener más números de teléfono](#get-more-phone-numbers) más adelante en este artículo.

1. Vaya a https://admin.teams.microsoft.com.
2. Escriba un nombre y una descripción para la solicitud del número de teléfono.
3. Seleccione **Voz** > **Números de teléfono**.
4. Seleccione un número de teléfono que quiera asignar a un usuario y después, seleccione **Editar**.
5. En el panel **Editar**, escriba el nombre del usuario al que quiere asignar el número en **Asignar a**. Después, seleccione **Asignar**.
6. Para **Ubicación de emergencia**, escriba la ubicación en la que se encuentra el usuario y después, seleccione **Aplicar**

## <a name="get-more-phone-numbers"></a>Obtener más números de teléfono

Si no dispone de números de teléfono suficientes para asignarlos a los nuevos usuarios, puede obtener más. Puede tardar hasta 24 horas para que los números que solicite estén disponibles.

1. Vaya a https://admin.teams.microsoft.com.
2. Escriba un nombre y una descripción para la solicitud del número de teléfono.
3. Seleccione **Voz** > **Números de teléfono** > **Agregar**.
4. Elija el país o la región para el número de teléfono.
5. Para **Tipo de número**, seleccione **Usuario (suscriptor)**.
6. Para **Ubicación**, busque la ubicación del usuario y selecciónela. También puede elegir **Agregar una ubicación**.
7. Elija un código de área, escriba la cantidad de números de teléfono que necesita y después, seleccione **Siguiente**.
8. Espere a que se reserven los números de teléfono y después, compruebe los números que obtiene. Si todo es correcto, seleccione **Realizar pedido** y después, **Finalizar**.
