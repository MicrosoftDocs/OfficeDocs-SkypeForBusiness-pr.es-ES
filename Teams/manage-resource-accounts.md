---
title: Administrar cuentas de recursos en Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: En este artículo, aprenderá a crear, editar y administrar cuentas de recursos en Microsoft Teams.
ms.openlocfilehash: 2bf333eef72de4744f13cfe25a4457facaf4b3e6
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565913"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Administrar cuentas de recursos en Microsoft Teams

Una cuenta de recursos también se conoce como un *objeto de usuario deshabilitado* en Azure ad, y se puede usar para representar recursos en general. En Exchange podría usarse para representar salas de conferencias, por ejemplo, y permitirles que tengan un número de teléfono. Una cuenta de recursos puede encontrarse en Microsoft 365 o en una ubicación local con Skype empresarial Server 2019.

En Microsoft Teams o Skype empresarial online, cada cola de llamadas de sistema o operador automático debe tener al menos una cuenta de recursos asociada. Si una cuenta de recursos necesita un número de teléfono asignado dependerá del uso previsto de la cola de llamadas asociada o del operador automático, como se muestra en el siguiente diagrama. También puede consultar los artículos sobre las colas de llamadas y los operadores automáticos vinculados al final de este artículo antes de asignar un número de teléfono a una cuenta de recursos.

![ejemplo de cuentas de recursos y licencias de usuario](media/resource-account.png)

> [!NOTE]
> Este artículo se aplica a Microsoft Teams y a Skype empresarial online. Para cuentas de recursos alojados en Skype empresarial Server 2019, consulte [configurar cuentas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a>Asignar un número de teléfono a una cola de llamadas de sistema

Si su organización ya usa al menos una licencia de sistema telefónico, para asignar un número de teléfono a una cola de llamadas de sistema, el proceso es el siguiente:

1. Obtener un número de servicio.
2. Obtener un sistema telefónico gratis: [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) o una licencia de sistema telefónico de pagos para usar con la cuenta de recursos o una licencia de sistema telefónico.
3. Crear la cuenta de recursos. Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas.
4. Asigne el sistema telefónico o un sistema telefónico (licencia de usuario virtual) a la cuenta de recursos.
5. Asigne un número de teléfono de servicio a la cuenta de recursos a la que acaba de asignar licencias.
6. Crear una cola de llamadas de sistema telefónicas o un operador automático
7. Vincular la cuenta de recursos con una cola de llamadas o un operador automático.

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

Si el operador automático o la cola de llamadas están anidados bajo un operador automático de nivel superior, la cuenta de recursos asociada solo necesita un número de teléfono si desea tener varios puntos de entrada en la estructura de las colas de llamadas y los operadores automáticos.

Para redirigir las llamadas a las personas de su organización que estén conectadas en línea, deben tener una licencia de **sistema telefónico** y estar habilitadas para telefonía IP empresarial o tener planes de llamadas de Office 365. Consulte [asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md). Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell. Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> Para evitar problemas con la cuenta de recursos, siga estos pasos en este orden.

Si la cola de llamadas del sistema telefónicas o el operador automático que está creando va a estar anidado y no necesitará un número de teléfono, el proceso es el siguiente:

1. Crear la cuenta de recursos
2. Crear una cola de llamadas de sistema telefónicas o un operador automático
3. Asociar la cuenta de recursos a una cola de llamadas de sistema telefónico o un operador automático

### <a name="create-a-resource-account-with-a-phone-number"></a>Crear una cuenta de recursos con un número de teléfono

<a name="phonenumber"> </a>

> [!IMPORTANT]
> Un número de teléfono no se asigna directamente al operador automático o a la cola de llamadas, sino a la cuenta de recursos asociada al operador automático o a la cola de llamadas.

Para un operador automático de nivel superior o una cola de llamadas, es necesario vincular un número de teléfono a su operador automático. Para crear una cuenta de recursos que use un número de teléfono, el proceso es el siguiente:

1. Puerto o recibe un número de servicio de pago o gratuito. El número no se puede asignar a ningún otro servicio de voz o cuenta de recursos.

   Antes de asignar un número de teléfono a una cuenta de recursos, necesita obtener o migrar los números de teléfono de pago o gratuitos existentes. Después de recibir los números de teléfono de pago o gratuitos, aparecerán en los números de teléfono del **centro de administración de Microsoft Teams**  >  **Voice**  >  **Phone numbers**, y el **tipo de número** se indicará como **servicio-** gratuito. Para obtener tus números de servicio, consulta [obtener números de teléfono de servicio](getting-service-phone-numbers.md) o, si deseas transferir un número de servicio existente, consulta [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

   Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de usuario virtual del sistema telefónico de sistema de costos. Esto proporciona capacidades de sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y de operador automático.

2. Obtener una licencia de usuario virtual del sistema telefónico o una licencia de sistema telefónico normal.

   Para obtener la licencia de usuario virtual, en el centro de administración de Microsoft 365 **Billing**, vaya a  >  suscripciones del complemento de**servicios de compra**de facturación  >  **Add-on subscriptions** y desplácese hasta el final: verá la licencia "phone system-virtual User". Seleccione **comprar ahora**. Hay un costo cero, pero sigue siendo necesario seguir estos pasos para adquirir la licencia.
3. Crear una cuenta de recursos nueva. Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell).
4. Asigne un sistema telefónico: [licencia de usuario virtual](teams-add-on-licensing/virtual-user.md) o licencia de sistema telefónico a la cuenta de recursos. Consulte [asignar licencias de complemento de Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) y [asignar licencias a los usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).
5. Asignar el número de servicio a la cuenta de recursos. Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).
6. Configure una de las opciones siguientes:
   - [Operador automático de la nube](create-a-phone-system-auto-attendant.md)
   - [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)
7. Vincule la cuenta de recursos al operador automático o a la cola de llamadas. Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services)

Al crear una cuenta de recursos al crear un operador automático, las licencias se aplican automáticamente.

### <a name="create-a-resource-account-without-a-phone-number"></a>Crear una cuenta de recursos sin un número de teléfono

Un operador automático o una cola de llamadas anidados requerirán una cuenta de recursos pero, en muchos casos, la cuenta de recursos correspondiente no necesitará un número de teléfono y las licencias necesarias para admitir un número de teléfono. Para crear una cuenta de recursos que no necesite un número de teléfono, es necesario realizar las siguientes tareas en el siguiente orden:

1. Crear una cuenta de recursos nueva. Consulte [crear una cuenta de recursos en el centro de administración de Microsoft Teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) o [crear una cuenta de recursos en PowerShell](#create-a-resource-account-in-powershell).

2. Configure una de las opciones siguientes:
   - [Operador automático de la nube](create-a-phone-system-auto-attendant.md)
   - [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)
   
3. Asignar la cuenta de recursos a la cola de llamadas o al operador automático. Consulte [asignar/desasignar números de teléfono y servicios](#assignunassign-phone-numbers-and-services).


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a>Crear una cuenta de recursos en el centro de administración de Microsoft Teams

Una vez que haya comprado una licencia de sistema telefónico, en el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a cuentas de recursos de **configuración de toda la organización**  >  **Resource accounts**.

![Captura de pantalla de la página cuentas de recursos](media/r-a-master.png)

![Icono del número 1, que hace referencia a una llamada en la captura de pantalla anterior](media/teamscallout1.png)

Para crear una nueva cuenta de recursos, haga clic en **Agregar**. En el panel **Agregar cuenta de recursos** , rellene el campo **nombre para mostrar**, nombre de **usuario** (el nombre de dominio debe rellenarse automáticamente) y tipo de **cuenta de recurso** para la cuenta de recursos. El tipo de cuenta de recurso puede ser de **operador automático** o **cola de llamadas**, en función de la aplicación que desee asociar a la cuenta de recursos. Cuando esté listo, haga clic en **Guardar**.

![Captura de pantalla de las opciones de nueva cuenta de recursos](media/res-acct.png)

A continuación, aplique una licencia a la cuenta de recursos en el centro de administración de Microsoft 365, como se describe en [asignar licencias a los usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide).

### <a name="edit-resource-account"></a>Editar cuenta de recursos 

![Icono del número 2, que hace referencia a una llamada en la captura de pantalla anterior, ](media/teamscallout2.png) puede editar el **nombre para mostrar** de la cuenta de recursos y el tipo de **cuenta de recursos** con la opción **Editar** . Haga clic en **Guardar** cuando haya terminado.

![Captura de pantalla de la opción Editar cuenta de recursos](media/r-a-edit.png)

<a name="phonenumber"> </a>

### <a name="assignunassign-phone-numbers-and-services"></a>Asignar o cancelar la asignación de números de teléfono y servicios

![Icono del número 3, que hace referencia a una llamada en la captura de pantalla anterior, ](media/teamscallout3.png) después de crear la cuenta de recurso y asignarle la licencia, puede hacer clic en **asignar/desasignar** para asignar un número de servicio a la cuenta de recursos, configurar el tipo de número de teléfono o asignar la cuenta de recursos a un operador automático específico o a una cola de llamadas que ya exista. La asignación de un número de enrutamiento directo puede realizarse solo con cmdlets. Si aún no ha creado la cola de llamadas o el operador automático que va a asociar a la cuenta de recursos, deje el campo en blanco. Puede vincular la cuenta de recursos mientras la crea. Haga clic en **Guardar** cuando haya terminado.

Las opciones para el **tipo de número de teléfono** son:

- Ninguna
- Online
- Gratuitos
- Local

![Captura de pantalla de las opciones de asignar/quitar asignación](media/r-a-assign.png)

Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, tendrá que usar PowerShell, consulte la sección siguiente.

> [!IMPORTANT]
> Si su cuenta de recursos no tiene una licencia válida, una comprobación interna provocará un error al intentar asignar el número de teléfono a la cuenta de recursos. No podrás asignar el número ni asociar la cuenta de recursos con una cola de llamadas o un operador automático.

> [!IMPORTANT]
> Un número de teléfono no se asigna directamente al operador automático o a la cola de llamadas, sino a la cuenta de recursos asociada al operador automático o a la cola de llamadas.



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Cambiar una cuenta de recursos existente para usar una licencia de usuario virtual

Si decide cambiar las licencias de la cuenta de recursos existente de una licencia de sistema telefónico a una licencia de usuario virtual, tendrá que adquirir la licencia de usuario virtual gratuita y, a continuación, seguir los pasos que se indican en el centro de administración de Microsoft 365 para [mover usuarios a una suscripción diferente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Quitar siempre una licencia de sistema telefónico completo y asignar la licencia de usuario virtual en la misma actividad de licencia. Si quita la licencia anterior, guarda los cambios de la cuenta, agrega la nueva licencia y, a continuación, vuelve a guardar la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto sucede, le recomendamos que cree una nueva cuenta de recursos para la licencia de usuario virtual y quite la cuenta de recursos dañados. 

## <a name="create-a-resource-account-in-powershell"></a>Crear una cuenta de recursos en PowerShell

En función de si la cuenta de recursos se encuentra en línea o en Skype empresarial Server 2019, tendrá que conectar con el aviso de PowerShell adecuado con privilegios de administrador.

- En los siguientes ejemplos de cmdlets de PowerShell se muestra cómo crear una cuenta de recursos conectada en línea con [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps). 

- Cuentas de recursos alojados en Skype empresarial Server 2019 que se pueden usar con las colas de llamadas en la nube y los operadores automáticos de la nube, consulte [planear colas de llamadas en la](/SkypeforBusiness/hybrid/plan-call-queue) nube o [planear operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Las implementaciones híbridas (números alojados en enrutamiento directo) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) en un servidor local de Skype empresarial Server 2019.

Los IDENTIFICADOres de la aplicación que necesita usar al crear las instancias de la aplicación son:

- **Operador automático:** ce933385-9390-45D1-9512-c8d228074e07
- **Cola de llamadas:** 11cd3e2e-FCCB-42ad-ad00-878b93575e07

> [!NOTE]
> Si desea que los usuarios de Skype empresarial Server 2019 puedan buscar en la cola de llamadas o en el operador automático, debe crear sus cuentas de recursos en Skype empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory. Cuando los registros SRV de DNS para sipfederationtls se resuelven en Skype empresarial Server 2019, las cuentas de recursos **deben** crearse en Skype empresarial Server 2019 con el shell de administración de SfB y se pueden sincronizar con Azure ad en línea.

 

1. Para crear una cuenta de recursos en línea para usarla con un operador automático, use el siguiente comando:

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. No podrá usar la cuenta de recursos hasta que aplique una licencia. Para obtener información sobre cómo aplicar una licencia a una cuenta en el centro de administración de Microsoft 365, consulte [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) y [asignar licencias de Skype empresarial](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

3. Faculta Después de aplicar la licencia correcta a la cuenta de recursos, puede asignar un número de teléfono a la cuenta de recursos, tal y como se muestra a continuación. No todas las cuentas de recursos requerirán un número de teléfono. Si no aplicó una licencia a la cuenta de recursos, se producirá un error en la asignación de número de teléfono.

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   Para obtener más información sobre este comando [, vea Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

   > [!NOTE]
   > Es más fácil establecer el número de teléfono en línea con el centro de administración de Microsoft Teams, como se ha descrito anteriormente.

   Para asignar un número de teléfono de enrutamiento directo a una cuenta de recursos (alojada en Microsoft Teams o en Skype empresarial Server 2019), use el siguiente cmdlet para Skype empresarial online PowerShell:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a>Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams

Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a cuentas de recursos de **configuración de toda**  >  **Resource accounts**la organización, seleccione la cuenta de recursos en la que necesita cambiar la configuración y, a continuación, haga clic en **Editar**. En el panel **Editar cuenta de recursos** , puede cambiar esta configuración:

- **Nombre para mostrar** de la cuenta
- Cola de llamadas o operador automático que usa la cuenta
- Número de teléfono asignado a la cuenta

Cuando haya terminado, haga clic en **Guardar**.

## <a name="delete-a-resource-account"></a>Eliminar una cuenta de recursos

Asegúrese de desasociar el número de teléfono de la cuenta de recursos antes de eliminarlo, para evitar que su número de servicio quede bloqueado en modo pendiente. Puede hacerlo usando el siguiente cmdlet:

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

Después de hacerlo, puede eliminar la cuenta de recursos en el centro de administración de Microsoft 365, en la pestaña usuarios.

Para desvincular un número de teléfono de enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a>No puede ver el número de teléfono asignado a la cuenta de recursos en el centro de administración de Microsoft Teams

Si no ve el número de teléfono asignado a la cuenta de recursos en el centro de administración de Microsoft Teams y no puede asignarle el número, compruebe lo siguiente:

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Si el atributo Departamento muestra el punto de conexión de aplicaciones de Skype empresarial, ejecute el siguiente cmdlet:

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> Actualice la página web del centro de administración de equipos después de ejecutar el cmldet y debería poder asignar el número correctamente.

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a>Recibe una "no podemos usar esta cuenta de recursos para servicios". mensaje de error

<a name="blocksignin"> </a>

Recibe el siguiente mensaje de error cuando intenta usar una cuenta de recursos:

"No podemos usar esta cuenta de recursos para servicios. La cuenta de recursos debe estar deshabilitada y estar BLOQUEAda para iniciar sesión. Debe bloquear los inicios de sesión de esta cuenta de recursos en la página usuarios del centro de administración de Microsoft 365.

Al crear una cuenta de recursos, de forma predeterminada, está deshabilitada e iniciar sesión está bloqueado para la cuenta. Esta configuración no debe cambiarse. Para resolver este mensaje de error, bloquee la cuenta de recursos para que no inicie sesión. Para ello, haga lo siguiente:

1. En el centro de administración de Microsoft 365, vaya a **usuarios**, buscar y, a continuación, seleccione la cuenta de recursos.
2. En la parte superior del panel debajo del nombre para mostrar, haga clic en **¿bloquear este usuario?**, active la casilla **de verificación bloquear este usuario para iniciar sesión** y, a continuación, seleccione **Guardar cambios**.

   ![Captura de pantalla de la opción bloquear este usuario](media/res-acct-block.png)

    Después de hacerlo, verás "iniciar sesión bloqueada" en el nombre para mostrar.

      ![Captura de pantalla del mensaje bloqueado de inicio de sesión](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a>Información relacionada

Para las implementaciones híbridas con Skype empresarial Server:

   [Planear los operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [Planear las colas de llamadas en la nube](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [Configurar cuentas de recursos locales](/SkypeForBusiness/hybrid/configure-onprem-ra)


Para las implementaciones de Teams o Skype empresarial online:

   [¿Qué son los operadores automáticos en la nube?](what-are-phone-system-auto-attendants.md)

   [Configurar un operador automático en la nube](/microsoftteams/create-a-phone-system-auto-attendant)

   [Ejemplo de pequeña empresa: configurar un operador automático](/microsoftteams/tutorial-org-aa)

   [Crear una cola de llamadas en la nube](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nuevo: CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nuevo: CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Nuevo: CsOnlineApplicationInstanceAssociation](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[Sistema telefónico-licencia de usuario virtual](teams-add-on-licensing/virtual-user.md)
