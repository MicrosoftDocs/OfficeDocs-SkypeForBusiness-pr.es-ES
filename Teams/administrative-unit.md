---
title: Administrar dispositivos con unidades administrativas
author: mahoffman
ms.author: serdars
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
---

# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Administrar dispositivos en el Teams de administración con unidades administrativas

Las unidades administrativas del Teams de administración proporcionan acceso detallado basado en roles para administrar Teams dispositivos. Las unidades administrativas Teams acceso de administrador a recursos específicos, pero limitan el acceso de ese administrador a otros recursos. Esto es especialmente útil si tiene administradores Teams locales en diferentes países o regiones.

Por ejemplo, Contoso tiene operaciones en todo el mundo. Alice es una administradora global de TI con sede en Londres, mientras que Prashant es un administrador local de TI con sede en Bangalore, India. Hoy, cuando Prashant inicia sesión en el centro de administración de Teams como administrador de dispositivos, puede ver Teams dispositivos de todo el mundo. Alicia quiere limitar el acceso de Prashant a Teams dispositivos solo en Bangalore. Las unidades administrativas le permiten hacerlo. Para obtener más información, vea [Unidades administrativas en Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Las unidades administrativas están disponibles actualmente en el Teams de administración solo para el rol de administrador Teams dispositivos.

## <a name="add-administrative-units"></a>Agregar unidades administrativas

Debe ser un administrador global para agregar unidades administrativas. Para obtener más información, vea [Agregar una unidad administrativa](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Asignar administradores a unidades administrativas

También tendrá que ser administrador global para asignar unidades administrativas. Puede asignar unidades administrativas con Azure Portal, PowerShell o la API Graph Microsoft. Para obtener más información, vea [Asignar Azure AD roles con ámbito de unidad administrativa](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Seleccionar unidades administrativas

Si es administrador de Teams dispositivos, después de que un administrador global le asigne a una unidad administrativa, puede iniciar sesión en el centro de administración de Teams para administrar dispositivos. Si solo está asignado a una unidad administrativa, solo verá los dispositivos asignados a esa unidad administrativa. Si está asignado a varias unidades administrativas, puede cambiar entre esas unidades administrativas sin salir del centro de administración Teams administración. 

1. Inicie sesión en el [Teams de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. En el **cuadro de diálogo Sus unidades** administrativas, siga uno de estos pasos:
    - Seleccione la unidad administrativa que desea administrar o 
    - Seleccione **Todos los dispositivos** si tiene permiso para administrar todos los dispositivos de su organización.

3. Seleccione **Guardar**.

## <a name="switch-administrative-units"></a>Cambiar las unidades administrativas

Si es administrador de Teams dispositivos, puede cambiar entre unidades administrativas si ha iniciado sesión en el Teams administración. Para cambiar a otra unidad administrativa:

1. Inicie sesión en el [Teams de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. En el panel de navegación izquierdo, **seleccione Teams dispositivos**.

3. En el panel derecho, en la esquina superior izquierda, seleccione la unidad administrativa que se muestra.

4. En el **cuadro de diálogo Sus unidades** administrativas, siga uno de estos pasos:
    - Seleccione la unidad administrativa que desea administrar o 
    - Seleccione **Todos los dispositivos** si tiene permiso para administrar todos los dispositivos de su organización.

5. Seleccione **Guardar**.
