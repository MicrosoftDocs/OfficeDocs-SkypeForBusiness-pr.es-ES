---
title: Configurar una cuenta de Microsoft 365 Teams Teléfono con la cuenta de recursos Plan de llamadas
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Obtenga información sobre cómo configurar un Microsoft 365 Teams Teléfono cuenta de recursos del plan de llamadas para su uso con operadores automáticos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91eb252073a2e2421afe8a12a308a429480e4664
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766203"
---
# <a name="step-4-set-up-a-teams-phone-with-calling-plan-resource-account"></a>Paso 4: Configurar un Teams Teléfono cuenta de recursos del Plan de llamadas

Las cuentas de recursos no se asignan a ningún usuario específico. En su lugar, las cuentas de recursos, que usan una licencia de usuario virtual gratuita, se usan en dispositivos y servicios en Microsoft 365. En Microsoft Teams, a las cuentas de recursos se les asignan números de teléfono y, a continuación, se asocian con operadores automáticos y colas de llamadas.

Al asociar cuentas de recursos a operadores automáticos y colas de llamadas, puede agregarles uno o varios números de teléfono gratuitos o de pago. Por ejemplo, podría asociar una cuenta de recurso con un número de pago a un operador automático para los autores de llamadas locales. Para llamadas de larga distancia, puede asociar otra cuenta de recursos con un número gratuito al mismo operador automático.

En las secciones de este artículo se muestra cómo configurar una cuenta de recursos y, a continuación, asignarle un número de teléfono. Más adelante, asociará la cuenta de recursos con un operador automático.

## <a name="obtain-virtual-user-licenses"></a>Obtener licencias de usuario virtual

Las cuentas de recursos requieren una licencia para trabajar con operadores automáticos y colas de llamadas. Puede usar una licencia *Microsoft 365 Sistema telefónico : usuario* virtual.

> [!NOTE]
> Solo debe realizar los pasos siguientes si se ha registrado para un Teams Teléfono de prueba del plan de llamadas. Si compró Teams Teléfono licencias del Plan de llamadas, las licencias virtuales ya deberían aplicarse a su cuenta.
>
> Para ver si ya tiene licencias virtuales, inicie sesión Microsoft 365 una cuenta con permisos de administrador global. A continuación, vaya a Facturación > [Sus productos.](https://admin.microsoft.com/Adminportal/Home#/subscriptions) Si tiene licencias virtuales, aparecerán como **Microsoft 365 Sistema telefónico : Usuario virtual.**

1. Abra el Centro de administración de Microsoft 365 e inicie sesión con un usuario que sea administrador global. Normalmente, esta es la cuenta que usó para registrarse para Microsoft 365.
2. En el panel de navegación izquierdo, vaya <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">  >  a</a>Complementos de servicios de compra de facturación Ver todos los productos de  >    >  **complementos.**
3. Desplácese hasta el final para buscar la **Microsoft 365 Sistema telefónico de usuario** virtual. Seleccione **Detalles** y, a continuación, **Comprar**.
4. En la página de compra de licencia, seleccione el número de licencias de usuario virtual que desee. Necesita una licencia virtual para cada operador automático y la cola de llamadas que tiene previsto configurar. Se recomienda seleccionar al menos cinco licencias para que pueda configurar fácilmente más operadores automáticos y colas de llamadas en el futuro sin tener que comprar más licencias inmediatamente.
5. Desactive **Asignar automáticamente a todos los usuarios sin licencias.**
6. Seleccione **Des check-out now**.
7. Confirme el pedido, seleccione **Siguiente** y, a continuación, **Realizar pedido.**

> [!NOTE]
> Tenga en cuenta que aún debe  **comprar** la licencia aunque tenga un costo de cero.

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Después de recibir la licencia *Microsoft 365 Sistema telefónico usuario virtual,* puede crear su cuenta de recursos.

1. Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global. Normalmente, esta es la cuenta que usó para registrarse para Microsoft 365.
2. En el panel de navegación izquierdo, vaya a Configuración de toda la organización <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **Cuentas de recursos.**</a>
3. Seleccione **Agregar**.
4. En el **panel Agregar cuenta de recursos,** rellene Nombre para **mostrar** y, a continuación, Nombre **de usuario.** Elija un nombre para mostrar descriptivo, como "Operador automático de línea principal" para describir el propósito de la cuenta de recursos.
5. En **Tipo de cuenta de recursos,** seleccione Operador **automático.**
6. Seleccione **Guardar**.

## <a name="assign-a-license"></a>Asignar una licencia

Después de crear la cuenta de recursos, debe asignar una *Microsoft 365 Sistema telefónico:* licencia de usuario virtual *o Sistema telefónico* usuario.

1. Abra el Centro de administración de Microsoft 365 e inicie sesión con un usuario que sea administrador global. Normalmente, esta es la cuenta que usó para registrarse para Microsoft 365.
1. En el panel de navegación izquierdo, vaya a <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank"> **Usuarios**  >  **usuarios activos.**</a>
1. Seleccione su cuenta de recursos.
1. En la **pestaña Licencias y aplicaciones,** en **Licencias,** **seleccione Microsoft 365 Sistema telefónico - Usuario virtual.**
1. Seleccione **Guardar cambios y,** a continuación, **Cerrar**.

## <a name="assign-a-service-number"></a>Asignar un número de servicio

1. Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global. Normalmente, esta es la cuenta que usó para registrarse para Microsoft 365.
1. En el panel de navegación izquierdo, vaya a Configuración de toda la organización <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">   >  **Cuentas de recursos.**</a>
1. Seleccione la cuenta de recursos que acaba de crear y, a continuación, haga clic **en Asignar o desasignación.**
1. En la **lista Teléfono de tipo de número,** elija En **línea.**
1. En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.** Asegúrese de incluir el código de país (por ejemplo, **+1** 250 555 0012)
1. Haga clic en **Guardar**.

> [!div class="nextstepaction"]
> [Paso siguiente: Asignar números de teléfono a los usuarios](set-up-assign-numbers.md)
