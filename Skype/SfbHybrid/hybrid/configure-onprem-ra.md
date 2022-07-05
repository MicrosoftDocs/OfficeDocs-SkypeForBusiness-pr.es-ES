---
title: Configuración de una cuenta de recursos en Skype Empresarial Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Configure una cuenta de recursos para Skype Empresarial Server 2019.
ms.openlocfilehash: ebaf79229097df8d3477b4d9b74504c278bfd59c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615616"
---
# <a name="configure-resource-accounts"></a>Configurar cuentas de recursos

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Empresarial Server implementaciones híbridas de 2019 solo usan servicios en la nube proporcionados por Phone System para la mensajería unificada y no se integran con Exchange Online. En Skype Empresarial Server 2019 ahora puede usar las colas de llamadas en la nube y los operadores automáticos que se describen en [Esto es lo que obtiene con Phone System en Microsoft 365 o Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Para usar un operador automático del sistema telefónico o una cola de llamadas con Skype Empresarial Server 2019, tendrá que crear cuentas de recursos que actúen como puntos de conexión de la aplicación y se puedan asignar números de teléfono y, a continuación, usar el Centro de administración de Teams en línea para configurar la cola de llamadas o el operador automático. Esta cuenta de recursos se puede hospedar en línea (consulte [Administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) para crear cuentas de recursos en línea) o de forma local, como se describe en este artículo. Normalmente tendrá varios nodos de cola de llamadas o operador automático del sistema telefónico, cada uno de los cuales está asignado a cuentas de recursos, que se pueden hospedar en línea o en Skype Empresarial Server 2019.

Si tiene un operador automático de mensajería unificada de Exchange y un sistema de cola de llamadas existentes, antes de cambiar a Exchange Server 2019 o Exchange Online, deberá registrar manualmente los detalles como se describe a continuación e implementar un sistema completamente nuevo mediante el Centro de administración de Teams.

## <a name="overview"></a>Información general

Si el operador automático del sistema telefónico o la cola de llamadas necesitarán un número de servicio, las distintas dependencias se pueden cumplir en la secuencia siguiente:

1. Obtenga un número de servicio.
2. Obtenga una [licencia gratuita Teléfono Microsoft Teams cuenta de recursos](/MicrosoftTeams/teams-add-on-licensing/virtual-user) o una licencia de sistema telefónico de pago para usarla con la cuenta de recursos.
3. Cree la cuenta de recursos. Se requiere un operador automático o una cola de llamadas para tener una cuenta de recursos asociada.
4. Espere una sincronización de Active Directory entre en línea y local.
5. Asigne la licencia del sistema telefónico a la cuenta de recursos.
6. Asigne un número de servicio a la cuenta de recursos.
7. Cree una cola de llamadas del sistema telefónico o un operador automático.
8. Asocie la cuenta de recursos con un operador automático o una cola de llamadas: (New-CsApplicationInstanceAssociation).

Si el operador automático o la cola de llamadas están anidados en un operador automático de nivel superior, la cuenta de recursos asociada solo necesita un número de teléfono si desea varios puntos de entrada en la estructura de operadores automáticos y colas de llamadas.

Para redirigir las llamadas a las personas de su organización que están hospedados en línea, deben tener una licencia **del sistema telefónico** y estar habilitadas para Telefonía IP empresarial o tener Planes de llamadas de Microsoft 365 o Office 365. Consulte [Asignación de licencias de Microsoft Teams](/MicrosoftTeams/assign-teams-licenses). Para habilitarlos para Telefonía IP empresarial, puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si el operador automático del sistema telefónico o la cola de llamadas que está creando se anidarán y no necesitarán un número de teléfono, el proceso es:

1. Creación de la cuenta de recursos  
2. Esperar una sincronización de Active Directory entre en línea y local
3. Creación de un operador automático del sistema telefónico o una cola de llamadas
4. Asociación de la cuenta de recursos con un operador automático del sistema telefónico o una cola de llamadas

## <a name="create-a-resource-account-with-a-phone-number"></a>Creación de una cuenta de recursos con un número de teléfono

La creación de una cuenta de recursos que use un número de teléfono requeriría realizar las siguientes tareas en el orden siguiente:

1. Porte o obtenga un número de servicio gratuito o de pago. El número no se puede asignar a ningún otro servicio de voz o cuentas de recursos.

   Antes de asignar un número de teléfono a una cuenta de recursos, deberá obtener o transferir los números de servicio gratuitos o de peaje existentes. Después de obtener los números de teléfono de servicio gratuitos o de pago, se mostrarán en **los números de teléfono** de **voz** >  del Centro  >  de **administración de Microsoft Teams** y el **tipo de número** que aparece se mostrará como **Servicio - Gratuito**. Para obtener los números de servicio, consulte [Obtención de números de teléfono de servicio](/MicrosoftTeams/getting-service-phone-numbers) o si desea transferir un número de servicio existente, consulte [Transferencia de números de teléfono a Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Si está fuera de la Estados Unidos, no puede usar el Centro de administración de Microsoft Teams para obtener números de servicio. Vaya a [Administrar números de teléfono de su organización](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) en su lugar para ver cómo hacerlo desde fuera de la Estados Unidos.

2. Comprar una licencia del sistema telefónico. Vea:  
   - [Teléfono Microsoft Teams licencia de la cuenta de recursos](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 y E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Cree una cuenta de recursos local mediante la ejecución del `New-CsHybridApplicationEndpoint` cmdlet para cada operador automático del sistema telefónico o cola de llamadas, y asigne a cada uno un nombre, una dirección SIP, etc.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

4. (Opcional) Una vez creadas las cuentas de recursos, puede esperar a que AD se sincronice entre en línea y local, o forzar una sincronización y continuar con la configuración en línea del operador automático del sistema telefónico o las colas de llamadas. Para forzar una sincronización, ejecutaría el siguiente comando en el equipo que ejecuta AAD Connect (si aún no lo ha hecho, tendría que cargar `import-module adsync` para ejecutar el comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obtener más información sobre este comando.

    En este momento, es posible que la cuenta se haya sincronizado, pero es posible que el aprovisionamiento no esté completo.  Compruebe la salida de [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Si el punto de conexión sincronizado aún no ha completado el aprovisionamiento, no aparecerá aquí.  Puede comprobar el estado de las solicitudes de aprovisionamiento en el portal de M365 en [Estado de instalación de Teams](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).  Esta fase de aprovisionamiento puede tardar hasta 24 horas.

5. Asigne la licencia **de Teléfono Microsoft Teams cuenta de recursos** o **la licencia de Teléfono Teams Estándar** a la cuenta de recursos. Consulte [Asignación de licencias de complementos de Microsoft Teams](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) y [Asignación de licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

   Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia de **cuenta de recursos Teléfono Microsoft Teams** gratuita. Esto proporciona funcionalidades del sistema telefónico a los números de teléfono en el nivel organizativo y le permite crear funcionalidades de operador automático y cola de llamadas.

6. Asigne el número de servicio a la cuenta de recursos. Use el `Set-CsHybridApplicationEndpoint` comando para asignar un número de teléfono (con la opción -LineURI) a la cuenta de recursos.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Consulte [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

    Para asignar un enrutamiento directo o un número híbrido a una cuenta de recursos, use el siguiente cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   La cuenta de recursos necesitará un número de teléfono asignado si se asignará a un operador automático de nivel superior o a una cola de llamadas. Los números de teléfono de usuario (suscriptor) no se pueden asignar a una cuenta de recursos, solo se pueden usar números de teléfono gratuitos o de pago por servicio.

     Puede asignar un enrutamiento directo o un número híbrido a la cuenta de recursos. Para obtener más información, consulte [Planeamiento del enrutamiento directo y Planeamiento](/MicrosoftTeams/direct-routing-plan) de [operadores automáticos en la nube](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Los números de servicio de enrutamiento directo asignados a cuentas de recursos para el operador automático y las colas de llamadas solo son compatibles con los usuarios y agentes de Microsoft Teams.

7. Cree el operador automático del sistema telefónico o la cola de llamadas. Vea una de las opciones siguientes:

   - [Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Asocie la cuenta de recursos con el operador automático del sistema telefónico o la cola de llamadas que eligió anteriormente.

## <a name="create-a-resource-account-without-a-phone-number"></a>Creación de una cuenta de recursos sin un número de teléfono

En esta sección se describe la creación de una cuenta de recursos que se encuentra en el entorno local. La creación de una cuenta de recursos hospedada en línea se describe en [Administración de cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Estos pasos son necesarios tanto si va a crear un operador automático del sistema telefónico nuevo como a una estructura de cola de llamadas o a una estructura de recompilación creada originalmente en la mensajería unificada de Exchange.

Inicie sesión en el servidor front-end Skype Empresarial y ejecute los siguientes cmdlets de PowerShell:

1. Cree una cuenta de recursos local mediante la ejecución del `New-CsHybridApplicationEndpoint` cmdlet para cada operador automático del sistema telefónico o cola de llamadas, y asigne a cada uno un nombre, una dirección SIP, etc.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

2. (Opcional) Una vez creadas las cuentas de recursos, puede esperar a que AD se sincronice entre en línea y local, o forzar una sincronización y continuar con la configuración en línea del operador automático del sistema telefónico o las colas de llamadas. Para forzar una sincronización, ejecutaría el siguiente comando en el equipo que ejecuta AAD Connect (si aún no lo ha hecho, tendría que cargar `import-module adsync` para ejecutar el comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulte [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obtener más información sobre este comando.

3. Cree el operador automático del sistema telefónico o la cola de llamadas. Vea una de las opciones siguientes:
   - [Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Asocie la cuenta de recursos y el operador automático del sistema telefónico o la cola de llamadas que eligió anteriormente.

## <a name="test-the-implementation"></a>Prueba de la implementación

La mejor manera de probar la implementación es llamar al número configurado para un operador automático del sistema telefónico o una cola de llamadas y conectarse a uno de los agentes o menús. También puede realizar rápidamente una llamada de prueba mediante el **botón Probar** del panel Acción del centro de administración. Si desea realizar cambios en un operador automático del sistema telefónico o en una cola de llamadas, selecciónelo y, a continuación, en el panel Acción, haga clic en **Editar**. 

> [!TIP]
> Si la cuenta de recursos tiene dificultades para asignarse a una cola de llamadas o a un operador automático, consulte [Problemas conocidos de Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) y la sección [Cómo corregir las instancias de aplicaciones híbridas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) en el blog de Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Traslado de un operador automático de mensajería unificada de Exchange o una cola de llamadas al sistema telefónico

La migración de la mensajería unificada de Exchange al sistema telefónico requerirá volver a crear la cola de llamadas y la estructura de operador automático, ya que no se admite la migración directa de una a la otra. Para volver a implementar un conjunto de colas de llamadas y operadores automáticos:

1. Para obtener una lista de todos los operadores automáticos de mensajería unificada de Exchange y las colas de llamadas, ejecute el siguiente comando en el sistema de Exchange 2013 o 2016 mientras ha iniciado sesión como administrador:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Para cada operador automático o cola de llamadas de mensajería unificada de Exchange en la lista, tenga en cuenta su lugar en la estructura, la configuración y obtenga copias de los archivos de sonido o de texto a voz asociados (el guid de la salida será el nombre de una carpeta donde se almacenan los archivos). Para obtener estos detalles, ejecute el comando :

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Consulte [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) para obtener más información sobre este comando. Una lista completa de las opciones que puede que necesite capturar se encuentra en [los miembros UMAutoAttendant](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) , pero las opciones más importantes para anotar son:

    - Horario comercial
    - Horas no laborables
    - Idioma
    - Programación de días festivos

3. Cree nuevos puntos de conexión locales como se describió anteriormente.
   Asigne al operador automático de nivel superior un número temporal con fines de prueba.

4. Configure un operador automático del sistema telefónico o una cola de llamadas que use los puntos de conexión como se describió anteriormente.

5. Pruebe el operador automático del sistema telefónico o la cola de llamadas.

6. Reasignar el número de teléfono vinculado a la cola de llamadas de mensajería unificada de Exchange o al operador automático del sistema telefónico correspondiente o a la cola de llamadas.  

   En este momento, si ya ha migrado el correo de voz de mensajería unificada, debería estar en condiciones de migrar a Exchange Server 2019.

## <a name="see-also"></a>Consulta también

[Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)

[¿Qué son los operadores automáticos en la nube?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planear los operadores automáticos en la nube](plan-cloud-auto-attendant.md)

[Planear las colas de llamadas en la nube](plan-call-queue.md)

[Planear Correo de voz en la nube servicio para usuarios locales](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Administración de cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \( para crear cuentas de recursos hospedados en línea\)