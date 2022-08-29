---
title: Asignar licencias de Microsoft Teams para el ámbito educativo
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Obtenga información sobre cómo asignar licencias para Microsoft Teams para Educación.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426807"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>Asignar licencias de Microsoft Teams para el ámbito educativo

Este artículo es para administradores de TI en el ámbito educativo que necesitan asignar licencias de Team a sus profesores, personal y estudiantes.

Para que los usuarios estén listos para Usar Teams, deberá:

1. [Habilite Microsoft Teams para su centro educativo en la Centro de administración de Microsoft 365](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
2. Asigne licencias a cuentas de usuario para obtener acceso a los servicios de Microsoft 365, incluido Teams.

## <a name="ways-to-assign-teams-licenses"></a>Formas de asignar licencias de Teams

Puede asignar licencias a cuentas de usuario:

- Individualmente o para un pequeño grupo de usuarios de la Centro de administración de Microsoft 365.
- Automáticamente a través de la pertenencia a grupos con [PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) o [licencias basadas en grupos de Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

En este artículo se explica cómo asignar licencias en el Centro de administración de Microsoft 365.

En la Centro de administración de Microsoft 365, puede asignar licencias a los usuarios en:

- La página **Licencias** para asignar licencias de producto a usuarios específicos.
- La página **Usuarios activos** para asignar licencias de usuarios a productos específicos.

> [!NOTE]
> Debe ser un administrador global, administrador de facturación, administrador de licencias o administrador de administración de usuarios. Para obtener más información, consulte [Información sobre los roles de administrador de Office 365](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Asignar licencias a los usuarios en la página licencias

En la página **Licencias** , verá una lista de todos los productos para los que tiene suscripciones, el número total de licencias para cada producto, cuántas licencias están asignadas y cuántas están disponibles.

1. En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), vaya a la página [Licencias](https://go.microsoft.com/fwlink/p/?linkid=842264) **de facturación** > .

2. Seleccione un producto para el que quiera asignar licencias. Microsoft Teams forma parte de la Microsoft 365 A1 gratuita para estudiantes SKU.

3. Seleccione **Asignar licencias**.

4. En el panel **Asignar licencias a los usuarios**, empiece a escribir un nombre, lo que generará una lista de nombres.

5. Elija en los resultados el nombre que busca para agregarlo a la lista. Puede agregar hasta 20 usuarios a la vez.

6. Seleccione **Activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos, como Microsoft Teams. Asegúrese de que **Microsoft Teams** y **Office para la web (Educación)** estén seleccionados.

7. Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>Cambiar las aplicaciones y los servicios a los que un usuario tiene acceso

1. Seleccione la fila que contiene el usuario.

2. En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.

3. Cuando haya terminado, seleccione **Guardar** y haga clic en **Cerrar**.

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>Asignar licencias a usuarios en la página Usuarios activos

1. En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), vaya a la página **Usuarios** > [activos](https://go.microsoft.com/fwlink/p/?linkid=834822) .

2. Seleccione los círculos junto al (a los) nombre(s) del (de los) usuario(s) al (a los) que quiere asignar licencias.

3. En la parte superior, seleccione **Administrar licencias de producto**.

4. En el panel **Administrar licencias de producto**, seleccione **Agregar a las asignaciones de licencias de producto existentes**  >  **Siguiente**.

5. En el panel **Agregar a los productos existentes**, cambie el botón de alternancia a la posición de **Activado** para la licencia que quiere que tengan los usuarios seleccionados. Asegúrese de que **Microsoft Teams** y **Office para la web (Educación)** estén seleccionados.

   De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente al usuario o los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **Desactivado** para los servicios que no quiere que tengan los usuarios.

6. En la parte inferior del panel, seleccione **Agregar** > **cerrar**.
