---
title: Administrar las conferencias de acceso telefónico local en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Resumen: Conozca cómo administrar conferencias de acceso telefónico en Skype para Business Server 2015.'
ms.openlocfilehash: 44427a9109fd061233d1c8676166788e162c7e08
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server-2015"></a>Administrar las conferencias de acceso telefónico local en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a administrar conferencias de acceso telefónico en Skype para Business Server 2015.
  
En este tema se describe cómo administrar las conferencias de acceso telefónico local. Para obtener más información acerca de cómo planear y configurar el acceso telefónico de la conferencia en la implementación, consulte el [Plan de marcado de conferencia en Skype para Business Server 2015](../../plan-your-deployment/conferencing/dial-in-conferencing.md) y [Configurar acceso telefónico conferencia en Skype para Business Server 2015](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Puede realizar las siguientes tareas para administrar conferencias de acceso telefónico: habilitar o deshabilitar conferencias de acceso telefónico, administrar los números de acceso, administrar directivas de NIP para hacer llamadas en conferencia, administrar la incorporación a la conferencia y dejar anuncios, modificar asignaciones de teclas de DTMF comandos y usuarios Bienvenidos a las conferencias de acceso telefónico. 
  
Para obtener más información acerca de cómo administrar planes de marcado, consulte [crear o modificar un plan de marcado de Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Para obtener más información acerca del uso PSTN, consulte [Configurar directivas de voz, registros de uso PSTN y rutas de voz de Skype para negocios 2015](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Administrar conferencias de acceso telefónico mediante Skype para Panel de Control de servidor empresarial

Para administrar la información sobre la conferencia de acceso telefónico local:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia**.
    
Para administrar la información sobre los planes de marcado y el uso de RTC:
  
1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2.  Abre Skype para Panel de Control del servidor de empresa.
    
3. En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Administrar conferencias de acceso telefónico mediante Skype para el Shell de administración de servidor empresarial

Para administrar conferencias de acceso telefónico mediante Skype para el Shell de administración de servidor de negocio, use los siguientes cmdlets:
  
**Opciones de configuración de acceso telefónico**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Devuelve información sobre los directorios de conferencia configurados en su organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera información acerca de cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Devuelve información sobre todos los números de acceso a conferencias de acceso telefónico local que estén configurados para el uso en la organización La conferencia de acceso telefónico permite a los usuarios utilizar un teléfono móvil "normal", o un dispositivo de la red telefónica conmutada (RTC), para unirse a la parte de audio de una conferencia en línea.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Devuelve la configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) que se usa para las conferencias de acceso telefónico local. DTMF permite a los usuarios que participan por teléfono en una conferencia controlar la configuración de la conferencia (por ejemplo, activar y desactivar el audio o bloquear y desbloquear la conferencia) con el teclado numérico del teléfono.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Devuelve una lista de idiomas, incluidos los idiomas regionales o minoritarios, compatibles con Skype para Business Server marcado en conferencias. Estos idiomas se usan para retransmitir mensajes de audio e instrucciones a los usuarios que participan en una conferencia por teléfono.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Devuelve información sobre los planes de marcado usados en la organización.  <br/> |
|[Concesión CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Asigna un plan de marcado a uno o más usuarios o grupos.  <br/> |
|[CsLegacyConferenceDirectory de importación](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa directorios de conferencia de Microsoft Office Communications Server 2007 R2 a Skype para Business Server. Esto ayuda a proporcionar interoperabilidad entre Skype para Business Server y Office Communications Server 2007 R2.  <br/> |
|[Mover CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Mueve un directorio de conferencia existente de un grupo a otro.  <br/> |
|[Nueva CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea un directorio de conferencia para su uso en la organización.  <br/> |
|[Nueva CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un número de acceso para conferencia de acceso telefónico local.  <br/> |
|[Nueva CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de conferencias de acceso telefónico local. Estos ajustes determinan cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico. Concretamente, la información se devuelve dependiendo de si es necesario o no que los participantes graben su nombre cuando se unen a una conferencia y de cómo (o si) el sistema anuncia que alguien se ha unido a la conferencia o la ha abandonado.  <br/> |
|[Nueva CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crea una recopilación de configuraciones de señalización de tono de marcado de frecuencia múltiple (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[Nueva CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un plan de marcado.  <br/> |
|[Quitar CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Quita un directorio de conferencia existente.  <br/> |
|[Quitar CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Quita un número de acceso de conferencias de acceso telefónico local.  <br/> |
|[Quitar CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Quita una o más colecciones de la configuración de conferencia de acceso telefónico local. Estos ajustes determinan cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico.  <br/> |
|[Quitar CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Quita una colección existente de opciones de configuración de señalización de tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Conjunto de CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica los valores de propiedad de un número de acceso de conferencia de acceso telefónico.  <br/> |
|[Conjunto de CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica opciones que determinan cómo Skype para Business Server responde cuando los usuarios unirse o abandonar una conferencia de acceso telefónico.  <br/> |
|[Conjunto de CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica la configuración de señalización tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Conjunto de CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un plan de marcado existente.  <br/> |
   
**Configuración de la directiva de NIP**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Devuelve información sobre las directivas del número de identificación personal (PIN) de los clientes configuradas para el uso en la organización. Autenticación de PIN permite a los usuarios acceder a Skype para Business Server con un PIN en lugar de un nombre de usuario y una contraseña.  <br/> |
|[Concesión CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Asigna una directiva de número de identificación personal (PIN) de cliente a un usuario o a un grupo de usuarios.  <br/> |
|[Nueva CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea una nueva directiva de número de identificación personal (PIN) de cliente.  <br/> |
|[Quitar CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Elimina la directiva especificada de número de identificación personal (PIN).  <br/> |
|[Conjunto de CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica una o varias directivas de número de identificación personal (PIN) de cliente.  <br/> |
   

