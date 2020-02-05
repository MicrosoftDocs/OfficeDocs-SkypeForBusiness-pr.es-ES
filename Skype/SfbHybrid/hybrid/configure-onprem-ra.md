---
title: Configurar una cuenta de recursos en Skype empresarial Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Configure una cuenta de recursos para Skype empresarial Server 2019.
ms.openlocfilehash: e16f75063cfbe794ff0257cb9cccdf44065a5448
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726780"
---
# <a name="configure-resource-accounts"></a>Configurar cuentas de recursos

Las implementaciones híbridas de Skype empresarial Server 2019 solo usan los servicios en la nube proporcionados por el sistema telefónico para la mensajería unificada y no se integran con Exchange Online. En Skype empresarial Server 2019, ahora puede usar las colas de llamadas en la nube y los operadores automáticos que se describen en [esto es lo que obtiene con el sistema telefónico en Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Para usar un operador automático de sistema telefónico o una cola de llamadas con Skype empresarial Server 2019, tendrá que crear cuentas de recursos que actúen como extremos de aplicación y a los que se les puedan asignar números de teléfono y, a continuación, usar el centro de administración de Teams online para configurar la cola de llamadas o operador automático. Esta cuenta de recursos se puede hospedar en línea (consulte [administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) para crear cuentas de recursos hospedadas en línea) o en locales, tal como se describe en este artículo. Normalmente, tendrá varios operadores automáticos de sistema telefónico o de cola de llamadas, cada uno de los cuales se asigna a una cuenta de recursos, que se puede hospedar en línea o en Skype empresarial Server 2019.

Si tiene un operador automático de mensajería unificada de Exchange y un sistema de cola de llamadas, antes de cambiar a Exchange Server 2019 o Exchange Online tendrá que registrar manualmente los detalles como se describe a continuación y, a continuación, implementar un sistema completamente nuevo con el centro de administración de Teams. .

## <a name="overview"></a>Información general

Si el operador automático del sistema telefónico o la cola de llamadas van a necesitar un número de servicio, se pueden cumplir las distintas dependencias en la secuencia siguiente:

1. Obtener un número de servicio
2. Obtenga una licencia de sistema telefónico gratuita para el [usuario](/MicrosoftTeams/teams-add-on-licensing/virtual-user) o una licencia de sistema telefónico de pago para usarla con la cuenta de recursos.
3. Cree la cuenta de recurso. Un operador automático o cola de llamadas debe tener una cuenta de recurso asociada.
4. Espere a que se sincronice Active Directory entre las instalaciones en línea y locales.
5. Asigne la licencia de sistema telefónico a la cuenta de recurso.
6. Asigne un número de servicio a la cuenta de recurso.
7. Cree una cola de llamadas del sistema telefónico o un operador automático.
8. Asocie la cuenta de recurso con un operador automático o una cola de llamadas: (New-CsApplicationInstanceAssociation).

Si el operador automático o la cola de llamadas están anidados bajo un operador automático de nivel superior, la cuenta de recurso asociada solo necesita un número de teléfono si desea tener varios puntos de entrada en la estructura de los operadores automáticos y las colas de llamadas.

Para redirigir las llamadas a los usuarios de su organización que estén hospedados en línea, deben tener una licencia de **sistema telefónico** y estar habilitados para telefonía IP empresarial o tener planes de llamadas de Office 365. Consulte [asignar licencias de Microsoft Teams](/MicrosoftTeams/assign-teams-licenses). Para habilitarlos para telefonía IP empresarial, puede usar Windows PowerShell. Por ejemplo, ejecute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si el operador automático del sistema telefónico o la cola de llamadas que está creando estarán anidados y no necesitará un número de teléfono, el proceso es:

1. Crear la cuenta de recursos  
2. Esperar una sincronización de Active Directory entre la ubicación en línea y local
3. Crear un operador automático o cola de llamadas del sistema telefónico
4. Asociar la cuenta de recurso a un operador automático o cola de llamadas del sistema telefónico

## <a name="create-a-resource-account-with-a-phone-number"></a>Crear una cuenta de recurso con un número de teléfono

La creación de una cuenta de recursos que use un número de teléfono requeriría realizar las siguientes tareas en el orden siguiente:

1. Puerto u obtenga un número de servicio de pago o gratuito. El número no se puede asignar a otros servicios de voz o cuentas de recursos.

   Antes de asignar un número de teléfono a una cuenta de recursos, tendrá que obtener o migrar los números de servicio de pago o gratuitos existentes. Una vez que obtenga los números de teléfono de servicio de pago o gratuitos, se mostrarán en**los números de teléfono****de telefonía del** > centro > de **Administración de Microsoft Teams**, y el **tipo de número** que aparezca en la lista aparecerá como **servicio-** gratuito. Para obtener los números de servicio, consulte [obtener números de teléfono de servicio](/MicrosoftTeams/getting-service-phone-numbers) o, si desea transferir un número de servicio existente, consulte [transferir números de teléfono a Microsoft Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener los números de servicio. Vaya a [administrar los números de teléfono de su organización](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) en lugar de ver cómo hacerlo desde fuera de los Estados Unidos.

2. Compre una licencia de sistema telefónico. Vea:  
   - [Sistema telefónico: licencia de usuario virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 y E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Software de empresa Office 365 Enterprise E5](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Cree una cuenta de recursos local mediante la ejecución del `New-CsHybridApplicationEndpoint` cmdlet para cada operador automático del sistema telefónico o cola de llamadas, y asigne a cada uno de ellos un nombre, una dirección SIP, etc.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Vea [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

4. Opcional Una vez que se hayan creado las cuentas de recursos, puede esperar a que AD se sincronice entre los locales y en línea, o forzar una sincronización y continuar con la configuración en línea del operador automático del sistema telefónico o las colas de llamadas. Para forzar una sincronización, ejecute el siguiente comando en el equipo que ejecuta AAD Connect (si no lo ha hecho ya, necesita cargar `import-module adsync` para ejecutar el comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obtener más información sobre este comando.

5. Asigne la licencia de sistema telefónico o usuario virtual a la cuenta del recurso. Consulte [asignar licencias de Microsoft Teams](/MicrosoftTeams/assign-teams-licenses) y [asignar licencias a un usuario](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).

   Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de sistema telefónico y usuario virtual sin costo. Esto proporciona funciones del sistema telefónico a números de teléfono en el nivel de la organización y le permite crear funciones de cola de llamadas y operador automático.


6. Asigne el número de servicio a la cuenta de recurso. Use el `Set-CsHybridApplicationEndpoint` comando para asignar un número de teléfono (con la opción-LineURI) a la cuenta del recurso.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Consulte [set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

    Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, use el siguiente cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

La cuenta de recurso necesitará un número de teléfono asignado si se va a asignar a un operador automático de nivel superior o a una cola de llamadas. Los números de teléfono de usuario (suscriptor) no se pueden asignar a una cuenta de recursos; solo se pueden usar números de teléfono de servicio de pago o gratuitos.

  Puede asignar un número híbrido de enrutamiento directo a su cuenta de recursos.  Consulte [plan Direct Routing](/MicrosoftTeams/direct-routing-plan) para obtener más información.

  > [!NOTE]
  > Los números del servicio de enrutamiento directo asignados a las cuentas de recursos para el operador automático y las colas de llamadas solo se admiten para los usuarios y agentes de Microsoft Teams.

7. Cree el operador automático o la cola de llamadas del sistema telefónico. Vea una de las opciones siguientes:

   - [Configurar un operador automático de la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Asocie la cuenta de recurso con el operador automático de sistema telefónico o la cola de llamadas que eligió anteriormente.

Un ejemplo de implementación de una pequeña empresa está disponible en [Small Business ejemplo: configurar un operador automático](/microsoftteams/tutorial-org-aa) y una [pequeña empresa-configurar una cola de llamadas](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).

## <a name="create-a-resource-account-without-a-phone-number"></a>Crear una cuenta de recurso sin un número de teléfono

En esta sección se describe cómo crear una cuenta de recursos que esté hospedada en local. La creación de una cuenta de recursos que se hospeda en línea se explica en [Manage Resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Estos pasos son necesarios para crear un operador automático de sistema telefónico de marca o una estructura de cola de llamadas, o bien para reconstruir la estructura creada originalmente en la mensajería unificada de Exchange.

Inicie sesión en el servidor front-end de Skype empresarial y ejecute los siguientes cmdlets de PowerShell:

1. Cree una cuenta de recursos local mediante la ejecución del `New-CsHybridApplicationEndpoint` cmdlet para cada operador automático del sistema telefónico o cola de llamadas, y asigne a cada uno de ellos un nombre, una dirección SIP, etc.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Vea [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

2. Opcional Una vez que se hayan creado las cuentas de recursos, puede esperar a que AD se sincronice entre los locales y en línea, o forzar una sincronización y continuar con la configuración en línea del operador automático del sistema telefónico o las colas de llamadas. Para forzar una sincronización, ejecute el siguiente comando en el equipo que ejecuta AAD Connect (si no lo ha hecho ya, necesita cargar `import-module adsync` para ejecutar el comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obtener más información sobre este comando.

3. Cree el operador automático o la cola de llamadas del sistema telefónico. Vea una de las opciones siguientes:
   - [Configurar un operador automático de la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Asocie la cuenta de recurso y el operador automático o la cola de llamadas del sistema telefónico que eligió anteriormente.

Un ejemplo de implementación de una pequeña empresa está disponible en [Small Business ejemplo: configurar un operador automático](/microsoftteams/tutorial-org-aa) y una [pequeña empresa-configurar una cola de llamadas](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).

## <a name="test-the-implementation"></a>Probar la implementación

La mejor manera de probar la implementación es llamar al número configurado para un operador automático de sistema telefónico o una cola de llamadas y conectarse a uno de los agentes o menús. También puede realizar rápidamente una llamada de prueba mediante el **botón probar** del panel de acciones del centro de administración. Si desea realizar cambios en un operador automático de sistema telefónico o cola de llamadas, selecciónelo y, a continuación, en el panel de acciones, haga clic en **Editar**. 

> [!TIP]
> Si su cuenta de recurso tiene dificultades para asignarse a una cola de llamadas o a un operador automático, consulte [problemas conocidos de Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) y la sección [cómo solucionar mis instancias de aplicaciones híbridas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) en el blog de Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Mover una cola de llamadas o un operador automático de mensajería unificada de Exchange al sistema telefónico

La migración de la mensajería unificada de Exchange al sistema telefónico necesitará volver a crear la cola de llamadas y la estructura del operador automático, la migración directa de una a otra no es compatible. Para volver a implementar un conjunto de colas de llamadas y operadores automáticos:

1. Para obtener una lista de todos los operadores automáticos de mensajería unificada de Exchange y las colas de llamadas, ejecute el siguiente comando en el sistema de Exchange 2013 o 2016 mientras tiene una sesión iniciada como administrador:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Por cada cola de llamadas de mensajería unificada de Exchange o operador automático, anote su lugar en la estructura, configuración y obtener copias de los archivos de texto o de texto a voz asociados (el GUID del resultado será el nombre de una carpeta en la que se almacenan los archivos). Puede obtener estos detalles si ejecuta el comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Consulte [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) para obtener más información sobre este comando. Una lista completa de las opciones que es posible que necesite capturar está en [los miembros de UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , pero las opciones más importantes para destacar son:

    - Horario comercial
    - Horario no comercial
    - Idioma
    - Programación de vacaciones

3. Cree nuevos puntos de conexión locales como se describió anteriormente.
   Asigne al operador automático de nivel superior un número temporal para fines de prueba.

4. Configure un operador automático o cola de llamadas del sistema telefónico que use los puntos de conexión como se ha descrito anteriormente.

   Es posible que le resulte útil usar los ejercicios del tutorial titulado [Small Business example-configure a un operador automático](/microsoftteams/tutorial-org-aa) para crear un mapa lógico de las jerarquías en su antiguo sistema de mensajería unificada de Exchange.
5. Pruebe el operador automático del sistema telefónico o la cola de llamadas.
6. Reasigne el número de teléfono vinculado a la cola de llamadas de mensajería unificada de Exchange o al operador automático al operador automático o la cola de llamadas del sistema telefónico correspondiente.  

   En este punto, si ya ha migrado el correo de voz de mensajería unificada, debe estar en una ubicación para migrar a Exchange Server 2019.

## <a name="see-also"></a>Vea también

[Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)

[¿Qué son los operadores automáticos de la nube?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurar un operador automático de la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planeación de operadores automáticos en la nube](plan-cloud-auto-attendant.md)

[Planear colas de llamadas en la nube](plan-call-queue.md)

[Planear el servicio de correo de voz en la nube para usuarios locales](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(para crear cuentas de recursos alojadas en línea\)
