---
title: Administrar y filtrar Microsoft Teams etiquetas de dispositivo
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
description: Obtenga información sobre cómo administrar y filtrar etiquetas en Microsoft Teams dispositivos.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: a264b6f2679576fac0eb95dbbfafa93037b98cfc3b5f5dfbfa9a07d6b6eeb3bc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321492"
---
# <a name="manage-microsoft-teams-device-tags"></a>Administrar Microsoft Teams etiquetas de dispositivo

Las etiquetas de dispositivo Microsoft Teams le permiten agrupar, organizar y administrar más fácilmente los dispositivos que ha implementado en su organización. Con el centro de administración de Microsoft Teams, puede agregar una o más etiquetas a los dispositivos, usar filtros para ver los dispositivos que coincidan con la etiqueta que especifique y, después, realizar acciones en los dispositivos que tienen esa etiqueta.

Puede agregar una etiqueta de dispositivo a más de un tipo de dispositivo. Sin embargo, al abrir un panel de dispositivos en el centro de administración, solo se devuelven los dispositivos de ese tipo. Por ejemplo, puede asignar la etiqueta "Corporativo" a teléfonos y Salas de Teams dispositivos. Si busca la etiqueta "Corporativo" mientras está en **Teléfonos**  >  **de** dispositivos, solo se devuelven los teléfonos. De forma similar, si busca la etiqueta "Corporativo" en Dispositivos Salas de Teams , solo  >  Salas de Teams dispositivos se devuelven.

Para administrar etiquetas de dispositivo, debe ser administrador global, administrador Teams servicio o Teams de dispositivo. Para obtener más información sobre los roles de administrador, [vea Usar Microsoft Teams de administrador para administrar Teams](../using-admin-roles.md).

> [!IMPORTANT]
> Las etiquetas de dispositivo se asignan a la cuenta de recursos que ha iniciado sesión en un dispositivo. Si firma una cuenta de recurso de un dispositivo y la usa para iniciar sesión en otro dispositivo, las etiquetas del dispositivo se aplican al nuevo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Crear, quitar o cambiar el nombre de etiquetas de dispositivo

Con el panel de administración de etiquetas de dispositivo, puede:

- Ver todas las etiquetas de dispositivo.
- Cree varias etiquetas de dispositivo fácilmente y, a continuación, asígnelas a dispositivos más adelante. Las etiquetas pueden tener hasta 25 caracteres.
- Quite etiquetas de dispositivo que ya no sean necesarias. Antes de poder quitar una etiqueta de dispositivo, tendrá que quitarla de todos los dispositivos a los que se ha agregado.
- Cambie el nombre de las etiquetas de dispositivo. Al cambiar el nombre de una etiqueta de dispositivo, ese cambio se refleja en todos los dispositivos a los que se ha agregado. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en Microsoft Teams de administración visitando https://admin.teams.microsoft.com .
2. Vaya a **Dispositivos** y, a continuación, elija cualquier panel de dispositivo, como **Teléfonos.**
3. Seleccione **Acciones** en la esquina superior derecha de la página y seleccione **Todas las etiquetas de dispositivo.**
4. Para crear una etiqueta de dispositivo, seleccione **+ Agregar**, proporcione un valor para la etiqueta de dispositivo y seleccione el **icono** Guardar.
5. Para quitar una etiqueta de dispositivo, seleccione los puntos suspensivos **...** junto a la etiqueta de dispositivo que desea quitar y seleccione **Eliminar**.
    > [!NOTE]
    > Si intenta quitar una etiqueta de dispositivo que se ha agregado a los dispositivos, recibirá un mensaje que le preguntará si desea quitarla de todos los dispositivos. Si desea hacer esto y continuar quitando la etiqueta del dispositivo, seleccione **Desatag dispositivos**.
6. Para cambiar el nombre de una etiqueta de dispositivo, selecciona los puntos suspensivos **...** junto a la etiqueta de dispositivo a la que quieres cambiar el nombre y selecciona **Editar**. Proporcione un nuevo valor para la etiqueta del dispositivo y seleccione el **icono** Guardar.

## <a name="add-or-remove-tags-on-a-single-device"></a>Agregar o quitar etiquetas en un único dispositivo

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en Microsoft Teams de administración visitando https://admin.teams.microsoft.com .
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

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres. Si desea quitar una etiqueta de varios dispositivos, debe seleccionar el usuario Teams asociado al dispositivo y quitar la etiqueta del usuario.

1. Inicie sesión en Microsoft Teams de administración visitando https://admin.teams.microsoft.com .
2. Vaya a **Dispositivos** y, a continuación, elija el panel de dispositivos que contiene los dispositivos en los que desea agregar o quitar etiquetas.
3. Coloque una marca de verificación junto a los dispositivos en los que desea agregar o quitar etiquetas y seleccione **Administrar etiquetas.**
4. Si desea agregar una etiqueta:
    1. Empiece a escribir el nombre de etiqueta que desea agregar en Administrar etiquetas para todos los dispositivos **de Teams usuarios.**
    2. Si la etiqueta ya existe, selecciónelo en la lista de etiquetas que se devuelven.
    3. Si la etiqueta no existe, seleccione **Agregar " " como una etiqueta \<tag name> nueva.**
5. Si desea quitar una etiqueta:
    1. Expandir **Seleccionar Teams usuarios**.
    2. Expanda **\<x> etiquetas** debajo del nombre Teams usuario del que desea quitar etiquetas.
    3. Seleccione **X** junto a la etiqueta que desea quitar.
6. Repita los pasos anteriores si desea agregar o quitar más etiquetas.
7. Seleccione **Aplicar**.

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usar filtros para devolver dispositivos con una etiqueta específica

Si ha agregado etiquetas de dispositivo a sus dispositivos, puede usarlas para filtrar la lista de dispositivos para devolver solo los dispositivos que han agregado una etiqueta especificada. Esto puede ser útil si solo desea ver todos los dispositivos de una sala específica, todos los dispositivos de un tipo determinado o cualquier otro criterio que haya usado al agregar las etiquetas. También puede realizar acciones masivas en dispositivos devueltos, como aplicar actualizaciones en oleadas o establecer directivas de configuración diferentes en función de los grupos de dispositivos identificados con etiquetas de dispositivo.

1. Inicie sesión en Microsoft Teams de administración visitando https://admin.teams.microsoft.com .
2. Vaya a **Dispositivos** y, a continuación, elija el panel de dispositivos que contiene los dispositivos que desea filtrar.
3. Seleccione el **icono Filtro.**
4. Si solo desea especificar una sola etiqueta o si desea buscar dispositivos que tengan todas las etiquetas especificadas, seleccione Coincidir todas **estas condiciones.**
5. Si desea buscar dispositivos que coincidan con una o más etiquetas de dispositivo, seleccione **Coincidir con cualquiera de estas condiciones.**
6. Seleccione el **campo Etiqueta** y, a continuación, especifique un nombre de etiqueta de dispositivo en el campo **Escribir un** valor.
7. Si desea agregar más etiquetas de dispositivo, seleccione **Agregar más** y repita el paso 6 para cada etiqueta que quiera agregar.
8. Seleccione **Aplicar**.

Después de filtrar los dispositivos de la lista de dispositivos, puede realizar acciones en ellos como lo haría normalmente. Por ejemplo, puede seleccionarlas y, a continuación, asignar configuraciones, editar su configuración (si están Salas de Teams dispositivos) y así sucesivamente. Cuando haya terminado, puede quitar el filtro seleccionando la  **X** junto a  la entrada Filtro de etiquetas o seleccionando Borrar todo en el lado derecho de la lista.
