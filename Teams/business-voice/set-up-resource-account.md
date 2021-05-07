---
title: Configurar una cuenta de Microsoft 365 Business Voice de recursos
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Obtenga información sobre cómo configurar una cuenta de Microsoft 365 Business Voice para su uso con operadores automáticos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130441"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>Paso 4: Configurar una cuenta de recursos de Business Voice

En Microsoft Teams, se requiere una cuenta de recursos para cada operador automático o cola de llamadas. Las cuentas de recursos también pueden tener asignados números de teléfono de servicio. Así se asignan números de teléfono a operadores automáticos y colas de llamadas, lo que permite que los autores de llamadas de fuera de Teams lleguen al operador automático o a la cola de llamadas.

## <a name="obtain-virtual-user-licenses"></a>Obtener licencias de usuario virtual

Las cuentas de recursos requieren una licencia para trabajar con operadores automáticos y colas de llamadas. Puede usar una licencia *Microsoft 365 Sistema telefónico : usuario* virtual.

1. Inicie sesión en el Centro de administración de Microsoft 365.
2. Ir a **Complementos de servicios** de compra de  >    >  **facturación** Ver todos los productos de  >  **complementos**
3. Desplácese hasta el final para buscar la **Microsoft 365 Sistema telefónico de usuario** virtual. Seleccione **Detalles** y, a continuación, **Comprar**.
4. En la página de compra de licencia, seleccione el número de licencias de usuario virtual que desee. Necesita una licencia virtual para cada operador automático y la cola de llamadas que tiene previsto configurar. Se recomienda seleccionar al menos cinco licencias para que pueda configurar fácilmente más operadores automáticos y colas de llamadas en el futuro sin tener que comprar más licencias inmediatamente.
5. Desactive **Asignar automáticamente a todos los usuarios sin licencias.**
6. Seleccione **Des check-out now**.
7. Confirme el pedido, seleccione **Siguiente** y, a continuación, **Realizar pedido.**

> [!NOTE]
> Tenga en cuenta que aún debe  **comprar** la licencia aunque tenga un costo de cero.

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Después de recibir la licencia *Microsoft 365 Sistema telefónico usuario virtual,* puede crear su cuenta de recursos.

![Captura de pantalla de la interfaz de usuario agregar cuenta de recursos](../media/resource-account-add.png)

1. En el Teams de administración, expanda **Configuración de** toda la organización y, a continuación, haga clic en Cuentas **de recursos.**
2. Seleccione **Agregar**.
3. En el **panel Agregar cuenta de recursos,** rellene Nombre para **mostrar** y, a continuación, Nombre **de usuario.** Elija un nombre para mostrar descriptivo, como "Operador automático de línea principal" para describir el propósito de la cuenta de recursos.
4. En **Tipo de cuenta de recursos,** seleccione Operador **automático.**
5. Seleccione **Guardar**.

![Captura de pantalla de una lista de cuentas de recursos](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a>Asignar una licencia

Después de crear la cuenta de recursos, debe asignar una *Microsoft 365 Sistema telefónico:* licencia de usuario virtual *o Sistema telefónico* usuario.

![Captura de pantalla de la interfaz de usuario asignar licencias en el Microsoft 365 de administración](../media/resource-account-assign-virtual-user-license.png)

1. En el Microsoft 365 de administración, vaya a **Usuarios**  >  **usuarios activos.**
2. Seleccione su cuenta de recursos.
1. En la **pestaña Licencias y aplicaciones,** en **Licencias,** **seleccione Microsoft 365 Sistema telefónico - Usuario virtual.**
1. Seleccione **Guardar cambios y,** a continuación, **Cerrar**.

## <a name="assign-a-service-number"></a>Asignar un número de servicio

![Captura de pantalla de la interfaz de usuario asignar número de servicio](../media/resource-account-assign-phone-number.png)

1. En el Teams de administración, vaya a Configuración **de toda** la organización y, a continuación, Cuentas **de recursos.** 
1. Seleccione la cuenta de recursos que acaba de crear y, a continuación, haga clic **en Asignar o desasignación.**
1. En la **lista Teléfono de tipo de número,** elija En **línea.**
1. En el **cuadro Número de teléfono** asignado, busque el número que desea usar y haga clic en **Agregar.** Asegúrese de incluir el código de país (por ejemplo, **+1** 250 555 0012)
1. Haga clic en **Guardar**.
    > [!NOTE]
    > No es necesario seleccionar un operador  automático en Asignar a porque el operador automático al que desea agregar el número ya está seleccionado.

> [!div class="nextstepaction"]
> [Paso siguiente: Asignar números de teléfono a los usuarios](set-up-assign-numbers.md)