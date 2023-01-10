---
title: Retirar Microsoft Teams gratuito (clásico) de su organización
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
robots: noindex
description: Obtenga información sobre cómo quitar las licencias gratuitas (clásicas) de Teams y asignar licencias de pago de Teams a los usuarios de su organización.
ms.openlocfilehash: 027f84577a50d445eb01bce896417f23e503abb7
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749164"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>Retirar Microsoft Teams gratuito (clásico) de su organización

A mediados de abril de 2023, Microsoft retirará la licencia **de Microsoft Teams gratuito (clásico)**.

Este artículo proporciona instrucciones a los administradores de TI sobre cómo retirar las licencias **de Microsoft Teams gratuito (clásico)** de su organización y pasar a licencias de Teams de pago.

Si no mueve las licencias gratuitas de Teams de los usuarios a licencias de Teams pagadas antes de mediados de abril de 2023, los usuarios perderán el acceso a Teams.

Para completar este proceso, puede elegir uno de estos dos métodos:

- [Use el Centro de administración de Microsoft 365.](#use-microsoft-365-admin-center-to-replace-licenses)
- [Use Microsoft PowerShell.](#use-microsoft-powershell-to-replace-licenses)

Si su organización decide no migrar a una licencia de Teams de pago, puede exportar el contenido de su organización desde Teams. Para obtener instrucciones sobre cómo exportar contenido de Teams, consulte [Exportar contenido con las API de exportación de Microsoft Teams](/microsoftteams/export-teams-content).

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>Usar Centro de administración de Microsoft 365 para reemplazar licencias

Si su organización tiene pocos usuarios asignados a la licencia **de Teams gratuito (clásico**), le recomendamos que use la Centro de administración de Microsoft 365 para quitar y asignar licencias.

### <a name="check-users-current-teams-licensing"></a>Comprobar las licencias actuales de Teams de los usuarios

1. Inicia sesión en la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
1. En el menú de la izquierda, vaya a **Usuarios** > y seleccione [**Usuarios activos**](https://go.microsoft.com/fwlink/p/?linkid=834822) para ver las licencias asignadas a los usuarios.
    1. La columna **Licencia** mostrará **Microsoft Teams gratuito (clásico)** junto a los usuarios asignados a esa licencia.
1. En el menú de la izquierda, vaya a **Facturación** > y seleccione [**Licencias**](https://go.microsoft.com/fwlink/p/?linkid=842264) para ver si tiene licencias de Teams pagadas disponibles.
    1. Si su organización tiene licencias disponibles, vaya directamente a [Asignar licencias de Teams de pago](#assign-paid-teams-licenses) para asignar esas licencias a los usuarios con licencias **gratuitas (clásicas) de Teams** .
1. Determine el número de licencias de Teams pagadas que necesita comprar, si las hay.

### <a name="purchase-paid-teams-licenses"></a>Comprar licencias de Teams de pago

1. En la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), ve a **> de facturación** y selecciona **Servicios de compra**.
1. Seleccione **Ver productos** para ver todas las licencias disponibles.
1. Seleccione el filtro de categoría **Comunicación y colaboración** para ver las licencias de Teams.
1. Elija la licencia de teams de pago que quiere reemplazar a **Teams gratuito (clásico).**
    1. Le recomendamos la licencia de [**Teams Essentials**](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF), que está disponible para un máximo de 300 puestos.
    1. Si necesitas más de 300 puestos, te recomendamos comprar [licencias de Microsoft 365 E1](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA).
1. Escriba el número de licencias que desea comprar y, a continuación, elija una frecuencia de facturación.
1. Selecciona el botón **Comprar** para completar el proceso de compra.

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>Comprar licencias en el Centro de administración de Marketplace

Algunos inquilinos tienen acceso a Centro de administración de Microsoft 365 Marketplace. Para estos inquilinos, comprará licencias en Marketplace.

1. En la [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), selecciona **Marketplace** en el menú de la izquierda.
1. Seleccione la pestaña **Todos los productos** .
1. Seleccione el filtro de categoría **Comunicación y colaboración** para ver las licencias de Teams.
1. Elija la licencia de teams de pago que quiere reemplazar a **Teams gratuito (clásico).**
1. Escriba el número de licencias que desea comprar y, a continuación, elija una frecuencia de facturación.
1. Selecciona el botón **Comprar** para completar el proceso de compra.

### <a name="assign-paid-teams-licenses"></a>Asignar licencias de Teams pagadas

1. Cuando esté listo para reemplazar las licencias **gratuitas (clásicas) de Teams**, en la Centro de administración de Microsoft 365, vaya a **Usuarios** > [**activos**](https://admin.microsoft.com/adminportal/home#/users).
1. Seleccione todos los usuarios con la licencia **gratuita (clásica) de Teams** que se muestra en la columna **Licencias** .
1. En la parte superior del centro de administración, seleccione la opción **Administrar licencias de producto** .
1. En el panel derecho, seleccione **Reemplazar**.
    1. Al seleccionar la opción **Reemplazar** es necesario volver a seleccionar todas las licencias que desea que se asignen a esos usuarios. Si solo selecciona la nueva licencia de Pago de Teams, las demás licencias asignadas a esos usuarios se quitarán de los usuarios y se reemplazarán por la licencia de Teams.
    1. Si los usuarios tienen distintas necesidades de licencias, complete este proceso en lotes para evitar que los usuarios tengan licencias incorrectas.
1. En el panel de viaje lateral, elija la nueva licencia de pago de Teams y cualquier otra licencia que deban asignar los usuarios y, a continuación, seleccione el botón **Guardar cambios** .

## <a name="use-microsoft-powershell-to-replace-licenses"></a>Usar Microsoft PowerShell para reemplazar licencias

Si su organización tiene un gran número de usuarios asignados a la licencia **gratuita (clásica) de Teams** , le recomendamos que use PowerShell para anular la asignación en masa y asignar licencias a los usuarios.

Antes de completar este proceso, necesitará licencias de Teams de pago para los usuarios que tengan asignada la licencia **de Teams gratuito (clásico** ). Para comprar licencias para esos usuarios, consulte [Comprar licencias de Teams de pago](#purchase-paid-teams-licenses).

1. Conecte su inquilino de Microsoft 365 al [SDK de Microsoft Graph PowerShell](/powershell/microsoftgraph/get-started).
1. Abra la aplicación de escritorio de Microsoft PowerShell.
1. [Establecer permisos de usuario y de organización para Graph API](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk).
1. [Quite las licencias **gratuitas (clásicas) de Teams** de las cuentas de usuarios](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts).
1. [Asigne licencias de Teams de pago a los usuarios](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts).

Para obtener más información sobre el proceso del SDK de PowerShell de Graph, consulte [Usar el SDK de Microsoft Graph PowerShell](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell).
