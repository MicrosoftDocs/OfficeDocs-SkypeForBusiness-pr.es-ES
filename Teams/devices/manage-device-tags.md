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
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
description: Obtenga información sobre cómo administrar y filtrar etiquetas en sus dispositivos de Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a372aacb7a8917dc169855fd671b1382d390f32
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271355"
---
# <a name="manage-microsoft-teams-device-tags"></a>Administrar etiquetas de dispositivos de Microsoft Teams

Las etiquetas de dispositivo en Microsoft Teams le permiten agrupar, organizar y administrar más fácilmente los dispositivos que ha implementado en su organización. Con el Centro de administración de Microsoft Teams, puede agregar una o más etiquetas a los dispositivos, usar filtros para ver los dispositivos que coincidan con la etiqueta que especifique y, a continuación, realizar acciones en los dispositivos que tienen esa etiqueta.

Puedes agregar una etiqueta de dispositivo a más de un tipo de dispositivo. Sin embargo, al abrir un panel de dispositivos en el centro de administración, solo se devuelven los dispositivos de ese tipo. Por ejemplo, puede asignar la etiqueta "Corporativo" tanto a teléfonos como a Salas de Teams dispositivos. Si busca la etiqueta "Corporativo" en **Teléfonos** de **dispositivos** >  de Teams, solo se devolverán los teléfonos. De forma similar, si busca la etiqueta "Corporativo" en **Dispositivos** >  de Teams **Salas de Teams**, solo se devolverán Salas de Teams dispositivos.

Para administrar las etiquetas de dispositivo, debe ser administrador global, administrador de servicio de Teams o administrador de dispositivos de Teams. Para obtener más información sobre los roles de administrador, vea [Usar los roles de administrador de Microsoft Teams para administrar Teams](../using-admin-roles.md).

> [!IMPORTANT]
> Las etiquetas de dispositivo se asignan a la cuenta de recursos que ha iniciado sesión en un dispositivo. Si cierra la sesión de una cuenta de recursos de un dispositivo y la usa para iniciar sesión en otro dispositivo, las etiquetas de dispositivo se aplicarán al nuevo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Crear, quitar o cambiar el nombre de etiquetas de dispositivo

Con el panel de administración de etiquetas de dispositivo, puedes:

- Ver todas las etiquetas de dispositivo.
- Crea varias etiquetas de dispositivo fácilmente y luego agrégalos a dispositivos más adelante. Las etiquetas pueden tener hasta 25 caracteres.
- Quita las etiquetas de dispositivo que ya no sean necesarias. Antes de poder quitar una etiqueta de dispositivo, tendrás que quitarla de todos los dispositivos a los que se ha agregado.
- Cambiar el nombre de las etiquetas de dispositivo. Al cambiar el nombre de una etiqueta de dispositivo, ese cambio se refleja en todos los dispositivos a los que se ha agregado. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Vaya a **Dispositivos de Teams** y, después, elija cualquier panel de dispositivos, como **Teléfonos**.
3. Seleccione **Acciones** en la esquina superior derecha de la página y seleccione **Todas las etiquetas de dispositivo**.
4. Para crear una etiqueta de dispositivo, selecciona **+ Agregar**, proporciona un valor para la etiqueta de dispositivo y selecciona el icono **Guardar** .
5. Para quitar una etiqueta de dispositivo, selecciona los puntos suspensivos **...** junto a la etiqueta de dispositivo que quieras quitar y selecciona **Eliminar**.
    > [!NOTE]
    > Si intentas quitar una etiqueta de dispositivo que se ha agregado a los dispositivos, recibirás un mensaje en el que se te pregunta si quieres quitarla de todos los dispositivos. Si quieres hacer esto y seguir quitando la etiqueta del dispositivo, selecciona **Quitar etiqueta a dispositivos**.
6. Para cambiar el nombre de una etiqueta de dispositivo, seleccione los puntos suspensivos **...** junto a la etiqueta de dispositivo a la que desea cambiar el nombre y seleccione **Editar**. Proporciona un nuevo valor para la etiqueta del dispositivo y selecciona el icono **Guardar** .

## <a name="add-or-remove-tags-on-a-single-device"></a>Agregar o quitar etiquetas en un único dispositivo

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Vaya a **Dispositivos de Teams** y, a continuación, elija el panel de dispositivos que contiene el dispositivo en el que quiere agregar o quitar etiquetas.
3. Coloca una marca de verificación junto al dispositivo en el que quieras agregar o quitar etiquetas y selecciona **Administrar etiquetas**.
4. Si desea agregar una etiqueta:
    1. Comience a escribir el nombre de la etiqueta que desea agregar.
    2. Si la etiqueta ya existe, selecciónela en la lista de etiquetas que se devuelven.
    3. Si la etiqueta no existe, selecciona **Agregar "\<tag name>" como nueva etiqueta**. Las etiquetas pueden tener hasta 25 caracteres.
5. Si quieres quitar una etiqueta, selecciona **X** junto a la etiqueta que quieres quitar.
6. Repita los pasos anteriores si desea agregar o quitar más etiquetas.
7. Seleccione **Aplicar**.

## <a name="add-or-remove-tags-on-multiple-devices"></a>Agregar o quitar etiquetas en varios dispositivos

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres. Si desea quitar una etiqueta de varios dispositivos, debe seleccionar el usuario de Teams que está asociado con el dispositivo y quitarle la etiqueta.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Vaya a **Dispositivos de Teams** y, a continuación, elija el panel de dispositivos que contiene los dispositivos en los que desea agregar o quitar etiquetas.
3. Coloca una marca de verificación junto a los dispositivos en los que quieras agregar o quitar etiquetas y selecciona **Administrar etiquetas**.
4. Si desea agregar una etiqueta:
    1. Empiece a escribir el nombre de la etiqueta que desea agregar en **Administrar etiquetas para todos los dispositivos de los usuarios de Teams**.
    2. Si la etiqueta ya existe, selecciónela en la lista de etiquetas que se devuelven.
    3. Si la etiqueta no existe, selecciona **Agregar "\<tag name>" como nueva etiqueta**.
5. Si quieres quitar una etiqueta:
    1. Expanda **Seleccionar usuarios de Teams**.
    2. Expanda **\<x> las etiquetas** bajo el nombre del usuario de Teams del que desea quitar etiquetas.
    3. Selecciona **X** junto a la etiqueta que quieras quitar.
6. Repita los pasos anteriores si desea agregar o quitar más etiquetas.
7. Seleccione **Aplicar**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usar filtros para devolver dispositivos con una etiqueta específica

Si has agregado etiquetas de dispositivo a tus dispositivos, puedes usarlas para filtrar la lista de dispositivos y devolver solo los dispositivos que tenían agregada una etiqueta especificada. Esto puede ser útil si solo desea ver todos los dispositivos de una sala específica, todos los dispositivos de un determinado tipo o cualquier otro criterio que haya usado al agregar las etiquetas. También puede realizar acciones masivas en dispositivos devueltos, como aplicar actualizaciones en ondas o establecer diferentes directivas de configuración según los grupos de dispositivos identificados con etiquetas de dispositivo.

1. Inicie sesión en el Centro de administración de Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Vaya a **Dispositivos de Teams** y, a continuación, elija el panel de dispositivos que contiene los dispositivos que desea filtrar.
3. Seleccione el icono **Filtro** .
4. Si solo quieres especificar una sola etiqueta, o si quieres buscar dispositivos que tengan todas las etiquetas que especifiques, selecciona **Coincidir con todas estas condiciones**.
5. Si quieres buscar dispositivos que coincidan con una o más etiquetas de dispositivo, selecciona **Coincidir con cualquiera de estas condiciones**.
6. Seleccione el campo **Etiqueta** y especifique un nombre de etiqueta de dispositivo en el campo **Escriba un valor** .
7. Si quieres agregar más etiquetas de dispositivo, selecciona **Agregar más** y repite el paso 6 para cada etiqueta que quieras agregar.
8. Seleccione **Aplicar**.

Después de filtrar los dispositivos en la lista de dispositivos, puedes realizar acciones en ellos como lo harías normalmente. Por ejemplo, puede seleccionarlas y, a continuación, asignar configuraciones, editar su configuración (si están Salas de Teams dispositivos), etc. Cuando haya terminado, puede quitar el filtro seleccionando la **X**  junto a la entrada **Filtro de etiqueta** o seleccionando **Borrar todo** en el lado derecho de la lista.
