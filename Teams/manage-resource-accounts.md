---
title: Administrar cuentas de recursos en Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Administración de cuentas de recursos en Microsoft Teams
ms.openlocfilehash: 685361c829a20a216e240e9f502e6ab24dcb86c5
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120943"
---
# <a name="manage-resource-accounts-in-teams"></a>Administrar cuentas de recursos en los equipos 

Una cuenta de recursos es también conocida como un objeto de usuario deshabilitado en Azure Active Directory y puede usarse para representar los recursos en general. En Exchange pueden usarse para representar salas de conferencias, por ejemplo y permitir que tengan un número de teléfono. Una cuenta de recursos puede estar alojada en Microsoft 365 o local mediante Skype para Business server, y estas cuentas se crean utilizando los comandos de Powershell.

En Microsoft Teams os Skype para profesionales en línea, cada llamada de cola o auto attendant se requiere para tienen una cuenta de recurso asociado. Si una cuenta de recursos necesita un número de teléfono asignado se dependen el uso intencionado de la cola de llamada asociada o el operador automático. Hacer referencia a los artículos en las colas de llamadas y automáticos vinculado en la parte inferior de este artículo antes de asignar a un número de teléfono a una cuenta de recurso.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Requisitos previos para asignar a un número de teléfono a una cuenta de recurso

Para empezar a es importante recordar algunas cosas:
  
- Su organización debe tener (como mínimo) una licencia Enterprise E3 plus **Sistema telefónico** o una licencia Enterprise E5. El número de licencias de usuario de **Sistema telefónico** que se asignan afecta al número de números de servicio que están disponibles para ser usadas para las cuentas de recursos asignadas a las colas u operadores automáticos de llamadas. El número de cuentas de recursos que puede hacer que depende el número de licencias de **Sistema telefónico** y **Conferencias de Audio** que se asignan en la organización. Para obtener más información acerca de las licencias, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365. Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Para obtener más información acerca de planes de llamada de Office 365, vea [Llamar a planes de Office 365](calling-plans-for-office-365.md).
- Sólo se pueden asignar números de pago y los números de teléfono gratuito de servicio que se obtuvo en el **Centro de administración de equipos de Microsoft** o se transfiere desde otro proveedor de servicios a una cuenta de recurso. Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.

> [!NOTE]
> Los números de teléfono del usuario (suscriptor) no se pueden asignar a una cuenta de recurso. Se pueden usar solo números de pago de servicio o números de teléfono gratuito.

Para asignar un número de teléfono a una cuenta de recurso, necesitará obtener o transferir su pago existente o un servicio gratuito números. Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el **Centro de administración de equipos de Microsoft** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**. Para obtener sus números de servicio, vea [los números de teléfono del servicio de introducción](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) o si desea transferir y el número de servicio existente, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio. Vaya a [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.

## <a name="create-a-resource-account-in-powershell"></a>Crear una cuenta de recursos en Powershell

 Debe crear una cuenta de recurso ejecutando el cmdlet de Powershell apropiado según sea necesario (para una o más cuentas de recursos) y asigne un nombre a cada uno de ellos y así sucesivamente. Actualmente no hay ninguna opción para crear una cuenta de recursos en el centro de administración de Microsoft Teams, pero puede editar los números de teléfono y cambiar la llamada cola o auto attendant asignaciones para una cuenta de recurso.

Dependiendo de si su número de teléfono se encuentra en línea o local, sería necesario para conectarse a la adecuada símbolo del sistema Powershell con privilegios de administrador.

- Las implementaciones de híbrido (números de números hospedados en el enrutamiento directo, OPCH y CCE) se utilizará [CsHybridApplicationEndpoint de nuevo](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para crear una cuenta de recurso que se hospeda en local.  
- En línea sólo las implementaciones utilizarán [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para una cuenta de recurso que se hospeda en línea.

El siguiente es un ejemplo de un entorno en línea de la creación de una cuenta de recursos:

``` Powershell
New-CsOnlineApplicationInstance -DisplayName Node1 -SipAddress sip:node1@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
```

Para obtener más información acerca de este comando, vea [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .

> [!NOTE]
> Es más fácil de establecer el número de teléfono con el centro de administración de Microsoft Teams, tal como se describe en la siguiente sección. También puede usar el `Set-CsOnlineApplicationInstance` de comando a un asignar un número de teléfono a la cuenta del recurso después de su creación inicial tal como se muestra:

``` Powershell
Set-CsOnlineApplicationInstance -Identity "CN={4f6c99fe-7999-4088-ac4d-e88e0b3d3820},OU=Redmond,DC=litwareinc,DC=com" -DisplayName Node1 -LineURI tel:+14255550100
```

Para obtener más información acerca de este comando, vea [Set-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlineapplicationinstance?view=skype-ps) .

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams

Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización**  > **las cuentas de recursos**, seleccione la cuenta de recursos que necesita para cambiar la configuración para y, a continuación, haga clic en el botón **Editar** . en la pantalla **Editar la cuenta del recurso** , podrá cambiar el:

- **Nombre para mostrar** para la cuenta
- Cola de llamadas u operadores automáticos que usa la cuenta
- Número de teléfono asignado a la cuenta

Cuando haya terminado, haga clic en **Guardar**.

## <a name="related-information"></a>Información relacionada

Para las implementaciones que son híbrida con Skype para Business Server:

[Planeación de operador automático de la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar operadores automáticos en la nube](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para las implementaciones en los equipos o Skype para empresarial en línea:

[¿Qué son los operadores automáticos del Sistema telefónico?](what-are-phone-system-auto-attendants.md)

[Configurar un operador automático de Sistema telefónico](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Ejemplo de pequeña empresa - configurar un operador automático](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Crear una cola de llamadas de Sistema telefónico](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nueva CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nueva CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
