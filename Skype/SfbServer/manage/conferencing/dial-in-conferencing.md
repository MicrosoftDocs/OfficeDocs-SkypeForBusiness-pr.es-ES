---
title: Administrar conferencias de acceso telefónico local en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Resumen: obtenga información sobre cómo administrar las conferencias de acceso telefónico local en Skype Empresarial Server.'
ms.openlocfilehash: 3c6f72d3e2c5e19ef970e7d8e5410dcc9cad2d14
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772066"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Administrar conferencias de acceso telefónico local en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo administrar las conferencias de acceso telefónico local en Skype Empresarial Server.
  
En este tema se describe cómo administrar conferencias de acceso telefónico local. Para obtener más información sobre cómo planear y configurar conferencias de acceso telefónico local en la implementación, vea [Plan for dial-in conferencing in Skype Empresarial Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) y Configure [dial-in conferencing in Skype Empresarial Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Puede realizar las siguientes tareas para administrar conferencias de acceso telefónico local: habilitar o deshabilitar conferencias de acceso telefónico local, administrar números de acceso, administrar directivas de PIN para la conferencia de acceso telefónico local, administrar anuncios de unión y salida de conferencias, modificar asignaciones de teclas para comandos DTMF y dar la bienvenida a los usuarios a las conferencias de acceso telefónico local. 
  
Para obtener más información acerca de la administración de planes de marcado, vea [Create or modify a dial plan in Skype Empresarial Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Para obtener más información sobre el uso de RTC, vea [Configure voice policies, PSTN usage records, and voice routes in Skype Empresarial](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Administrar conferencias de acceso telefónico local mediante Skype Empresarial Server Panel de control

Para administrar información sobre conferencias de acceso telefónico local:
  
1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia**.
    
Para administrar información sobre los planes de marcado y el uso de RTC:
  
1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2.  Abra Skype Empresarial Server Panel de control.
    
3. En la barra de navegación izquierda, haga clic **en Enrutamiento de voz.**
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Administrar conferencias de acceso telefónico local mediante Skype Empresarial Server Shell de administración

Para administrar conferencias de acceso telefónico local mediante Skype Empresarial Server Shell de administración, use los cmdlets siguientes:
  
**Opciones de configuración de acceso telefónico**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Devuelve información sobre los directorios de conferencia configurados en su organización. Los directorios de conferencia se usan para ayudar a los usuarios de conferencia de acceso telefónico local a localizar la información de conferencias.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera información sobre cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Devuelve información sobre todos los números de acceso a conferencias de acceso telefónico local configurados para su uso en la organización.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Devuelve la configuración de señalización de frecuencia múltiple de tono dual (DTMF) usada para conferencias de acceso telefónico local. El DTMF permite a los usuario que obtengan acceso telefónico a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio o bloquear y desbloquear la conferencia) mediante el teclado de su teléfono.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Devuelve una lista de idiomas, incluidos los idiomas regionales o minoritarios, admitidos para su uso con Skype Empresarial Server conferencias de acceso telefónico local. Estos idiomas se usan para retransmitir mensajes de audio e instrucciones a los usuarios que participan en una conferencia por teléfono.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Devuelve información sobre los planes de marcado usados en la organización.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Asigna un plan de marcado a uno o más usuarios o grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa directorios de conferencia de Microsoft Office Communications Server 2007 R2 a Skype Empresarial Server. Esto ayuda a proporcionar interoperabilidad entre Skype Empresarial Server y Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Mueve un directorio de conferencia existente de un grupo a otro.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Crea un directorio de conferencia para su uso en la organización.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Crea un número de acceso para conferencia de acceso telefónico local.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Crea una colección de opciones de configuración de conferencias de acceso telefónico local. Esta configuración determina cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico. Concretamente, la información se devuelve dependiendo de si es necesario o no que los participantes graben su nombre cuando se unen a una conferencia y de cómo (o si) el sistema anuncia que alguien se ha unido a la conferencia o la ha abandonado.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Crea una nueva colección de configuraciones de señalización de frecuencia múltiple de tono dual (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Crea un plan de marcado.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Quita un directorio de conferencia existente.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Quita un número de acceso de conferencias de acceso telefónico local.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Quita una o más colecciones de la configuración de conferencia de acceso telefónico local. Esta configuración determina cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Quita una colección existente de opciones de señalización de frecuencia múltiple de tono dual (DTMF) usadas para conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica los valores de propiedad de un número de acceso de conferencia de acceso telefónico.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica la configuración que determina cómo Skype Empresarial Server responde cuando los usuarios se unen o salen de una conferencia de acceso telefónico.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica la configuración de señalización tono de marcado de frecuencia múltiple (DTMF) usada para las conferencias de acceso telefónico local.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica un plan de marcado existente.  <br/> |
   
**Configuración de directiva de PIN**

|**Cmdlet**|**Descripción**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Devuelve información acerca de las directivas del número de identificación personal (PIN) de los clientes configuradas para el uso en la organización. La autenticación de PIN permite a los usuarios acceder a Skype Empresarial Server proporcionando un PIN en lugar de un nombre de usuario y una contraseña.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Asigna una directiva de número de identificación personal (PIN) de cliente a un usuario o a un grupo de usuarios.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Crea una nueva directiva de número de identificación personal de cliente (PIN).  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Elimina la directiva especificada de número de identificación personal (PIN).  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica una o más directivas existentes de número de identificación personal de cliente (PIN).  <br/> |
