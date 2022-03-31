---
title: Configurar una cuenta de Teléfono Microsoft Teams del sistema
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
description: Obtenga información sobre cómo configurar una cuenta de recursos Teléfono Microsoft Teams sistema para su uso con operadores automáticos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7764d6b7f7d09cd2c5065ab24e73cb0fdec9c5c6
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556551"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>Paso 4: Configurar una cuenta de Teams Sistema telefónico de recursos

Las cuentas de recursos no se asignan a ningún usuario específico. En su lugar, las cuentas de recursos, que usan una licencia de usuario virtual gratuita, son usadas por dispositivos y servicios en Microsoft 365. En Microsoft Teams, a las cuentas de recursos se les asignan números de teléfono y, a continuación, se asocian con operadores automáticos y colas de llamadas.

Al asociar cuentas de recursos a operadores automáticos y colas de llamadas, puede agregarles uno o varios números de teléfono gratuitos o de pago. Por ejemplo, podría asociar una cuenta de recurso con un número de pago a un operador automático para los autores de llamadas locales. Para llamadas de larga distancia, puede asociar otra cuenta de recursos con un número gratuito al mismo operador automático.

En las secciones de este artículo se muestra cómo configurar una cuenta de recursos y, a continuación, asignarle un número de teléfono. Más adelante, asociará la cuenta de recursos con un operador automático.

## <a name="obtain-virtual-user-licenses"></a>Obtener licencias de usuario virtual

Las cuentas de recursos requieren una licencia para trabajar con operadores automáticos y colas de llamadas. Puede usar una licencia *gratuita Teléfono Microsoft Teams estándar : usuario* virtual.

> [!NOTE]
> Solo debe realizar los pasos siguientes si se ha registrado para un período de prueba Teams Teléfono licencia del paquete Plan de llamadas. Si compró Teams Teléfono licencias de paquetes del Plan de llamadas, las licencias virtuales ya deberían aplicarse a su cuenta.
>
> Para ver si ya tiene licencias virtuales, inicie sesión Microsoft 365 una cuenta con permisos de administrador global. A continuación, vaya a Facturación > [Sus productos](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Si tiene licencias virtuales, aparecerán como **Teléfono Microsoft Teams estándar: usuario virtual**.

1. Abra el Centro de administración de Microsoft 365 e inicie sesión con un usuario que sea administrador global. Normalmente, esta es la cuenta que usó para registrarse para Microsoft 365.
2. En el panel de navegación izquierdo, vaya a <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-onsVer** >  >  **todos los productos de complementos**.
3. Desplácese hasta el final para buscar la **Teléfono Microsoft Teams estándar: licencia de usuario** virtual. Seleccione **Detalles** y, a continuación **, Comprar**.
4. En la página de compra de licencia, seleccione el número de licencias de usuario virtual que desee. Necesita una licencia virtual para cada operador automático y la cola de llamadas que tiene previsto configurar. Se recomienda seleccionar al menos cinco licencias para que pueda configurar fácilmente más operadores automáticos y colas de llamadas en el futuro sin tener que comprar más licencias inmediatamente.
5. Desactive **Asignar automáticamente a todos los usuarios sin licencias**.
6. Seleccione **Comprobar ahora**.
7. Confirme el pedido, seleccione **Siguiente** y, a continuación, **Realizar pedido**.

> [!NOTE]
> Tenga en cuenta que aún debe  **comprar** la licencia aunque tenga un costo de cero.

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

Una vez que haya recibido su *Teléfono Microsoft Teams estándar: licencia* de usuario virtual, puede crear su cuenta de recursos.

1. Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).
2. En el panel de navegación izquierdo, vaya a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Cuentas de VoiceResource** > </a>.
3. Seleccione **Agregar**.
4. En el **panel Agregar cuenta de recursos** , rellene **Nombre para mostrar** y, a continuación, **Nombre de usuario**. Elija un nombre para mostrar descriptivo, como "Operador automático de línea principal" para describir el propósito de la cuenta de recursos.
5. En **Tipo de cuenta de recursos**, seleccione **Operador automático**.
6. Seleccione **Guardar**.

## <a name="assign-a-license"></a>Asignar una licencia

Después de crear la cuenta de recursos, debe asignar una licencia estándar Teléfono Microsoft Teams *de usuario virtual* o Teams Teléfono *licencia estándar*.

1. Abra el Centro de administración de Microsoft 365 e inicie sesión con un usuario que sea administrador global. Normalmente, esta es la cuenta que usó para registrarse para Microsoft 365.
1. En el panel de navegación izquierdo, vaya a <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**UsuariosActivos** > </a>.
1. Seleccione su cuenta de recursos.
1. En la **pestaña Licencias y aplicaciones**, en **Licencias, seleccione** **Teléfono Microsoft Teams Estándar: usuario virtual**.
1. Seleccione **Guardar cambios y** , a continuación **, Cerrar**.

## <a name="assign-a-service-number"></a>Asignar un número de servicio

![Captura de pantalla de la interfaz de usuario asignar número de servicio.](../media/resource-account-assign-phone-number.png)

1. Abra el Microsoft Teams de administración e inicie sesión con un usuario que sea administrador global (normalmente es la cuenta que usó para registrarse para Microsoft 365).
1. En el panel de navegación izquierdo, vaya a <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Cuentas de VoiceResource** > </a>.
1. Seleccione la cuenta de recursos que acaba de crear y, a continuación, haga clic **en Asignar o desasignación**.
1. En la **lista Teléfono de tipo de número**, elija **En línea**.
1. En el **cuadro Número de teléfono asignado** , busque el número que desea usar y haga clic en **Agregar**. Asegúrese de incluir el código de país (por ejemplo, **+1** 250 555 0012).
1. Haga clic en **Guardar**.

> [!div class="nextstepaction"]
> [Paso siguiente: Asignar números de teléfono a los usuarios](set-up-assign-numbers.md)
