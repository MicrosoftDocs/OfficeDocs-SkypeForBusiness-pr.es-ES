---
title: Crear usuarios de Microsoft 365, agregar licencias de Business Voice y asignar números de teléfono
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
ms.openlocfilehash: cb8277c11cbcc459da9da8fd8d4f5b9c329470f3
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269286"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a>Cree y otorgue licencias a los usuarios de Business Voice y asígneles números de teléfono

Para usar :::no-loc text="Microsoft 365 Business Voice":::, necesita una cuenta de :::no-loc text="Microsoft 365"::: que tenga una licencia de :::no-loc text="Microsoft 365 Business Voice with SMS":::. Cuando tenga una cuenta y una licencia, puede asignarle un número de teléfono.

## <a name="create-and-license-users"></a>Crear y asignar licencias a los usuarios

Siga los pasos descritos en [Agregar usuarios individualmente o de forma masiva a :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users).

> [!NOTE]
> En el panel **Asignar licencias de producto**, seleccione **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.

## <a name="assign-phone-numbers-to-users"></a>Asignar números de teléfono a los usuarios

Después de crear los usuarios y asignarles una licencia de:::no-loc text="Microsoft 365 Business Voice with SMS":::, también puede asignarles números de teléfono. Debe tener un número de teléfono sin asignar para cada usuario que necesite realizar o recibir llamadas hacia o desde números de teléfono externos. Si no tiene suficientes números de teléfono sin asignar, consulte [Obtener más números de teléfono](#get-more-phone-numbers) más adelante en este artículo.

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
