---
title: Crear una cuenta de recursos con el centro de administración de Microsoft 365
description: Si prefiere usar una interfaz gráfica de usuario, puede crear una cuenta de recursos para sus salas de colaboración y salas de Microsoft Teams para Microsoft Teams mediante el centro de administración de Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: crear una cuenta de dispositivo, Microsoft 365 UI, centro de administración de Microsoft 365
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268068"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Crear una cuenta de recursos de Microsoft 365 con el centro de administración de Microsoft 365

Las cuentas de recursos de Microsoft 365 son cuentas de buzón y de equipo dedicadas a recursos específicos, como una sala, un proyector, etc. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones con reglas que usted define al crearlas. Por ejemplo, si tiene un recurso común, como una sala de conferencias, puede configurar una cuenta de recursos para esa sala de conferencias que acepte o rechace automáticamente las invitaciones a reuniones en función de la disponibilidad de su calendario.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licencias

Antes de crear una cuenta de recursos de 365 de Microsoft, compruebe qué tipo de licencia necesita. Si solo va a usar una cuenta de recursos para reservar un recurso (es decir, invita el recurso a la reunión y hacer que acepte o rechace la invitación automáticamente), no es necesario asignar una licencia a una cuenta de recursos. Tendrá que asignar una licencia a la cuenta de recursos en las siguientes situaciones:

- **Reunión de Teams** Si quiere que el recurso (como una consola de salas de Microsoft Teams, la barra de colaboración, etc.) se una a una reunión de Teams para que los asistentes puedan usarlo para presentar vídeo y audio a través de él, necesita una licencia de sala de reuniones. 
- **Llamadas RTC** Si desea que el recurso realice o reciba llamadas a o desde números de teléfono externos (lo que se conoce como una llamada de red telefónica conmutada o RTC), necesita un sistema telefónico de Microsoft 365 o una licencia de voz empresarial de Microsoft 365.

Para obtener más información sobre las licencias de sala de reuniones, sistema telefónico y Business Voice, consulte [licencias de complementos de Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Crear una cuenta de recursos en el centro de administración de Microsoft 365

1. Para iniciar sesión en Microsoft 365, visitehttps://admin.microsoft.com
2. Proporcione las credenciales de administrador para el inquilino de Microsoft 365. Esto le llevará a su centro de administración de Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centro de administración de Microsoft 365":::
3. En el centro de administración, vaya a **recursos** en el panel izquierdo (es posible que tenga que seleccionar **Mostrar todo** primero) y, a continuación, seleccione **salas & equipo**.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centro de administración de Microsoft 365: recursos":::
4. Seleccione **Agregar un buzón de recursos** para crear una nueva cuenta de sala. Escriba un nombre para mostrar y una dirección de correo electrónico para la cuenta, seleccione **Agregar**y, después, haga clic en **cerrar**. Le recomendamos que se normalizan las convenciones de nomenclatura para todas las cuentas de recursos.

> [!NOTE]
> De forma predeterminada, las cuentas de recursos se configuran con la siguiente configuración. Si desea cambiarlos, seleccione **establecer opciones de programación** antes de seleccionar **cerrar**. Si desea cambiarlos más tarde, vaya a **recursos**  >  **locales & equipo**, seleccione la cuenta de recursos y, después, seleccione **Editar** en **Opciones de reserva**.
>
> - Permitir reuniones de repetición
> - Rechazar automáticamente las reuniones que se encuentren fuera de los siguientes límites
>   - Ventana de reserva (días): 180
>   - Duración máxima (horas): 24
> - Aceptar automáticamente convocatorias de reunión

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centro de administración de Microsoft 365: agregar recursos":::
5. Vaya a la sección **usuarios** en el centro de administración y, en la lista **usuarios activos** , verá la sala que acaba de crear.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centro de administración de Microsoft 365: ver usuarios activos":::
6. Seleccione en el nombre del salón y aparecerá un panel de propiedades de cuenta a la derecha.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centro de administración de Microsoft 365-propiedades de usuario":::
7. Ahora debe asignar una contraseña a la cuenta de recursos. En el panel, puede ver las propiedades de la cuenta y varias acciones opcionales. Seleccione el icono restablecer clave de **contraseña** debajo del nombre de usuario para cambiar la contraseña. Anule la selección de **requerir que este usuario cambie su contraseña la primera vez que inicie sesión**. No es posible cambiar la contraseña a través del proceso de inicio de sesión del dispositivo. Seleccione **restablecer**.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centro de administración de Microsoft 365: restablecer contraseña":::
8. En la sección **licencias y aplicaciones** , **Seleccione la ubicación** en el país o la región en la que se instalará el dispositivo. Desplácese hacia abajo y active la casilla que se encuentra junto a la licencia que desea asignar (por ejemplo, sala de reuniones) y, a continuación, seleccione **Guardar cambios**. La licencia puede variar en función de su organización.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centro de administración de Microsoft 365: asignar licencia":::
