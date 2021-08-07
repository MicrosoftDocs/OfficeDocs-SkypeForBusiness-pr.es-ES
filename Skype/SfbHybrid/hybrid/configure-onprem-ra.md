---
title: Configurar una cuenta de recurso en Skype Empresarial Server 2019
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
localization_priority: Normal
ms.collection: ''
description: Configurar una cuenta de recurso para Skype Empresarial Server 2019.
ms.openlocfilehash: 87db9779a6f90730d6aa53e3084a2014a71bad5aba91844d2e545f7d78ae37cf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304702"
---
# <a name="configure-resource-accounts"></a>Configurar cuentas de recursos

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Empresarial Server implementaciones híbridas de 2019 solo usan servicios en la nube proporcionados por Sistema telefónico para mensajería unificada y no se integran con Exchange Online. En Skype Empresarial Server 2019, ahora puede usar las colas de llamadas en la nube y los operadores automáticos que se describen en Esto es lo que obtiene con Sistema telefónico en Microsoft 365 o [Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

Para usar un operador automático de Sistema telefónico o una cola de llamadas con Skype Empresarial Server 2019, deberá crear cuentas de recursos que actúen como extremos de aplicación y se puedan asignar números de teléfono y, a continuación, use el Centro de administración de Teams en línea para configurar la cola de llamadas o el operador automático. Esta cuenta de recurso se puede hospedar en línea (vea Administrar cuentas de recursos en [Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) para crear cuentas de recursos en línea) o local, como se describe en este artículo. Normalmente, tendrá varios nodos Sistema telefónico operador automático o cola de llamadas, cada uno de los cuales está asignado a una cuenta de recursos, que se puede hospedar en línea o en Skype Empresarial Server 2019.

Si ya tiene un operador automático de mensajería unificada de Exchange y un sistema de cola de llamadas, antes de cambiar a Exchange Server 2019 o Exchange en línea, deberá registrar manualmente los detalles como se describe a continuación y, a continuación, implementar un sistema completamente nuevo mediante el Centro de administración de Teams.

## <a name="overview"></a>Información general

Si su Sistema telefónico operador automático o cola de llamadas necesitará un número de servicio, las distintas dependencias se pueden cumplir en la siguiente secuencia:

1. Obtener un número de servicio.
2. Obtener una licencia Sistema telefónico: licencia de usuario [virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user) o una licencia de Sistema telefónico de pago para usar con la cuenta de recurso.
3. Cree la cuenta de recurso. Se necesita un operador automático o una cola de llamadas para tener una cuenta de recurso asociada.
4. Espere una sincronización de Active Directory entre en línea y local.
5. Asigne la Sistema telefónico a la cuenta de recurso.
6. Asigne un número de servicio a la cuenta de recurso.
7. Cree una cola Sistema telefónico llamada o un operador automático.
8. Asocie la cuenta de recurso con un operador automático o una cola de llamadas: (New-CsApplicationInstanceAssociation).

Si el operador automático o la cola de llamadas están anidados en un operador automático de nivel superior, la cuenta de recurso asociada solo necesita un número de teléfono si desea varios puntos de entrada en la estructura de operadores automáticos y colas de llamadas.

Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitadas para Telefonía IP empresarial o tener planes de Microsoft 365 o Office 365 llamadas. Consulte [Asignar Microsoft Teams licencias](/MicrosoftTeams/assign-teams-licenses). Para habilitarlos para Telefonía IP empresarial, puede usar Windows PowerShell. Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

Si el Teléfono automático del sistema o la cola de llamadas que está creando se anidarán y no necesitarán un número de teléfono, el proceso es:

1. Crear la cuenta de recurso  
2. Esperar una sincronización de Active Directory entre online y local
3. Crear un operador Sistema telefónico automático o cola de llamadas
4. Asociar la cuenta de recurso con un operador Sistema telefónico automático o cola de llamadas

## <a name="create-a-resource-account-with-a-phone-number"></a>Crear una cuenta de recurso con un número de teléfono

Crear una cuenta de recurso que use un número de teléfono requeriría realizar las siguientes tareas en el siguiente orden:

1. Puerto u obtener un número de servicio gratuito o de pago. El número no se puede asignar a ninguna otra cuenta de recursos o servicios de voz.

   Antes de asignar un número de teléfono a una cuenta de recursos, deberá obtener o portabilidad los números de servicio gratuitos o de pago existentes. Después de obtener los números de teléfono de servicio gratuito o de pago **Microsoft Teams,** aparecerán en un centro de administración números de voz Teléfono y el tipo de número enumerado aparecerá como  >    >   **Servicio -**  Gratuito . Para obtener los números de servicio, vea [Obtener](/MicrosoftTeams/getting-service-phone-numbers) números de teléfono de servicio o si desea transferir un número de servicio existente, vea Transferir números de teléfono [a Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

   Si está fuera de los Estados Unidos, no puede usar el centro de administración Microsoft Teams para obtener números de servicio. Vaya a [Administrar números de teléfono para su organización](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.

2. Comprar una Sistema telefónico licencia. Vea:  
   - [Sistema telefónico de usuario virtual](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [Office 365 Enterprise E1 y E3](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [Office 365 Enterprise E5](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [Office 365 Enterprise Software empresarial de E5](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. Cree una cuenta de recurso local ejecutando el cmdlet para cada operador automático o cola de llamadas de Sistema telefónico y asigne a cada uno un nombre, una dirección `New-CsHybridApplicationEndpoint` sip, entre otros.

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

4. (Opcional) Una vez creadas las cuentas de recursos, puede esperar a que AD se sincronice entre en línea y local Sistema telefónico, o forzar una sincronización y continuar con la configuración en línea de un operador automático o colas de llamadas. Para forzar una sincronización, ejecutaría el siguiente comando en el equipo que ejecuta AAD Conectar (si no lo ha hecho ya, tendría que cargar para ejecutar `import-module adsync` el comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulta [Start-ADSyncSyncCycle para](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) obtener más información sobre este comando.
    
    Nota: en este momento, es posible que la cuenta se haya sincronizado, pero es posible que el aprovisionamiento no esté completo.  Compruebe el resultado de [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).  Si el punto de conexión sincronizado aún no ha completado el aprovisionamiento, no aparecerá aquí.  Puede comprobar el estado de las solicitudes de aprovisionamiento en el portal M365 [en Teams estado de instalación](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).  Esta fase de aprovisionamiento puede tardar hasta 24 horas.

5. Asigne la Sistema telefónico: usuario virtual o Sistema telefónico licencia a la cuenta de recurso. Consulte [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) y [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).

   Si va a asignar un número de teléfono a una cuenta de recursos, ahora puede usar la licencia gratuita Sistema telefónico - Licencia de usuario virtual. Esto proporciona Sistema telefónico funcionalidades a los números de teléfono en el nivel de la organización y le permite crear funciones de operador automático y cola de llamadas.


6. Asigne el número de servicio a la cuenta de recurso. Use el `Set-CsHybridApplicationEndpoint` comando para asignar un número de teléfono (con la opción -LineURI) a la cuenta de recurso.

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    Vea [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

    Para asignar un enrutamiento directo o un número híbrido a una cuenta de recurso, use el siguiente cmdlet:

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   La cuenta de recurso necesitará un número de teléfono asignado si se asignará a un operador automático de nivel superior o a una cola de llamadas. Los números de teléfono de usuario (suscriptor) no se pueden asignar a una cuenta de recursos, solo se pueden usar números de teléfono gratuitos o de pago.

     Puede asignar un enrutamiento directo o un número híbrido a su cuenta de recurso. Para obtener más información, vea [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and Plan Cloud auto [attendants](plan-cloud-auto-attendant.md).

     > [!NOTE]
     > Los números de servicio de enrutamiento directo asignados a cuentas de recursos para el operador automático y las colas de llamadas solo se admiten Microsoft Teams usuarios y agentes.

7. Cree el Sistema telefónico operador automático o la cola de llamadas. Vea una de las opciones siguientes:

   - [Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. Asocie la cuenta de recurso con Sistema telefónico operador automático o cola de llamadas que eligió anteriormente.

## <a name="create-a-resource-account-without-a-phone-number"></a>Crear una cuenta de recurso sin número de teléfono

En esta sección se describe la creación de una cuenta de recursos que se encuentra en el entorno local. La creación de una cuenta de recurso que está en línea se describe en Administrar cuentas de recursos [en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).

Estos pasos son necesarios tanto si va a crear un operador automático o una estructura de cola de llamadas Sistema telefónico nueva, como si está creando una estructura de reconstrucción originalmente en Exchange mensajería unificada.

Inicie sesión en el Skype Empresarial front-end y ejecute los siguientes cmdlets de PowerShell:

1. Cree una cuenta de recurso local ejecutando el cmdlet para cada operador automático o cola de llamadas de Sistema telefónico y asigne a cada uno un nombre, una dirección `New-CsHybridApplicationEndpoint` sip, entre otros.

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    Consulte [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obtener más información sobre este comando.

2. (Opcional) Una vez creadas las cuentas de recursos, puede esperar a que AD se sincronice entre en línea y local Sistema telefónico, o forzar una sincronización y continuar con la configuración en línea de un operador automático o colas de llamadas. Para forzar una sincronización, ejecutaría el siguiente comando en el equipo que ejecuta AAD Conectar (si no lo ha hecho ya, tendría que cargar para ejecutar `import-module adsync` el comando):

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    Consulta [Start-ADSyncSyncCycle para](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) obtener más información sobre este comando.

3. Cree el Sistema telefónico operador automático o la cola de llamadas. Vea una de las opciones siguientes:
   - [Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. Asocie la cuenta de recurso y Sistema telefónico operador automático o cola de llamadas que eligió anteriormente.

## <a name="test-the-implementation"></a>Probar la implementación

La mejor manera de probar la implementación es llamar al número configurado para un operador automático o cola de llamadas de Sistema telefónico y conectarse a uno de los agentes o menús. También puede realizar rápidamente una llamada de prueba mediante el botón **Probar** en el panel acción del centro de administración. Si desea realizar cambios en un operador Sistema telefónico automático o cola de llamadas, selecciónelo y, a continuación, en el panel Acción, haga clic en **Editar**. 

> [!TIP]
> Si su cuenta de recurso tiene dificultades para asignarse a una cola de llamadas o un operador automático, consulte Problemas conocidos de [Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) y la sección Cómo corregir mis instancias de aplicación híbrida [en](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) el blog de Microsoft Teams.

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a>Mover un operador Exchange de mensajería unificada o una cola de llamadas a Sistema telefónico

La migración Exchange de mensajería unificada a Sistema telefónico requiere volver a crear la cola de llamadas y la estructura del operador automático, ya que no se admite la migración directa de una a otra. Para volver a implementar un conjunto de colas de llamadas y operadores automáticos:

1. Para obtener una lista de todos Exchange operadores automáticos de mensajería unificada y colas de llamadas, ejecute el siguiente comando en el sistema de Exchange 2013 o 2016 mientras inició sesión como administrador:

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. Para cada cola de llamadas de mensajería unificada o operador automático que aparece en la lista, anote su lugar en la estructura, la configuración y obtenga copias de los archivos de sonido o texto a voz asociados (el guid de la salida será el nombre de una carpeta donde se almacenan los archivos). Exchange Para obtener estos detalles, ejecute el comando:

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    Vea [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) para obtener más información sobre este comando. Una lista completa de opciones que es posible que necesite capturar es en los miembros [de UMAutoAttendant,](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) pero las opciones más importantes a tener en cuenta son:

    - Horario comercial
    - Horario no comercial
    - Idioma
    - Programación de días festivos

3. Cree nuevos extremos locales como se describió anteriormente.
   Asigne al operador automático de nivel superior un número temporal con fines de prueba.

4. Configure un Sistema telefónico automático o cola de llamadas que use los extremos como se describió anteriormente.

5. Pruebe el operador Sistema telefónico automático o la cola de llamadas.

6. Reasigna el número de teléfono vinculado a la cola Exchange llamada de mensajería unificada o al operador automático al operador Sistema telefónico o cola de llamadas.  

   En este momento, si ya ha migrado el correo de voz de mensajería unificada, debería estar en posición de migrar a Exchange Server 2019.

## <a name="see-also"></a>Consulte también

[Crear una cola de llamadas en la nube](/MicrosoftTeams/create-a-phone-system-call-queue)

[¿Qué son los operadores automáticos en la nube?](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[Configurar un operador automático en la nube](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[Planear los operadores automáticos en la nube](plan-cloud-auto-attendant.md)

[Planear las colas de llamadas en la nube](plan-call-queue.md)

[Planeación Correo de voz en la nube servicio para usuarios locales](plan-cloud-voicemail.md)

[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[Administrar cuentas de recursos en Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( para crear cuentas de recursos en línea\)