---
title: Recursos de Microsoft Teams para administradores de educación
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Tutorial de licencias de Microsoft Teams para EDU.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83448f32ddfc96800a14b5a599ef9cb7af52bb9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119239"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a>Asignar licencias de Microsoft Teams para EDU

Microsoft Teams es un centro digital que reúne conversaciones, contenido y aplicaciones en un solo lugar. Dado que se basa en Office 365, las escuelas se benefician de la integración con aplicaciones y los servicios de Office universalmente conocidos. Su institución puede usar Microsoft Teams para crear clases colaborativas, ponerse en contacto los unos con los otros en comunidades de aprendizaje profesional y comunicarse con el personal del centro educativo. Y todo ello a través de una sola experiencia de Office 365 para el ámbito educativo.

Para empezar, los administradores de TI tienen que usar el Centro de administración de Microsoft 365 para [habilitar Microsoft Teams en su escuela](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
Cuando termine, debe asignar las licencias a las cuentas de usuario para que el profesor, el personal y los alumnos puedan acceder a los servicios de Office 365, como Microsoft Teams.

Puede asignar licencias a las cuentas de usuario, ya sea de forma individual o automáticamente mediante la pertenencia a grupos. Este artículo le guiará por los pasos para asignar licencias de Office 365 a una persona o a un conjunto reducido de cuentas de usuario en el Centro de administración de Microsoft 365. Para asignar licencias automáticamente mediante la pertenencia a grupos, consulte uno de nuestros artículos de soporte técnico:

- [PowerShell de Office 365](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [Concesión de licencias basada en grupo en Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)

Puede asignar licencias a los usuarios en la página **Licencias** o en la página **Usuarios activos**. El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Asignar licencias a los usuarios en la página licencias

> [!NOTE]
> Debe ser un administrador global, administrador de facturación, administrador de licencias o administrador de administración de usuarios. Para obtener más información, consulte [Información sobre los roles de administrador de Office 365](/microsoft-365/admin/add-users/about-admin-roles).

Al usar la página de **Licencias** para asignar licencias, asigna licencias para un producto específico a un máximo de 20 usuarios. En la página **Licencias**, verá una lista de todos los productos para los que tiene suscripciones, junto con el número total de licencias de cada producto, cuántas licencias están asignadas y cuántas están disponibles.

1. En el Centro de administración, vaya a la página **Facturación** > [Licencias](https://go.microsoft.com/fwlink/p/?linkid=842264).

   ![Captura de pantalla de la ventana facturación y las opciones de menú.](media/EDU-Lic-Billing-License.png)
2. Seleccione un producto para el que quiera asignar licencias. Microsoft Teams forma parte del SKU para estudiantes gratuito de Office 365 A1.

   ![Captura de pantalla de la página Licencias con productos disponibles para asignar licencias.](media/EDU-Lic-Licenses-Products.png)
3. Seleccione **Asignar licencias**.

   ![Captura de pantalla de la sección Usuarios de la página y la opción Asignar licencias con el signo más delante.](media/EDU-Lic-Assign-Licenses.png)
4. En el panel **Asignar licencias a los usuarios**, empiece a escribir un nombre, lo que generará una lista de nombres. Elija en los resultados el nombre que busca para agregarlo a la lista. Puede agregar hasta 20 usuarios a la vez.

   ![Captura de pantalla de la página de Asignar licencias a los usuarios con un nombre parcial escrito, donde se muestran los resultados de la búsqueda para ese nombre parcial.](media/EDU-Lic-Assign-Licenses-Users.png)
5. Seleccione **Activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos, como Microsoft Teams. Asegúrese de que **Microsoft Teams** y **Office para la web (Educación)** estén seleccionados.
6. Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.

Para cambiar las aplicaciones y los servicios a los que tiene acceso un usuario:

1. Seleccione la fila que contiene el usuario.
1. En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.
1. Cuando haya terminado, seleccione **Guardar** y haga clic en **Cerrar**.

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a>Asignar licencias a un usuario individual o a varios usuarios en la página Usuarios activos

1. En el Centro de administración, vaya a la página **Usuarios**  >  [Usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822).

   ![Captura de pantalla de la opción de menú Usuarios activos en el Centro de administración de Microsoft O365.](media/EDU-Lic-Active-Users.png)
2. Seleccione los círculos junto al (a los) nombre(s) del (de los) usuario(s) al (a los) que quiere asignar licencias.

   ![Captura de pantalla de la página Usuarios activos y una lista de los usuarios activos de la página, con algunos usuarios seleccionados, ya que se ha rellenado un círculo junto a sus nombres.](media/EDU-Lic-Active-Users-List.png)
3. En la parte superior, seleccione **Administrar licencias de producto**.

   ![Captura de pantalla de la pestaña Administrar licencias de producto y un usuario que aparece sin licencia.](media/EDU-Lic-Manage-Product-Licenses.png)
4. En el panel **Administrar licencias de producto**, seleccione **Agregar a las asignaciones de licencias de producto existentes**  >  **Siguiente**.

   ![Captura de pantalla de la ventana Administrar licencias de producto, con el botón de radio Agregar a las asignaciones de licencias de producto existentes activado.](media/EDU-Lic-Add-Existing-Product.png)
5. En el panel **Agregar a los productos existentes**, cambie el botón de alternancia a la posición de **Activado** para la licencia que quiere que tengan los usuarios seleccionados. Asegúrese de que **Microsoft Teams** y **Office para la web (Educación)** estén seleccionados.

   ![Captura de pantalla de la pestaña Agregar a los productos existentes en la que se ha seleccionado Microsoft Teams y Office para la web, Educación.](media/EDU-Lic-Add-Existing-Products.png)

   De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente al usuario o los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **Desactivado** para los servicios que no quiere que tengan los usuarios.
6. En la parte inferior del panel, seleccione Agregar > Cerrar.