---
title: Administrar cuentas de recursos en Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: En este artículo, aprenderá a crear, editar y administrar cuentas de recursos en Microsoft Teams.
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763581"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Administrar cuentas de recursos en Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Pasos siguientes

Una vez que haya completado la configuración de la cuenta de recursos y asignado un número de teléfono si es necesario, está listo para usar la cuenta de recursos con un operador automático o una cola de llamadas.

Vea las siguientes referencias para obtener más información:

- [Operador automático en la nube](create-a-phone-system-auto-attendant.md)
- [Cola de llamadas en la nube](create-a-phone-system-call-queue.md)

Puede editar la cuenta de recursos **Nombre para mostrar** y el tipo **de cuenta de recurso** con la opción **Editar** . Selecciona **Guardar** cuando hayas terminado.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Cambiar una cuenta de recursos existente para usar una licencia de cuenta de recursos de Teléfono Microsoft Teams

Para cambiar las licencias de su cuenta de recursos existente de una licencia **de Teléfono Teams Estándar** a una licencia de cuenta de recursos **de Teléfono Microsoft Teams**, tendrá que adquirir la licencia de cuenta de recursos **de Teléfono Microsoft Teams** y, a continuación, seguir los pasos de la Centro de administración de Microsoft 365 mover [usuarios a una suscripción diferente](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Quite siempre una licencia **de Teléfono Teams Estándar** y asigne la licencia **Teléfono Microsoft Teams cuenta de** recursos en la misma actividad de licencia. Si quita la licencia antigua, guarda los cambios en la cuenta, agrega la nueva licencia y, a continuación, guarda de nuevo la configuración de la cuenta, es posible que la cuenta de recursos ya no funcione según lo esperado. Si esto ocurre, le recomendamos que cree una nueva cuenta de recursos para la licencia **de cuenta de recursos de Teléfono Microsoft Teams** y quite la cuenta de recursos rota.

## <a name="skype-for-business-server-2019"></a>Skype Empresarial Server 2019

Para las cuentas de recursos alojados en Skype Empresarial Server 2019 que se pueden usar con colas de llamadas en la nube y operadores automáticos en la nube, consulte [Planear colas de llamadas](/SkypeforBusiness/hybrid/plan-call-queue) en la nube o [Planear operadores automáticos de la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Las implementaciones híbridas (números alojados en Direct Routing) se configuran mediante el cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) en un servidor local de Skype Empresarial Server 2019.

Los identificadores de aplicación que necesita usar al crear las instancias de la aplicación son:

- **Operador automático:** ce933385-9390-45d1-9512-c8d228074e07
- **Cola de llamadas:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Si quiere que los usuarios de Skype Empresarial Server 2019 puedan buscar la cola de llamadas o el operador automático, debe crear sus cuentas de recursos en Skype Empresarial Server 2019, ya que las cuentas de recursos en línea no se sincronizan con Active Directory. Cuando los registros SRV de DNS para sipfederationtls se resuelvan en Skype Empresarial Server 2019, las cuentas de recursos **deben** crearse en Skype Empresarial Server 2019 con el shell de administración de SfB y sincronizarse con Azure AD.

Para implementaciones híbridas con Skype Empresarial Server:

- [Planear operadores automáticos en la nube](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).
- [Planear colas de llamadas en la nube](/SkypeforBusiness/hybrid/plan-call-queue).
- [Configurar cuentas de recursos locales](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="delete-a-resource-account"></a>Eliminar una cuenta de recursos

Asegúrese de disociar el número de teléfono de la cuenta de recursos antes de eliminarla, para evitar que su número de teléfono se quede atascado en el modo pendiente.

Después de hacerlo, puede eliminar la cuenta de recursos en la Centro de administración de Microsoft 365, en la pestaña **Usuarios**.

Para desasociar un número de teléfono de Enrutamiento directo de la cuenta de recursos, use el siguiente cmdlet:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>Ocultar cuentas de recursos a los usuarios de Teams

Es posible que desee ocultar determinadas cuentas de recursos a los usuarios de Teams. Por ejemplo, es posible que desee evitar que los usuarios de Teams llamen directamente a una cola de llamadas y omitan al operador automático donde están configuradas las horas de operación.

[Las barreras de información](information-barriers-in-teams.md) se usan para ocultar las cuentas de recursos.  Revise la documentación de barreras de información para comprender los posibles impactos antes de continuar con los pasos que se indican a continuación.

### <a name="required-subscriptions-and-permissions"></a>Suscripciones y permisos necesarios 

Para acceder a las barreras de la información y usarlas, su organización debe tener una de las siguientes suscripciones o complementos: 

-   suscripción Microsoft 365 E5/A5 (versión de pago o de prueba).
-   Office 365 E5/A5/A3/A1 (versión de pago o de prueba).
-   Cumplimiento avanzado de Office 365 complemento.
-   suscripción Microsoft 365 E3/A3/A1 + el complemento cumplimiento Microsoft 365 E5/A5.
- suscripción Microsoft 365 E3/A3/A1 + el complemento Administración de riesgos de Insider Microsoft 365 E5/A5.

> [!NOTE]
> Si ya tiene [Exchange Online](/exchange/address-books/address-book-policies/address-book-policies) directivas de libreta de direcciones configuradas, deben quitarse antes de continuar con los pasos siguientes.   
> 
> Todos los pasos siguientes los realiza el administrador global de inquilinos. 
>   
> Estas instrucciones asumen que no hay otras barreras de la información configuradas.

#### <a name="teams-admin-center"></a>Centro de administración de Teams

1. Inicie sesión en el [Centro de administración de Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. En el menú de la barra izquierda, expanda **Teams**.
3. Seleccione **Configuración de Teams**. 
4. Desplácese hacia abajo hasta **Buscar por nombre**.
5. Activa el botón de alternancia y guarda el cambio.

Para obtener más información sobre esta opción, vea [Limitar los usuarios que pueden ver al buscar en el directorio en Teams](teams-scoped-directory-search.md).

#### <a name="compliance---auditing"></a>Cumplimiento: auditoría

1. Inicia sesión en la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/).
2. En el panel de navegación izquierdo, seleccione **Auditoría**.
3. Si la auditoría está desactivada, se mostrará el siguiente banner: 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="Captura de pantalla que muestra un banner de auditoría si la auditoría no está habilitada":::
  
4. Seleccione **Iniciar la grabación de la actividad administrativa y de usuario**. 

Para obtener más información sobre la auditoría, vea [Configurar auditoría (estándar) en Microsoft 365](/microsoft-365/compliance/audit-standard-setup).

#### <a name="segmenting-data"></a>Datos de segmentación

Las cuentas de recursos a las que no se debe llamar directamente deben segmentarse y identificarse fácilmente.  Esto puede hacerse haciendo que sean miembros de un grupo en particular o mediante alguna información única en su perfil de usuario, como: 

-   Compañía
-   Nombre principal de usuario
-   Ubicación
-   Departamento
-   Ubicación de uso
-   Alias de correo (alias)
-   Nombre de la oficina de entrega física (Office)
-   Código postal
-   Dirección del proxy (dirección Email)
-   Dirección
-   Dirección de destino (ExternalEmailAddress)
-   Correo (WindowsEmailAddress)
-   Descripción

En los pasos de ejemplo siguientes, se usará el `Department` campo. 

Para obtener más información sobre la segmentación de usuarios, consulte  [Identificar segmentos](/microsoft-365/compliance/information-barriers-policies).

#### <a name="microsoft-admin-center"></a>Centro de administración de Microsoft

1. Inicia sesión en el [Centro de Administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. En el panel de navegación izquierdo, seleccione **Usuarios activos**.
3. Seleccione la primera cuenta de recursos a la que bloquear llamadas directas.
4. Seleccione **Administrar información de contacto** en el panel derecho.
5. Reemplace el contenido del `Department` campo por una única palabra o acrónimo que no se use como nombre de departamento. Por ejemplo, `DNC`.
6. Guardar los cambios.
7. Repita este procedimiento para cada cuenta de recursos que tenga que bloquearse para que no reciba llamadas directas.

#### <a name="compliance---information-barriers"></a>Cumplimiento: barreras de la información

1. Inicia sesión en la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/).
2. En el panel de navegación izquierdo, seleccione **Segmentos de barreras de** >  información.
3. Seleccione **Nuevo segmento**.
4. Escriba un nombre para el segmento y seleccione **Siguiente**. Por ejemplo, `Uncallable Resource Accounts`.
5. Seleccione **+ Agregar** y, después, **Departamento**.
6. Escriba la palabra o acrónimo único que se usa en el paso 5 anterior del Centro de administración de Microsoft. Por ejemplo, `DNC`.
7. Selecciona **Siguiente** y, a continuación, **Enviar**.
8. Seleccione **Nuevo segmento**.
9. Escriba un nombre para el segmento y seleccione **Siguiente**. Por ejemplo, `Callable Users`.
10. Seleccione **+ Agregar** y, después, **Departamento**.
11. Seleccione el menú desplegable **Igual** y seleccione **No es igual a**.
12. Escriba la palabra o acrónimo único que se usa en el paso 5 anterior del Centro de administración de Microsoft. Por ejemplo, `DNC`.
13. Selecciona **Siguiente** y, a continuación, **Enviar**. 
14. En el panel de navegación izquierdo, seleccione **Directivas** de **barreras de** >  información.
15. Seleccione **Crear directiva**.
16. Escriba un nombre para la directiva y seleccione **Siguiente**. Por ejemplo, `Uncallable Resource Accounts`.
17. Seleccione **+ Elegir segmento**, agregue el segmento creado en el paso 9 anterior y seleccione **Siguiente**. Por ejemplo, `Callable Users`.
18. Seleccione **Bloqueado** en la lista desplegable **Comunicación y colaboración** .
19. Seleccione **+ Elegir segmento**, agregue el segmento creado en el paso 4 anterior y seleccione **Siguiente**. Por ejemplo, `Uncallable Resource Accounts`.
20. Establece la directiva **en Activado**, selecciona **Siguiente** y, a continuación, **Enviar**.
21. Seleccione **Crear directiva**.
22. Escriba un nombre para la directiva y seleccione **Siguiente**. Por ejemplo, `Callable Users`.
23. Seleccione **+ Elegir segmento**, agregue el segmento creado en el paso 4 y seleccione **Siguiente**.
24. Seleccione **Bloqueado** en la lista desplegable **Comunicación y colaboración** . 
25. Seleccione **+ Elegir segmento**, agregue el segmento creado en el paso 9 anterior y seleccione **Siguiente**.
26. Establece la directiva **en Activado**, selecciona **Siguiente** y, a continuación, **Enviar**.
27. En el panel de navegación izquierdo, seleccione **Aplicación de directiva** **de barreras** >  de información.
28. Seleccione **Aplicar todas las directivas**.

> [!NOTE]
> La directiva puede tardar 30 minutos o más en aplicarse.  
> 
> Una vez que se haya completado el estado, vaya al cliente de Teams e intente buscar las cuentas de recursos que se bloquearon. Es posible que sea necesario borrar la caché de Teams.  
> 
> Si un usuario de Teams ha guardado la cuenta de recursos como contacto, ya no podrá llamarla.
