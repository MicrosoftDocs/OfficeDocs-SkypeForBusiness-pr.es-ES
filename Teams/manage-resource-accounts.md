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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Más información sobre la administración de cuentas de recursos en Microsoft Teams
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394503"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Administrar cuentas de recursos en Microsoft Teams

Una cuenta de recursos también se conoce como un objeto de usuario deshabilitado en Azure Active Directory y se puede usar para representar recursos en general. En Exchange podría usarse para representar salas de conferencias, por ejemplo, y permitirles que tengan un número de teléfono. Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.

En Microsoft Teams o Skype empresarial online, cada cola de llamadas o operador automático debe tener una cuenta de recursos asociada. Si una cuenta de recursos necesita un número de teléfono asignado, dependerá del uso previsto de la cola de llamadas asociada o del operador automático. Consulte los artículos sobre las colas de llamadas y los operadores automáticos vinculados al final de este artículo antes de asignar un número de teléfono a una cuenta de recursos.

> [!NOTE]
> Este artículo se aplica a Microsoft Teams y a Skype empresarial online. Para cuentas de recursos alojados en Skype empresarial Server 2019, consulte [configurar cuentas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="overview"></a>Información general

Si el servicio del sistema telefónico necesita un número de servicio, las diversas dependencias se pueden cumplir en la siguiente secuencia:

1. Obtener un número de servicio
2. Comprar una licencia de sistema telefónico (Office 365 Enterprise E1 o E3 con el sistema telefónico agregado u Office 365 Enterprise E5 que incluye el sistema telefónico)
3. Crear la cuenta de recursos. Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas.
4. Asigne la licencia de sistema telefónico a la cuenta de recursos.
5. Asigne un número de teléfono a la cuenta de recursos.
6. Crear un servicio de sistema de teléfono (una cola de llamadas o un operador automático)
7. Asociar la cuenta de recursos con un servicio: (New-CsApplicationInstanceAssociation)

Si el operador automático o la cola de llamadas están anidados bajo un operador automático de nivel superior, la cuenta de recursos asociada solo necesita un número de teléfono si desea tener varios puntos de entrada en la estructura de las colas de llamadas y los operadores automáticos.

Para redirigir las llamadas a las personas de su organización que estén conectadas en línea, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365. Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si el servicio del sistema telefónico que está creando va a estar anidado y no necesitará un número de teléfono, el proceso es el siguiente:

1. Crear la cuenta de recursos  
2. Crear un servicio de sistema de teléfono
3. Asociar la cuenta de recursos con un servicio de sistema de teléfono

### <a name="create-a-resource-account-with-a-phone-number"></a>Crear una cuenta de recursos con un número de teléfono

Para crear una cuenta de recursos que use un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:

1. Puerto o recibe un número de servicio de pago o gratuito. El número no se puede asignar a ningún otro servicio de voz o cuenta de recursos.

   Antes de asignar un número de teléfono a una cuenta de recursos, tendrá que obtener o migrar los números de teléfono de pago o gratuitos existentes. Una vez que obtenga los números de teléfono de pago o gratuitos, aparecerán en los**** > **números de teléfono**del **Centro** > de administración de Microsoft Teams, y el **tipo de número** que aparece en la lista aparecerá como **servicio-** gratuito. Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md).

2. Compre una licencia de sistema telefónico. Verá  
   - [Office 365 Enterprise E1 y E3](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 Enterprise E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [Software Office 365 Enterprise E5 para empresas](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Crear una cuenta de recursos nueva. Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)
4. Asigne la licencia de sistema telefónico a la cuenta de recursos. Consulte [asignar licencias de Microsoft Teams](assign-teams-licenses.md) y [asignar licencias a un usuario](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).
5. Asignar el número de servicio a la cuenta de recursos. Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).
6. Configure una de las opciones siguientes:
   - [Operador automático de la nube](create-a-phone-system-auto-attendant.md)
   - [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)
7. Asignar la cuenta de recursos al servicio. Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)

### <a name="create-a-resource-account-without-a-phone-number"></a>Crear una cuenta de recursos sin un número de teléfono

Para crear una cuenta de recursos que no necesite un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:

1. Crear una cuenta de recursos nueva. Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell)
2. Configure una de las opciones siguientes:
   - [Operador automático de la nube](create-a-phone-system-auto-attendant.md)
   - [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)
3. Asignar la cuenta de recursos al servicio. Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Crear una cuenta de recursos en el centro de administración de Microsoft Teams

Una vez que haya comprado una licencia de sistema telefónico y un plan de llamadas, usando el centro de administración de Microsoft Teams, vaya a**cuentas de recursos** **de configuración** > de toda la organización.

![Captura de pantalla de la página cuentas de recursos](media/r-a-master.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/sfbcallout1.png)

Para crear una cuenta de recursos, haga clic en **+ nueva cuenta**. En la ventana emergente, rellene el nombre para mostrar y el nombre de usuario de la cuenta de recursos (el nombre de dominio debe llenarse automáticamente) y luego haga clic en **Guardar**.

![Captura de pantalla de las opciones de la nueva cuenta de recursos](media/res-acct.png)

A continuación, aplique una licencia a la cuenta de recursos en el centro de administración de O365, como se describe en [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)

### <a name="edit-resource-account-name"></a>Editar el nombre de la cuenta de recursos

![Icono del número 2, que hace referencia a una llamada en la](media/sfbcallout2.png) captura de pantalla anterior, puede editar el nombre para mostrar la cuenta de recursos mediante la opción **Editar** .  Haga clic en **Guardar** cuando haya terminado.
![Captura de pantalla de la opción Editar cuenta de recursos](media/r-a-edit.png)

### <a name="assignunassign-phone-numbers-and-services"></a>Asignar o cancelar la asignación de números de teléfono y servicios

![Icono del número 3, que hace referencia a una llamada en la](media/sfbcallout3.png) captura de pantalla anterior una vez que ha creado la cuenta de recurso y asignada la licencia, puede hacer clic en **asignar/anular asignación** para asignar un número de servicio a la cuenta de recursos o asignar el recurso. cuenta a un operador automático o a una cola de llamadas que ya exista. La asignación de un número de enrutamiento directo puede realizarse solo con cmdlets. Si la cola de llamadas o el operador automático siguen necesitando crearse, puede vincular la cuenta de recursos mientras la crea. Haga clic en **Guardar** cuando haya terminado.

Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, tendrá que usar PowerShell, consulte la sección siguiente.

> [!IMPORTANT]
> Si su inquilino no tiene una licencia de sistema de teléfono, una comprobación interna provocará un error cuando intente asignar el número de teléfono a la cuenta de recursos. No podrá asignar el número ni asociar la cuenta de recursos con un servicio.

![Captura de pantalla de las opciones de asignar/quitar asignación](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a>Crear una cuenta de recursos en PowerShell

En función de si su cuenta de recursos se encuentra en línea o local, tendrá que conectar con el símbolo del sistema de PowerShell adecuado con privilegios de administrador.

- Los siguientes ejemplos de cmdlet de PowerShell suponen que la cuenta de recursos está conectada en línea mediante [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para crear una cuenta de recursos que se ha conectado en línea.

- Las cuentas de recursos hospedadas localmente en Skype empresarial Server 2019 que pueden usarse con las colas de llamadas en la nube y los operadores automáticos de la nube, consulte [configurar colas de llamadas en la](/skypeforbusiness/hybrid/configure-call-queue.md) nube o [configurar operadores automáticos de la nube](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md). Las implementaciones híbridas (números alojados en enrutamiento directo) usarán [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).

Los IDENTIFICADOres de la aplicación que necesita usar al crear las instancias de la aplicación son:

- **Operador automático:** ce933385-9390-45D1-9512-c8d228074e07
- **Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07

> [!NOTE]
> Si quiere que los usuarios locales puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos locales, ya que las cuentas de recursos en línea no se sincronizan con Active Directory.

1. Para crear una cuenta de recursos en línea para usarla con un operador automático, use el siguiente comando.  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. No podrá usar la cuenta de recursos hasta que aplique una licencia. Para obtener información sobre cómo aplicar una licencia a una cuenta en el centro de administración de O365, vea [asignar licencias a usuarios en Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , así como [asignar licencias de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Faculta Una vez que se aplica la licencia correcta a la cuenta de recursos, puede establecer un número de teléfono para la cuenta de recursos, tal como se muestra a continuación. No todas las cuentas de recursos requerirán un número de teléfono. Si no aplicó una licencia a la cuenta de recursos, la asignación de número de teléfono fallará.

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

Para obtener más información sobre este comando [, vea Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

> [!NOTE]
> Es más fácil establecer el número de teléfono en línea con el centro de administración de Microsoft Teams, como se ha descrito anteriormente.

Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, use el siguiente cmdlet:

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams

Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a**cuentas de recursos**de **configuración**  > de toda la organización, seleccione la cuenta de recursos en la que necesita cambiar la configuración y, a continuación, haga clic en el botón **Editar** . en la pantalla **Editar cuenta de recursos** , podrá cambiar esta configuración:

- **Nombre para mostrar** de la cuenta
- Cola de llamadas o operador automático que usa la cuenta
- Número de teléfono asignado a la cuenta

Cuando haya terminado, haga clic en **Guardar**.

## <a name="delete-a-resource-account"></a>Eliminar una cuenta de recursos

Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente. Puede hacerlo usando los siguientes commandlet:

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

Una vez que lo haga, puede eliminar la cuenta de recursos del portal de administración de O365, en la pestaña usuarios.

## <a name="troubleshooting"></a>Solución de problemas

En caso de que no vea el número de teléfono asignado a la cuenta de recursos en el centro de administración de Teams y no pueda asignarle el número, compruebe lo siguiente:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Si el atributo Departamento muestra el punto de conexión de aplicaciones de Skype empresarial, ejecute el siguiente cmdlet:

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> Actualice la página web del centro de administración de equipos después de ejecutar el cmldet y debería poder asignar el número correctamente.

## <a name="related-information"></a>Información relacionada

Para las implementaciones híbridas con Skype empresarial Server:

[Planear los operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurar los operadores automáticos en la nube](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Para las implementaciones de Teams o Skype empresarial online:

[¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)

[Configurar un operador automático en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa)

[Crear una cola de llamadas en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nuevo: CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nuevo: CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
