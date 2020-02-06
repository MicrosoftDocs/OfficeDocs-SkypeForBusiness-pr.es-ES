---
title: Administrar conferencias de acceso telefónico local en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Resumen: Obtenga información sobre cómo administrar las conferencias de acceso telefónico local en Skype empresarial Server.'
ms.openlocfilehash: ba8b62456a1fa2024f2cf37642658e76d528ebf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818581"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Administrar conferencias de acceso telefónico local en Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar las conferencias de acceso telefónico local en Skype empresarial Server.
  
En este tema se describe cómo administrar las conferencias de acceso telefónico local. Para obtener más información sobre cómo planear y configurar las conferencias de acceso telefónico local en la implementación, consulte [planear la Conferencia de acceso telefónico local en Skype empresarial Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) y [configurar conferencias de acceso telefónico local en Skype empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Puede realizar las siguientes tareas para administrar las conferencias de acceso telefónico local: habilitar o deshabilitar las conferencias de acceso telefónico local, administrar números de acceso, administrar directivas de PIN para realizar conferencias de acceso telefónico local, administrar la combinación de conferencia y abandonar las asignaciones de teclas para DTMF y les da la bienvenida a las conferencias de acceso telefónico local. 
  
Para obtener más información sobre la administración de planes de marcado, consulte [crear o modificar un plan de marcado en Skype empresarial Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Para obtener más información sobre el uso de RTC, consulte [configurar directivas de voz, registros de uso de RTC y rutas de voz en Skype empresarial](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Administrar conferencias de acceso telefónico local con el panel de control de Skype empresarial Server

Para administrar la información sobre la conferencia de acceso telefónico local:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia**.
    
Para administrar la información sobre los planes de marcado y el uso de RTC:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abra el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Administrar conferencias de acceso telefónico local con el shell de administración de Skype empresarial Server

Para administrar las conferencias de acceso telefónico local mediante el shell de administración de Skype empresarial Server, use los siguientes cmdlets:
  
**Opciones de configuración de conferencia de acceso telefónico local**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Devuelve información sobre los directorios de conferencia configurados en su organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera información sobre cómo responde Skype empresarial Server cuando los usuarios se unen o salen de una conferencia de acceso telefónico local.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Devuelve información sobre todos los números de acceso a conferencias de acceso telefónico local que estén configurados para el uso en la organización La conferencia de acceso telefónico permite a los usuarios utilizar un teléfono móvil "normal", o un dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia en línea.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Devuelve la configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) que se usa para las conferencias de acceso telefónico local. DTMF permite a los usuarios que participan por teléfono en una conferencia controlar la configuración de la conferencia (por ejemplo, activar y desactivar el audio o bloquear y desbloquear la conferencia) con el teclado numérico del teléfono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Devuelve una lista de idiomas, incluidos los idiomas regionales e minoritarios, que se pueden usar con las conferencias de acceso telefónico local de Skype empresarial Server. Estos idiomas se usan para retransmitir mensajes de audio e instrucciones a los usuarios que participan en una conferencia por teléfono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Devuelve información sobre los planes de marcado usados en la organización.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Asigna un plan de marcado a uno o más usuarios o grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa directorios de conferencia de Microsoft Office Communications Server 2007 R2 a Skype empresarial Server. Esto ayuda a proporcionar una interoperabilidad entre Skype empresarial Server y Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Mueve un directorio de conferencia existente de un grupo a otro.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea un directorio de conferencia para su uso en la organización.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un número de acceso para conferencia de acceso telefónico local.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de conferencias de acceso telefónico local. Esta configuración determina cómo responde Skype empresarial Server cuando los usuarios se unen a una conferencia de acceso telefónico local o salen de ella. Concretamente, la información se devuelve dependiendo de si es necesario o no que los participantes graben su nombre cuando se unen a una conferencia y de cómo (o si) el sistema anuncia que alguien se ha unido a la conferencia o la ha abandonado.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crea una recopilación de configuraciones de señalización de tono de marcado de frecuencia múltiple (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un plan de marcado.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Quita un directorio de conferencia existente.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Quita un número de acceso de conferencias de acceso telefónico local.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Quita una o más colecciones de la configuración de conferencia de acceso telefónico local. Esta configuración determina cómo responde Skype empresarial Server cuando los usuarios se unen a una conferencia de acceso telefónico local o salen de ella.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Quita una colección existente de opciones de configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica los valores de propiedad de un número de acceso de conferencia de acceso telefónico.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica la configuración que determina cómo responde Skype empresarial Server cuando los usuarios se unen o salen de una conferencia de acceso telefónico local.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica la configuración de señalización tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un plan de marcado existente.  <br/> |
   
**Configuración de la directiva de PIN**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas del número de identificación personal (PIN) de los clientes configuradas para el uso en la organización. La autenticación con PIN permite a los usuarios acceder a Skype empresarial Server proporcionando un PIN en lugar de un nombre de usuario y una contraseña.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Asigna una directiva de número de identificación personal (PIN) de cliente a un usuario o a un grupo de usuarios.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea una nueva directiva de número de identificación personal (PIN) de cliente.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Elimina la directiva especificada de número de identificación personal (PIN).  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica una o varias directivas de número de identificación personal (PIN) de cliente.  <br/> |
   

