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
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Obtenga información acerca de cómo administrar las cuentas de recursos en Microsoft Teams
ms.openlocfilehash: e8d3da4938a5040972b3c4853434808ca7457c90
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914597"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Administrar cuentas de recursos en Microsoft Teams

Una cuenta de recursos es también conocida como un objeto de usuario deshabilitado en Azure Active Directory y puede usarse para representar los recursos en general. En Exchange pueden usarse para representar salas de conferencias, por ejemplo y permitir que tengan un número de teléfono. Una cuenta de recursos puede estar alojada en Microsoft 365 o local mediante Skype para Business server, y estas cuentas se crean utilizando los comandos de Powershell.

En Microsoft Teams o Skype para profesionales en línea, cada llamada de cola o auto attendant se requiere para tienen una cuenta de recurso asociado. Si una cuenta de recursos necesita un número de teléfono asignado se dependen el uso intencionado de la cola de llamada asociada o el operador automático. Hacer referencia a los artículos en las colas de llamadas y automáticos vinculado en la parte inferior de este artículo antes de asignar a un número de teléfono a una cuenta de recurso.

> [!NOTE]
> En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Requisitos previos para asignar a un número de teléfono a una cuenta de recurso

Para empezar a es importante recordar algunas cosas:
  
- Una cola de llamada o de operador automático es necesario tener una cuenta de recurso asociado. Para obtener información detallada sobre las cuentas de recursos, vea [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) .
- Si tiene previsto asignar un número de enrutamiento directa, debe adquirir y asignar las siguientes licencias para las cuentas de recursos \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico\).
- Si se asigna un número de servicio de Microsoft en su lugar, debe adquirir y asignar las licencias siguientes a la cuenta del recurso \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico y un Plan de llamar a\).
- Sólo debe obtener licencia para las cuentas de recursos con un número de teléfono que se les haya asignado. En una cola de llamada o de operador automático anidados, no es necesario para el resto de los operadores automáticos de licencia o colas de llamadas si no tienen números de teléfono asociados con ellos

> [!NOTE] 
> Operador automático de los números de servicio de enrutamiento directos para y colas de llamadas se admite para los agentes y los usuarios de Microsoft Teams sólo en el momento.

> [!NOTE] 
> Microsoft está trabajando en un modelo de licencias adecuado para aplicaciones como automáticos en la nube y las colas de llamadas, para ahora tiene que usar el modelo de licencias de usuario.
    
> [!NOTE]
> Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365. Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Puede asignar a un número de híbrido de enrutamiento directa a la cuenta del recurso.  Para obtener información detallada, vea [Planear el enrutamiento directo](direct-routing-plan.md) .
- Planes de llamada de Microsoft, puede asignar sólo números de pago y los números de teléfono de un servicio gratuito que obtuvo en el **Centro de administración de equipos de Microsoft** o trasladado desde otro proveedor de servicios a una cuenta de recursos. Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.

> [!NOTE]
> Los números de teléfono del usuario (suscriptor) no se pueden asignar a una cuenta de recurso. Se pueden usar solo números de pago de servicio o números de teléfono gratuito.

Para asignar un número de teléfono a una cuenta de recurso, necesitará obtener o su teléfono de pago existente o un servicio gratuito de puerto números. Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el **Centro de administración de equipos de Microsoft** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**. Para obtener sus números de servicio, vea [los números de teléfono del servicio de obtención](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) o si desea transferir un número de servicio existente, vea [los números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio. Vaya a [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Crear una cuenta de recursos en el centro de administración de Microsoft Teams

Para crear una cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización** > **las cuentas de recursos**, a continuación, haga clic en **+ Agregar**. En el menú emergente, rellene el nombre para mostrar y nombre de usuario para la cuenta del recurso (el nombre de dominio debe rellenar automáticamente), a continuación, haga clic en **Guardar**.

![cuenta de recurso](media/res-acct.png)

También necesitará aplicar una licencia a la cuenta del recurso, tal como se describe en [asignar licencias a los usuarios de Office 365 para profesionales](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)

Una vez que haya creado la cuenta del recurso y asignado la licencia, puede hacer clic en **Asignar o Cancelar asignación** para asignar a un número de teléfono a la cuenta del recurso, o para asignar la cuenta de recurso a una cola de llamada o de operador automático.

## <a name="create-a-resource-account-in-powershell"></a>Crear una cuenta de recursos en Powershell

Planes de llamada de Microsoft, puede asignar sólo números de pago y los números de teléfono de un servicio gratuito que obtuvo en el **Centro de administración de equipos de Microsoft** o trasladado desde otro proveedor de servicios a una cuenta de recursos. Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.

Dependiendo de si su número de teléfono se encuentra en línea o local, sería necesario para conectarse a la adecuada símbolo del sistema Powershell con privilegios de administrador.


- Las implementaciones de híbrido (números hospedados en el enrutamiento directo) se utilizará [CsHybridApplicationEndpoint de nuevo](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para crear una cuenta de recurso que se hospeda en local.  
- En línea sólo las implementaciones utilizarán [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para una cuenta de recurso que se hospeda en línea.

El siguiente es un ejemplo de un entorno en línea de creación de cuenta de recurso con un operador automático de ApplicationID. Para una cola de llamadas, puede usar el siguiente ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

Para obtener más información acerca de este comando, vea [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .

> [!NOTE]
> Es más fácil de establecer el número de teléfono en línea mediante el centro de administración de Microsoft Teams, tal como se describe en la siguiente sección. También puede usar el `Set-CsOnlineVoiceApplicationInstance` de comando a un asignar un número de teléfono a la cuenta del recurso después de su creación inicial tal como se muestra:

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Si no se aplican una licencia durante la creación de la cuenta del recurso se producirá un error en la asignación de números de teléfono. 

Para obtener más información acerca de este comando, vea [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams

Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización**  > **las cuentas de recursos**, seleccione la cuenta de recursos que necesita para cambiar la configuración para y, a continuación, haga clic en el botón **Editar** . en la pantalla **Editar la cuenta del recurso** , podrá cambiar el:

- **Nombre para mostrar** para la cuenta
- Cola de llamadas u operadores automáticos que usa la cuenta
- Número de teléfono asignado a la cuenta

Cuando haya terminado, haga clic en **Guardar**.

## <a name="related-information"></a>Información relacionada

Para las implementaciones que son híbrida con Skype para Business Server:

[Planear los operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar los operadores automáticos en la nube](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para las implementaciones en los equipos o Skype para empresarial en línea:

[¿Cuáles son los operadores automáticos de la nube?](what-are-phone-system-auto-attendants.md)

[Configurar un operador automático de la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Ejemplo de pequeña empresa: configurar un operador automático](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Crear una cola de llamada de nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nueva CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nueva CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
