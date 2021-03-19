---
title: Administrar y filtrar etiquetas de dispositivos de Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
description: Obtenga información sobre cómo administrar y filtrar etiquetas en sus dispositivos de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a4f8ac718a965834678098a8960347278d13aa3
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875000"
---
# <a name="manage-microsoft-teams-device-tags"></a>Administrar etiquetas de dispositivos de Microsoft Teams

Las etiquetas de dispositivo en Microsoft Teams le permiten agrupar, organizar y administrar con mayor facilidad los dispositivos que ha implementado en su organización. Con el Centro de administración de Microsoft Teams, puede agregar una o más etiquetas a dispositivos, usar filtros para ver dispositivos que coincidan con la etiqueta que especifique y, a continuación, realizar acciones en los dispositivos que tengan esa etiqueta.

Puede agregar una etiqueta de dispositivo a más de un tipo de dispositivo. Sin embargo, al abrir un panel de dispositivos en el centro de administración, solo se devuelven los dispositivos de ese tipo. Por ejemplo, puede asignar la etiqueta "Corporativo" tanto a teléfonos como a dispositivos de Teams Rooms. Si busca la etiqueta "Corporativo" mientras está en **Teléfonos**  >  **de** dispositivos, solo se devuelven los teléfonos. De forma similar, si busca la etiqueta "Corporativo" en Salas de Teams de dispositivos, solo se devolverán los dispositivos  >  salas de Teams.

Para administrar etiquetas de dispositivo, debe ser administrador global, administrador del servicio de Teams o administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, vea [Usar roles de administrador de Microsoft Teams para administrar Teams.](../using-admin-roles.md)

> [!IMPORTANT]
> Las etiquetas de dispositivo se asignan a la cuenta de recursos que ha iniciado sesión en un dispositivo. Si firma una cuenta de recurso de un dispositivo y la usa para iniciar sesión en otro dispositivo, las etiquetas del dispositivo se aplican al nuevo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Crear, quitar o cambiar el nombre de etiquetas de dispositivo

Con el panel de administración de etiquetas de dispositivo, puede:

- Ver todas las etiquetas de dispositivo.
- Cree varias etiquetas de dispositivo fácilmente y, a continuación, asígnelas a dispositivos más adelante. Las etiquetas pueden tener hasta 25 caracteres.
- Quite etiquetas de dispositivo que ya no sean necesarias. Antes de poder quitar una etiqueta de dispositivo, tendrá que quitarla de todos los dispositivos a los que se ha agregado.
- Cambie el nombre de las etiquetas de dispositivo. Al cambiar el nombre de una etiqueta de dispositivo, ese cambio se refleja en todos los dispositivos a los que se ha agregado. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Vaya a **Dispositivos** y, a continuación, elija cualquier panel de dispositivo, como **Teléfonos.**
3. Seleccione **Acciones** en la esquina superior derecha de la página y seleccione **Todas las etiquetas de dispositivo.**
4. Para crear una etiqueta de dispositivo, seleccione **+ Agregar**, proporcione un valor para la etiqueta de dispositivo y seleccione el **icono** Guardar.
5. Para quitar una etiqueta de dispositivo, seleccione los puntos suspensivos **...** junto a la etiqueta de dispositivo que desea quitar y seleccione **Eliminar**.
    > [!NOTE]
    > Si intenta quitar una etiqueta de dispositivo que se ha agregado a los dispositivos, recibirá un mensaje que le preguntará si desea quitarla de todos los dispositivos. Si desea hacer esto y continuar quitando la etiqueta del dispositivo, seleccione **Desatag dispositivos**.
6. Para cambiar el nombre de una etiqueta de dispositivo, selecciona los puntos suspensivos **...** junto a la etiqueta de dispositivo a la que quieres cambiar el nombre y selecciona **Editar**. Proporcione un nuevo valor para la etiqueta del dispositivo y seleccione el **icono** Guardar.

## <a name="add-or-remove-tags-on-a-single-device"></a>Agregar o quitar etiquetas en un único dispositivo

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Vaya a **Dispositivos** y, a continuación, elija el panel de dispositivo que contiene el dispositivo en el que desea agregar o quitar etiquetas.
3. Coloque una marca de verificación junto al dispositivo en el que desea agregar o quitar etiquetas y seleccione **Administrar etiquetas.**
4. Si desea agregar una etiqueta:
    1. Empiece a escribir el nombre de etiqueta que desea agregar.
    2. Si la etiqueta ya existe, selecciónelo en la lista de etiquetas que se devuelven.
    3. Si la etiqueta no existe, seleccione **Agregar " " como una etiqueta \<tag name> nueva.** Las etiquetas pueden tener hasta 25 caracteres.
5. Si desea quitar una etiqueta, seleccione **X** junto a la etiqueta que desea quitar.
6. Repita los pasos anteriores si desea agregar o quitar más etiquetas.
7. Seleccione **Aplicar**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Agregar o quitar etiquetas en varios dispositivos

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres. Si desea quitar una etiqueta de varios dispositivos, debe seleccionar el usuario de Teams asociado al dispositivo y quitar la etiqueta del usuario.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Vaya a **Dispositivos** y, a continuación, elija el panel de dispositivos que contiene los dispositivos en los que desea agregar o quitar etiquetas.
3. Coloque una marca de verificación junto a los dispositivos en los que desea agregar o quitar etiquetas y seleccione **Administrar etiquetas.**
4. Si desea agregar una etiqueta:
    1. Empiece a escribir el nombre de etiqueta que desea agregar en **Administrar etiquetas para todos los dispositivos de los usuarios de Teams.**
    2. Si la etiqueta ya existe, selecciónelo en la lista de etiquetas que se devuelven.
    3. Si la etiqueta no existe, seleccione **Agregar " " como una etiqueta \<tag name> nueva.**
5. Si desea quitar una etiqueta:
    1. Expandir **Seleccionar usuarios de Teams**.
    2. Expanda **\<x> etiquetas** bajo el nombre del usuario de Teams del que desea quitar etiquetas.
    3. Seleccione **X** junto a la etiqueta que desea quitar.
6. Repita los pasos anteriores si desea agregar o quitar más etiquetas.
7. Seleccione **Aplicar**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usar filtros para devolver dispositivos con una etiqueta específica

Si ha agregado etiquetas de dispositivo a sus dispositivos, puede usarlas para filtrar la lista de dispositivos para devolver solo los dispositivos que han agregado una etiqueta especificada. Esto puede ser útil si solo desea ver todos los dispositivos de una sala específica, todos los dispositivos de un tipo determinado o cualquier otro criterio que haya usado al agregar las etiquetas. También puede realizar acciones masivas en dispositivos devueltos, como aplicar actualizaciones en oleadas o establecer directivas de configuración diferentes en función de los grupos de dispositivos identificados con etiquetas de dispositivo.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com .
2. Vaya a **Dispositivos** y, a continuación, elija el panel de dispositivos que contiene los dispositivos que desea filtrar.
3. Seleccione el **icono Filtro.**
4. Si solo desea especificar una sola etiqueta o si desea buscar dispositivos que tengan todas las etiquetas especificadas, seleccione Coincidir todas **estas condiciones.**
5. Si desea buscar dispositivos que coincidan con una o más etiquetas de dispositivo, seleccione **Coincidir con cualquiera de estas condiciones.**
6. Seleccione el **campo Etiqueta** y, a continuación, especifique un nombre de etiqueta de dispositivo en el campo **Escribir un** valor.
7. Si desea agregar más etiquetas de dispositivo, seleccione **Agregar más** y repita el paso 6 para cada etiqueta que quiera agregar.
8. Seleccione **Aplicar**.

Después de filtrar los dispositivos de la lista de dispositivos, puede realizar acciones en ellos como lo haría normalmente. Por ejemplo, puede seleccionarlas y, a continuación, asignar configuraciones, editar su configuración (si son dispositivos salas de Teams) y así sucesivamente. Cuando haya terminado, puede quitar el filtro seleccionando la  **X** junto a  la entrada Filtro de etiquetas o seleccionando Borrar todo en el lado derecho de la lista.
