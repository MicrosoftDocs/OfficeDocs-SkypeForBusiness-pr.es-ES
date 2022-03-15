---
title: Crear una cuenta de recursos con el Centro de administración de Microsoft 365
description: Si prefiere usar una interfaz gráfica de usuario, puede crear una cuenta de recursos para su Salas de Microsoft Teams y barras de colaboración para Microsoft Teams con el Centro de Administración de Microsoft 365 gráfico.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: crear una cuenta de dispositivo, Microsoft 365 interfaz de usuario, Centro de administración de Microsoft 365
ms.sitesec: library
ms.service: msteams
author: cazawideh
ms.author: czawideh
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1d4d3a24222183c8798bb5d0e7eda879acca8d3e
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503947"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Crear una Microsoft 365 de recursos con el Centro de administración de Microsoft 365

Microsoft 365 de recursos son cuentas de buzón y Teams que están dedicadas a recursos específicos, como un salón, un proyector, y así sucesivamente. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones mediante reglas que defina cuando se crean. Por ejemplo, si tiene un recurso común como una sala de conferencias, puede configurar una cuenta de recursos para esa sala de conferencias que aceptará o rechazará automáticamente las invitaciones a reuniones según la disponibilidad del calendario.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licencias

Antes de crear una Microsoft 365 de recursos, compruebe qué tipo de licencia necesita. Si solo usará una cuenta de recursos para reservar un recurso (es decir, invite el recurso a la reunión y haga que acepte o rechace automáticamente la invitación), no es necesario asignar una licencia a una cuenta de recursos. Deberá asignar una licencia a la cuenta de recursos en las situaciones siguientes:

- **Teams** reunión Si desea que el recurso (como una consola de Salas de Microsoft Teams, una barra de colaboración, entre otros) se una a una reunión de Teams para que los asistentes puedan usarlo para presentar vídeo y audio a través de él, necesita una licencia de Sala de reuniones. 
- **Llamadas RTC** Si desea que el recurso realice o reciba llamadas a o desde un número de teléfono externo (denominado Red telefónica conmutada pública o llamada RTC), necesita una licencia Microsoft 365 Sistema telefónico o Microsoft 365 Business Voice.

Para obtener más información sobre Sala de reuniones, Sistema telefónico y licencias de Business Voice, [vea Microsoft Teams de](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) complementos

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Crear una cuenta de recurso en el Centro de administración de Microsoft 365

1. Inicie sesión en Microsoft 365 visitandohttps://admin.microsoft.com
2. Proporcione las credenciales de administrador para su Microsoft 365 inquilino. Esto le llevará a su Centro de administración de Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centro de administración de Microsoft 365.":::
3. En el centro de administración, vaya a **Recursos** en el panel izquierdo (es posible que tenga  que seleccionar Mostrar todo primero) y, a continuación, seleccione **Salas & equipo**.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centro de administración de Microsoft 365: recursos.":::
4. Seleccione **Agregar un buzón de recursos** para crear una nueva cuenta de salón. Escriba un nombre para mostrar y una dirección de correo electrónico para la cuenta, seleccione **Agregar** y, a continuación, **seleccione Cerrar**. Se recomienda estandarizar una convención de nomenclatura para todas las cuentas de recursos.

> [!NOTE]
> De forma predeterminada, las cuentas de recursos están configuradas con la siguiente configuración. Si desea cambiarlas, seleccione **Establecer opciones de programación** antes de seleccionar **Cerrar**. Si desea cambiarlos más adelante, vaya **a ResourcesRooms** >  & equipo, seleccione la cuenta de recursos y, a continuación, **seleccione Editar** en **Opciones de reserva**.
>
> - Permitir reuniones repetidas
> - Rechazar automáticamente reuniones fuera de los límites siguientes
>   - Ventana de reserva (días): 180
>   - Duración máxima (horas): 24
> - Aceptar automáticamente las solicitudes de reunión

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centro de administración de Microsoft 365: agregar recursos.":::
5. Vaya a la **sección Usuarios** del Centro de administración y, en la **lista Usuarios** activos, verá el salón que acaba de crear.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centro de administración de Microsoft 365: ver usuarios activos.":::
6. Seleccione el nombre del salón y aparecerá un panel de propiedades de la cuenta a la derecha.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centro de administración de Microsoft 365: propiedades de usuario.":::
7. Ahora debe asignar una contraseña a la cuenta de recursos. En el panel, puede ver las propiedades de la cuenta y varias acciones opcionales. Seleccione el **icono Restablecer clave de** contraseña debajo del nombre de usuario para cambiar la contraseña. Anular la **selección Requerir que este usuario cambie su contraseña al iniciar sesión por primera vez**. No es posible cambiar la contraseña a través del proceso de inicio de sesión del dispositivo. Seleccione **Restablecer**.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centro de administración de Microsoft 365: Restablecer contraseña.":::
8. En la **sección Licencias y aplicaciones** , establezca **Seleccionar ubicación** en el país o región donde se instalará el dispositivo. Desplácese hacia abajo y active la casilla situada junto a la licencia que se va a asignar (por ejemplo, Sala de reuniones) y, a continuación, seleccione **Guardar cambios**. La licencia puede variar según su organización.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centro de administración de Microsoft 365: Asignar licencia.":::
