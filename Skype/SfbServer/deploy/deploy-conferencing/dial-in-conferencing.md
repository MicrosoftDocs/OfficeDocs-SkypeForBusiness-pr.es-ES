---
title: Configurar conferencias de acceso telefónico local en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Resumen: lea este tema para obtener información sobre cómo configurar las conferencias de acceso telefónico local en Skype Empresarial Server.'
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103856"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Configurar conferencias de acceso telefónico local en Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar las conferencias de acceso telefónico local en Skype Empresarial Server.
  
Después de crear una topología que incluya la carga de trabajo de conferencia y las conferencias de acceso telefónico local seleccionadas, debe realizar pasos adicionales para configurar las conferencias de acceso telefónico local. Antes de leer este tema, asegúrese de leer [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), Hardware and software requirements for [conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)y [el](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)diagrama de flujo de implementación y la lista de comprobación para conferencias de acceso telefónico local . 
  
Para configurar las conferencias de acceso telefónico local, debe realizar las siguientes tareas:
  
- [Configurar planes de marcado](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configurar regiones de conferencia de acceso telefónico local](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configurar números de acceso telefónico](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configurar directivas de conferencia](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Asignar un URI de línea a una cuenta de usuario](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
Además, puede realizar las siguientes tareas opcionales. Para obtener más información acerca de estas tareas opcionales, vea [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).
  
- Administrar directivas de PIN para conferencias de acceso telefónico local
    
- Administrar la asignación de claves para comandos DTMF
    
- Crear directorios de conferencia
    
- Administrar anuncios de unirse y dejar conferencias
    
- Probar la configuración de conferencia de acceso telefónico local
    
- Enviar correo de bienvenida a usuarios de acceso telefónico
    
## <a name="configure-dial-plans"></a>Configurar planes de marcado
<a name="BKMK_ConfigureDialPlans"> </a>

Al implementar conferencias de acceso telefónico local, debe crear o modificar uno o varios planes de marcado para enrutar números de teléfono de acceso telefónico local. También debe asegurarse de que cada plan de marcado contenga al menos una regla de normalización, una regla que convierte las extensiones telefónicas en números de teléfono completos en formato E.164. 
  
Los usuarios de conferencias de acceso telefónico local se unen a conferencias como usuarios de empresa autenticados especificando su número de identificación personal (PIN) y su número de teléfono. Necesita una regla de normalización para convertir extensiones en números de teléfono completos para que los usuarios puedan autenticarse cuando escriben solo una extensión telefónica.
  
Para configurar planes de marcado para conferencias de acceso telefónico local:
  
- Tanto si implementa Telefonía IP empresarial, modifique el plan de marcado global para agregar una región de conferencia de acceso telefónico local y para asegurarse de que una regla de normalización convierte con precisión los números de acceso telefónico local. Para obtener instrucciones detalladas, vea [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Si no implementó Telefonía IP empresarial, cree planes de marcado para los números de acceso de conferencia de acceso telefónico local. Asegúrese de incluir una región de conferencia de acceso telefónico local. Para obtener instrucciones detalladas, vea [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Si implementó Telefonía IP empresarial, modifique Telefonía IP empresarial de marcado según sea necesario para incluir regiones y usar las reglas de normalización adecuadas para los números de acceso telefónico. También puede crear planes de marcado dedicados que solo se usan para números de acceso telefónico. Para obtener instrucciones detalladas, vea [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
Para obtener más información sobre cómo crear reglas de normalización, vea [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Configurar regiones de conferencia de acceso telefónico local
<a name="BKMK_ConfigureDialInRegions"> </a>

Cuando se configura un plan de marcado, se especifica la región de conferencias de acceso telefónico local que se aplica a dicho plan de marcado. La región de conferencia de acceso telefónico local asocia los números de acceso de conferencia de acceso telefónico local con el plan de marcado adecuado. Cuando se crea el número de acceso telefónico local, se seleccionan las regiones que asocian el número de acceso con los planes de marcado pertinentes. 
  
Dado que es importante especificar una región para todos los planes de marcado, se recomienda comprobar que todos los planes de marcado tienen regiones de conferencia. 
  
Para comprobar si la región está establecida para todos los planes de marcado de conferencia de acceso telefónico local, use el cmdlet **Get-CsDialPlan.** Si falta la región en los planes de marcado, puede usar el cmdlet **Set-CsDialPlan** para establecerla. También puede usar el Panel de control de Skype Empresarial Server para actualizar la región en los planes de marcado existentes. Para obtener más información acerca del uso del Panel de control de Skype Empresarial Server, vea [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Para comprobar si se ha establecido la propiedad Región en los planes de marcado

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
3. Ejecute los siguientes comandos en símbolo del sistema:
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Por ejemplo:
    
   ```powershell
   Get-CsDialPlan
   ```

   En este ejemplo, se devuelven todos los planes de marcado configurados para la organización.
    
4. Revise los planes de marcado devueltos para identificar si a alguno le falta la región de conferencias de acceso telefónico local. 
    
Para obtener más información, [vea Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps).
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>Para establecer la propiedad Región en un plan de marcado

1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.
    
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en Inicio **,** en Todos los programas **,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración **de Skype Empresarial Server**.
    
3. Para los planes de marcado a los que les falte la región de conferencias de acceso telefónico local, ejecute:
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Por ejemplo:
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   En este ejemplo, se modifica el plan de marcado con la identidad de Redmond para establecer la propiedad DialinConferencingRegion en "Us West Coast". 
    
Para obtener más información, [vea Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps).
  
## <a name="configure-dial-in-access-numbers"></a>Configurar números de acceso telefónico
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Al implementar conferencias de acceso telefónico local, debe configurar los números de teléfono que los usuarios pueden marcar desde la red telefónica conmutada (RTC) para unirse a la parte de audio de las conferencias. Estos números de acceso telefónico local aparecen en las invitaciones a reuniones y en la página web Configuración de conferencia de acceso telefónico local.
  
Para poder crear números de acceso telefónico local, primero debe planear las regiones de conferencia de acceso telefónico local y, a continuación, configurar los planes de marcado con las regiones. Para obtener más información acerca de las regiones, vea [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Para obtener más información sobre cómo configurar planes de marcado para conferencias de acceso telefónico local, vea [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
> [!NOTE]
> No puede usar un nuevo número de acceso telefónico local hasta que se complete la replicación de servicios de dominio de Active Directory (AD DS) de ese número de acceso. La replicación puede tardar varias horas en completarse. 
  
> [!NOTE]
> Después de crear números de acceso telefónico local, puede modificar el nombre para mostrar de los objetos de contacto de Active Directory para que los usuarios puedan identificar más fácilmente el número de acceso correcto. Para modificar el nombre para mostrar, use el cmdlet [Set-CsDialInConferencingAccessNumber.](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) No debe modificar objetos de Active Directory manualmente.
  
### <a name="to-create-a-dial-in-access-number"></a>Para crear un número de acceso telefónico

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.
    
4. En la **página Número de acceso telefónico,** realice una de las siguientes acciones:
    
   - Haga **clic en** Nuevo para abrir Nuevo número de acceso **telefónico.**
    
   - Haga clic en uno de los números de acceso telefónico en la lista, haga clic **en Editar** y, a continuación, haga clic en **Mostrar detalles.**
    
     > [!NOTE]
     > El uso del campo de búsqueda para buscar el contenido de una columna en la lista de números de acceso telefónico no puede producir los resultados esperados. En su lugar, ordena la lista por la columna de interés para identificar el número de acceso telefónico que quieres ver o cambiar. 
  
5. En **Número de pantalla**, escriba el número de teléfono que los usuarios telefónicos de la red telefónica conmutada (RTC) marcan para unirse a una conferencia. Este número se muestra en invitaciones a reuniones y en la página web Configuración de conferencia de acceso telefónico local.
    
6. En **Nombre para mostrar,** escriba una descripción para el número de acceso telefónico. Este es el nombre asociado al número de acceso telefónico en los resultados de búsqueda de Skype Empresarial. Este nombre se muestra en el cliente cuando un usuario llama al número de acceso. 
    
7. En **URI** de línea , escriba el número E.164 del número de acceso telefónico en formato URI de TEL, incluido el símbolo + antes del número y excluyendo espacios. Por ejemplo, tel:+14255550200.
    
    > [!NOTE]
    > Otro número de acceso de conferencia de acceso telefónico local no puede reutilizar el mismo URI de línea. 
  
8. En **URI de SIP,** haga lo siguiente:
    
   - En el cuadro de texto, escriba un URI SIP único para este número de acceso de conferencia de acceso telefónico local. Este URI de SIP se muestra en varias ubicaciones, incluidos, entre otros, los mensajes de notificación de llamadas y las versiones anteriores de los clientes de Lync.
    
     > [!NOTE]
     > Otro número de acceso de conferencia de acceso telefónico local no puede reutilizar el mismo URI de SIP. El URI de SIP no se puede modificar después de crear el número de acceso. La única forma de cambiar el URI de SIP es eliminar y volver a crear el número de acceso. 
  
   - En el cuadro de lista desplegable, haga clic en el dominio de la aplicación operador de conferencia que admite este número de acceso telefónico local.
    
9. En **Grupo** de servidores, haga clic en el grupo que ejecuta la instancia de Operador de conferencia que admite este número de acceso telefónico local.
    
    > [!NOTE]
    > Si necesita cambiar el grupo después de crear el número de acceso, debe usar el cmdlet [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) o eliminar y volver a crear el número de acceso.
  
10. En **Idioma principal,** haga clic en el idioma en el que se reproducen los mensajes de este número de acceso telefónico local. 
    
    El idioma principal es el idioma que usa el operador de conferencia para responder a la llamada. Los idiomas admitidos se muestran junto con cada número de teléfono de acceso en la página web Configuración de conferencia de acceso telefónico local.
    
11. (Opcional) En **Idiomas** secundarios (máximo de cuatro), haga clic en Agregar **,** seleccione uno o más idiomas adicionales que desee admitir para los autores de llamadas a este número de acceso telefónico local y, a continuación, haga clic en **Aceptar**. 
    
    Puede elegir hasta cuatro idiomas secundarios para cada número de acceso telefónico local. Los usuarios pueden seleccionar un idioma secundario antes de escribir el identificador de conferencia cuando llamen a una conferencia.
    
12. Para agregar una región para el número de acceso telefónico, en Regiones **asociadas,** haga clic en Agregar **,** haga clic en una o más regiones asociadas con los planes de marcado para este número de acceso telefónico y, a continuación, haga clic en **Aceptar**.
    
13. Para eliminar una región del número de acceso telefónico, en Regiones **asociadas,** haga clic en la región que desea eliminar y, a continuación, haga clic en **Quitar**.
    
14. Haga clic en **Confirmar**.
    
## <a name="configure-conferencing-policies"></a>Configurar directivas de conferencia
<a name="BKMK_ConfigureConferencingPolicies"> </a>

Las directivas de conferencias son una opción de cuenta de usuario que especifica la experiencia de conferencia de los participantes. Puede crear directivas de conferencia cuyo ámbito sea de sitio o de usuario. La configuración de directiva de conferencias abarca muchos aspectos de la programación de conferencias y de la participación en ellas. Varias configuraciones de directiva de conferencias admiten las conferencias de acceso telefónico local para los participantes. Cuando configure la característica de conferencia de acceso telefónico local, debe comprobar que estos campos estén definidos de la forma apropiada para su organización, y modificarlos según sea necesario. 
  
Para obtener más información acerca de cómo configurar directivas de conferencia, vea [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Asignar un URI de línea a una cuenta de usuario
<a name="BKMK_AssignaLineURI"> </a>

Los usuarios de acceso telefónico escriben su número de teléfono o extensión y un PIN para participar en conferencias como usuarios autenticados. El URI de **línea de** telefonía especificado en las cuentas de usuario de Skype Empresarial Server es necesario para la autenticación.
  
En el procedimiento de este tema se explica cómo asignar un **URI de línea** para una sola cuenta de usuario. Si desea asignar un **URI de línea** para varias cuentas de usuario, puede crear un script que use el cmdlet **Set-CsUser**. Para obtener más información sobre cómo usar un script de ejemplo para asignar **uri** de línea a varias cuentas de usuario, vea Asignar URI de línea a [varios usuarios.](https://go.microsoft.com/fwlink/p/?linkId=196945)
  
1. Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.
    
2.  Abra el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el campo de búsqueda, escriba el nombre del usuario que desea configurar para las conferencias de acceso telefónico local o haga clic en **Agregar filtro** para especificar campos de búsqueda y, a continuación, haga clic en **Buscar**.
    
5. Haga doble clic en el nombre de usuario para abrir el cuadro de diálogo Editar usuario de Skype Empresarial **Server.**
    
6. En **Telefonía**, en el campo **URI de línea**, escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200).
    
    > [!NOTE]
    > Solo puede especificar **uri** de línea si **telefonía** está establecida en solo pc **a pc**, **Telefonía IP empresarial**, **control** remoto de llamadas o control remoto de **llamadas solo**. 
  
7. Haga clic en **Confirmar**.
