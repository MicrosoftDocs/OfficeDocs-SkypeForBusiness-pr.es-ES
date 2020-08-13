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
description: Obtenga información sobre cómo administrar y filtrar etiquetas en los dispositivos de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f428a40e5a9adf4a53d4b2e12064b90b4ceebe43
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46657108"
---
# <a name="manage-microsoft-teams-device-tags"></a>Administrar etiquetas de dispositivos de Microsoft Teams

> [!NOTE]
> La capacidad de agregar etiquetas a dispositivos está disponible para los clientes de Microsoft Teams en ondas. Si no ve la opción de administrar etiquetas en el centro de administración de Teams, aún no se han habilitado en su inquilino las etiquetas del dispositivo. Vuelve a consultar más tarde.

Las etiquetas de dispositivos de Microsoft Teams le permiten agrupar, organizar y administrar más fácilmente los dispositivos que ha implementado en su organización. Con el centro de administración de Microsoft Teams, puede Agregar una o más etiquetas a los dispositivos, usar filtros para ver los dispositivos que coincidan con la etiqueta que especifique y, a continuación, realizar acciones en los dispositivos que tienen esa etiqueta.

Puede Agregar una etiqueta de dispositivo a más de un tipo de dispositivo. Sin embargo, al abrir un panel de dispositivos en el centro de administración, solo se devuelven los dispositivos de ese tipo. Por ejemplo, puede asignar la etiqueta "empresa" a teléfonos y a dispositivos de salas de equipos. Si buscas la etiqueta "empresa" en teléfonos de **dispositivos**  >  **Phones**, solo se devuelven teléfonos. De forma similar, si busca la etiqueta "Corporate" en **dispositivos**  >  **salas de equipos**, solo se devolverán los dispositivos de salas de equipos.

Para administrar etiquetas de dispositivo, debe ser un administrador global o un administrador del servicio de Teams.

> [!IMPORTANT]
> Las etiquetas de dispositivos se asignan a la cuenta de recursos que se ha conectado en un dispositivo. Si firma una cuenta de recursos fuera de un dispositivo y luego la usa para iniciar sesión en otros dispositivos, las etiquetas del dispositivo se aplican al nuevo dispositivo.

## <a name="create-remove-or-rename-device-tags"></a>Crear, quitar o cambiar el nombre de etiquetas de dispositivo

Con el panel de administración de etiquetas de dispositivos, puede hacer lo siguiente:

- Ver todas las etiquetas de tu dispositivo.
- Crear varias etiquetas de dispositivo fácilmente y después asignarlas a dispositivos más adelante. Las etiquetas pueden tener hasta 25 caracteres.
- Quite las etiquetas de dispositivo que ya no se necesiten. Antes de que pueda quitar una etiqueta de dispositivo, tendrá que quitarla de todos los dispositivos a la que se ha agregado.
- Cambie el nombre de las etiquetas del dispositivo. Al cambiar el nombre de una etiqueta de dispositivo, ese cambio se refleja en todos los dispositivos a los que se ha agregado. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en el centro de administración de Microsoft Teams visitandohttps://admin.teams.microsoft.com
2. Vaya a **dispositivos** y, a continuación, elija cualquier panel de dispositivos, como **teléfonos**
3. Seleccione **acciones** en la esquina superior derecha de la página y seleccione **todas las etiquetas de dispositivo**
4. Para crear una etiqueta de dispositivo, seleccione **+ Agregar**, proporcione un valor para la etiqueta de dispositivo y seleccione el icono **Guardar** .
5. Para quitar una etiqueta de dispositivo, seleccione los puntos suspensivos **...** junto a la etiqueta de dispositivo que desea quitar y, después, seleccione **eliminar** .
    > [!NOTE]
    > Si intenta quitar una etiqueta de dispositivo que se ha agregado a los dispositivos, recibirá un mensaje en el que se le preguntará si desea quitarlo de todos los dispositivos. Si desea hacerlo y continuar con la eliminación de la etiqueta de dispositivo, seleccione quitar **dispositivos**.
6. Para cambiar el nombre de una etiqueta de dispositivo, seleccione los puntos suspensivos **...** junto a la etiqueta de dispositivo a la que desea cambiarle el nombre y seleccione **Editar**. Proporcione un nuevo valor para la etiqueta de dispositivo y seleccione el icono **Guardar** .

## <a name="add-or-remove-tags-on-a-single-device"></a>Agregar o quitar etiquetas en un solo dispositivo

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres.

1. Inicie sesión en el centro de administración de Microsoft Teams visitandohttps://admin.teams.microsoft.com
2. Vaya a **dispositivos** y, a continuación, elija el panel de dispositivos que contiene el dispositivo en el que desea agregar o quitar etiquetas.
3. Coloca una marca de verificación junto al dispositivo en el que deseas agregar o quitar etiquetas y selecciona **administrar etiquetas** .
4. Si desea agregar una etiqueta:
    1. Comience a escribir el nombre de etiqueta que desea agregar.
    2. Si la etiqueta ya existe, selecciónela de la lista de etiquetas que se devuelven
    3. Si la etiqueta no existe, seleccione **Agregar " \<tag name> " como nueva etiqueta**. Las etiquetas pueden tener hasta 25 caracteres.
5. Si desea quitar una etiqueta, seleccione **X** junto a la etiqueta que quiere quitar.
6. Repita los pasos anteriores si desea agregar o quitar más etiquetas.
7. Seleccione **aplicar**

## <a name="add-or-remove-tags-on-multiple-devices"></a>Agregar o quitar etiquetas en varios dispositivos

Al agregar etiquetas a un dispositivo, puede seleccionar una etiqueta existente o crear una nueva. Las etiquetas pueden tener hasta 25 caracteres. Si desea quitar una etiqueta de varios dispositivos, debe seleccionar el usuario de teams que está asociado con el dispositivo y quitar la etiqueta del usuario.

1. Inicie sesión en el centro de administración de Microsoft Teams visitandohttps://admin.teams.microsoft.com
2. Vaya a **dispositivos** y, a continuación, elija el panel de dispositivos que contiene los dispositivos en los que desea agregar o quitar etiquetas.
3. Coloca una marca de verificación junto a los dispositivos en los que deseas agregar o quitar etiquetas y selecciona **administrar etiquetas** .
4. Si desea agregar una etiqueta:
    1. Comience a escribir el nombre de etiqueta que desea agregar en **administrar etiquetas para todos los dispositivos de los usuarios de Teams**
    2. Si la etiqueta ya existe, selecciónela de la lista de etiquetas que se devuelven
    3. Si la etiqueta no existe, selecciona **añadir " \<tag name> " como nueva etiqueta**
5. Si desea quitar una etiqueta:
    1. Expandir **Seleccionar usuarios de Teams**
    2. Expandir ** \<x> etiquetas** debajo del nombre del usuario de Teams del que desea quitar etiquetas
    3. Seleccione una **X** junto a la etiqueta que quiere quitar.
6. Repita los pasos anteriores si desea agregar o quitar más etiquetas.
7. Seleccione **aplicar**

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a>Usar filtros para devolver dispositivos con una etiqueta específica

Si ha agregado etiquetas de dispositivo a sus dispositivos, puede usarlas para filtrar la lista de dispositivos y devolver solo los dispositivos a los que se les haya agregado una etiqueta especificada. Esto puede ser útil si solo quiere ver todos los dispositivos de un salón específico, todos los dispositivos de un tipo determinado o cualquier otro criterio que haya usado al agregar las etiquetas. También puede realizar acciones en masa en dispositivos devueltos, como aplicar actualizaciones en ondas o establecer diferentes directivas de configuración según los grupos de dispositivos identificados mediante etiquetas de dispositivo.

1. Inicie sesión en el centro de administración de Microsoft Teams visitandohttps://admin.teams.microsoft.com
2. Vaya a **dispositivos** y, a continuación, elija el panel de dispositivos que contiene los dispositivos que desea filtrar.
3. Seleccione el icono de **filtro**
4. Si solo desea especificar una única etiqueta o si desea buscar dispositivos que tengan todas las etiquetas que especifique, seleccione **cumplir todas estas condiciones**.
5. Si desea buscar dispositivos que coincidan con una o más etiquetas de dispositivo, seleccione **coincidir cualquiera de estas condiciones** .
6. Seleccione el campo de **etiqueta** y, a continuación, especifique un nombre de etiqueta de dispositivo en el campo **introducir un valor**
7. Si quiere agregar más etiquetas de dispositivo, seleccione **Agregar más** y repita el paso 6 para cada etiqueta que desee agregar.
8. Seleccione **aplicar**

Después de filtrar los dispositivos en la lista de dispositivos, puede realizar acciones en ellos como lo haría normalmente. Por ejemplo, puede seleccionarlos y, a continuación, asignar configuraciones, editar su configuración (si son dispositivos de salas de equipos) y así sucesivamente. Cuando haya terminado, puede quitar el filtro seleccionando la **X** junto a la entrada de filtro de **etiqueta** o seleccionando **Borrar todo** en el lado derecho de la lista.
