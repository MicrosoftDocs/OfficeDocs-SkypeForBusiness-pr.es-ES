---
title: Administrar dispositivos con unidades administrativas
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar unidades administrativas en Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5afbc4acd33acf7e950218e7cf2e30383b3b1d12
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790435"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Administrar dispositivos en el Centro de administración de Teams con unidades administrativas

Las unidades administrativas del Centro de administración de Teams proporcionan acceso detallado basado en roles para administrar dispositivos de Teams. Las unidades administrativas conceden a los administradores de Teams acceso a recursos específicos, pero limitan el acceso de ese administrador a otros recursos. Esto es especialmente útil si tiene administradores locales de Teams en diferentes países o regiones.

Por ejemplo, Contoso tiene operaciones en todo el mundo. Alice es una administradora global de TI con sede en Londres, mientras que Prashant es una administradora de TI local con sede en Bangalore, India. Hoy, cuando Prashant inicia sesión en el Centro de administración de Teams como administrador de dispositivos, puede ver los dispositivos de Teams en todo el mundo. Alice quiere limitar el acceso de Prashant a los dispositivos de Teams solo en Bangalore. Las unidades administrativas le dejó hacer esto. Para obtener más información, consulte [Unidades administrativas en Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Las unidades administrativas están disponibles actualmente en el Centro de administración de Teams solo para el rol de administrador de dispositivos de Teams.

## <a name="add-administrative-units"></a>Agregar unidades administrativas

Debe ser administrador global para agregar unidades administrativas. Para obtener información sobre cómo hacerlo, consulte [Agregar una unidad administrativa](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Asignar administradores a unidades administrativas

También tendrá que ser administrador global para asignar unidades administrativas. Puede asignar unidades administrativas con Azure Portal, PowerShell o microsoft Graph API. Para obtener más información, consulte [Asignar roles de Azure AD con ámbito de unidad administrativa](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Seleccionar unidades administrativas

Si es administrador de dispositivos de Teams, después de que un administrador global le asigne a una unidad administrativa, puede iniciar sesión en el Centro de administración de Teams para administrar dispositivos. Si solo está asignado a una unidad administrativa, verá solo los dispositivos asignados a esa unidad administrativa. Si se le asignan varias unidades administrativas, puede cambiar entre esas unidades administrativas sin cerrar la sesión en el Centro de administración de Teams. 

1. Inicie sesión en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. En el cuadro de diálogo **Sus unidades administrativas** , siga uno de estos pasos:
    - Seleccione la unidad administrativa que desea administrar, o bien 
    - Seleccione **Todos los dispositivos** si tiene permiso para administrar todos los dispositivos de su organización.

3. Seleccione **Guardar**.

## <a name="switch-administrative-units"></a>Cambiar unidades administrativas

Si es administrador de dispositivos de Teams, puede cambiar entre unidades administrativas si ha iniciado sesión en el Centro de administración de Teams. Para cambiar a una unidad administrativa diferente:

1. Inicie sesión en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. En el panel de navegación izquierdo, seleccione **Dispositivos de Teams**.

3. En el panel derecho, en la parte superior izquierda, seleccione la unidad administrativa que se muestra.

4. En el cuadro de diálogo **Sus unidades administrativas** , siga uno de estos pasos:
    - Seleccione la unidad administrativa que desea administrar, o bien 
    - Seleccione **Todos los dispositivos** si tiene permiso para administrar todos los dispositivos de su organización.

5. Seleccione **Guardar**.

## <a name="related-topics"></a>Temas relacionados

- [Agregar usuarios o grupos a una unidad administrativa](/azure/active-directory/roles/admin-units-members-add)
