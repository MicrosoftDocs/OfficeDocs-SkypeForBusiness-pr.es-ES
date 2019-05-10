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
ms.openlocfilehash: dea4a154e25c719ddabc572ba26ddb7d25c43d71
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835421"
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
> Números de servicio de enrutamiento directo para colas de operador y llamada automático es compatible con los usuarios de Microsoft Teams y sólo los agentes.

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

En el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización** > **las cuentas de recursos**. 

![ASD](media/r-a-master.png)

![número 1](media/sfbcallout1.png)

Para crear un nuevo recurso cuenta haga clic en **+ nueva cuenta**. En el menú emergente, rellene el nombre para mostrar y nombre de usuario para la cuenta del recurso (el nombre de dominio debe rellenar automáticamente), a continuación, haga clic en **Guardar**.

![cuenta de recurso](media/res-acct.png)

A continuación, deberá aplicar una licencia a la cuenta del recurso, tal como se describe en [asignar licencias a los usuarios de Office 365 para profesionales](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)

![número 3](media/sfbcallout3.png) una vez que se ha creado la cuenta del recurso y asigna la licencia, puede hacer clic en **Asignar o Cancelar asignación** para asignar un número de servicio de planeación de la llamada a la cuenta del recurso, o asignar la cuenta de recurso a una cola de llamada o de operador automático que ya existe. Asignación de un número de enrutamiento directo puede realizarse con sólo los Cmdlets. Si la cola de llamadas u operador automático aún debe crearse, puede vincular la cuenta del recurso al crearlo. Cuando haya terminado, haga clic en **Guardar** .

![asignar la cuenta de recurso](media/r-a-assign.png)

![número 2](media/sfbcallout2.png) puede editar el nombre para mostrar recursos cuenta con la opción de **Editar** .  Cuando haya terminado, haga clic en **Guardar** .
![editar la cuenta de recurso](media/r-a-edit.png)

## <a name="create-a-resource-account-in-powershell"></a>Crear una cuenta de recursos en Powershell

Planes de llamada de Microsoft, puede asignar sólo números de pago y los números de teléfono de un servicio gratuito que obtuvo en el **Centro de administración de equipos de Microsoft** o trasladado desde otro proveedor de servicios a una cuenta de recursos. Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.

Dependiendo de si la cuenta del recurso se encuentra en línea o local, sería necesario para conectarse a la adecuada símbolo del sistema Powershell con privilegios de administrador. 
- El siguiente Powershell cmdlet ejemplos suponen que la cuenta del recurso está hospeda en línea utilizando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para crear una cuenta de recurso que se hospeda en línea.

- Para recursos cuentas alojarse en local en Skype para 2019 de Business Server que se pueden usar con colas de llamadas en la nube y en la nube operadores automáticos, consulte [Configurar colas de llamadas en la nube](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) o [Configurar operadores automáticos de la nube](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md). Las implementaciones de híbrido (números hospedados en el enrutamiento directo) se utilizará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).

La aplicación de ID que necesita utilizarlo durante la creación de la aplicación de instancias son:
- **Operadores automáticos:** ce933385-9390-45d1-9512-c8d228074e07
- **Cola de llamadas:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Si desea que la cola de llamadas u operador para que pueda buscarse por usuarios locales automático, debe crear los recursos cuentas locales, ya que las cuentas de recursos en línea no están sincronizadas hacia abajo a Active Directory.

1. Para crear una cuenta de recursos en línea para usar con el uso auto attendant, el siguiente comando.  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. No podrá usar la cuenta del recurso hasta que se aplican una licencia a ella. Cómo aplicar una licencia a una cuenta en el centro de administración de Office 365, vea [asignar licencias a los usuarios de Office 365 para la empresa](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , así como [Asignar Skype para licencias de negocio](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. (Opcional) Una vez que la licencia correcta se aplica a la cuenta del recurso puede establecer un número de teléfono a la cuenta del recurso, tal y como se muestra a continuación. No todas las cuentas de recursos requerirá un número de teléfono. Si no aplicó una licencia para la cuenta del recurso, se producirá un error en la asignación de números de teléfono.

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Para obtener más información acerca de este comando, vea [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

> [!NOTE]
> Es más fácil de establecer el número de teléfono en línea mediante el centro de administración de Microsoft Teams, tal y como se ha descrito anteriormente.

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams

Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización**  > **las cuentas de recursos**, seleccione la cuenta de recursos que necesita para cambiar la configuración para y, a continuación, haga clic en el botón **Editar** . en la pantalla **Editar la cuenta del recurso** , podrá cambiar esta configuración:

- **Nombre para mostrar** para la cuenta
- Cola de llamadas u operadores automáticos que usa la cuenta
- Número de teléfono asignado a la cuenta

Cuando haya terminado, haga clic en **Guardar**.

## <a name="delete-a-resource-account"></a>Eliminar una cuenta de recurso

Asegúrese de que disociar el número de teléfono de la cuenta del recurso antes de eliminarlo, para evitar la introducción de su número de servicio se bloquee en pendiente de modo. Puede hacerlo mediante el commandlet siguiente: 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```
                
Una vez que lo, puede eliminar la cuenta del recurso desde el portal de administración de Office 365, en la ficha de los usuarios.


## <a name="related-information"></a>Información relacionada

Para las implementaciones que son híbrida con Skype para Business Server:

[Planear los operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar los operadores automáticos en la nube](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para las implementaciones en los equipos o Skype para empresarial en línea:

[¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)

[Configurar un operador automático en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Ejemplo de pequeña empresa: configurar un operador automático](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Crear una cola de llamadas en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nueva CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nueva CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
