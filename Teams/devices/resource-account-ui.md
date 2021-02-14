---
title: Crear una cuenta de recurso mediante el Centro de administración de Microsoft 365
description: Si prefiere usar una interfaz de usuario gráfica, puede crear una cuenta de recursos para sus salas de Microsoft Teams y barras de colaboración para Microsoft Teams mediante el Centro de administración de Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: crear una cuenta de dispositivo, interfaz de usuario de Microsoft 365, Centro de administración de Microsoft 365
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Crear una cuenta de recursos de Microsoft 365 mediante el Centro de administración de Microsoft 365

Las cuentas de recursos de Microsoft 365 son cuentas de buzón y de Teams que están dedicadas a recursos específicos, como una sala, proyector, entre otras. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones mediante las reglas que defina cuando se crean. Por ejemplo, si tiene un recurso común como una sala de conferencias, puede configurar una cuenta de recursos para esa sala de conferencias que aceptará o rechazará automáticamente las invitaciones a reuniones en función de su disponibilidad en el calendario.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licencias

Antes de crear una cuenta de recursos de Microsoft 365, compruebe qué tipo de licencia necesita. Si va a usar solo una cuenta de recursos para reservar un recurso (es decir, invitar al recurso a la reunión y hacer que acepte o rechace automáticamente la invitación), no es necesario asignar una licencia a una cuenta de recurso. Tendrá que asignar una licencia a la cuenta de recurso en las siguientes situaciones:

- **Reunión de Teams** Si desea que el recurso (como una consola de salas de Microsoft Teams, la barra de colaboración, entre otros) se una a una reunión de Teams para que los asistentes puedan usarlo para presentar vídeo y audio a través de este, necesita una licencia de sala de reuniones. 
- **Llamadas RTC** Si desea que el recurso realice o reciba llamadas a o desde un número de teléfono externo (denominado red telefónica conmutada pública o llamada RTC), necesita una licencia de Microsoft 365 Phone System o Microsoft 365 Business Voice.

Para obtener más información sobre las licencias de Salas de reuniones, Sistema telefónico y Voz [empresarial,](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) consulte licencias de complementos de Microsoft Teams

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Crear una cuenta de recurso en el Centro de administración de Microsoft 365

1. Inicia sesión en Microsoft 365 visitando https://admin.microsoft.com
2. Proporcione las credenciales de administrador para su inquilino de Microsoft 365. Esto le llevará al Centro de administración de Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centro de administración de Microsoft 365":::
3. En el centro de  administración, vaya a Recursos en  el panel izquierdo (es posible que tenga que seleccionar Mostrar todo primero) y, después, seleccione Salas **& equipamiento.**

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centro de administración de Microsoft 365: recursos":::
4. Seleccione **Agregar un buzón de recursos** para crear una nueva cuenta de salón. Escriba un nombre para mostrar y una dirección de correo electrónico para la cuenta, seleccione Agregar **y,** a continuación, seleccione **Cerrar.** Le recomendamos que se normaliza en una convención de nomenclatura para todas las cuentas de recursos.

> [!NOTE]
> De forma predeterminada, las cuentas de recursos se establecen con los valores siguientes. Si desea cambiarlas, seleccione **Establecer opciones de programación** antes de seleccionar **Cerrar.** Si desea cambiarlos más adelante, vaya a Salas de recursos & equipo, seleccione la cuenta de recurso y, a continuación,  >  seleccione **Editar** en Opciones de **reserva.**
>
> - Permitir la repetición de reuniones
> - Rechazar reuniones automáticamente fuera de los siguientes límites
>   - Ventana de reserva (días): 180
>   - Duración máxima (horas): 24
> - Aceptar automáticamente las solicitudes de reunión

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centro de administración de Microsoft 365: Agregar recursos":::
5. Vaya a la **sección Usuarios** del  Centro de administración y, en la lista Usuarios activos, verá el salón que acaba de crear.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centro de administración de Microsoft 365: ver usuarios activos":::
6. Seleccione el nombre del salón y se mostrará un panel de propiedades de la cuenta a la derecha.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centro de administración de Microsoft 365: Propiedades del usuario":::
7. Ahora necesita asignar una contraseña a la cuenta del recurso. En el panel, puede ver las propiedades de la cuenta y varias acciones opcionales. Seleccione el **icono de la tecla Restablecer** contraseña bajo el nombre de usuario para cambiar la contraseña. Anule la **selección de Requerir que este usuario cambie su contraseña la primera vez que inicie sesión.** No es posible cambiar la contraseña a través del proceso de inicio de sesión del dispositivo. Seleccione **Restablecer.**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centro de administración de Microsoft 365: Restablecer contraseña":::
8. En la **sección Licencias y aplicaciones,** establece **la** ubicación de selección del país o la región donde se instalará el dispositivo. Desplácese hacia abajo y active la casilla junto a la licencia que se va a asignar (por ejemplo, sala de reuniones) y, a continuación, **seleccione Guardar cambios.** La licencia puede variar en función de su organización.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centro de administración de Microsoft 365: Asignar licencia":::
