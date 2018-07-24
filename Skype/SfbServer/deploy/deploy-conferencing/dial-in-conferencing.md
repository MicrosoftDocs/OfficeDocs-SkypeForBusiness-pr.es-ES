---
title: Configurar conferencias de acceso telefónico en Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar conferencias de acceso telefónico en Skype para Business Server.'
ms.openlocfilehash: a0ac408fbdf221d565f17c2d714d7aa1765d5097
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982009"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Configurar conferencias de acceso telefónico en Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar conferencias de acceso telefónico en Skype para Business Server.
  
Después de haber creado una topología que incluya la carga de trabajo de conferencia y conferencia de acceso telefónico seleccionada, debe realizar pasos adicionales para configurar conferencias de acceso telefónico. Antes de leer este tema, no olvide ha leído [planear para conferencias de acceso telefónico en Skype para Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [los requisitos de Hardware y software para conferencias en Skype para Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)y el diagrama de flujo de [implementación y el lista de comprobación para conferencia de acceso telefónico](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing). 
  
Para configurar la conferencia de acceso telefónico local, necesita realizar las siguientes tareas:
  
- [Configure dial plans](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configure dial-in conferencing regions](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configure dial-in access numbers](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configure conferencing policies](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
Además, puede realizar las siguientes tareas opcionales. Para obtener más información acerca de estas tareas opcionales, vea [Administrar telefónico en Skype para Business Server](../../manage/conferencing/dial-in-conferencing.md).
  
- Administrar directivas de PIN para las conferencias de acceso telefónico local
    
- Administrar la asignación de teclas para comandos DTMF
    
- Crear directorios de conferencia
    
- Administrar los anuncios al unirse y abandonar conferencias
    
- Probar la configuración de conferencia de acceso telefónico
    
- Enviar un mensaje de correo electrónico de bienvenida a los usuarios de acceso telefónico local
    
## <a name="configure-dial-plans"></a>Configurar planes de marcado
<a name="BKMK_ConfigureDialPlans"> </a>

Al implementar la conferencia de acceso telefónico local, tiene que crear o modificar uno o más planes de marcado para enrutar números de teléfono de acceso telefónico local. También debe asegurarse de que cada plan de marcado contiene al menos una regla de normalización--una regla que convierte extensiones de teléfono en los números de teléfono completo en formato E.164. 
  
Los usuarios de la conferencia de acceso telefónico local se unen a las conferencias como usuarios de empresa autenticados al escribir su número de identificación personal (PIN) y su número de teléfono. Necesita una regla de normalización para convertir las extensiones en números de teléfono completos, de modo que los usuarios puedan autenticarse cuando solo introduzcan una extensión telefónica.
  
Para configurar planes de marcado para las conferencias de acceso telefónico local:
  
- Tanto si implementa la Telefonía IP empresarial como si no, modifique el plan de marcado global para agregar una región de conferencia de acceso telefónico local y para garantizar que una regla de normalización convierta de forma precisa los números de acceso telefónico. Para obtener instrucciones detalladas, consulte [crear o modificar un plan de marcado de Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Si no implementó la Telefonía IP empresarial, cree planes de marcado para los números de acceso a conferencias de acceso telefónico local. Recuerde incluir una región de conferencia de acceso telefónico local. Para obtener instrucciones detalladas, consulte [crear o modificar un plan de marcado de Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Si ha implementado la Telefonía IP empresarial, modifique los planes de marcado de la Telefonía IP empresarial según sea necesario para incluir regiones y usar las reglas de normalización pertinentes para los números de acceso telefónico. También puede crear planes de marcado dedicados que solo se usarán para números de acceso telefónico. Para obtener instrucciones detalladas, consulte [crear o modificar un plan de marcado de Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
Para obtener información detallada sobre la creación de reglas de normalización, vea [crear o modificar una regla de normalización en Skype para la empresa](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Configurar regiones de conferencias de acceso telefónico local
<a name="BKMK_ConfigureDialInRegions"> </a>

Al configurar un plan de marcado, especifica la región de conferencia de acceso telefónico local que se aplica a ese plan de marcado. La región de conferencia de acceso telefónico local asocia los números de acceso a conferencias de acceso telefónico local con el plan de marcado apropiado. Cuando crea el número de acceso telefónico local, selecciona las regiones que asocian el número de acceso con los planes de marcado pertinentes. 
  
Como es importante especificar una región para todos los planes de marcado, le recomendamos que compruebe que todos los planes de marcado tienen regiones de conferencia. 
  
Para comprobar si se ha establecido la región en todos los planes de marcado de conferencia de acceso telefónico local, use el cmdlet **Get-CsDialPlan**. Si a los planes de marcado les falta la región, puede usar el cmdlet **Set-CsDialPlan** para establecer la región. También puede usar Skype para el Panel de Control de servidor empresarial para actualizar la región en los planes de marcado existentes. Para obtener información detallada acerca del uso de Skype para el Panel de Control de servidor empresarial, vea [crear o modificar un plan de marcado de Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Para comprobar si se ha establecido la propiedad Región en los planes de marcado

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Por ejemplo:
    
   ```
   Get-CsDialPlan
   ```

   En este ejemplo, se devuelven todos los planes de marcado configurados para la organización.
    
4. Revise los planes de marcado devueltos para identificar si a alguno le falta la región de conferencias de acceso telefónico local. 
    
Para obtener más información, vea [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>Para establecer la propiedad Región en un plan de marcado

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Para los planes de marcado a los que les falte la región de conferencias de acceso telefónico local, ejecute:
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Por ejemplo:
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   En este ejemplo, se modifica el plan de marcado con la Identity de Redmond para establecer la propiedad DialinConferencingRegion en "Costa oeste de EE. UU.". 
    
Para obtener más información, vea [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).
  
## <a name="configure-dial-in-access-numbers"></a>Configurar números de acceso telefónico local
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Cuando se implementa la característica de conferencia de acceso telefónico local, es necesario establecer números de teléfono que los usuarios puedan marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias. Estos números de acceso telefónico se muestran en invitaciones a reuniones y en la página web de configuración de conferencia de acceso telefónico local.
  
Antes de poder crear números de acceso telefónico local, necesita planear las regiones de conferencia de acceso telefónico local y luego configurar planes de marcado con las regiones. Para obtener información detallada acerca de las regiones, consulte [Plan para conferencias de acceso telefónico en Skype para Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Para obtener información detallada acerca de cómo configurar los planes para conferencias de acceso telefónico de marcado, vea [crear o modificar un plan de marcado de Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
> [!NOTE]
> No puede usar un nuevo número de acceso telefónico local hasta que se complete la replicación de Servicios de dominio de Active Directory (AD DS) de ese número de acceso telefónico local. La replicación puede prolongarse durante varias horas. 
  
> [!NOTE]
> Una vez creados los números de acceso telefónico local, puede modificar el nombre para mostrar de los objetos de contacto de Active Directory, de modo que los usuarios puedan identificar con mayor facilidad el número de acceso correcto. Para modificar el nombre para mostrar, use el cmdlet [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) . No modifique los objetos de Active Directory manualmente.
  
### <a name="to-create-a-dial-in-access-number"></a>Para crear un número de acceso telefónico local

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.
    
4. En la página **Número de acceso telefónico local**, siga uno de estos procedimientos:
    
   - Haga clic en **Nuevo** para abrir **Nuevo número de acceso telefónico local**.
    
   - Haga clic en uno de los números de acceso telefónico local de la lista, haga clic en **Editar** y después haga clic en **Mostrar detalles**.
    
    > [!NOTE]
    > Usar el campo de búsqueda para buscar el contenido de una columna de la lista de números de acceso telefónico no siempre permite obtener los resultados esperados. En lugar de eso, ordene la lista por la columna que le interese para identificar el número de acceso telefónico que desea ver o modificar. 
  
5. En **Número para mostrar**, escriba el número de teléfono que los usuarios de teléfono de la red telefónica conmutada (RTC) marcan para unirse a una conferencia. Este número se muestra en las invitaciones a reuniones y en la página web Configuración de la conferencia de acceso telefónico local.
    
6. En **Nombre para mostrar**, escriba una descripción del número de acceso telefónico local. Éste es el nombre que está asociado con el número de acceso telefónico de Skype para los resultados de búsqueda empresarial. Este número se muestra en el cliente cuando un usuario llama al número de acceso. 
    
7. En **URI de línea**, escriba el número E.164 del número de acceso telefónico local en el formato de URI TEL, con el símbolo + delante del número y sin espacios. Por ejemplo, tel.: +14255550200.
    
    > [!NOTE]
    > El mismo URI de línea no puede volver a usarse por otro número de acceso telefónico a conferencias. 
  
8. En **URI del SIP**, siga este procedimiento:
    
   - En el cuadro de texto, escriba un URI del SIP único para este número de acceso a conferencias de acceso telefónico local. Este URI del SIP se muestra en varias ubicaciones, incluidos, pero sin limitarse, para llamar a los mensajes de notificación y las versiones anteriores de clientes de Lync.
    
    > [!NOTE]
    > El mismo URI del SIP no puede volver a usarse por otro número de acceso telefónico a conferencias. El URI del SIP no puede modificarse una vez creado el número de acceso. El único modo de cambiar el URI del SIP es eliminar y volver a crear el número de acceso. 
  
   - En el cuadro de lista desplegable, haga clic en el dominio de la aplicación de operador de conferencia que admite el número de acceso telefónico.
    
9. En **Grupo de servidores**, haga clic en el grupo que ejecuta la instancia del operador de conferencia que admite el número de acceso telefónico local.
    
    > [!NOTE]
    > Si necesita cambiar el grupo de servidores después de crear el número de acceso, debe usar el cmdlet [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) o eliminar y volver a crear el número de acceso.
  
10. En **Idioma principal**, haga clic en el idioma en el que se mostrarán las indicaciones para este número de acceso telefónico local. 
    
    El idioma principal es el idioma que usa el operador de conferencia para responder la llamada. Los idiomas admitidos se muestran junto a cada número de teléfono de acceso en la página web de configuración de conferencias de acceso telefónico.
    
11. (Opcional) En **Idiomas secundarios (cuatro máximo)**, haga clic en **Agregar**, seleccione uno o más idiomas adicionales que desee poner a disposición de los que llaman a este número de acceso telefónico local y luego haga clic en **Aceptar**. 
    
    Puede seleccionar hasta cuatro idiomas secundarios para cada número acceso telefónico. Los usuarios pueden seleccionar un idioma secundario antes de especificar el ID de conferencia cuando marcan para acceder a una conferencia.
    
12. Para agregar una región para el número de acceso telefónico, en **regiones asociadas**, haga clic en **Agregar**, haga clic en una o más regiones que están asociados con los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.
    
13. Para eliminar una región del número de acceso telefónico local, en **Regiones asociadas**, seleccione la región que desea eliminar y haga clic en **Quitar**.
    
14. Haga clic en **Confirmar**.
    
## <a name="configure-conferencing-policies"></a>Configurar directivas de conferencia
<a name="BKMK_ConfigureConferencingPolicies"> </a>

Las directivas de conferencias son una opción de cuenta de usuario que especifica la experiencia de conferencia de los participantes. Puede crear directivas de conferencia cuyo ámbito sea de sitio o de usuario. La configuración de directiva de conferencias abarca muchos aspectos de la programación de conferencias y de la participación en ellas. Varias configuraciones de directiva de conferencias admiten las conferencias de acceso telefónico local para los participantes. Cuando configure la característica de conferencia de acceso telefónico local, debe comprobar que estos campos estén definidos de la forma apropiada para su organización, y modificarlos según sea necesario. 
  
Para obtener más información acerca de cómo configurar las directivas de conferencia, vea [administrar las directivas de conferencia en Skype para Business Server](../../manage/conferencing/conferencing-policies.md).
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Assign a Line URI to a user account
<a name="BKMK_AssignaLineURI"> </a>

Los usuarios de acceso telefónico local escriben su número de teléfono o extensión y un PIN para participar en conferencias como usuarios autenticados. El **URI de línea** especificado en Skype Business Server las cuentas de usuario de telefonía se requiere para la autenticación.
  
En el procedimiento de este tema se describe cómo asignar un **URI de línea** para una sola cuenta de usuario. Si desea asignar un **URI de línea** para varias cuentas de usuarios, puede crear un script que use el cmdlet **Set-CsUser**. Para obtener información detallada sobre el uso de un script de ejemplo para asignar el **URI de línea** a varias cuentas de usuario, vea [Los URI de línea asignar a varios usuarios](https://go.microsoft.com/fwlink/p/?linkId=196945).
  
1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.
    
2.  Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el campo de búsqueda, escriba el nombre del usuario que desea configurar para las conferencias de acceso telefónico local o haga clic en **Agregar filtro** para especificar campos de búsqueda y después haga clic en **Buscar**.
    
5. Haga doble clic en el nombre de usuario para abrir el cuadro de diálogo **Editar usuario de Skype Empresarial Server**.
    
6. En **Telefonía**, en el campo **URI de línea**, escriba un número de teléfono único y normalizado (por ejemplo, tel.: +14255550200).
    
    > [!NOTE]
    > Puede especificar un **URI de línea** solo si la **Telefonía** está establecida en **Solo de PC a PC**, **Telefonía IP empresarial**, **Control remoto de llamadas** o **Solo control remoto de llamadas**. 
  
7. Haga clic en **Confirmar**.
    

